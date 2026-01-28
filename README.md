# ryan-fitzgibbons.github.io
Executive Portfolio website 
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ryan Fitzgibbons | Nonprofit Executive Consultant</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --primary: #1e3a5f;
            --accent: #c9a227;
            --light: #f8f6f3;
            --dark: #0f172a;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--light);
            color: var(--dark);
            overflow-x: hidden;
        }
        
        h1, h2, h3, .serif {
            font-family: 'Playfair Display', serif;
        }
        
        .gradient-text {
            background: linear-gradient(135deg, var(--primary) 0%, #2d5a8f 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero-pattern {
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(30, 58, 95, 0.05) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(201, 162, 39, 0.05) 0%, transparent 50%);
        }
        
        .card-hover {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .card-hover:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.1);
        }
        
        .timeline-line {
            background: linear-gradient(to bottom, var(--primary), var(--accent));
        }
        
        .nav-blur {
            backdrop-filter: blur(12px);
            background: rgba(248, 246, 243, 0.85);
        }
        
        .skill-tag {
            background: rgba(30, 58, 95, 0.08);
            border: 1px solid rgba(30, 58, 95, 0.15);
            transition: all 0.3s ease;
        }
        
        .skill-tag:hover {
            background: var(--primary);
            color: white;
            transform: scale(1.05);
        }
        
        .reveal {
            opacity: 0;
            transform: translateY(30px);
        }
        
        .counter {
            font-variant-numeric: tabular-nums;
        }
        
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        
        ::-webkit-scrollbar-track {
            background: var(--light);
        }
        
        ::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 5px;
        }
        
        .hero-image-mask {
            mask-image: linear-gradient(to bottom, black 50%, transparent 100%);
            -webkit-mask-image: linear-gradient(to bottom, black 50%, transparent 100%);
        }
    </style>
