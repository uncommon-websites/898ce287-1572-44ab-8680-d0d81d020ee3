<script lang="ts">
	import { onMount } from 'svelte';

    // Data for sections
    const navLinks = ["Features", "How It Works", "Subjects", "Pricing"];
    
    const schools = [
        "Lincoln High School",
        "Washington Academy",
        "Roosevelt Prep",
        "Jefferson High",
        "Madison School"
    ];

    const features = [
        {
            tag: "AI MATH TUTOR",
            title: "Get help that actually teaches you, not just answers",
            image: "phone",
            color: "bg-gray-100"
        },
        {
            tag: "NOTEBOOK ENVIRONMENT",
            title: "Work on homework in a familiar, intuitive space",
            image: "notebook",
            color: "bg-gray-100"
        },
        {
            tag: "IMAGE UPLOAD",
            title: "Snap a photo of your problem and get instant help",
            image: "camera",
            color: "bg-gray-100"
        },
        {
            tag: "COURSE REGISTRATION",
            title: "Personalized to your exact math courses",
            image: "courses",
            color: "bg-gray-100"
        },
        {
            tag: "TEXTBOOK GROUNDED",
            title: "AI trained on your actual textbooks for accurate help",
            image: "textbook",
            color: "bg-gray-100"
        },
        {
            tag: "PROGRESS TRACKING",
            title: "See your improvement and master concepts over time",
            image: "progress",
            color: "bg-gray-100"
        }
    ];

    const testimonials = [
        {
            quote: "I went from struggling with calculus to actually understanding it. Tootor doesn't just give you answers—it helps you learn.",
            name: "Sarah Chen",
            role: "Junior, Lincoln High School",
            avatar: "SC",
            image: "/generated/image-confident-teenage-girl-with-backpack-smi-1765754161273-4.webp"
        },
        {
            quote: "The image upload feature is a game changer. I can snap my homework and get help right away, even at 10pm.",
            name: "Marcus Johnson",
            role: "Sophomore, Washington Academy",
            avatar: "MJ",
            image: "/generated/image-teenage-boy-with-glasses-looking-happy-a-1765754163733-5.webp"
        },
         {
            quote: "My daughter's grades improved from a C to an A- in just one semester. Tootor made math finally click for her.",
            name: "Jennifer Martinez",
            role: "Parent",
            avatar: "JM",
            image: null
        },
        {
            quote: "It's like having a patient tutor available 24/7. The AI actually explains things in a way I understand.",
            name: "Alex Rivera",
            role: "Senior, Roosevelt Prep",
            avatar: "AR",
            image: "/generated/image-high-school-girl-writing-in-notebook-whi-1765754166008-6.webp"
        },
        {
            quote: "I love that it uses my actual textbook. The explanations match what we're learning in class perfectly.",
            name: "Emily Thompson",
            role: "Junior, Jefferson High",
            avatar: "ET",
            image: null
        },
        {
            quote: "Tootor helped me prepare for the SAT math section. My score went up 120 points!",
            name: "David Kim",
            role: "Senior, Madison School",
            avatar: "DK",
            image: null
        }
    ];

    const howItWorks = [
        {
            step: "1",
            title: "Register Your Courses",
            description: "Tell us which math classes you're taking so we can personalize your experience"
        },
        {
            step: "2",
            title: "Upload Your Homework",
            description: "Snap a photo or type in your problem in our notebook environment"
        },
        {
            step: "3",
            title: "Learn Step-by-Step",
            description: "Get AI-powered guidance that teaches you how to solve it, not just the answer"
        }
    ];

    const subjects = [
        "Algebra I & II",
        "Geometry",
        "Trigonometry",
        "Pre-Calculus",
        "Calculus AB & BC",
        "Statistics",
        "SAT/ACT Math Prep"
    ];

    const faqs = [
        "What math subjects does Tootor cover?",
        "How does the AI tutor work?",
        "Will Tootor just give me the answers to my homework?",
        "Can I upload photos of my homework problems?",
        "What textbooks does Tootor support?",
        "How much does Tootor cost?",
        "Can I use Tootor on my phone or tablet?",
        "Is my homework data private and secure?",
        "Can parents track their child's progress?"
    ];

</script>

