<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HackSphere 2025 - Code. Create. Conquer.</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.6;
            color: #ffffff;
            background: #000;
            overflow-x: hidden;
            cursor: none;
        }

        /* Custom cursor */
        .cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            mix-blend-mode: difference;
            transition: transform 0.1s ease;
        }

        .cursor-follower {
            position: fixed;
            width: 40px;
            height: 40px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9998;
            transition: all 0.3s ease;
        }

        /* Epic animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #000 0%, #1a1a2e 25%, #16213e 50%, #0f3460 75%, #000 100%);
            background-size: 400% 400%;
            animation: epicGradient 10s ease infinite;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 20%, rgba(255, 107, 107, 0.4) 0%, transparent 40%),
                radial-gradient(circle at 80% 80%, rgba(78, 205, 196, 0.4) 0%, transparent 40%),
                radial-gradient(circle at 40% 60%, rgba(69, 183, 209, 0.4) 0%, transparent 40%),
                radial-gradient(circle at 70% 30%, rgba(150, 206, 180, 0.4) 0%, transparent 40%);
            animation: morphingOrbs 15s ease-in-out infinite;
        }

        .bg-animation::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="0.5"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
            animation: gridMove 20s linear infinite;
        }

        @keyframes epicGradient {
            0%, 100% { background-position: 0% 50%; }
            25% { background-position: 100% 0%; }
            50% { background-position: 100% 100%; }
            75% { background-position: 0% 100%; }
        }

        @keyframes morphingOrbs {
            0%, 100% { transform: translate(0, 0) scale(1) rotate(0deg); opacity: 0.8; }
            25% { transform: translate(50px, -30px) scale(1.2) rotate(90deg); opacity: 1; }
            50% { transform: translate(-30px, 40px) scale(0.8) rotate(180deg); opacity: 0.6; }
            75% { transform: translate(40px, -50px) scale(1.1) rotate(270deg); opacity: 0.9; }
        }

        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(10px, 10px); }
        }

        /* Hero Section with 3D effects */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 2rem;
            position: relative;
            perspective: 1000px;
        }

        .hero-content {
            max-width: 900px;
            z-index: 2;
            transform-style: preserve-3d;
            animation: heroFloat 6s ease-in-out infinite;
        }

        @keyframes heroFloat {
            0%, 100% { transform: translateY(0px) rotateX(0deg); }
            50% { transform: translateY(-20px) rotateX(2deg); }
        }

        .hero h1 {
            font-size: clamp(3.5rem, 10vw, 8rem);
            font-weight: 900;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #feca57, #ff9ff3);
            background-size: 600% 600%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: rainbowShimmer 4s ease-in-out infinite;
            text-shadow: 0 0 30px rgba(255, 107, 107, 0.5);
            letter-spacing: -0.02em;
        }

        @keyframes rainbowShimmer {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .tagline {
            font-size: clamp(1.5rem, 4vw, 2.5rem);
            margin-bottom: 2rem;
            font-weight: 300;
            letter-spacing: 0.15em;
            opacity: 0.95;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
            animation: taglinePulse 3s ease-in-out infinite;
        }

        @keyframes taglinePulse {
            0%, 100% { opacity: 0.95; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.02); }
        }

        .event-details {
            font-size: clamp(1.1rem, 3vw, 1.8rem);
            margin-bottom: 3rem;
            padding: 2rem 3rem;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(25px);
            border-radius: 25px;
            border: 2px solid transparent;
            background-clip: padding-box;
            box-shadow: 
                0 15px 40px rgba(0, 0, 0, 0.3),
                inset 0 1px 0 rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            animation: detailsGlow 4s ease-in-out infinite;
        }

        .event-details::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            border-radius: 25px;
            z-index: -1;
            animation: borderGlow 3s linear infinite;
        }

        @keyframes detailsGlow {
            0%, 100% { box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3), inset 0 1px 0 rgba(255, 255, 255, 0.2); }
            50% { box-shadow: 0 25px 60px rgba(255, 107, 107, 0.4), inset 0 1px 0 rgba(255, 255, 255, 0.3); }
        }

        @keyframes borderGlow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .cta-button {
            display: inline-block;
            padding: 25px 60px;
            font-size: 1.4rem;
            font-weight: 800;
            text-decoration: none;
            color: #000;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 50px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 
                0 15px 40px rgba(255, 107, 107, 0.5),
                0 5px 20px rgba(78, 205, 196, 0.3);
            position: relative;
            overflow: hidden;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            border: 2px solid transparent;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.6), transparent);
            transition: left 0.6s ease;
        }

        .cta-button::after {
            content: '🚀';
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.2em;
            opacity: 0;
            transition: all 0.3s ease;
        }

        .cta-button:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 
                0 25px 60px rgba(255, 107, 107, 0.7),
                0 10px 30px rgba(78, 205, 196, 0.5);
            background: linear-gradient(45deg, #4ecdc4, #ff6b6b);
        }

        .cta-button:hover::before {
            left: 100%;
        }

        .cta-button:hover::after {
            opacity: 1;
            right: 15px;
        }

        /* About Section with enhanced effects */
        .about {
            padding: 10rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
        }

        .about h2 {
            font-size: clamp(3rem, 6vw, 5rem);
            text-align: center;
            margin-bottom: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #feca57);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: megaGradientFlow 5s ease infinite;
            text-shadow: 0 0 40px rgba(255, 107, 107, 0.3);
        }

        @keyframes megaGradientFlow {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.3rem;
            line-height: 1.9;
            opacity: 0.95;
        }

        .about-text p {
            margin-bottom: 2rem;
            padding: 3rem;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.03));
            backdrop-filter: blur(20px);
            border-radius: 25px;
            border: 1px solid rgba(255, 255, 255, 0.15);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .about-text p::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.8s ease;
        }

        .about-text p:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.08));
        }

        .about-text p:hover::before {
            left: 100%;
        }

        /* Enhanced Features Section */
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 5rem;
        }

        .feature {
            text-align: center;
            padding: 3rem 2rem;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.12), rgba(255, 255, 255, 0.04));
            backdrop-filter: blur(20px);
            border-radius: 30px;
            border: 2px solid rgba(255, 255, 255, 0.1);
            transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .feature::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(255, 107, 107, 0.2), transparent, rgba(78, 205, 196, 0.2), transparent);
            animation: rotate 10s linear infinite;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .feature:hover::before {
            opacity: 1;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .feature:hover {
            transform: translateY(-15px) scale(1.05);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.18), rgba(255, 255, 255, 0.08));
            border-color: rgba(255, 255, 255, 0.3);
        }

        .feature-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            display: block;
            animation: iconBounce 2s ease-in-out infinite;
        }

        @keyframes iconBounce {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .feature h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .feature p {
            font-size: 1.1rem;
            line-height: 1.6;
            opacity: 0.9;
        }

        /* Enhanced Footer */
        .footer {
            text-align: center;
            padding: 5rem 2rem;
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.8), rgba(26, 26, 46, 0.8));
            backdrop-filter: blur(30px);
            border-top: 2px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .footer::before {
            content: '';
            position: absolute;
            top: -2px;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            animation: footerGlow 3s linear infinite;
        }

        @keyframes footerGlow {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .footer p {
            font-size: 1.1rem;
            opacity: 0.8;
            font-weight: 300;
        }

        /* Enhanced floating particles */
        .particle {
            position: absolute;
            border-radius: 50%;
            pointer-events: none;
            animation: megaFloat 20s infinite linear;
        }

        .particle:nth-child(odd) {
            background: radial-gradient(circle, rgba(255, 107, 107, 0.8), transparent);
        }

        .particle:nth-child(even) {
            background: radial-gradient(circle, rgba(78, 205, 196, 0.8), transparent);
        }

        @keyframes megaFloat {
            0% {
                transform: translateY(100vh) rotate(0deg) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
                transform: translateY(90vh) rotate(36deg) scale(1);
            }
            90% {
                opacity: 1;
                transform: translateY(10vh) rotate(324deg) scale(1);
            }
            100% {
                transform: translateY(-10vh) rotate(360deg) scale(0);
                opacity: 0;
            }
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .hero {
                padding: 1rem;
            }
            
            .about {
                padding: 6rem 1rem;
            }
            
            .features {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .cta-button {
                padding: 20px 40px;
                font-size: 1.2rem;
            }

            body {
                cursor: auto;
            }

            .cursor, .cursor-follower {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="cursor"></div>
    <div class="cursor-follower"></div>
    <div class="bg-animation"></div>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>HackSphere 2025</h1>
            <p class="tagline">Code. Create. Conquer.</p>
            <div class="event-details">
                <strong>June 20–22, 2025 – Online</strong><br>
                48 Hours of Innovation & Global Collaboration
            </div>
            <a href="#register" class="cta-button">Register Now</a>
        </div>
    </section>

    <!-- About Section -->
    <section class="about">
        <h2>About HackSphere</h2>
        <div class="about-content">
            <div class="about-text">
                <p>HackSphere 2025 is the ultimate global hackathon experience, bringing together the brightest minds in technology for an intense 48-hour marathon of creativity and innovation. Join thousands of developers, designers, and creators from around the world as they collaborate, compete, and push the boundaries of what's possible in the digital realm.</p>
                
                <p>Whether you're a seasoned developer or just starting your coding journey, HackSphere offers the perfect platform to showcase your skills, learn from industry experts, and build solutions that could change the world. With mentorship from tech leaders, exciting prizes, and networking opportunities that last a lifetime, this is more than just a hackathon—it's your gateway to the future of technology and innovation.</p>
            </div>
        </div>

        <div class="features">
            <div class="feature">
                <span class="feature-icon">🌍</span>
                <h3>Global Community</h3>
                <p>Connect with innovators from every continent and build lasting relationships with the world's most creative minds.</p>
            </div>
            <div class="feature">
                <span class="feature-icon">⚡</span>
                <h3>48-Hour Sprint</h3>
                <p>Intense, focused development sessions that transform wild ideas into working prototypes in record time.</p>
            </div>
            <div class="feature">
                <span class="feature-icon">🏆</span>
                <h3>Epic Prizes</h3>
                <p>Compete for life-changing cash prizes, dream internships, and exclusive opportunities with leading tech giants.</p>
            </div>
            <div class="feature">
                <span class="feature-icon">🚀</span>
                <h3>Expert Mentorship</h3>
                <p>Get personalized guidance from industry legends and successful entrepreneurs throughout your hackathon journey.</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <p>© 2025 HackSphere. All rights reserved.</p>
    </footer>

    <script>
        // Custom cursor
        const cursor = document.querySelector('.cursor');
        const cursorFollower = document.querySelector('.cursor-follower');

        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX - 10 + 'px';
            cursor.style.top = e.clientY - 10 + 'px';
            
            setTimeout(() => {
                cursorFollower.style.left = e.clientX - 20 + 'px';
                cursorFollower.style.top = e.clientY - 20 + 'px';
            }, 100);
        });

        // Cursor hover effects
        const hoverElements = document.querySelectorAll('a, .feature, .about-text p');
        hoverElements.forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursor.style.transform = 'scale(1.5)';
                cursorFollower.style.transform = 'scale(1.5)';
            });
            el.addEventListener('mouseleave', () => {
                cursor.style.transform = 'scale(1)';
                cursorFollower.style.transform = 'scale(1)';
            });
        });

        // Enhanced floating particles
        function createMegaParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            
            const size = Math.random() * 8 + 3;
            particle.style.width = size + 'px';
            particle.style.height = size + 'px';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDuration = (Math.random() * 15 + 15) + 's';
            particle.style.animationDelay = Math.random() * 5 + 's';
            
            document.body.appendChild(particle);
            
            setTimeout(() => {
                particle.remove();
            }, 25000);
        }

        // Create particles more frequently
        setInterval(createMegaParticle, 200);

        // Enhanced CTA button interaction
        document.querySelector('.cta-button').addEventListener('click', function(e) {
            e.preventDefault();
            
            // Create explosion effect
            for (let i = 0; i < 20; i++) {
                const spark = document.createElement('div');
                spark.style.position = 'absolute';
                spark.style.left = e.clientX + 'px';
                spark.style.top = e.clientY + 'px';
                spark.style.width = '4px';
                spark.style.height = '4px';
                spark.style.background = '#ff6b6b';
                spark.style.borderRadius = '50%';
                spark.style.pointerEvents = 'none';
                spark.style.zIndex = '9999';
                
                const angle = (i / 20) * Math.PI * 2;
                const velocity = Math.random() * 100 + 50;
                
                spark.style.animation = `sparkFly 1s ease-out forwards`;
                spark.style.setProperty('--dx', Math.cos(angle) * velocity + 'px');
                spark.style.setProperty('--dy', Math.sin(angle) * velocity + 'px');
                
                document.body.appendChild(spark);
                setTimeout(() => spark.remove(), 1000);
            }
            
            this.style.transform = 'scale(0.9)';
            setTimeout(() => {
                this.style.transform = 'translateY(-8px) scale(1.05)';
            }, 150);
        });

        // Add spark animation
        const sparkStyle = document.createElement('style');
        sparkStyle.textContent = `
            @keyframes sparkFly {
                0% { 
                    transform: translate(0, 0) scale(1); 
                    opacity: 1; 
                }
                100% { 
                    transform: translate(var(--dx), var(--dy)) scale(0); 
                    opacity: 0; 
                }
            }
        `;
        document.head.appendChild(sparkStyle);

        // Enhanced scroll-triggered animations
        function animateOnScroll() {
            const elements = document.querySelectorAll('.feature, .about-text p, .about h2');
            
            elements.forEach((element, index) => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    setTimeout(() => {
                        element.style.opacity = '1';
                        element.style.transform = 'translateY(0) scale(1)';
                    }, index * 100);
                }
            });
        }

        // Initialize elements for staggered animation
        document.querySelectorAll('.feature, .about-text p, .about h2').forEach((element, index) => {
            element.style.opacity = '0';
            element.style.transform = 'translateY(80px) scale(0.8)';
            element.style.transition = 'all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
        });

        window.addEventListener('scroll', animateOnScroll);
        window.addEventListener('load', animateOnScroll);

        // Parallax scrolling effect
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.bg-animation');
            const speed = scrolled * 0.5;
            parallax.style.transform = `translateY(${speed}px)`;
        });

        // Interactive background response to mouse
        document.addEventListener('mousemove', (e) => {
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            document.querySelector('.bg-animation').style.transform = 
                `translate(${x * 20}px, ${y * 20}px)`;
        });
    </script>
</body>
</html>