</head>
<body class="antialiased">

    <!-- Navigation -->
    <nav class="fixed w-full z-50 nav-blur border-b border-gray-200/50 transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex-shrink-0">
                    <span class="serif text-2xl font-bold text-slate-800 tracking-tight">RF.</span>
                </div>
                <div class="hidden md:flex space-x-8">
                    <a href="#about" class="text-sm font-medium text-slate-600 hover:text-slate-900 transition-colors">About</a>
                    <a href="#expertise" class="text-sm font-medium text-slate-600 hover:text-slate-900 transition-colors">Expertise</a>
                    <a href="#experience" class="text-sm font-medium text-slate-600 hover:text-slate-900 transition-colors">Experience</a>
                    <a href="#impact" class="text-sm font-medium text-slate-600 hover:text-slate-900 transition-colors">Impact</a>
                    <a href="#contact" class="text-sm font-medium text-slate-600 hover:text-slate-900 transition-colors">Contact</a>
                </div>
                <button onclick="document.getElementById('contact').scrollIntoView({behavior: 'smooth'})" 
                        class="hidden md:inline-flex items-center px-6 py-2.5 border border-slate-800 text-sm font-medium rounded-full text-slate-800 hover:bg-slate-800 hover:text-white transition-all duration-300">
                    Let's Connect
                </button>
                <button class="md:hidden text-slate-800" onclick="toggleMobileMenu()">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
                    </svg>
                </button>
            </div>
        </div>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-t border-gray-200">
            <div class="px-4 pt-2 pb-6 space-y-1">
                <a href="#about" class="block px-3 py-2 text-base font-medium text-slate-700 hover:bg-slate-50">About</a>
                <a href="#expertise" class="block px-3 py-2 text-base font-medium text-slate-700 hover:bg-slate-50">Expertise</a>
                <a href="#experience" class="block px-3 py-2 text-base font-medium text-slate-700 hover:bg-slate-50">Experience</a>
                <a href="#contact" class="block px-3 py-2 text-base font-medium text-slate-700 hover:bg-slate-50">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center hero-pattern pt-20 overflow-hidden">
        <div class="absolute inset-0 z-0">
            <div class="absolute top-0 right-0 w-1/2 h-full bg-gradient-to-l from-slate-100/50 to-transparent"></div>
            <div class="absolute bottom-0 left-0 w-96 h-96 bg-amber-100/30 rounded-full blur-3xl"></div>
        </div>
        
        <div class="relative z-10 max-w-7xl mx-auto px-6 lg:px-8 py-20 lg:py-32">
            <div class="grid lg:grid-cols-2 gap-12 lg:gap-20 items-center">
                <div class="space-y-8 reveal">
                    <div class="inline-flex items-center space-x-2 px-4 py-2 rounded-full bg-slate-100 border border-slate-200">
                        <span class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></span>
                        <span class="text-sm font-medium text-slate-600">Available for Consulting Engagements</span>
                    </div>
                    
                    <h1 class="text-5xl lg:text-7xl font-bold leading-tight text-slate-900">
                        Ryan <br>
                        <span class="gradient-text">Fitzgibbons</span>
                    </h1>
                    
                    <p class="text-xl lg:text-2xl text-slate-600 font-light leading-relaxed max-w-2xl">
                        Senior nonprofit consultant and interim executive specializing in <span class="font-semibold text-slate-800">organizational stabilization</span>, <span class="font-semibold text-slate-800">turnaround</span>, and <span class="font-semibold text-slate-800">operational transformation</span>.
                    </p>
                    
                    <div class="flex flex-wrap gap-4 pt-4">
                        <button onclick="document.getElementById('contact').scrollIntoView({behavior: 'smooth'})" 
                                class="px-8 py-4 bg-slate-900 text-white rounded-full font-medium hover:bg-slate-800 transition-all duration-300 shadow-lg hover:shadow-xl transform hover:-translate-y-1">
                            Start a Conversation
                        </button>
                        <button onclick="document.getElementById('experience').scrollIntoView({behavior: 'smooth'})" 
                                class="px-8 py-4 border-2 border-slate-300 text-slate-700 rounded-full font-medium hover:border-slate-900 hover:text-slate-900 transition-all duration-300">
                            View Experience
                        </button>
                    </div>
                    
                    <div class="flex items-center space-x-6 pt-8 text-sm text-slate-500">
                        <div class="flex items-center space-x-2">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                            </svg>
                            <span>New London, CT</span>
                        </div>
                        <div class="flex items-center space-x-2">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                            </svg>
                            <span>rjfitzgibbons22@gmail.com</span>
                        </div>
                    </div>
                </div>
                
                <div class="relative lg:h-[600px] flex items-center justify-center reveal">
                    <div class="relative w-full max-w-md aspect-[4/5] rounded-2xl overflow-hidden shadow-2xl">
                        <div class="absolute inset-0 bg-gradient-to-br from-slate-800 to-slate-900 flex items-center justify-center">
                            <div class="text-center text-white p-8">
                                <div class="w-32 h-32 mx-auto mb-6 rounded-full bg-white/10 backdrop-blur-sm flex items-center justify-center border-2 border-white/20">
                                    <span class="serif text-5xl font-bold">RF</span>
                                </div>
                                <p class="text-lg font-light opacity-90">Trusted advisor to boards and executive teams during periods of change, growth, or leadership transition.</p>
                            </div>
                        </div>
                    </div>
                    <!-- Decorative elements -->
                    <div class="absolute -top-4 -right-4 w-24 h-24 bg-amber-400/20 rounded-full blur-2xl"></div>
                    <div class="absolute -bottom-4 -left-4 w-32 h-32 bg-slate-800/10 rounded-full blur-2xl"></div>
                </div>
            </div>
        </div>
        
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
            <svg class="w-6 h-6 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/>
            </svg>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="py-20 bg-white border-y border-gray-100">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
                <div class="reveal">
                    <div class="text-4xl lg:text-5xl font-bold text-slate-900 counter" data-target="15">0</div>
                    <div class="text-sm text-slate-500 mt-2 uppercase tracking-wider">Years Experience</div>
                </div>
                <div class="reveal">
                    <div class="text-4xl lg:text-5xl font-bold text-slate-900 counter" data-target="50">0</div>
                    <div class="text-sm text-slate-500 mt-2 uppercase tracking-wider">Organizations Advised</div>
                </div>
                <div class="reveal">
                    <div class="text-4xl lg:text-5xl font-bold text-slate-900 counter" data-target="4">0</div>
                    <div class="text-sm text-slate-500 mt-2 uppercase tracking-wider">States Led In</div>
                </div>
                <div class="reveal">
                    <div class="text-4xl lg:text-5xl font-bold text-slate-900">CT<span class="text-2xl">+</span></div>
                    <div class="text-sm text-slate-500 mt-2 uppercase tracking-wider">Dual Citizenship</div>
                </div>
            </div>
        </div>
    </section>

    <!-- About / Executive Summary -->
    <section id="about" class="py-24 lg:py-32 relative">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="grid lg:grid-cols-3 gap-12 lg:gap-20">
                <div class="lg:col-span-1 reveal">
                    <h2 class="text-sm font-bold text-amber-600 uppercase tracking-widest mb-4">Executive Summary</h2>
                    <h3 class="text-4xl lg:text-5xl font-bold text-slate-900 mb-6">Leadership Rooted in <span class="italic text-slate-600">Transformation</span></h3>
                    <div class="w-20 h-1 bg-amber-500"></div>
                </div>
                <div class="lg:col-span-2 space-y-6 text-lg text-slate-600 leading-relaxed reveal">
                    <p>
                        As a senior nonprofit consultant and interim executive, I specialize in entering complex environments, diagnosing structural and performance issues, and implementing practical solutions that strengthen governance, operations, and long-term sustainability.
                    </p>
                    <p>
                        My approach combines strategic vision with hands-on operational expertise. Whether serving as CEO, COO, or strategic advisor, I bring deep experience in organizational stabilization, digital transformation, and board relations. I have successfully led multi-site operations, managed complex budgets, and guided organizations through critical transitions across the nonprofit sector.
                    </p>
                    <p>
                        Based in New London, CT, I am available for consulting engagements, interim executive roles, and board advisory positions. I hold dual U.S. and Irish citizenship and am open to relocation or remote work arrangements.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Core Competencies -->
    <section id="expertise" class="py-24 bg-slate-50">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="text-center mb-16 reveal">
                <h2 class="text-sm font-bold text-amber-600 uppercase tracking-widest mb-4">Areas of Expertise</h2>
                <h3 class="text-4xl lg:text-5xl font-bold text-slate-900">Core Competencies</h3>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Competency 1 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover reveal border border-gray-100">
                    <div class="w-12 h-12 bg-slate-900 rounded-xl flex items-center justify-center mb-6 text-white">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
                        </svg>
                    </div>
                    <h4 class="text-xl font-bold text-slate-900 mb-3">Organizational Strategy & Turnarounds</h4>
                    <p class="text-slate-600 leading-relaxed">Leading strategic planning engagements that define growth priorities, performance metrics, and multi-year action plans for sustainable success.</p>
                </div>

                <!-- Competency 2 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover reveal border border-gray-100">
                    <div class="w-12 h-12 bg-slate-900 rounded-xl flex items-center justify-center mb-6 text-white">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/>
                        </svg>
                    </div>
                    <h4 class="text-xl font-bold text-slate-900 mb-3">Board Relations & Governance</h4>
                    <p class="text-slate-600 leading-relaxed">Trusted advisor to nonprofit boards, facilitating governance improvements and strategic alignment between leadership and oversight bodies.</p>
                </div>

                <!-- Competency 3 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover reveal border border-gray-100">
                    <div class="w-12 h-12 bg-slate-900 rounded-xl flex items-center justify-center mb-6 text-white">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 7h6m0 10v-3m-3 3h.01M9 17h.01M9 14h.01M12 14h.01M15 11h.01M12 11h.01M9 11h.01M7 21h10a2 2 0 002-2V5a2 2 0 00-2-2H7a2 2 0 00-2 2v14a2 2 0 002 2z"/>
                        </svg>
                    </div>
                    <h4 class="text-xl font-bold text-slate-900 mb-3">Financial Management</h4>
                    <p class="text-slate-600 leading-relaxed">Comprehensive budgeting, forecasting, and financial analysis with established internal controls for fiscal responsibility and transparency.</p>
                </div>

                <!-- Competency 4 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover reveal border border-gray-100">
                    <div class="w-12 h-12 bg-slate-900 rounded-xl flex items-center justify-center mb-6 text-white">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
                        </svg>
                    </div>
                    <h4 class="text-xl font-bold text-slate-900 mb-3">Operational Excellence</h4>
                    <p class="text-slate-600 leading-relaxed">Process redesign and workflow optimization to improve accountability, efficiency, and organizational capacity across departments.</p>
                </div>

                <!-- Competency 5 -->
                <div class="bg-white p-8 rounded-2xl shadow-sm card-hover reveal border border-gray-100">
                    <div class="w-12 h-12 bg-slate-900 rounded-xl flex items-center justify-center mb-6 text-white">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.82