<div class="font-sans text-gray-900 bg-white selection:bg-primary-200 selection:text-black">
    <!-- Navbar -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 h-16 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <!-- Logo Mark -->
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                    <path d="M15.7321 18.4096C15.464 19.0054 15.1307 19.5889 14.7312 20.0937C18.0462 18.9764 20.4865 15.9576 20.7551 12.3344H19.5751C18.135 12.3344 16.9782 13.4839 16.7442 14.9048C16.5284 16.2146 16.1832 17.4073 15.7321 18.4096Z" fill="currentColor"/>
                    <path d="M13.122 12.3344C14.6297 12.3344 15.8632 13.5922 15.5862 15.0743C14.9847 18.2935 13.5564 20.5574 11.8901 20.5574C9.78166 20.5574 8.05421 16.9326 7.90082 12.3344H13.122Z" fill="currentColor"/>
                    <path d="M16.7748 8.62303C16.9953 10.0573 18.1574 11.2232 19.6085 11.2232H20.7689C20.5856 7.50155 18.1137 4.38174 14.7312 3.24164C15.1307 3.74646 15.464 4.32993 15.7321 4.9257C16.2052 5.97693 16.5618 7.23753 16.7748 8.62303Z" fill="currentColor"/>
                    <path d="M15.6307 8.5099C15.8829 9.98453 14.6549 11.2232 13.1588 11.2232H7.89462C7.99881 6.52003 9.74782 2.77795 11.8901 2.77795C13.599 2.77795 15.0576 5.15916 15.6307 8.5099Z" fill="currentColor"/>
                    <path d="M6.78316 11.2232C6.83365 8.81927 7.29225 6.60525 8.04807 4.9257C8.31614 4.32993 8.64941 3.74646 9.04901 3.24164C5.66642 4.38174 3.19455 7.50155 3.01129 11.2232H6.78316Z" fill="currentColor"/>
                    <path d="M3.02502 12.3344C3.29367 15.9576 5.73401 18.9764 9.04903 20.0937C8.64944 19.5889 8.31616 19.0054 8.0481 18.4096C7.31563 16.7819 6.86229 14.6523 6.78903 12.3344H3.02502Z" fill="currentColor"/>
                </svg>
                <span class="font-medium text-lg tracking-tight">Tootor</span>
            </div>

            <div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
                {#each navLinks as link}
                    <a href="#" class="hover:text-black transition-colors">{link}</a>
                {/each}
            </div>

            <button class="bg-primary-600 text-white px-5 py-2 rounded-full text-sm font-medium hover:bg-primary-700 transition-colors">
                Get Started Free
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-20 pb-16 px-6 text-center overflow-hidden">
        <div class="max-w-4xl mx-auto mb-12">
            <h1 class="font-serif text-6xl md:text-7xl lg:text-[5rem] leading-[1.1] mb-6 font-normal tracking-tight">
                Master math homework<br/> with AI that teaches
            </h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto mb-8 leading-relaxed">
                Tootor is your personal AI math tutor, grounded in your textbooks and trained to maximize learning—not just give you answers.
            </p>
            <button class="bg-primary-600 text-white px-8 py-3 rounded-full text-base font-medium hover:bg-primary-700 transition-colors">
                Start Learning Free
            </button>
        </div>

        <!-- Hero Image -->
        <div class="relative max-w-[1200px] mx-auto mt-12">
            <div class="rounded-2xl overflow-hidden shadow-2xl border border-gray-200">
                <img 
                    src="/generated/image-high-school-student-working-on-math-home-1765754150334-0.webp" 
                    alt="Student using Tootor for math homework"
                    class="w-full h-auto"
                />
            </div>
        </div>
    </section>

    <!-- Social Proof Section -->
    <section class="py-16 border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                <div>
                    <h3 class="text-3xl font-serif mb-4">Trusted by students nationwide</h3>
                    <p class="text-gray-600 mb-6">Join thousands of high school students who are mastering math with Tootor's AI-powered learning platform.</p>
                    <div class="flex flex-wrap gap-4 text-sm text-gray-500">
                        {#each schools as school}
                            <span class="px-3 py-1 bg-gray-50 rounded-full">{school}</span>
                        {/each}
                    </div>
                </div>
                <div class="rounded-2xl overflow-hidden">
                    <img 
                        src="/generated/image-diverse-group-of-high-school-students-st-1765754158964-3.webp" 
                        alt="Students studying together"
                        class="w-full h-auto"
                    />
                </div>
            </div>
        </div>
    </section>

    <!-- Features Grid -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Everything you need to excel in math</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Tootor combines the best AI technology with proven learning methods to help you truly understand math, not just memorize formulas.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                {#each features as feature}
                    <div class="group bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-md transition-shadow duration-300 flex flex-col">
                        <div class="p-8">
                            <span class="inline-block bg-primary-100 text-primary-700 text-[10px] font-bold tracking-wider px-2 py-1 rounded mb-4 uppercase">
                                {feature.tag}
                            </span>
                            <h3 class="font-serif text-2xl leading-tight mb-4">
                                {feature.title}
                            </h3>
                        </div>
                        <div class="h-[200px] bg-gray-100 relative overflow-hidden mt-auto">
                            <!-- Simple icon representation -->
                            <div class="absolute inset-0 flex items-center justify-center">
                                {#if feature.image === 'phone'}
                                    <div class="w-16 h-16 bg-primary-600 rounded-2xl flex items-center justify-center text-white">
                                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                            <rect x="5" y="2" width="14" height="20" rx="2" ry="2"></rect>
                                            <line x1="12" y1="18" x2="12.01" y2="18"></line>
                                        </svg>
                                    </div>
                                {:else if feature.image === 'notebook'}
                                    <div class="w-16 h-16 bg-primary-600 rounded-2xl flex items-center justify-center text-white">
                                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                            <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
                                            <polyline points="14 2 14 8 20 8"></polyline>
                                        </svg>
                                    </div>
                                {:else if feature.image === 'camera'}
                                    <div class="w-16 h-16 bg-primary-600 rounded-2xl flex items-center justify-center text-white">
                                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                            <path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"></path>
                                            <circle cx="12" cy="13" r="4"></circle>
                                        </svg>
                                    </div>
                                {:else if feature.image === 'courses'}
                                    <div class="w-16 h-16 bg-primary-600 rounded-2xl flex items-center justify-center text-white">
                                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                            <path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"></path>
                                            <path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"></path>
                                        </svg>
                                    </div>
                                {:else if feature.image === 'textbook'}
                                    <div class="w-16 h-16 bg-primary-600 rounded-2xl flex items-center justify-center text-white">
                                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                            <path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path>
                                            <path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path>
                                        </svg>
                                    </div>
                                {:else}
                                    <div class="w-16 h-16 bg-primary-600 rounded-2xl flex items-center justify-center text-white">
                                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                            <line x1="18" y1="20" x2="18" y2="10"></line>
                                            <line x1="12" y1="20" x2="12" y2="4"></line>
                                            <line x1="6" y1="20" x2="6" y2="14"></line>
                                        </svg>
                                    </div>
                                {/if}
                            </div>
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
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Students and parents love Tootor</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Real stories from students who transformed their math grades and confidence with Tootor's AI-powered learning.
                </p>
            </div>

            <div class="columns-1 md:columns-2 lg:columns-3 gap-6 space-y-6">
                {#each testimonials as testimonial}
                    <div class="break-inside-avoid bg-gray-50 p-8 rounded-2xl">
                        <p class="text-lg leading-relaxed mb-6">"{testimonial.quote}"</p>
                        <div class="flex items-center gap-3">
                            {#if testimonial.image}
                                <img src={testimonial.image} alt={testimonial.name} class="w-10 h-10 rounded-full object-cover" />
                            {:else}
                                <div class="w-10 h-10 bg-primary-200 rounded-full flex items-center justify-center text-sm font-bold text-primary-700">
                                    {testimonial.avatar}
                                </div>
                            {/if}
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

    <!-- How It Works Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Getting started is easy</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Three simple steps to transform your math homework experience
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                {#each howItWorks as step}
                    <div class="text-center">
                        <div class="w-16 h-16 bg-primary-600 text-white rounded-2xl flex items-center justify-center text-2xl font-bold mx-auto mb-6">
                            {step.step}
                        </div>
                        <h3 class="font-serif text-2xl mb-4">{step.title}</h3>
                        <p class="text-gray-600 leading-relaxed">{step.description}</p>
                    </div>
                {/each}
            </div>

            <div class="mt-16 rounded-3xl overflow-hidden">
                <img 
                    src="/generated/image-young-student-celebrating-success-with-r-1765754168494-7.webp" 
                    alt="Student celebrating success"
                    class="w-full h-auto"
                />
            </div>
        </div>
    </section>

    <!-- Subjects Section -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">All your math courses covered</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    From basic algebra to advanced calculus, Tootor supports every high school math subject
                </p>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-12">
                {#each subjects as subject}
                    <div class="bg-white p-6 rounded-xl text-center hover:shadow-md transition-shadow">
                        <h3 class="font-medium text-lg">{subject}</h3>
                    </div>
                {/each}
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center bg-white p-12 rounded-3xl">
                <div>
                    <h3 class="font-serif text-3xl mb-4">Grounded in your textbooks</h3>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        Our AI is trained on actual high school math textbooks, ensuring explanations match what you're learning in class. No generic answers—just help that's perfectly aligned with your curriculum.
                    </p>
                    <ul class="space-y-3">
                        <li class="flex items-start gap-3">
                            <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                            </div>
                            <span class="text-gray-700">Aligned with Common Core standards</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                            </div>
                            <span class="text-gray-700">Supports major textbook publishers</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                            </div>
                            <span class="text-gray-700">Updated for current academic year</span>
                        </li>
                    </ul>
                </div>
                <div class="rounded-2xl overflow-hidden">
                    <img 
                        src="/generated/image-high-school-student-taking-photo-of-math-1765754156654-2.webp" 
                        alt="Student with textbook"
                        class="w-full h-auto"
                    />
                </div>
            </div>
        </div>
    </section>

    <!-- Why Tootor Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Why students choose Tootor</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    We're not just another homework helper. Tootor is designed to help you actually learn and understand math.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="bg-gray-50 p-10 rounded-2xl">
                    <div class="w-12 h-12 bg-primary-600 rounded-xl flex items-center justify-center text-white mb-6">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"></path>
                            <polyline points="22 4 12 14.01 9 11.01"></polyline>
                        </svg>
                    </div>
                    <h3 class="font-serif text-2xl mb-4">Learning-first approach</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Unlike other apps that just give you answers, Tootor guides you through step-by-step solutions to help you understand the concepts. You'll learn how to solve problems, not just what the answer is.
                    </p>
                </div>

                <div class="bg-gray-50 p-10 rounded-2xl">
                    <div class="w-12 h-12 bg-primary-600 rounded-xl flex items-center justify-center text-white mb-6">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path>
                            <path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path>
                        </svg>
                    </div>
                    <h3 class="font-serif text-2xl mb-4">Grounded in your textbooks</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Our AI is trained on actual textbooks, so explanations match what you're learning in class. No confusing different methods—just consistent help aligned with your curriculum.
                    </p>
                </div>

                <div class="bg-gray-50 p-10 rounded-2xl">
                    <div class="w-12 h-12 bg-primary-600 rounded-xl flex items-center justify-center text-white mb-6">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M12 2v20M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"></path>
                        </svg>
                    </div>
                    <h3 class="font-serif text-2xl mb-4">Affordable for everyone</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Get unlimited access to AI tutoring for less than the cost of a single hour with a human tutor. Quality math help shouldn't break the bank.
                    </p>
                </div>

                <div class="bg-gray-50 p-10 rounded-2xl">
                    <div class="w-12 h-12 bg-primary-600 rounded-xl flex items-center justify-center text-white mb-6">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <circle cx="12" cy="12" r="10"></circle>
                            <polyline points="12 6 12 12 16 14"></polyline>
                        </svg>
                    </div>
                    <h3 class="font-serif text-2xl mb-4">Available 24/7</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Stuck on homework at 11pm? No problem. Tootor is always available when you need help, whether it's after school, late at night, or on weekends.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Simple, affordable pricing</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Get unlimited access to AI math tutoring for less than one hour with a traditional tutor
                </p>
            </div>

            <div class="max-w-md mx-auto bg-white rounded-3xl p-10 shadow-lg border border-gray-100">
                <div class="text-center mb-8">
                    <div class="text-5xl font-bold mb-2">$19<span class="text-2xl text-gray-500">/month</span></div>
                    <p class="text-gray-600">Unlimited access to all features</p>
                </div>
                
                <ul class="space-y-4 mb-8">
                    <li class="flex items-start gap-3">
                        <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        </div>
                        <span class="text-gray-700">Unlimited homework help</span>
                    </li>
                    <li class="flex items-start gap-3">
                        <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        </div>
                        <span class="text-gray-700">All math subjects covered</span>
                    </li>
                    <li class="flex items-start gap-3">
                        <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        </div>
                        <span class="text-gray-700">Image upload for problems</span>
                    </li>
                    <li class="flex items-start gap-3">
                        <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        </div>
                        <span class="text-gray-700">Step-by-step explanations</span>
                    </li>
                    <li class="flex items-start gap-3">
                        <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        </div>
                        <span class="text-gray-700">Progress tracking</span>
                    </li>
                    <li class="flex items-start gap-3">
                        <div class="w-5 h-5 rounded-full bg-primary-100 flex items-center justify-center shrink-0 mt-0.5">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" class="text-primary-600"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        </div>
                        <span class="text-gray-700">Works on all devices</span>
                    </li>
                </ul>

                <button class="w-full bg-primary-600 text-white px-8 py-4 rounded-full text-base font-medium hover:bg-primary-700 transition-colors">
                    Start Free Trial
                </button>
                <p class="text-center text-sm text-gray-500 mt-4">7-day free trial, cancel anytime</p>
            </div>
        </div>
    </section>

    <!-- Bottom CTA -->
    <section class="py-32 px-6 text-center bg-white">
        <div class="max-w-4xl mx-auto">
            <h2 class="font-serif text-6xl md:text-7xl mb-6">Ready to ace your <br/> math homework?</h2>
            <p class="text-xl text-gray-600 mb-10">Join thousands of students who are transforming their math grades with Tootor</p>
            <button class="bg-primary-600 text-white px-8 py-3 rounded-full text-base font-medium hover:bg-primary-700 transition-colors">
                Start Free Trial
            </button>
            <p class="text-sm text-gray-500 mt-4">No credit card required • 7-day free trial</p>
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
                     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                        <path d="M15.7321 18.4096C15.464 19.0054 15.1307 19.5889 14.7312 20.0937C18.0462 18.9764 20.4865 15.9576 20.7551 12.3344H19.5751C18.135 12.3344 16.9782 13.4839 16.7442 14.9048C16.5284 16.2146 16.1832 17.4073 15.7321 18.4096Z" fill="currentColor"/>
                        <path d="M13.122 12.3344C14.6297 12.3344 15.8632 13.5922 15.5862 15.0743C14.9847 18.2935 13.5564 20.5574 11.8901 20.5574C9.78166 20.5574 8.05421 16.9326 7.90082 12.3344H13.122Z" fill="currentColor"/>
                        <path d="M16.7748 8.62303C16.9953 10.0573 18.1574 11.2232 19.6085 11.2232H20.7689C20.5856 7.50155 18.1137 4.38174 14.7312 3.24164C15.1307 3.74646 15.464 4.32993 15.7321 4.9257C16.2052 5.97693 16.5618 7.23753 16.7748 8.62303Z" fill="currentColor"/>
                        <path d="M15.6307 8.5099C15.8829 9.98453 14.6549 11.2232 13.1588 11.2232H7.89462C7.99881 6.52003 9.74782 2.77795 11.8901 2.77795C13.599 2.77795 15.0576 5.15916 15.6307 8.5099Z" fill="currentColor"/>
                        <path d="M6.78316 11.2232C6.83365 8.81927 7.29225 6.60525 8.04807 4.9257C8.31614 4.32993 8.64941 3.74646 9.04901 3.24164C5.66642 4.38174 3.19455 7.50155 3.01129 11.2232H6.78316Z" fill="currentColor"/>
                        <path d="M3.02502 12.3344C3.29367 15.9576 5.73401 18.9764 9.04903 20.0937C8.64944 19.5889 8.31616 19.0054 8.0481 18.4096C7.31563 16.7819 6.86229 14.6523 6.78903 12.3344H3.02502Z" fill="currentColor"/>
                    </svg>
                    <span class="font-medium text-xl tracking-tight">Tootor</span>
                </div>
                <p class="text-sm text-gray-600 mb-8">AI-powered math tutoring for high school students</p>
                <div class="text-xs text-gray-400">© Tootor 2025</div>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-3 gap-8 col-span-1 md:col-span-3">
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Product</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Features</a></li>
                        <li><a href="#" class="hover:text-black">How It Works</a></li>
                        <li><a href="#" class="hover:text-black">Subjects</a></li>
                        <li><a href="#" class="hover:text-black">Pricing</a></li>
                        <li><a href="#" class="hover:text-black">Mobile App</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Support</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Help Center</a></li>
                        <li><a href="#" class="hover:text-black">Contact Us</a></li>
                        <li><a href="#" class="hover:text-black">FAQ</a></li>
                        <li><a href="#" class="hover:text-black">Student Resources</a></li>
                        <li><a href="#" class="hover:text-black">Parent Guide</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Company</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">About</a></li>
                        <li><a href="#" class="hover:text-black">Blog</a></li>
                        <li><a href="#" class="hover:text-black">Privacy Policy</a></li>
                        <li><a href="#" class="hover:text-black">Terms of Service</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>

</div>

