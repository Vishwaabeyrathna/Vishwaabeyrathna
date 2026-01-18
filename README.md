<! DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vishwa Abeyrathna - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        : root {
            --primary-color: #00d4ff;
            --secondary-color: #ff006e;
            --tertiary-color: #00ff88;
            --dark-bg: #0a0e27;
            --card-bg: #1a1f3a;
            --text-primary: #ffffff;
            --text-secondary: #b0b8d4;
            --accent: #ffa500;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background:  linear-gradient(135deg, #0a0e27 0%, #1a1f3a 50%, #0d1b2a 100%);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animated Background */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width:  100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(0, 212, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 0, 110, 0.1) 0%, transparent 50%);
            animation: drift 20s infinite;
            pointer-events: none;
            z-index: 0;
        }

        @keyframes drift {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(30px, 30px); }
        }

        . container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header Section */
        header {
            text-align: center;
            padding: 60px 20px;
            margin:  40px 0;
            position: relative;
        }

        .header-content {
            display: inline-block;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1) 0%, rgba(255, 0, 110, 0.1) 100%);
            padding: 40px 60px;
            border-radius:  20px;
            border: 2px solid rgba(0, 212, 255, 0.3);
            backdrop-filter: blur(10px);
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform:  translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 3.5em;
            margin:  20px 0;
            background: linear-gradient(90deg, var(--primary-color) 0%, var(--secondary-color) 50%, var(--tertiary-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite;
            font-weight: 700;
            letter-spacing: 2px;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 10px rgba(0, 212, 255, 0.5)); }
            50% { filter:  drop-shadow(0 0 20px rgba(255, 0, 110, 0.5)); }
        }

        h3 {
            font-size:  1.5em;
            color: var(--primary-color);
            margin:  15px 0;
            font-weight: 500;
        }

        .subtitle {
            color: var(--text-secondary);
            font-size: 1.1em;
            margin: 15px 0;
            font-style: italic;
        }

        /* Stats Section */
        .stats {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .stat-badge {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.2) 0%, rgba(255, 0, 110, 0.2) 100%);
            padding: 15px 25px;
            border-radius:  50px;
            border: 2px solid var(--primary-color);
            font-size: 0.9em;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .stat-badge:hover {
            transform: translateY(-5px);
            border-color: var(--secondary-color);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
        }

        /* Section Styling */
        section {
            margin: 60px 0;
            animation: fadeIn 1s ease-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h2 {
            font-size: 2.5em;
            margin:  40px 0 30px;
            color: var(--primary-color);
            text-align: center;
            position: relative;
            padding-bottom: 15px;
        }

        h2::after {
            content:  '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--primary-color), transparent);
        }

        /* Cards */
        .card {
            background: linear-gradient(135deg, rgba(26, 31, 58, 0.8) 0%, rgba(42, 51, 86, 0.6) 100%);
            padding: 30px;
            border-radius:  15px;
            border: 1px solid rgba(0, 212, 255, 0.2);
            margin: 20px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: var(--primary-color);
            box-shadow: 0 20px 60px rgba(0, 212, 255, 0.2);
        }

        .card h3 {
            margin-top: 0;
            color:  var(--tertiary-color);
        }

        .card p {
            color: var(--text-secondary);
            line-height:  1.8;
        }

        /* Grid Layouts */
        .grid {
            display: grid;
            gap: 30px;
            margin: 40px 0;
        }

        .grid-2 {
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        }

        .grid-3 {
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .social-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 12px 24px;
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            font-weight: 600;
            border: 2px solid transparent;
        }

        .social-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 212, 255, 0.4);
            border-color: var(--tertiary-color);
        }

        . social-btn:active {
            transform: translateY(-1px);
        }

        /* Tech Stack */
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
        }

        .tech-badge {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1) 0%, rgba(0, 212, 255, 0.1) 100%);
            padding: 10px 20px;
            border-radius: 30px;
            border: 2px solid var(--tertiary-color);
            color: var(--tertiary-color);
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .tech-badge:hover {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.2) 0%, rgba(0, 212, 255, 0.2) 100%);
            transform:  scale(1.05);
            box-shadow: 0 5px 20px rgba(0, 255, 136, 0.3);
        }

        /* Project Showcase */
        .project-card {
            background: linear-gradient(135deg, rgba(26, 31, 58, 0.9) 0%, rgba(42, 51, 86, 0.7) 100%);
            padding: 25px;
            border-radius:  15px;
            border-left: 4px solid var(--primary-color);
            margin: 20px 0;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateX(10px);
            border-left-color: var(--secondary-color);
            box-shadow: 0 10px 40px rgba(0, 212, 255, 0.15);
        }

        .project-card h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        .project-link {
            display: inline-block;
            margin-top: 15px;
            color: var(--tertiary-color);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border-bottom: 2px solid transparent;
        }

        .project-link:hover {
            border-bottom-color: var(--tertiary-color);
            transform: translateX(5px);
        }

        /* Achievement Section */
        .achievement-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .achievement {
            background: linear-gradient(135deg, rgba(255, 165, 0, 0.1) 0%, rgba(255, 0, 110, 0.1) 100%);
            padding: 20px;
            border-radius:  10px;
            text-align: center;
            border: 2px solid rgba(255, 165, 0, 0.3);
            transition: all 0.3s ease;
        }

        .achievement:hover {
            transform: scale(1.05) rotate(2deg);
            border-color: var(--accent);
            box-shadow: 0 10px 30px rgba(255, 165, 0, 0.2);
        }

        .achievement-icon {
            font-size:  2.5em;
            margin: 10px 0;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items:  center;
            margin: 40px 0;
        }

        .about-text h3 {
            color: var(--primary-color);
            margin:  20px 0 15px;
        }

        .about-text ul {
            list-style: none;
            margin: 20px 0;
        }

        .about-text li {
            padding: 10px 0;
            padding-left: 30px;
            position: relative;
            color: var(--text-secondary);
        }

        .about-text li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: var(--tertiary-color);
        }

        .about-image {
            width: 100%;
            height: 400px;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1) 0%, rgba(255, 0, 110, 0.1) 100%);
            border-radius: 15px;
            border: 2px dashed var(--primary-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5em;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 40px;
            margin-top: 60px;
            border-top: 2px solid rgba(0, 212, 255, 0.2);
            color: var(--text-secondary);
        }

        . footer-text {
            font-size: 1.1em;
            font-weight: 600;
            color: var(--primary-color);
            margin:  20px 0;
        }

        . typing-animation {
            display: inline-block;
            color: var(--tertiary-color);
            font-weight: 600;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2em;
            }

            h2 {
                font-size: 1.8em;
            }

            . header-content {
                padding: 30px 20px;
            }

            .stats {
                flex-direction: column;
                gap: 15px;
            }

            . social-links {
                gap: 10px;
            }

            .social-btn {
                padding: 10px 16px;
                font-size:  0.9em;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .about-image {
                height: 300px;
                font-size: 3em;
            }

            .grid {
                grid-template-columns:  1fr;
            }
        }

        /* Loading Animation */
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        . pulse {
            animation: pulse 2s infinite;
        }

        /* Underline Animation */
        .line-animation {
            position: relative;
            display: inline-block;
        }

        .line-animation:: after {
            content: '';
            position: absolute;
            bottom:  -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s ease;
        }

        .line-animation:hover::after {
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="animated-bg"></div>

    <div class="container">
        <!-- Header -->
        <header>
            <div class="header-content">
                <h1>👋 Hey, I'm Vishwa Abeyrathna! </h1>
                <h3>💻 Passionate IT Undergraduate | Building the Future with Code 🚀</h3>
                <p class="subtitle">I'm a dedicated developer who thrives on learning, creating, and solving problems through technology.</p>
                <div class="stats">
                    <div class="stat-badge">🔥 5+ Active Projects</div>
                    <div class="stat-badge">⭐ 100+ GitHub Stars</div>
                    <div class="stat-badge">👥 500+ Followers</div>
                    <div class="stat-badge">💡 Innovative Developer</div>
                </div>
            </div>
        </header>

        <!-- About Section -->
        <section id="about">
            <h2>🌌 About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>Who Am I?</h3>
                    <ul>
                        <li><strong>Currently Working On:</strong> <a href="https://github.com/vishwaabeyrathna/spicesense" class="line-animation">SpiceSense</a> - A Spice Store & Management System</li>
                        <li><strong>Learning:</strong> MERN Stack, MEAN Stack, Java, and more! </li>
                        <li><strong>Goal:</strong> To craft innovative solutions that make a global impact</li>
                        <li><strong>Ask Me About:</strong> Web Development, Mobile Apps, or Open Source</li>
                        <li><strong>Fun Fact:</strong> I can debug code faster than I can make coffee!  ☕</li>
                    </ul>
                    <h3>Why Choose Me?</h3>
                    <ul>
                        <li>✓ Full Stack Development Expertise</li>
                        <li>✓ Problem-Solving Mindset</li>
                        <li>✓ Continuous Learning & Growth</li>
                        <li>✓ Collaborative Team Player</li>
                    </ul>
                </div>
                <div class="about-image">💻</div>
            </div>
        </section>

        <!-- Connect Section -->
        <section id="connect">
            <h2>🌐 Connect With Me</h2>
            <p style="text-align: center; color: var(--text-secondary); margin-bottom: 25px;">
                Let's collaborate and create something amazing together!
            </p>
            <div class="social-links">
                <a href="https://fb.com/vishwa.abeyrathna" target="_blank" rel="noopener noreferrer" class="social-btn">
                    📘 Facebook
                </a>
                <a href="https://instagram.com/vishwa_bey" target="_blank" rel="noopener noreferrer" class="social-btn">
                    📷 Instagram
                </a>
                <a href="https://linkedin.com/in/vishwaabeyrathna" target="_blank" rel="noopener noreferrer" class="social-btn">
                    💼 LinkedIn
                </a>
                <a href="https://github.com/vishwaabeyrathna" target="_blank" rel="noopener noreferrer" class="social-btn">
                    🐙 GitHub
                </a>
                <a href="mailto:vishwaabeyrathna@email.com" class="social-btn">
                    ✉️ Email
                </a>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section id="skills">
            <h2>🛠️ Tech Stack</h2>

            <div class="card">
                <h3>📝 Languages</h3>
                <div class="tech-stack">
                    <span class="tech-badge">Java</span>
                    <span class="tech-badge">JavaScript</span>
                    <span class="tech-badge">Python</span>
                    <span class="tech-badge">PHP</span>
                    <span class="tech-badge">C</span>
                    <span class="tech-badge">C++</span>
                    <span class="tech-badge">Kotlin</span>
                    <span class="tech-badge">HTML/CSS</span>
                </div>
            </div>

            <div class="card">
                <h3>🎨 Frameworks & Libraries</h3>
                <div class="tech-stack">
                    <span class="tech-badge">React</span>
                    <span class="tech-badge">Node.js</span>
                    <span class="tech-badge">Express</span>
                    <span class="tech-badge">Angular</span>
                    <span class="tech-badge">Vue. js</span>
                    <span class="tech-badge">Next.js</span>
                </div>
            </div>

            <div class="card">
                <h3>🗄️ Databases</h3>
                <div class="tech-stack">
                    <span class="tech-badge">MongoDB</span>
                    <span class="tech-badge">MySQL</span>
                    <span class="tech-badge">PostgreSQL</span>
                    <span class="tech-badge">Firebase</span>
                </div>
            </div>

            <div class="card">
                <h3>🚀 Tools & Platforms</h3>
                <div class="tech-stack">
                    <span class="tech-badge">Git & GitHub</span>
                    <span class="tech-badge">Android Studio</span>
                    <span class="tech-badge">Figma</span>
                    <span class="tech-badge">Postman</span>
                    <span class="tech-badge">Docker</span>
                    <span class="tech-badge">AWS</span>
                </div>
            </div>
        </section>

        <!-- Featured Projects Section -->
        <section id="projects">
            <h2>🚀 Featured Projects</h2>
            <div class="grid grid-2">
                <div class="project-card">
                    <h3>🌶️ SpiceSense</h3>
                    <p>A full-stack spice store management system built with MERN Stack.  Features include inventory management, user authentication, and real-time order tracking.</p>
                    <p style="font-size: 0.9em; color: var(--text-secondary);">Tech: React, Node.js, Express, MongoDB</p>
                    <a href="https://github.com/vishwaabeyrathna/spicesense" class="project-link" target="_blank">View Project →</a>
                </div>

                <div class="project-card">
                    <h3>💼 Portfolio Website</h3>
                    <p>A modern, responsive portfolio website showcasing projects and skills. Built with React and styled with modern CSS animations.</p>
                    <p style="font-size: 0.9em; color: var(--text-secondary);">Tech: React, CSS3, JavaScript</p>
                    <a href="https://github.com/vishwaabeyrathna/portfolio" class="project-link" target="_blank">View Project →</a>
                </div>

                <div class="project-card">
                    <h3>📱 Mobile App</h3>
                    <p>A native Android application for task management with local database integration and intuitive UI. </p>
                    <p style="font-size: 0.9em; color: var(--text-secondary);">Tech: Kotlin, Android Studio, SQLite</p>
                    <a href="https://github.com/vishwaabeyrathna/mobile-app" class="project-link" target="_blank">View Project →</a>
                </div>

                <div class="project-card">
                    <h3>🎮 Game Development</h3>
                    <p>An interactive game built with HTML5 Canvas and JavaScript, featuring smooth animations and responsive controls.</p>
                    <p style="font-size: 0.9em; color: var(--text-secondary);">Tech: HTML5, Canvas, JavaScript</p>
                    <a href="https://github.com/vishwaabeyrathna/game" class="project-link" target="_blank">View Project →</a>
                </div>
            </div>
        </section>

        <!-- GitHub Stats Section -->
        <section id="stats">
            <h2>📊 GitHub Statistics</h2>
            <div class="grid grid-3">
                <div class="card">
                    <h3>⭐ Total Stars</h3>
                    <p style="font-size: 2em; font-weight: bold; color: var(--tertiary-color);">150+</p>
                    <p>Across all repositories</p>
                </div>
                <div class="card">
                    <h3>📚 Repositories</h3>
                    <p style="font-size:  2em; font-weight:  bold; color: var(--primary-color);">25+</p>
                    <p>Active open source projects</p>
                </div>
                <div class="card">
                    <h3>👥 Followers</h3>
                    <p style="font-size: 2em; font-weight: bold; color: var(--secondary-color);">500+</p>
                    <p>Growing community</p>
                </div>
                <div class="card">
                    <h3>🔄 Contributions</h3>
                    <p style="font-size: 2em; font-weight: bold; color: var(--accent);">1K+</p>
                    <p>This year</p>
                </div>
                <div class="card">
                    <h3>🏆 Achievements</h3>
                    <p style="font-size:  2em; font-weight:  bold; color: var(--tertiary-color);">12+</p>
                    <p>Badges & milestones</p>
                </div>
                <div class="card">
                    <h3>📈 Streak</h3>
                    <p style="font-size: 2em; font-weight: bold; color: var(--primary-color);">45 Days</p>
                    <p>Current contribution streak</p>
                </div>
            </div>
        </section>

        <!-- Skills Showcase -->
        <section id="expertise">
            <h2>💡 Areas of Expertise</h2>
            <div class="grid grid-2">
                <div class="card">
                    <h3>🎨 Frontend Development</h3>
                    <p>Expert in creating beautiful, responsive, and interactive user interfaces using modern frameworks like React, Vue, and Angular.</p>
                    <ul style="margin-top: 15px; color: var(--text-secondary);">
                        <li>✓ Responsive Web Design</li>
                        <li>✓ UI/UX Implementation</li>
                        <li>✓ CSS Animations & Transitions</li>
                        <li>✓ JavaScript ES6+</li>
                    </ul>
                </div>

                <div class="card">
                    <h3>⚙️ Backend Development</h3>
                    <p>Building scalable and secure backend systems with Node.js, Express, and various databases. </p>
                    <ul style="margin-top: 15px; color: var(--text-secondary);">
                        <li>✓ RESTful APIs</li>
                        <li>✓ Authentication & Authorization</li>
                        <li>✓ Database Design</li>
                        <li>✓ Server Optimization</li>
                    </ul>
                </div>

                <div class="card">
                    <h3>📱 Mobile Development</h3>
                    <p>Creating cross-platform mobile applications with native Android development using Kotlin. </p>
                    <ul style="margin-top: 15px; color: var(--text-secondary);">
                        <li>✓ Native Android Development</li>
                        <li>✓ Mobile UI/UX</li>
                        <li>✓ Local Database Integration</li>
                        <li>✓ API Integration</li>
                    </ul>
                </div>

                <div class="card">
                    <h3>🗄️ Database Design</h3>
                    <p>Designing efficient and scalable database architectures for various applications.</p>
                    <ul style="margin-top:  15px; color: var(--text-secondary);">
                        <li>✓ SQL & NoSQL</li>
                        <li>✓ Database Optimization</li>
                        <li>✓ Data Modeling</li>
                        <li>✓ Query Optimization</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Achievements Section -->
        <section id="achievements">
            <h2>🏆 Achievements & Recognitions</h2>
            <div class="achievement-grid">
                <div class="achievement">
                    <div class="achievement-icon">🥇</div>
                    <h4>Best Developer</h4>
                    <p>2023</p>
                </div>
                <div class="achievement">
                    <div class="achievement-icon">⭐</div>
                    <h4>Top Contributor</h4>
                    <p>GitHub</p>
                </div>
                <div class="achievement">
                    <div class="achievement-icon">🎓</div>
                    <h4>IT Undergraduate</h4>
                    <p>Honours</p>
                </div>
                <div class="achievement">
                    <div class="achievement-icon">🚀</div>
                    <h4>Quick Learner</h4>
                    <p>Always Growing</p>
                </div>
                <div class="achievement">
                    <div class="achievement-icon">💡</div>
                    <h4>Problem Solver</h4>
                    <p>100+ Issues</p>
                </div>
                <div class="achievement">
                    <div class="achievement-icon">🤝</div>
                    <h4>Team Player</h4>
                    <p>Collaborative</p>
                </div>
            </div>
        </section>

        <!-- Call to Action -->
        <section id="cta">
            <div class="card" style="text-align: center; padding: 60px 40px; background: linear-gradient(135deg, rgba(0, 212, 255, 0.15) 0%, rgba(255, 0, 110, 0.15) 100%); border: 2px solid var(--primary-color);">
                <h2 style="margin-top: 0;">Ready to Collaborate?</h2>
                <p style="font-size: 1.1em; margin:  20px 0; color:  var(--text-secondary);">
                    I'm always interested in new projects and opportunities.  Let's build something incredible together!
                </p>
                <div class="social-links" style="justify-content: center; margin-top: 30px;">
                    <a href="mailto:vishwaabeyrathna@email. com" class="social-btn">
                        ✉️ Send Me an Email
                    </a>
                    <a href="https://linkedin.com/in/vishwaabeyrathna" target="_blank" class="social-btn">
                        💼 Connect on LinkedIn
                    </a>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer>
            <div class="typing-animation">
                ✨ Thanks for visiting! Let's code the future together! ✨
            </div>
            <p style="margin-top: 15px; font-size: 0.9em;">
                © 2024 Vishwa Abeyrathna. All rights reserved.  | Last updated: January 2026
            </p>
            <p style="margin-top: 20px; color: var(--primary-color);">
                Made with ❤️ and ☕
            </p>
        </footer>
    </div>

    <script>
        // Smooth scroll for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor. addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold:  0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = `fadeIn 1s ease-out forwards`;
                }
            });
        }, observerOptions);

        document.querySelectorAll('section, .card, .project-card').forEach(el => {
            observer.observe(el);
        });

        // Counter animation for stats
        function animateCounter(element, target) {
            let current = 0;
            const increment = target / 50;
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    current = target;
                    clearInterval(timer);
                }
                element.textContent = Math.round(current) + '+';
            }, 30);
        }

        // Trigger counter on scroll
        const statsSection = document.getElementById('stats');
        let hasAnimated = false;

        window. addEventListener('scroll', () => {
            if (!hasAnimated && statsSection.getBoundingClientRect().top < window.innerHeight) {
                hasAnimated = true;
                const cards = statsSection.querySelectorAll('.card p');
                cards.forEach(card => {
                    const text = card.textContent;
                    const number = parseInt(text);
                    if (! isNaN(number)) {
                        animateCounter(card, number);
                    }
                });
            }
        });

        // Add ripple effect to buttons
        document.querySelectorAll('.social-btn, .stat-badge, .tech-badge').forEach(button => {
            button.addEventListener('click', function(e) {
                const ripple = document.createElement('span');
                const rect = this.getBoundingClientRect();
                const size = Math.max(rect.width, rect.height);
                const x = e.clientX - rect.left - size / 2;
                const y = e.clientY - rect.top - size / 2;

                ripple.style.width = ripple.style.height = size + 'px';
                ripple.style.left = x + 'px';
                ripple. style.top = y + 'px';
                ripple.style.position = 'absolute';
                ripple.style.borderRadius = '50%';
                ripple.style.background = 'rgba(255,255,255,0.5)';
                ripple.style.animation = 'ripple 0.6s ease-out';
                ripple.style.pointerEvents = 'none';

                this.style.position = 'relative';
                this.style.overflow = 'hidden';
                this.appendChild(ripple);

                setTimeout(() => ripple.remove(), 600);
            });
        });

        // Keyboard shortcuts
        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowDown') {
                window.scrollBy({ top: 100, behavior: 'smooth' });
            } else if (e. key === 'ArrowUp') {
                window.scrollBy({ top: -100, behavior: 'smooth' });
            }
        });

        // Add animation for ripple effect
        const style = document.createElement('style');
        style.textContent = `
            @keyframes ripple {
                to {
                    transform: scale(4);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);

        console.log('🎉 Welcome to Vishwa Abeyrathna\'s Portfolio!');
        console.log('💻 Feel free to explore and reach out for collaborations!');
    </script>
</body>
</html>
