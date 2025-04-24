<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Matheus Lisboa | Full-Stack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        /* Custom CSS */
        :root {
            --primary: #3b82f6;
            --primary-dark: #2563eb;
            --dark: #1f2937;
            --light: #f9fafb;
            --gray: #6b7280;
            --white: #ffffff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        h1, h2, h3, h4, h5, h6 {
            font-weight: 700;
            line-height: 1.2;
        }
        
        p {
            margin-bottom: 1rem;
        }
        
        section {
            padding: 5rem 0;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }
        
        /* Header/Navbar */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            transition: all 0.3s ease;
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }
        
        .logo {
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .nav-links {
            display: flex;
            gap: 2rem;
        }
        
        .nav-link {
            font-weight: 500;
            transition: color 0.3s ease;
        }
        
        .nav-link:hover {
            color: var(--primary);
        }
        
        .menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark);
        }
        
        .mobile-menu {
            display: none;
            position: absolute;
            top: 70px;
            left: 0;
            width: 100%;
            background-color: var(--white);
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            padding: 1rem 0;
            z-index: 999;
        }
        
        .mobile-menu.active {
            display: block;
        }
        
        .mobile-nav-link {
            display: block;
            padding: 0.75rem 1.5rem;
            font-weight: 500;
            transition: background-color 0.3s ease;
        }
        
        .mobile-nav-link:hover {
            background-color: #f3f4f6;
            color: var(--primary);
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%);
            color: var(--white);
            position: relative;
        }
        
        .hero-content {
            text-align: center;
        }
        
        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 1rem;
        }
        
        .hero-subtitle {
            font-size: 1.75rem;
            font-weight: 300;
            margin-bottom: 2rem;
        }
        
        .hero-text {
            font-size: 1.25rem;
            max-width: 600px;
            margin: 0 auto 2.5rem;
        }
        
        .btn {
            display: inline-block;
            padding: 0.875rem 2rem;
            border-radius: 9999px;
            font-weight: 600;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: var(--white);
        }
        
        .btn-primary:hover {
            background-color: var(--primary-dark);
        }
        
        /* About Section */
        .section-title {
            font-size: 2rem;
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -0.75rem;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--primary);
        }
        
        .about-container {
            display: flex;
            align-items: center;
            gap: 3rem;
        }
        
        .about-img-container {
            flex: 1;
            display: flex;
            justify-content: center;
        }
        
        .about-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            border: 5px solid var(--primary);
            object-fit: cover;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        .about-content {
            flex: 2;
        }
        
        .about-text {
            font-size: 1.1rem;
            color: var(--gray);
        }
        
        /* Skills Section */
        .skills-section {
            background-color: #f3f4f6;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 2rem;
        }
        
        .skill-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: transform 0.3s ease;
        }
        
        .skill-item:hover {
            transform: translateY(-5px);
        }
        
        .skill-icon {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .skill-icon i {
            font-size: 2rem;
        }
        
        .skill-name {
            font-weight: 500;
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2.5rem;
        }
        
        .project-card {
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .project-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-title {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
        }
        
        .project-description {
            color: var(--gray);
            margin-bottom: 1rem;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }
        
        .project-tag {
            padding: 0.25rem 0.75rem;
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: 500;
        }
        
        .tag-react {
            background-color: #e0f2fe;
            color: #0369a1;
        }
        
        .tag-node {
            background-color: #dcfce7;
            color: #15803d;
        }
        
        .tag-mongo {
            background-color: #f3e8ff;
            color: #7e22ce;
        }
        
        .tag-socket {
            background-color: #fee2e2;
            color: #b91c1c;
        }
        
        .tag-firebase {
            background-color: #fef3c7;
            color: #92400e;
        }
        
        .tag-redux {
            background-color: #e0e7ff;
            color: #4338ca;
        }
        
        .tag-vue {
            background-color: #d1fae5;
            color: #065f46;
        }
        
        .tag-postgres {
            background-color: #fce7f3;
            color: #be185d;
        }
        
        .tag-next {
            background-color: #e5e7eb;
            color: #1f2937;
        }
        
        .tag-stripe {
            background-color: #f3f4f6;
            color: #4b5563;
        }
        
        .tag-tailwind {
            background-color: #dbeafe;
            color: #1d4ed8;
        }
        
        .tag-d3 {
            background-color: #ffedd5;
            color: #c2410c;
        }
        
        .tag-graphql {
            background-color: #fef3c7;
            color: #92400e;
        }
        
        .tag-django {
            background-color: #f3e8ff;
            color: #7e22ce;
        }
        
        .tag-redis {
            background-color: #fee2e2;
            color: #b91c1c;
        }
        
        .project-links {
            display: flex;
            gap: 1rem;
        }
        
        .project-link {
            flex: 1;
            padding: 0.75rem;
            text-align: center;
            border-radius: 6px;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .link-demo {
            background-color: var(--primary);
            color: var(--white);
        }
        
        .link-demo:hover {
            background-color: var(--primary-dark);
        }
        
        .link-github {
            background-color: var(--dark);
            color: var(--white);
        }
        
        .link-github:hover {
            background-color: #111827;
        }
        
        /* Contact Section */
        .contact-section {
            background-color: #f3f4f6;
        }
        
        .contact-container {
            display: flex;
            gap: 4rem;
        }
        
        .form-container {
            flex: 2;
            background-color: var(--white);
            border-radius: 8px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        
        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }
        
        .form-label {
            font-size: 0.875rem;
            font-weight: 500;
            color: var(--gray);
        }
        
        .form-input,
        .form-textarea {
            padding: 0.75rem 1rem;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            font-size: 1rem;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
        }
        
        .form-input:focus,
        .form-textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.25);
        }
        
        .form-textarea {
            resize: vertical;
            min-height: 150px;
        }
        
        .form-btn {
            width: 100%;
            background-color: var(--primary);
            color: var(--white);
            padding: 0.875rem;
            border: none;
            border-radius: 6px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        
        .form-btn:hover {
            background-color: var(--primary-dark);
        }
        
        .contact-info-container {
            flex: 1;
        }
        
        .contact-info {
            background-color: var(--white);
            border-radius: 8px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            height: 100%;
        }
        
        .contact-info-title {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
        }
        
        .info-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        
        .info-item {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }
        
        .info-icon {
            width: 1.5rem;
            height: 1.5rem;
            color: var(--primary);
        }
        
        .social-title {
            font-size: 1.25rem;
            font-weight: 600;
            margin: 2rem 0 1rem;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
        }
        
        .social-link {
            font-size: 1.5rem;
            color: var(--gray);
            transition: color 0.3s ease;
        }
        
        .social-link:hover {
            color: var(--primary);
        }
        
        /* Footer */
        .footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 2rem 0;
            text-align: center;
        }
        
        .back-to-top {
            display: inline-block;
            margin-top: 1rem;
            color: #9ca3af;
            transition: color 0.3s ease;
        }
        
        .back-to-top:hover {
            color: var(--white);
        }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .about-container {
                flex-direction: column;
                text-align: center;
            }
            
            .projects-grid {
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            }
            
            .contact-container {
                flex-direction: column;
            }
            
            .contact-info-container {
                order: -1;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .menu-btn {
                display: block;
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.5rem;
            }
            
            .section-title {
                font-size: 1.75rem;
            }
            
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            }
        }
        
        @media (max-width: 480px) {
            .hero-title {
                font-size: 2rem;
            }
            
            .hero-subtitle {
                font-size: 1.25rem;
            }
            
            .hero-text {
                font-size: 1rem;
            }
            
            .about-img {
                width: 200px;
                height: 200px;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <header class="navbar">
        <div class="container nav-container">
            <a href="#hero" class="logo">ML</a>
            <nav class="nav-links">
                <a href="#about" class="nav-link">About</a>
                <a href="#skills" class="nav-link">Skills</a>
                <a href="#projects" class="nav-link">Projects</a>
                <a href="#contact" class="nav-link">Contact</a>
            </nav>
            <button class="menu-btn" id="menu-btn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
        <div class="mobile-menu" id="mobile-menu">
            <a href="#about" class="mobile-nav-link">About</a>
            <a href="#skills" class="mobile-nav-link">Skills</a>
            <a href="#projects" class="mobile-nav-link">Projects</a>
            <a href="#contact" class="mobile-nav-link">Contact</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="hero">
        <div class="container hero-content">
            <h1 class="hero-title">Matheus Lisboa</h1>
            <h2 class="hero-subtitle">Full-Stack Developer</h2>
            <p class="hero-text">Crafting elegant solutions to complex problems through clean, efficient code.</p>
            <a href="#projects" class="btn btn-primary">View My Work</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-container">
                <div class="about-img-container">
                    <img src="/api/placeholder/300/300" alt="Matheus Lisboa" class="about-img" />
                </div>
                <div class="about-content">
                    <p class="about-text">Hi there! I'm Matheus, a passionate full-stack developer with over 5 years of experience building modern web applications. After graduating with a degree in Computer Science, I've worked with startups and established companies to deliver robust, scalable solutions that solve real-world problems.</p>
                    <p class="about-text">I specialize in JavaScript ecosystems, particularly React and Node.js, but I'm always exploring new technologies and approaches. My philosophy centers around writing clean, maintainable code and creating intuitive user experiences.</p>
                    <p class="about-text">When I'm not coding, you'll find me hiking, reading sci-fi novels, or experimenting with new cooking recipes. I believe that diverse interests fuel creativity and problem-solving in tech.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills-section">
        <div class="container">
            <h2 class="section-title">Technical Skills</h2>
            <div class="skills-grid">
                <!-- Skill 1 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-html5" style="color: #e34f26;"></i>
                    </div>
                    <span class="skill-name">HTML5</span>
                </div>
                <!-- Skill 2 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-css3-alt" style="color: #1572b6;"></i>
                    </div>
                    <span class="skill-name">CSS3</span>
                </div>
                <!-- Skill 3 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-js" style="color: #f7df1e;"></i>
                    </div>
                    <span class="skill-name">JavaScript</span>
                </div>
                <!-- Skill 4 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-react" style="color: #61dafb;"></i>
                    </div>
                    <span class="skill-name">React</span>
                </div>
                <!-- Skill 5 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-node-js" style="color: #339933;"></i>
                    </div>
                    <span class="skill-name">Node.js</span>
                </div>
                <!-- Skill 6 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-python" style="color: #3776ab;"></i>
                    </div>
                    <span class="skill-name">Python</span>
                </div>
                <!-- Skill 7 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-git-alt" style="color: #f05032;"></i>
                    </div>
                    <span class="skill-name">Git</span>
                </div>
                <!-- Skill 8 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-docker" style="color: #2496ed;"></i>
                    </div>
                    <span class="skill-name">Docker</span>
                </div>
                <!-- Skill 9 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fas fa-database" style="color: #47a248;"></i>
                    </div>
                    <span class="skill-name">MongoDB</span>
                </div>
                <!-- Skill 10 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fas fa-server" style="color: #000000;"></i>
                    </div>
                    <span class="skill-name">Express</span>
                </div>
                <!-- Skill 11 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-aws" style="color: #ff9900;"></i>
                    </div>
                    <span class="skill-name">AWS</span>
                </div>
                <!-- Skill 12 -->
                <div class="skill-item">
                    <div class="skill-icon">
                        <i class="fab fa-figma" style="color: #f24e1e;"></i>
                    </div>
                    <span class="skill-name">Figma</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section">
        <div class="container">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <!-- Project 1 -->
                <div class="project-card">
                    <img src="/api/placeholder/600/400" alt="TaskFlow Project" class="project-img" />
                    <div class="project-content">
                        <h3 class="project-title">TaskFlow</h3>
                        <p class="project-description">A collaborative task management application with real-time updates and intuitive UI.</p>
                        <div class="project-tags">
                            <span class="project-tag tag-react">React</span>
                            <span class="project-tag tag-node">Node.js</span>
                            <span class="project-tag tag-mongo">MongoDB</span>
                            <span class="project-tag tag-socket">Socket.io</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link link-demo">Live Demo</a>
                            <a href="#" class="project-link link-github">GitHub</a>
                        </div>
                    </div>
                </div>
                <!-- Project 2 -->
                <div class="project-card">
                    <img src="/api/placeholder/600/400" alt="HealthHub Project" class="project-img" />
                    <div class="project-content">
                        <h3 class="project-title">HealthHub</h3>
                        <p class="project-description">A fitness tracking platform with personalized workout plans and nutrition guidance.</p>
                        <div class="project-tags">
                            <span class="project-tag tag-react">React Native</span>
                            <span class="project-tag tag-firebase">Firebase</span>
                            <span class="project-tag tag-redux">Redux</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link link-demo">Live Demo</a>
                            <a href="#" class="project-link link-github">GitHub</a>
                        </div>
                    </div>
                </div>
                <!-- Project 3 -->
                <div class="project-card">
                    <img src="/api/placeholder/600/400" alt="CodeCollab Project" class="project-img" />
                    <div class="project-content">
                        <h3 class="project-title">CodeCollab</h3>
                        <p class="project-description">Real-time collaborative code editor with syntax highlighting and version control.</p>
                        <div class="project-tags">
                            <span class="project-tag tag-vue">Vue.js</span>
                            <span class="project-tag tag-node">Express</span>
                            <span class="project-tag tag-postgres">PostgreSQL</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link link-demo">Live Demo</a>
                            <a href="#" class="project-link link-github">GitHub</a>
                        </div>
                    </div>
                </div>
                <!-- Project 4 -->
                <div class="project-card">
                    <img src="/api/placeholder/600/400" alt="EcoMarket Project" class="project-img" />
                    <div class="project-content">
                        <h3 class="project-title">EcoMarket</h3>
                        <p class="project-description">An e-commerce platform for sustainable products with carbon footprint tracking.</p>
                        <div class="project-tags">
                            <span class="project-tag tag-next">Next.js</span>
                            <span class="project-tag tag-stripe">Stripe</span>
                            <span class="project-tag tag-tailwind">Tailwind</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link link-demo">Live Demo</a>
                            <a href="#" class="project-link link-github">GitHub</a>
                        </div>
                    </div>
                </div>
                <!-- Project 5 -->
                <div class="project-card">
                    <img src="/api/placeholder/600/400" alt="DataVizPro Project" class="project-img" />
                    <div class="project-content">
                        <h3 class="project-title">DataVizPro</h3>
                        <p class="project-description">Interactive data visualization dashboard with customizable charts and real-time analytics.</p>
                        <div class="project-tags">
                            <span class="project-tag tag-d3">D3.js</span>
                            <span class="project-tag tag-react">React</span>
                            <span class="project-tag tag-graphql">GraphQL</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link link-demo">Live Demo</a>
                            <a href="#" class="project-link link-github">GitHub</a>
                        </div>
                    </div>
                </div>
                <!-- Project 6 -->
                <div class="project-card">
                    <img src="/api/placeholder/600/400" alt="DevConnect Project" class="project-img" />
                    <div class="project-content">
                        <h3 class="project-title">DevConnect</h3>
                        <p class="project-description">Professional networking platform for developers with project collaboration features.</p>
                        <div class="project-tags">
                            <span class="project-tag tag-django">Django</span>
                            <span class="project-tag tag-react">React</span>
                            <span class="project-tag tag-redis">Redis</span>
                        </div>
                        <div class="project-links">