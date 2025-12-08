<script lang="ts">
	import { onMount } from 'svelte';

    // Data for sections
    const navLinks = ["Solutions", "Partner stories", "Integrations", "Events", "Pricing"];
    
    const logos = [
        { name: "Strava", width: 100 },
        { name: "piab", width: 60 },
        { name: "Huel", width: 80 },
        { name: "swile", width: 70 },
        { name: "Polestar", width: 110 },
        { name: "Electrolux Group", width: 120 },
        { name: "Brex", width: 80 }
    ];

    const features = [
        {
            tag: "AI LEARNING EXPERIENCE",
            title: "A personal tutor at every learner's fingertips",
            image: "phone",
            color: "bg-gray-100"
        },
        {
            tag: "VIRTUAL CLASSROOM",
            title: "Blended learning streamlined in one platform",
            image: "video",
            color: "bg-gray-100"
        },
        {
            tag: "JUST-IN-TIME LEARNING",
            title: "Instant search and answers to any question",
            image: "search",
            color: "bg-gray-100"
        },
        {
            tag: "COLLABORATIVE AUTHORING",
            title: "Beautiful interactive content created at lightning speed",
            image: "editor",
            color: "bg-gray-100"
        },
        {
            tag: "LEARNING MANAGEMENT",
            title: "All your manual learning admin on autopilot",
            image: "admin",
            color: "bg-gray-100"
        },
        {
            tag: "LEARNING ANALYTICS",
            title: "Shareable dashboards and insights in seconds",
            image: "analytics",
            color: "bg-gray-100"
        }
    ];

    const testimonials = [
        {
            quote: "Sana Learn has helped us go from manual, one-size-fits-all onboarding to a fully automated, yet still tailored experience.",
            name: "Olivia Winkvist",
            role: "Talent manager at Foodora",
            avatar: "OW"
        },
        {
            quote: "The first system I've seen that can truly be an end-to-end learning platform for companies.",
            name: "Josh Bersin",
            role: "The Josh Bersin Company",
            avatar: "JB"
        },
         {
            quote: "After my first demo, I couldn't believe Sana had all the tools I needed to efficiently design and evaluate the learning experience, not to mention a beautiful UI and engaging design.",
            name: "Ali Friedrich",
            role: "Director of Learning Experience at Superside",
            avatar: "AF"
        },
        // Adding more to fill the grid as per screenshot
        {
            quote: "Sana Learn was the end-to-end learning platform we had been waiting for. It isn't just a tool for L&D or People Partners. It's a tool for everyone.",
            name: "Amber de Wolde",
            role: "Senior People Partner at Veriff",
            avatar: "AW"
        },
        {
            quote: "This isn't just another learning platform. Sana is something unique and powerful, in equal measure.",
            name: "Luke O'Mahoney",
            role: "People Experience Advisor",
            avatar: "LO"
        },
        {
            quote: "Sana is not an LMS with Gen AI added. It's AI at its core.",
            name: "Josh Bersin",
            role: "The Josh Bersin Company",
            avatar: "JB"
        }
    ];

    const partnershipServices = [
        "Dedicated deployment lead",
        "Complete implementation support",
        "Tailored onboarding",
        "Priority support",
        "Content migration services",
        "L&D strategy and consulting",
        "Community, events, and resources"
    ];

    const comparisons = [
        {
            tag: "LEARNING MANAGEMENT",
            left: "Manage learning through static course catalogs and scheduled sessions through manual admin",
            right: "AI handles enrollments, scheduling, and updates automatically based on pre-configured rules"
        },
        {
            tag: "SKILLS MANAGEMENT",
            left: "Build a taxonomy, market voluntary courses, and manage skills",
            right: "AI monitors and designs learning experiences based on real-time, individual performance"
        },
        {
            tag: "CONTENT CREATION",
            left: "Design, create, and launch courses or programs based on scoped business partner requirements",
            right: "AI generates content dynamically from source material in a formal suited to the learner's preferences"
        },
        {
            tag: "JUST-IN-TIME LEARNING",
            left: "Purchase and build out a separate wiki for users to find company-specific information",
            right: "AI answers questions in natural language directly from the learning platform and cites sources"
        },
        {
            tag: "LEARNING ANALYTICS",
            left: "Export data from LMS, upload it to a BI tool for analysis, share results with stakeholders",
            right: "AI generates dashboards and answers performance questions in real time, instantly accessible to stakeholders"
        }
    ];

    const faqs = [
        "What can I use Sana Learn for?",
        "Can I brand the platform for a unique experience?",
        "Is the authoring built-in?",
        "What types of content can we create and include?",
        "Can I integrate Sana with my HRIS and CRM?",
        "Can I automate enrollments?",
        "Can we migrate existing content from other LMS platforms?",
        "What is Sana Learn's pricing?",
        "How secure will my company's knowledge and data be with Sana?"
    ];

