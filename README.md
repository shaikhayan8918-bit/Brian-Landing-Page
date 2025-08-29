# Brian-Landing-Page
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Action Academy - Build Real Wealth Through Asset Ownership</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            overflow-x: hidden;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #0f0f0f 0%, #1a1a2e 50%, #16213e 100%);
            color: white;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="1" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: 100px 100px;
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
        }

        .preheader {
            font-size: 1rem;
            color: #64ffda;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 30px;
            background: linear-gradient(45deg, #64ffda, #ffffff, #64ffda);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 3s ease infinite, fadeInUp 1s ease 0.4s both;
        }

        @keyframes gradient {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .subheader {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            margin-bottom: 40px;
            color: #e0e0e0;
            animation: fadeInUp 1s ease 0.6s both;
        }

        .vsl-container {
            margin: 40px 0;
            animation: fadeInUp 1s ease 0.8s both;
        }

        .vsl-placeholder {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 60px;
            position: relative;
            cursor: pointer;
            transition: all 0.3s ease;
            max-width: 600px;
            margin: 0 auto;
        }

        .vsl-placeholder:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(100, 255, 218, 0.2);
        }

        .play-button {
            width: 80px;
            height: 80px;
            background: linear-gradient(45deg, #64ffda, #4fc3f7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.3);
            transition: all 0.3s ease;
        }

        .play-button::after {
            content: '';
            width: 0;
            height: 0;
            border-left: 25px solid white;
            border-top: 15px solid transparent;
            border-bottom: 15px solid transparent;
            margin-left: 5px;
        }

        .vsl-placeholder:hover .play-button {
            transform: scale(1.1);
        }

        .cta-button {
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            color: white;
            padding: 20px 40px;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.3);
            animation: fadeInUp 1s ease 1s both;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 107, 53, 0.5);
        }

        /* Section Styles */
        .section {
            padding: 100px 0;
            position: relative;
        }

        .section:nth-child(even) {
            background: #f8fafc;
        }

        .section h2 {
            font-size: clamp(2rem, 4vw, 3.5rem);
            font-weight: 900;
            margin-bottom: 30px;
            text-align: center;
            color: #1a1a1a;
            position: relative;
        }

        .section.problem h2,
        .section.dark h2 {
            color: white;
        }

        .section.problem .section-content,
        .section.dark .section-content {
            color: #e0e0e0;
        }

        .section h2::after {
            content: '';
            width: 100px;
            height: 4px;
            background: linear-gradient(45deg, #64ffda, #4fc3f7);
            display: block;
            margin: 20px auto;
            border-radius: 2px;
        }

        .section-content {
            font-size: 1.2rem;
            line-height: 1.8;
            max-width: 800px;
            margin: 0 auto;
            color: #1a1a1a;
        }

        .section.problem .section-content,
        .section.dark .section-content {
            color: #e0e0e0;
        }

        /* Problem Section */
        .problem {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #1a1a1a;
        }

        .pain-points {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .pain-point {
            background: white;
            padding: 30px;
            border-radius: 15px;
            border: 1px solid #e2e8f0;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .pain-point:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        /* Solution Section */
        .solution-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .solution-card {
            background: white;
            padding: 40px 30px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid #e2e8f0;
        }

        .solution-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
        }

        .solution-card h3 {
            color: #64ffda;
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 20px;
        }

        /* Bullets */
        .benefits-list {
            list-style: none;
            margin: 40px 0;
        }

        .benefits-list li {
            padding: 15px 0;
            border-bottom: 1px solid #e2e8f0;
            position: relative;
            padding-left: 40px;
            font-size: 1.1rem;
            line-height: 1.6;
        }

        .benefits-list li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #64ffda;
            font-weight: 700;
            font-size: 1.2rem;
        }

        .benefits-list li:last-child {
            border-bottom: none;
        }

        /* FAQ Section */
        .faq-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .faq-item {
            background: white;
            border-radius: 10px;
            margin-bottom: 20px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .faq-question {
            padding: 25px;
            cursor: pointer;
            font-weight: 700;
            font-size: 1.1rem;
            border: none;
            background: none;
            width: 100%;
            text-align: left;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .faq-answer {
            padding: 0 25px 25px;
            display: none;
            color: #666;
            line-height: 1.6;
        }

        .faq-item.active .faq-answer {
            display: block;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 0 15px;
            }
            
            .section {
                padding: 60px 0;
            }
            
            .vsl-placeholder {
                padding: 40px 20px;
            }
            
            .play-button {
                width: 60px;
                height: 60px;
            }
            
            .cta-button {
                padding: 15px 30px;
                font-size: 1rem;
            }
        }

        /* Animations */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .animate-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Floating Elements */
        .floating-element {
            position: absolute;
            opacity: 0.1;
            animation: floatSlow 15s ease-in-out infinite;
        }

        @keyframes floatSlow {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(180deg); }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="floating-element" style="top: 10%; left: 10%; font-size: 3rem;">💼</div>
        <div class="floating-element" style="top: 20%; right: 15%; font-size: 2rem;">📈</div>
        <div class="floating-element" style="bottom: 20%; left: 20%; font-size: 2.5rem;">🏠</div>
        
        <div class="container">
            <div class="hero-content">
                <div class="preheader">For High-Performing Professionals Ready to Build Real Wealth</div>
                
                <h1>Replace Your Income With $10K-$20K Monthly Cash Flow From Assets... in 12 Months</h1>
                
                <div class="subheader">
                    Without quitting your job until the money's already flowing (and without wasting years on theoretical fluff that never pays)
                </div>
                
                <div class="vsl-container">
                    <div class="vsl-placeholder" onclick="playVideo()">
                        <div class="play-button"></div>
                        <h3 style="margin: 0; color: white;">Watch: How Sarah Went From Corporate Burnout to $18K/Month in Real Estate Cash Flow</h3>
                        <p style="margin: 10px 0 0; color: #e0e0e0;">See the exact 4-step system she used (without any prior experience)</p>
                    </div>
                </div>
                
                <button class="cta-button" onclick="bookCall()">Book Your FREE Strategy Call</button>
            </div>
        </div>
    </section>

    <!-- Problem Section -->
    <section class="section problem">
        <div class="container">
            <h2 style="color: #1a1a1a;">You're Smart, Successful... But Still Trading Time for Money</h2>
            
            <div class="section-content" style="text-align: center; color: #1a1a1a;">
                <p style="font-size: 1.3rem; margin-bottom: 40px; color: #1a1a1a;">
                    You've climbed the corporate ladder. You make good money. You've got the nice house, the decent savings...
                </p>
                
                <p style="font-size: 1.3rem; margin-bottom: 40px; color: #1a1a1a;">
                    <strong>But deep down, you know you're still just another highly-paid employee.</strong>
                </p>
            </div>
            
            <div class="pain-points animate-on-scroll">
                <div class="pain-point">
                    <h3 style="color: #64ffda; margin-bottom: 15px;">The Golden Handcuffs</h3>
                    <p style="color: #1a1a1a;">Your salary feels like a leash. Miss a few paychecks and everything falls apart. You're making someone else rich while your own wealth stays stuck.</p>
                </div>
                
                <div class="pain-point">
                    <h3 style="color: #64ffda; margin-bottom: 15px;">Analysis Paralysis</h3>
                    <p style="color: #1a1a1a;">You've researched real estate, businesses, crypto... but every "guru" gives you different advice. You're drowning in theory with no clear path to action.</p>
                </div>
                
                <div class="pain-point">
                    <h3 style="color: #64ffda; margin-bottom: 15px;">The Time Trap</h3>
                    <p style="color: #1a1a1a;">Your job demands 50+ hour weeks. When do you have time to build something meaningful? Evenings and weekends aren't enough to build real wealth.</p>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 60px;">
                <p style="font-size: 1.4rem; color: #ff6b35; font-weight: 700;">
                    Here's the brutal truth: Another year of "someday" thinking just cost you $120K+ in potential cash flow.
                </p>
            </div>
        </div>
    </section>

    <!-- Origin Story Section -->
    <section class="section">
        <div class="container">
            <h2>I Was Trapped in the Same Corporate Prison You're In Right Now</h2>
            
            <div class="section-content animate-on-scroll">
                <p><strong>Three years ago, I was making $180K as a senior consultant.</strong></p>
                
                <p>On paper, I had it made. Corner office, expense account, respect from colleagues...</p>
                
                <p>But I was miserable.</p>
                
                <p>I was working 60-hour weeks, missing my kids' bedtime stories, and watching my life slip by while making my boss richer.</p>
                
                <p><strong>The breaking point came during a "mandatory" Saturday meeting.</strong></p>
                
                <p>I was sitting there, listening to executives discuss their third vacation homes while I hadn't taken a real vacation in two years.</p>
                
                <p>That's when it hit me...</p>
                
                <p><strong>They weren't smarter than me. They just owned assets instead of selling their time.</strong></p>
                
                <p>So I started studying successful asset owners. Not the YouTube gurus or seminar speakers... but actual millionaires who built wealth through cash-flowing properties and businesses.</p>
                
                <p>I discovered something that changed everything:</p>
                
                <p><strong>There's a proven sequence that every successful asset owner follows. A step-by-step blueprint that works regardless of your starting capital or experience.</strong></p>
                
                <p>I call it the <strong>Freedom Blueprint</strong>... and it's the complete opposite of everything the "gurus" teach.</p>
            </div>
        </div>
    </section>

    <!-- Solution Section -->
    <section class="section" style="background: #f8fafc;">
        <div class="container">
            <h2>The Freedom Blueprint: How to Build $10K-$20K Monthly Cash Flow in 12 Months</h2>
            
            <div class="section-content animate-on-scroll" style="text-align: center;">
                <p style="font-size: 1.3rem; margin-bottom: 40px;">
                    Forget everything you've heard about "passive income." 
                    <strong>Real wealth comes from owning cash-flowing assets that pay you every month.</strong>
                </p>
                
                <p style="font-size: 1.3rem; margin-bottom: 60px;">
                    Here's exactly how it works:
                </p>
            </div>
            
            <div class="solution-grid">
                <div class="solution-card animate-on-scroll">
                    <h3>1. Freedom Blueprint</h3>
                    <p><strong>Your custom roadmap in 30 days.</strong> We reverse-engineer your dream life into specific asset targets, income goals, and daily KPIs. No more guessing what to buy or when to buy it.</p>
                </div>
                
                <div class="solution-card animate-on-scroll">
                    <h3>2. Acquisition Accelerator</h3>
                    <p><strong>6 years of deal-making knowledge in 60 days.</strong> Learn to source, underwrite, and negotiate like a pro. Our members average 3-5 qualified deals in their pipeline within 90 days.</p>
                </div>
                
                <div class="solution-card animate-on-scroll">
                    <h3>3. Connection Concierge</h3>
                    <p><strong>82% of our members get their deals funded.</strong> We connect you with vetted investors and partners, plus teach you the exact scripts and strategies to raise capital fast.</p>
                </div>
                
                <div class="solution-card animate-on-scroll">
                    <h3>4. Systems & Stabilization</h3>
                    <p><strong>Turn your asset into a cash-flowing machine.</strong> We show you how to structure operations, hire teams, and build systems so your investment pays you instead of headaches.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Product Introduction Section -->
    <section class="section">
        <div class="container">
            <h2>Introducing The Action Academy: Your 12-Month Journey to Asset Ownership</h2>
            
            <div class="section-content animate-on-scroll">
                <p style="font-size: 1.3rem; text-align: center; margin-bottom: 40px;">
                    This isn't another online course you'll never finish. 
                    <strong>It's a complete transformation system with live mentorship, deal support, and a community of successful asset owners.</strong>
                </p>
                
                <ul class="benefits-list">
                    <li><strong>Weekly Strategy Pods:</strong> Small group coaching with asset acquisition experts who've been in your shoes and built 7-figure portfolios → Get personalized guidance without paying $500/hour consulting fees → <em>Finally become the person who takes action instead of just consuming content</em></li>
                    
                    <li><strong>Deal Concierge Service:</strong> Our team helps you source, analyze, and structure your first acquisition → Skip the 2-year learning curve and avoid costly newbie mistakes → <em>Walk into every negotiation with confidence knowing experts have your back</em></li>
                    
                    <li><strong>Capital Connection Network:</strong> Access to vetted investors, lenders, and partners actively looking to fund deals → Raise $100K-$500K without touching your retirement accounts → <em>Never again say "I found a great deal but couldn't get the money"</em></li>
                    
                    <li><strong>Operations Playbook:</strong> Step-by-step systems for managing your asset post-acquisition → Turn your investment into a well-oiled cash-flowing machine → <em>Build something that pays you even when you're sleeping</em></li>
                    
                    <li><strong>Quarterly Mastermind Events:</strong> Network with other high-achievers building real wealth → Find potential partners, investors, and lifelong business relationships → <em>Surround yourself with people who think bigger than your current circle</em></li>
                    
                    <li><strong>24/7 Member Portal:</strong> Templates, contracts, analysis tools, and recorded training sessions → Everything you need to evaluate and close deals fast → <em>Stop wasting time recreating what already works perfectly</em></li>
                </ul>
                
                <div style="text-align: center; margin-top: 60px;">
                    <p style="font-size: 1.4rem; color: #1a1a1a; font-weight: 700; margin-bottom: 30px;">
                        <strong>82% of Action Academy members close their first deal within 6 months.</strong>
                    </p>
                    
                    <p style="font-size: 1.2rem; color: #666;">
                        Average first-year cash flow: $156,000
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Offer Section -->
    <section class="section dark" style="background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%); color: white;">
        <div class="container">
            <h2 style="color: white;">Here's How to Get Started Today</h2>
            
            <div class="section-content animate-on-scroll" style="text-align: center;">
                <p style="font-size: 1.3rem; margin-bottom: 40px;">
                    I could charge $25,000 for this level of personal mentorship and deal support. 
                    <strong>Most acquisition consultants charge $500-1,000 per hour.</strong>
                </p>
                
                <p style="font-size: 1.3rem; margin-bottom: 40px;">
                    But I'm not interested in working with just wealthy people who already have everything figured out.
                </p>
                
                <p style="font-size: 1.4rem; margin-bottom: 60px; color: #64ffda; font-weight: 700;">
                    I want to work with ambitious professionals who are ready to build something bigger.
                </p>
                
                <div style="background: rgba(255, 255, 255, 0.1); backdrop-filter: blur(10px); padding: 40px; border-radius: 20px; margin-bottom: 40px; border: 1px solid rgba(255, 255, 255, 0.2);">
                    <h3 style="color: #64ffda; font-size: 1.8rem; margin-bottom: 20px;">Your Investment: One Strategy Call</h3>
                    <p style="font-size: 1.2rem; margin-bottom: 20px;">
                        Book a 30-45 minute call where we'll create your personalized Freedom Blueprint and determine if you're a fit for our community.
                    </p>
                    <p style="font-size: 1rem; color: #e0e0e0;">
                        <strong>Fair Warning:</strong> We only work with serious action-takers who have at least $15K available for their first acquisition and the commitment to follow our proven system.
                    </p>
                </div>
                
                <p style="font-size: 1.1rem; margin-bottom: 40px; color: #e0e0e0;">
                    <strong>Here's my guarantee:</strong> If you complete our Freedom Blueprint process and don't have complete clarity on your path to asset ownership, I'll personally work with you until you do.
                </p>
                
                <button class="cta-button" onclick="bookCall()" style="font-size: 1.3rem; padding: 25px 50px;">
                    Book My Strategy Call Now
                </button>
                
                <p style="font-size: 0.9rem; margin-top: 20px; color: #ff6b35;">
                    <strong>Only 47 strategy calls available this month.</strong> We limit our intake to ensure quality support for every member.
                </p>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="section">
        <div class="container">
            <h2>Questions Smart People Ask (Before They Join)</h2>
            
            <div class="faq-container animate-on-scroll">
                <div class="faq-item">
                    <button class="faq-question" onclick="toggleFAQ(this)">
                        What if I don't have $100K to invest in real estate?
                        <span>+</span>
                    </button>
                    <div class="faq-answer">
                        <p>Most of our successful members started with $15K-50K. We teach you how to leverage other people's money, find creative financing, and structure deals that require minimal down payments. Our Connection Concierge has helped members raise $2.3M in capital in the past 12 months alone.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question" onclick="toggleFAQ(this)">
                        I work 50+ hours per week. Do I have time for this?
                        <span>+</span>
                    </button>
                    <div class="faq-answer">
                        <p>Actually, being busy is an advantage. You're already disciplined and results-focused. Our system is designed for working professionals - you'll spend 5-7 hours per week on structured activities that move you toward asset ownership. Most members close their first deal while still working full-time.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question" onclick="toggleFAQ(this)">
                        How is this different from other real estate courses?
                        <span>+</span>
                    </button>
                    <div class="faq-answer">
                        <p>Three key differences: 1) We focus on multiple asset classes (real estate, businesses, land), not just one strategy. 2) You get personal mentorship and deal support, not just video lessons. 3) Our Connection Concierge actually helps you raise capital - we don't just tell you to "find the money somewhere."</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question" onclick="toggleFAQ(this)">
                        What if I live outside the US?
                        <span>+</span>
                    </button>
                    <div class="faq-answer">
                        <p>Our principles work globally, but our specific deal flow and investor network is primarily US-focused. If you're outside the US, the strategy call will help determine if our approach fits your local market and regulations.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question" onclick="toggleFAQ(this)">
                        Do you guarantee I'll make money?
                        <span>+</span>
                    </button>
                    <div class="faq-answer">
                        <p>We guarantee the quality of our training, mentorship, and support - not your results. Asset ownership requires work, capital, and commitment. What we can promise is that if you follow our system completely and don't see clear progress toward your first acquisition within 90 days, we'll work with you personally until you do.</p>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 60px;">
                <button class="cta-button" onclick="bookCall()">
                    Stop Overthinking. Book Your Call.
                </button>
            </div>
        </div>
    </section>

    <script>
        // Animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.animate-on-scroll').forEach(el => {
            observer.observe(el);
        });

        // FAQ Toggle
        function toggleFAQ(button) {
            const item = button.parentElement;
            const isActive = item.classList.contains('active');
            
            // Close all FAQ items
            document.querySelectorAll('.faq-item').forEach(faq => {
                faq.classList.remove('active');
                faq.querySelector('.faq-question span').textContent = '+';
            });
            
            // Open clicked item if it wasn't active
            if (!isActive) {
                item.classList.add('active');
                button.querySelector('span').textContent = '-';
            }
        }

        // Mock functions for demo
        function playVideo() {
            alert('Video would play here in the actual implementation');
        }

        function bookCall() {
            // Replace with your actual booking URL
            window.open('https://calendly.com/actionacademy/strategy-call', '_blank');
        }

        // Smooth scrolling for internal links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Add some dynamic interactivity
        document.addEventListener('DOMContentLoaded', function() {
            // Add floating animation delays
            const floatingElements = document.querySelectorAll('.floating-element');
            floatingElements.forEach((el, index) => {
                el.style.animationDelay = `${index * 2}s`;
            });

            // Add scroll-triggered animations for cards
            const cards = document.querySelectorAll('.solution-card, .pain-point');
            cards.forEach((card, index) => {
                card.style.animationDelay = `${index * 0.1}s`;
            });
        });
    </script>
</body>
</html>