</script>

<div class="font-sans text-gray-900 bg-white selection:bg-sana-lime selection:text-black">
    <!-- Navbar -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 h-16 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <!-- Logo Mark -->
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-black">
                    <path d="M12 0L14.5 9.5L24 12L14.5 14.5L12 24L9.5 14.5L0 12L9.5 9.5L12 0Z" fill="currentColor"/>
                </svg>
                <span class="font-medium text-lg tracking-tight">Sana Learn</span>
            </div>

            <div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
                {#each navLinks as link}
                    <a href="#" class="hover:text-black transition-colors">{link}</a>
                {/each}
            </div>

            <button class="bg-sana-blue text-white px-5 py-2 rounded-full text-sm font-medium hover:bg-blue-600 transition-colors">
                Book an intro
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-20 pb-16 px-6 text-center overflow-hidden">
        <div class="max-w-4xl mx-auto mb-12">
            <h1 class="font-serif text-6xl md:text-7xl lg:text-[5rem] leading-[1.1] mb-6 font-normal tracking-tight">
                The future of <br/> enterprise learning
            </h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto mb-8 leading-relaxed">
                Sana Learn brings the best of an LMS, LXP, authoring tool, and virtual classroom into one AI-native learning platform.
            </p>
            <button class="bg-sana-lime text-black px-8 py-3 rounded-full text-base font-medium hover:bg-[#c2e600] transition-colors">
                Book an intro
            </button>
        </div>

        <!-- Hero Image Collage Mockup -->
        <div class="relative max-w-[1400px] mx-auto h-[400px] md:h-[600px] mt-12 select-none pointer-events-none">
            <!-- We will build a CSS composition of screens -->
            <div class="relative w-full h-full flex justify-center items-end">
                
                <!-- Left Laptop -->
                <div class="absolute left-[-10%] bottom-0 w-[60%] md:w-[45%] z-10 transform -translate-x-10 translate-y-10">
                     <div class="bg-gray-900 rounded-t-xl p-1 shadow-2xl border border-gray-800 aspect-[16/10] overflow-hidden">
                        <!-- Screen Content -->
                        <div class="bg-gray-800 w-full h-full rounded-lg relative overflow-hidden">
                            <div class="absolute inset-0 bg-gradient-to-br from-blue-900 to-black opacity-80"></div>
                            <div class="p-4 text-white">
                                <div class="text-xs text-gray-400 mb-2">Space Tech</div>
                                <div class="h-2 w-20 bg-gray-600 rounded mb-4"></div>
                                <div class="grid grid-cols-2 gap-4">
                                    <div class="h-20 bg-gray-700/50 rounded"></div>
                                    <div class="h-20 bg-gray-700/50 rounded"></div>
                                </div>
                            </div>
                        </div>
                     </div>
                </div>

                <!-- Center Laptop (Main) -->
                <div class="absolute bottom-0 z-20 w-[70%] md:w-[50%] transform translate-y-5">
                    <div class="bg-black rounded-t-2xl p-2 shadow-2xl border border-gray-800 aspect-[16/10]">
                        <div class="bg-white w-full h-full rounded-xl overflow-hidden relative">
                            <!-- Mock UI -->
                            <div class="flex h-full">
                                <div class="w-1/3 bg-gray-50 p-4 border-r border-gray-100">
                                    <div class="h-8 w-8 bg-gray-200 rounded-full mb-4"></div>
                                    <div class="h-2 w-20 bg-gray-200 rounded mb-2"></div>
                                    <div class="h-2 w-16 bg-gray-200 rounded mb-6"></div>
                                    <div class="space-y-2">
                                        <div class="h-8 w-full bg-white border border-gray-200 rounded shadow-sm"></div>
                                        <div class="h-8 w-full bg-transparent rounded"></div>
                                    </div>
                                </div>
                                <div class="w-2/3 p-4">
                                    <div class="h-32 bg-gray-100 rounded-lg mb-4 flex items-center justify-center">
                                        <div class="w-12 h-12 bg-gray-300 rounded-full"></div>
                                    </div>
                                    <div class="h-4 w-3/4 bg-gray-100 rounded mb-2"></div>
                                    <div class="h-4 w-1/2 bg-gray-100 rounded"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Right Phone/Tablet -->
                <div class="absolute right-[-5%] bottom-10 w-[25%] md:w-[15%] z-30 transform translate-x-5">
                    <div class="bg-black rounded-[2rem] p-2 shadow-2xl border border-gray-800 aspect-[9/19]">
                        <div class="bg-white w-full h-full rounded-[1.5rem] overflow-hidden p-2 flex flex-col">
                             <div class="h-4 w-20 bg-gray-100 rounded mx-auto mb-4 mt-2"></div>
                             <div class="flex-1 bg-gray-50 rounded-xl p-2">
                                <div class="h-16 bg-sana-lime/20 rounded-lg mb-2"></div>
                                <div class="h-16 bg-blue-50 rounded-lg mb-2"></div>
                             </div>
                        </div>
                    </div>
                </div>

                 <!-- Another Right Screen (Tablet?) -->
                <div class="absolute right-[10%] bottom-0 w-[40%] md:w-[30%] z-10 transform translate-x-10 translate-y-10">
                     <div class="bg-white rounded-t-xl p-1 shadow-2xl border border-gray-200 aspect-[4/3] overflow-hidden">
                        <div class="bg-gray-50 w-full h-full rounded-lg p-3">
                             <div class="flex gap-2 mb-3">
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                             </div>
                             <div class="h-32 bg-white shadow-sm rounded-lg"></div>
                        </div>
                     </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Logos Section -->
    <section class="py-16 border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 text-center">
            <p class="text-sm text-gray-500 mb-10">Trusted by market leaders and innovators alike</p>
            <div class="flex flex-wrap justify-center items-center gap-12 md:gap-16 opacity-70 grayscale hover:grayscale-0 transition-all duration-500">
                {#each logos as logo}
                    <div class="h-8 flex items-center justify-center">
                        <!-- Placeholder for logo text/svg -->
                        <span class="font-bold text-xl font-serif italic">{logo.name}</span>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Meet Sana Learn Grid -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Meet Sana Learn</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Say goodbye to fragmented learning tools. Sana Learn is the only platform designed to move you beyond one-size-fits-all content to a truly dynamic, personalized learning experience at scale.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                {#each features as feature}
                    <div class="group bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-md transition-shadow duration-300 flex flex-col h-[500px]">
                        <div class="p-8 pb-0 flex-1">
                            <span class="inline-block bg-sana-lime text-[10px] font-bold tracking-wider px-2 py-1 rounded mb-4 uppercase">
                                {feature.tag}
                            </span>
                            <h3 class="font-serif text-2xl leading-tight mb-4">
                                {feature.title}
                            </h3>
                        </div>
                        <div class="h-[300px] bg-gray-100 relative overflow-hidden mt-4 mx-4 rounded-t-xl group-hover:translate-y-[-5px] transition-transform duration-500">
                            <!-- Mockup Content based on type -->
                            {#if feature.image === 'phone'}
                                <div class="absolute bottom-[-20px] left-1/2 transform -translate-x-1/2 w-[180px] h-[350px] bg-black rounded-[2rem] border-4 border-black shadow-xl overflow-hidden">
                                     <div class="bg-white w-full h-full p-3 pt-8">
                                        <div class="h-2 w-12 bg-gray-200 rounded mx-auto mb-4"></div>
                                        <div class="space-y-2">
                                            <div class="h-16 bg-gray-50 rounded-lg"></div>
                                            <div class="h-16 bg-gray-50 rounded-lg"></div>
                                        </div>
                                     </div>
                                </div>
                            {:else if feature.image === 'video'}
                                <div class="absolute inset-0 p-4 flex items-end justify-center">
                                    <div class="w-full h-[90%] bg-gray-800 rounded-t-lg shadow-lg relative overflow-hidden">
                                        <div class="absolute inset-0 flex items-center justify-center text-white/20">
                                            <svg width="48" height="48" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 14.5v-9l6 4.5-6 4.5z"/></svg>
                                        </div>
                                        <div class="absolute bottom-4 left-4 flex gap-2">
                                            <div class="w-8 h-8 bg-gray-600 rounded-full"></div>
                                            <div class="w-8 h-8 bg-gray-600 rounded-full"></div>
                                        </div>
                                    </div>
                                </div>
                            {:else if feature.image === 'search'}
                                 <div class="absolute bottom-[-40px] right-[-20px] w-full h-full bg-white shadow-lg rounded-tl-2xl p-6 border border-gray-100">
                                     <div class="flex items-center gap-3 mb-4 border-b pb-4">
                                         <div class="w-8 h-8 bg-sana-lime rounded-full"></div>
                                         <div class="h-2 w-32 bg-gray-200 rounded"></div>
                                     </div>
                                     <div class="space-y-3">
                                         <div class="h-2 w-full bg-gray-100 rounded"></div>
                                         <div class="h-2 w-5/6 bg-gray-100 rounded"></div>
                                         <div class="h-2 w-4/6 bg-gray-100 rounded"></div>
                                     </div>
                                 </div>
                            {:else}
                                <div class="absolute inset-4 bg-white shadow-sm rounded-lg border border-gray-100 flex items-center justify-center">
                                    <div class="text-gray-300">UI Mockup</div>
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Loved by users, creators, <br/> and admins alike</h2>
                <p class="text-lg text-gray-600 leading-relaxed mb-10">
                    The modern learning experience everyone deserves. <br/> You don't have to choose between user-friendly and enterprise-ready.
                </p>
                <div class="flex justify-center gap-4">
                    <!-- G2 Badges Mockup -->
                    {#each Array(5) as _, i}
                        <div class="w-16 h-20 bg-gradient-to-br from-red-50 to-orange-50 border border-red-100 rounded flex flex-col items-center justify-center p-1 text-[8px] text-center text-red-800 font-bold shadow-sm">
                            <div class="w-6 h-6 bg-red-500 rounded-full mb-1 text-white flex items-center justify-center">G2</div>
                            Leader
                        </div>
                    {/each}
                </div>
            </div>

            <div class="columns-1 md:columns-2 lg:columns-3 gap-6 space-y-6">
                {#each testimonials as testimonial}
                    <div class="break-inside-avoid bg-gray-50 p-8 rounded-2xl">
                        <p class="text-lg leading-relaxed mb-6">"{testimonial.quote}"</p>
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 bg-gray-300 rounded-full flex items-center justify-center text-sm font-bold text-gray-600">
                                {testimonial.avatar}
                            </div>
                            <div>
                                <div class="font-medium">{testimonial.name}</div>
                                <div class="text-sm text-gray-500">{testimonial.role}</div>
                            </div>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Partnership Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">The proof is in <br/> the partnership</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    It isn't all about the technology. Organizations choose Sana <br/> because we're product-led and partnership-driven.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="bg-gray-50 p-12 rounded-3xl h-full">
                    <h3 class="font-serif text-2xl mb-8">Enterprise partnership services</h3>
                    <ul class="space-y-4">
                        {#each partnershipServices as service}
                            <li class="flex items-center gap-3">
                                <div class="w-5 h-5 rounded-full bg-sana-lime flex items-center justify-center shrink-0">
                                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                                </div>
                                <span class="text-gray-700">{service}</span>
                            </li>
                        {/each}
                    </ul>
                </div>
                <div class="h-full min-h-[500px] rounded-3xl overflow-hidden relative">
                    <!-- Placeholder image for people collaborating -->
                    <div class="absolute inset-0 bg-gray-200">
                        <div class="w-full h-full bg-[url('https://images.unsplash.com/photo-1522071820081-009f0129c71c?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center grayscale opacity-80 hover:grayscale-0 transition-all duration-700"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Case Studies Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
            <div class="flex justify-between items-end mb-12">
                <p class="text-lg text-gray-600 max-w-xl">Sana Learn is a fit for any industry. Read the results yourself.</p>
                <div class="flex gap-2">
                    <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center hover:bg-gray-50">
                        ←
                    </button>
                    <button class="w-10 h-10 rounded-full bg-black text-white flex items-center justify-center hover:bg-gray-800">
                        →
                    </button>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Card 1 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                        <!-- Mock Background Image -->
                        <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                        <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay opacity-40"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Polestar increases active users by 275%</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Employees: 3000 <br/> Industry: Automotive</div>
                        </div>
                        <div class="font-bold text-xl">Polestar</div>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                         <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                         <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1542744173-8e7e53415bb0?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay opacity-40"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Superside cuts design time by 80% and leads an AI revolution</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Employees: 750 <br/> Industry: Design and Marketing</div>
                        </div>
                        <div class="font-bold text-xl">Superside</div>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                         <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                         <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay opacity-40"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Ahlsell accelerates course creation...</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Employees: 7500 <br/> Industry: Wholesale</div>
                        </div>
                        <div class="font-bold text-xl">ahlsell</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Comparison Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">AI is not an add-on. <br/> It's what we do.</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    AI-first L&D can transform your team from a content delivery <br/> machine to a strategic value-driver.
                </p>
            </div>

            <div class="border-t border-gray-100">
                <div class="grid grid-cols-3 py-4 text-xs text-gray-400 uppercase tracking-wider border-b border-gray-100">
                    <div>Status quo</div>
                    <div class="text-center">→</div>
                    <div>Sana Learn</div>
                </div>
                {#each comparisons as item}
                    <div class="grid grid-cols-1 md:grid-cols-[1fr_auto_1fr] gap-8 py-12 border-b border-gray-100 items-center group hover:bg-gray-50 transition-colors px-4 -mx-4 rounded-xl">
                        <div class="text-gray-500 leading-relaxed md:pr-8">
                            {item.left}
                        </div>
                        <div class="flex justify-center">
                            <span class="bg-sana-lime text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase whitespace-nowrap">
                                {item.tag}
                            </span>
                        </div>
                        <div class="text-black font-medium leading-relaxed md:pl-8">
                            {item.right}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Integrations & Security Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Enterprise-grade <br/> integrations and security</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    We take this stuff as seriously as you do.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
                <!-- Integrations -->
                <div>
                    <div class="text-center mb-8">
                        <span class="bg-sana-lime text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase">
                            PLAYS NICE WITH YOUR FAVORITE TOOLS
                        </span>
                    </div>
                    <div class="grid grid-cols-4 gap-6">
                        {#each ['Google Drive', 'Teams', 'Slack', 'Salesforce', 'Coursera', 'Edcast', 'Degreed', 'HiBob', 'Workday', 'Personio', 'SAP Litmos', 'Okta'] as tool}
                            <div class="aspect-square bg-gray-50 rounded-xl flex flex-col items-center justify-center p-4 hover:bg-gray-100 transition-colors">
                                <div class="w-8 h-8 bg-gray-200 rounded-full mb-2"></div> <!-- Icon Placeholder -->
                                <span class="text-[10px] text-center text-gray-600 font-medium">{tool}</span>
                            </div>
                        {/each}
                    </div>
                </div>

                <!-- Security -->
                <div>
                    <div class="text-center mb-8">
                        <span class="bg-sana-lime text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase">
                            SECURITY YOU CAN STAND BY
                        </span>
                    </div>
                    <div class="grid grid-cols-4 gap-6">
                         {#each ['Custom user roles', 'User provisioning', 'Advanced permissions', 'Flexible groups', 'SOC 2 Type 2', 'GDPR compliant', 'ISO 27001', 'SCORM compliant', 'SAML single sign-on', '2FA with email codes', 'Regional deploys', 'Audit logging'] as item}
                            <div class="aspect-square bg-gray-50 rounded-xl flex flex-col items-center justify-center p-2 hover:bg-gray-100 transition-colors">
                                <div class="w-6 h-6 border-2 border-gray-300 rounded mb-2"></div> <!-- Icon Placeholder -->
                                <span class="text-[10px] text-center text-gray-600 font-medium leading-tight">{item}</span>
                            </div>
                        {/each}
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Mission Section -->
    <section class="py-24 px-6">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 min-h-[600px]">
            <div class="bg-white relative flex items-center justify-center p-12 overflow-hidden">
                <div class="flex gap-4 transform -rotate-6 scale-90">
                    <div class="w-64 h-80 bg-[#00D166] flex items-center justify-center text-white font-bold text-4xl shadow-2xl">FAST COMPANY</div>
                    <div class="w-64 h-80 bg-black flex items-center justify-center text-white font-bold text-4xl shadow-2xl z-10 -mt-12">Forbes</div>
                    <div class="w-64 h-80 bg-[#4CA6FF] flex items-center justify-center text-white font-bold text-4xl shadow-2xl">FAST COMPANY</div>
                </div>
            </div>
            <div class="bg-sana-lime p-12 lg:p-24 flex flex-col justify-center">
                <p class="font-serif text-3xl md:text-4xl leading-tight mb-8">
                    Sana has been on a mission to transform how organizations learn and access knowledge with AI since 2016.
                </p>
                <p class="font-serif text-3xl md:text-4xl leading-tight">
                    We have pioneered the application of AI to learning experiences, content creation, learning management, and learning analytics. We believe the best is yet to come.
                </p>
            </div>
        </div>
    </section>

    <!-- Bottom CTA -->
    <section class="py-32 px-6 text-center bg-white">
        <div class="max-w-4xl mx-auto">
            <h2 class="font-serif text-6xl md:text-7xl mb-6">The future of <br/> learning is here.</h2>
            <p class="text-xl text-gray-600 mb-10">Will you join us?</p>
            <button class="bg-sana-lime text-black px-8 py-3 rounded-full text-base font-medium hover:bg-[#c2e600] transition-colors">
                Book an intro
            </button>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
            <h2 class="font-serif text-5xl mb-16">FAQ</h2>
            <div class="space-y-4">
                {#each faqs as faq}
                    <div class="border-b border-gray-100 py-6 flex justify-between items-center cursor-pointer group hover:bg-gray-50 px-4 -mx-4 rounded-lg transition-colors">
                        <span class="text-lg font-medium">{faq}</span>
                        <div class="w-8 h-8 rounded-full bg-black text-white flex items-center justify-center group-hover:bg-gray-800 transition-colors">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-4 gap-12">
            <div class="col-span-1 md:col-span-1">
                <div class="flex items-center gap-2 mb-8">
                     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-black">
                        <path d="M12 0L14.5 9.5L24 12L14.5 14.5L12 24L9.5 14.5L0 12L9.5 9.5L12 0Z" fill="currentColor"/>
                    </svg>
                    <span class="font-medium text-xl tracking-tight">Sana</span>
                </div>
                <div class="text-sm text-gray-500 mb-4">Subscribe to our newsletter</div>
                <div class="flex gap-2 border-b border-gray-200 pb-2 mb-8">
                    <input type="email" placeholder="Email address" class="w-full outline-none text-sm" />
                    <button class="text-gray-400 hover:text-black">→</button>
                </div>
                <div class="text-xs text-gray-400">© Sana Labs AB 2025</div>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-3 gap-8 col-span-1 md:col-span-3">
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Sana Agents</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Overview</a></li>
                        <li><a href="#" class="hover:text-black">AI agents</a></li>
                        <li><a href="#" class="hover:text-black">Enterprise search</a></li>
                        <li><a href="#" class="hover:text-black">iOS app</a></li>
                        <li><a href="#" class="hover:text-black">Solutions</a></li>
                        <li><a href="#" class="hover:text-black">Integrations</a></li>
                        <li><a href="#" class="hover:text-black">Events</a></li>
                        <li><a href="#" class="hover:text-black">Security</a></li>
                        <li><a href="#" class="hover:text-black">Stories</a></li>
                        <li><a href="#" class="hover:text-black">Pricing</a></li>
                        <li><a href="#" class="hover:text-black">Help Center</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Sana Learn</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Overview</a></li>
                        <li><a href="#" class="hover:text-black">Learning management</a></li>
                        <li><a href="#" class="hover:text-black">Content creation</a></li>
                        <li><a href="#" class="hover:text-black">AI tutor</a></li>
                        <li><a href="#" class="hover:text-black">Solutions</a></li>
                        <li><a href="#" class="hover:text-black">Partner stories</a></li>
                        <li><a href="#" class="hover:text-black">Integrations</a></li>
                        <li><a href="#" class="hover:text-black">Events</a></li>
                        <li><a href="#" class="hover:text-black">Pricing</a></li>
                        <li><a href="#" class="hover:text-black">Help Center</a></li>
                        <li><a href="#" class="hover:text-black">Changelog</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Company</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Hexad Releases</a></li>
                        <li><a href="#" class="hover:text-black">Swedish AI Reform</a></li>
                        <li><a href="#" class="hover:text-black">Strange Loop Podcast</a></li>
                        <li><a href="#" class="hover:text-black">Mission</a></li>
                        <li><a href="#" class="hover:text-black">Careers</a></li>
                        <li><a href="#" class="hover:text-black">Press</a></li>
                        <li><a href="#" class="hover:text-black">Legal</a></li>
                        <li><a href="#" class="hover:text-black">Cookie settings</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>

</div>

