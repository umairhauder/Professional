<!DOCTYPE html>
<html lang="ur">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Professional Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;900&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
</head>
<style>
  
:root {
    --color-primary: #00bcd4; /* Cyan/Teal Accent */
    --color-secondary: #ff4081; /* Pink/Magenta Accent */
    --color-bg-dark: #121212; /* Deep Dark Background */
    --color-bg-light: #1e1e1e; /* Card/Section Background */
    --color-text-main: #e0e0e0;
    --color-text-secondary: #9e9e9e;
    --shadow-light: 0 4px 10px rgba(0, 0, 0, 0.5);
    --shadow-heavy: 0 10px 30px rgba(0, 0, 0, 0.7);
    --border-radius: 10px;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: 'Poppins', sans-serif;
    background-color: var(--color-bg-dark);
    color: var(--color-text-main);
    line-height: 1.6;
    overflow-x: hidden;
}

/* Base Utility Classes */
a {
    text-decoration: none;
    color: var(--color-primary);
    transition: all 0.3s ease;
}

a:hover {
    color: var(--color-secondary);
}

.container {
    max-width: 1280px;
    margin: 0 auto;
    padding: 0 2rem;
}

.section {
    padding: 6rem 0;
}

.section-title {
    font-family: 'Montserrat', sans-serif;
    font-size: 3.5rem;
    font-weight: 900;
    text-align: center;
    margin-bottom: 1rem;
    position: relative;
    color: #fff;
}

.section-title::after {
    content: '';
    display: block;
    width: 60px;
    height: 4px;
    background: var(--color-secondary);
    margin: 0.5rem auto 0;
    border-radius: 2px;
}

.section-subtitle {
    text-align: center;
    font-size: 1.2rem;
    color: var(--color-text-secondary);
    margin-bottom: 4rem;
}

.dark-bg {
    background-color: var(--color-bg-light);
    border-top: 1px solid rgba(255, 255, 255, 0.05);
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.text-center {
    text-align: center;
}
.mt-5 {
    margin-top: 3rem;
}

/* ====================================================================
    0.1 BUTTONS STYLING
==================================================================== */
.btn {
    padding: 0.8rem 2rem;
    border-radius: 50px;
    font-weight: 600;
    transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
    display: inline-block;
    border: 2px solid transparent;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.btn-primary {
    background: var(--color-primary);
    color: var(--color-bg-dark);
    box-shadow: 0 0 15px rgba(0, 188, 212, 0.5);
}

.btn-primary:hover {
    background: var(--color-secondary);
    color: #fff;
    transform: translateY(-5px) scale(1.05);
    box-shadow: 0 8px 20px rgba(255, 64, 129, 0.7);
}

.btn-secondary {
    background: transparent;
    color: var(--color-primary);
    border-color: var(--color-primary);
    box-shadow: none;
}

.btn-secondary:hover {
    background: var(--color-primary);
    color: var(--color-bg-dark);
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 188, 212, 0.5);
}


/* ====================================================================
    1. HEADER / NAVBAR STYLING (GLASSMORPHISM & STICKY)
==================================================================== */
#navbar {
    position: sticky;
    top: 0;
    z-index: 1000;
    padding: 1.5rem 0;
    
    /* Glassmorphism High-Level Effect */
    background: rgba(18, 18, 18, 0.85); 
    backdrop-filter: blur(15px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

#navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-family: 'Montserrat', sans-serif;
    font-size: 2rem;
    font-weight: 900;
    color: #fff;
    letter-spacing: -1px;
}
.logo span {
    color: var(--color-primary);
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 2.5rem;
}

.nav-links .nav-item {
    font-weight: 500;
    color: var(--color-text-main);
    padding: 0.5rem 0;
    position: relative;
}

.nav-links .nav-item::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 0;
    height: 3px;
    background: var(--color-primary);
    transition: width 0.3s ease;
}

.nav-links .nav-item:hover::after,
.nav-links .nav-item.active::after {
    width: 100%;
}

.special-link {
    background: var(--color-secondary);
    color: #fff;
    padding: 0.5rem 1rem;
    border-radius: 50px;
    font-weight: 700;
    transition: all 0.3s ease;
}
.special-link:hover {
    background: var(--color-primary);
    box-shadow: 0 0 15px var(--color-primary);
}
.special-link::after { /* Disable line hover for special link */
    display: none; 
}

/* Mobile Menu Toggle (Hidden on Desktop) */
.menu-toggle {
    display: none;
}

/* ====================================================================
    2. HERO SECTION STYLING (Animated Text & Image Frame)
==================================================================== */
.hero {
    min-height: 90vh;
    display: flex;
    align-items: center;
    padding-bottom: 8rem;
    position: relative;
    /* Subtle background glow/animation */
    background: radial-gradient(circle at top left, rgba(0, 188, 212, 0.1), transparent 50%),
                radial-gradient(circle at bottom right, rgba(255, 64, 129, 0.1), transparent 50%);
}

.hero-content {
    display: flex;
    align-items: center;
    gap: 4rem;
}

.hero .text-side {
    flex: 1.5;
}

.hero .image-side {
    flex: 1;
    display: flex;
    justify-content: center;
}

.greeting {
    font-size: 1.4rem;
    color: var(--color-primary);
    margin-bottom: 0.5rem;
}

.hero h1 {
    font-family: 'Montserrat', sans-serif;
    font-size: 4.5rem;
    font-weight: 900;
    line-height: 1.1;
    color: #fff;
    margin-bottom: 0.5rem;
}

.hero h2 {
    font-size: 2rem;
    font-weight: 600;
    color: var(--color-text-secondary);
    margin-bottom: 1.5rem;
}

/* High-Level Typed Text Animation (CSS only for demonstration) */
.typed-text {
    color: var(--color-secondary);
    border-right: 3px solid var(--color-secondary);
    animation: blink-caret 0.75s step-end infinite;
    display: inline-block;
}
@keyframes blink-caret {
    from, to { border-color: transparent }
    50% { border-color: var(--color-secondary); }
}

.intro-text {
    font-size: 1.1rem;
    color: var(--color-text-secondary);
    max-width: 600px;
    margin-bottom: 2.5rem;
}

.hero-actions {
    display: flex;
    gap: 1.5rem;
}

/* Profile Image Frame (High-Level Design) */
.profile-frame {
    width: 350px;
    height: 450px;
    position: relative;
    border-radius: var(--border-radius);
    overflow: hidden;
    box-shadow: var(--shadow-heavy);
}

.profile-frame::before {
    content: '';
    position: absolute;
    top: -20px;
    right: -20px;
    bottom: -20px;
    left: -20px;
    background: linear-gradient(45deg, var(--color-primary), var(--color-secondary));
    z-index: -1;
    opacity: 0.3;
    filter: blur(20px);
    border-radius: var(--border-radius);
}

.profile-frame img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: var(--border-radius);
    transition: transform 0.5s ease;
}

.profile-frame:hover img {
    transform: scale(1.05);
}

/* Scroll Indicator Animation */
.scroll-indicator {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 0.9rem;
    color: var(--color-text-secondary);
    animation: bounce 2s infinite;
}
@keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
    40% { transform: translateY(-10px); }
    60% { transform: translateY(-5px); }
}


/* ====================================================================
    3. ABOUT SECTION STYLING (Skills Bars)
==================================================================== */
.about-grid {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 5rem;
    align-items: center;
}

.about-text h3 {
    font-size: 2rem;
    color: var(--color-primary);
    margin-bottom: 1.5rem;
}

.about-text p {
    color: var(--color-text-secondary);
    margin-bottom: 1.5rem;
    font-size: 1.1rem;
}

.skills-side h3 {
    font-size: 1.5rem;
    color: #fff;
    margin-bottom: 2rem;
}

.skill-bar {
    margin-bottom: 1.5rem;
}

.skill-name {
    display: block;
    font-weight: 500;
    margin-bottom: 0.5rem;
    color: var(--color-text-main);
}

.progress-bar {
    background-color: var(--color-bg-light);
    height: 12px;
    border-radius: 6px;
    overflow: hidden;
    position: relative;
}

.progress {
    height: 100%;
    background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
    border-radius: 6px;
    /* High-Level Animation for Skills */
    animation: progress-fill 1.5s ease forwards;
    width: 0; /* Starts at 0, filled by inline style */
}
/* Keyframe animation for progress bars */
@keyframes progress-fill {
    0% { width: 0; }
    100% { /* Width is determined by the inline style */ }
}


/* ====================================================================
    4. SERVICES SECTION STYLING (3D Hover Effect)
==================================================================== */
.services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.service-card {
    background: var(--color-bg-dark);
    padding: 3rem 2rem;
    border-radius: var(--border-radius);
    text-align: center;
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: var(--shadow-light);
    
    /* High-Level 3D Hover Transition */
    transition: transform 0.5s ease, box-shadow 0.5s ease;
    transform-style: preserve-3d;
}

.service-card:hover {
    transform: translateY(-15px) rotateX(2deg);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.9);
    border-color: var(--color-primary);
}

.icon-big {
    font-size: 3rem;
    color: var(--color-secondary);
    margin-bottom: 1.5rem;
    display: block;
    /* Icon pulse effect on hover */
    transition: color 0.3s ease;
}

.service-card:hover .icon-big {
    color: var(--color-primary);
    animation: icon-pulse 1s infinite alternate;
}

@keyframes icon-pulse {
    from { transform: scale(1); opacity: 1; }
    to { transform: scale(1.1); opacity: 0.8; }
}

.service-card h3 {
    font-size: 1.5rem;
    color: #fff;
    margin-bottom: 1rem;
}

.service-card p {
    color: var(--color-text-secondary);
}


/* ====================================================================
    5. PORTFOLIO (PROJECTS) STYLING (Advanced Overlay Hover)
==================================================================== */
.project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
}

.project-card {
    position: relative;
    border-radius: var(--border-radius);
    overflow: hidden;
    box-shadow: var(--shadow-light);
}

.card-image img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    transition: transform 0.6s ease;
    display: block;
}

.card-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    
    /* Overlay Gradient Background */
    background: linear-gradient(to top, rgba(18, 18, 18, 0.9) 0%, rgba(18, 18, 18, 0) 100%);
    
    /* Initial state: Hidden */
    opacity: 0;
    transform: translateY(100%);
    transition: opacity 0.4s ease, transform 0.6s ease;
    
    display: flex;
    align-items: flex-end;
}

.overlay-content {
    padding: 2rem;
    width: 100%;
}

.overlay-content h3 {
    font-size: 1.8rem;
    color: var(--color-primary);
    margin-bottom: 0.5rem;
    transform: translateY(10px);
    transition: transform 0.5s ease;
}

.overlay-content p {
    color: var(--color-text-main);
    margin-bottom: 1rem;
    transform: translateY(10px);
    transition: transform 0.5s ease 0.1s;
}

.btn-project {
    color: var(--color-secondary);
    font-weight: 600;
    border-bottom: 1px solid var(--color-secondary);
    transform: translateY(10px);
    transition: transform 0.5s ease 0.2s, color 0.3s ease;
}

.btn-project:hover {
    color: var(--color-primary);
    border-color: var(--color-primary);
}

/* === HIGH-LEVEL HOVER EFFECT (Revealing Overlay) === */
.project-card:hover .card-image img {
    transform: scale(1.1);
}

.project-card:hover .card-overlay {
    opacity: 1;
    transform: translateY(0); /* Overlay slides up */
}

.project-card:hover .overlay-content h3,
.project-card:hover .overlay-content p,
.project-card:hover .btn-project {
    transform: translateY(0); /* Content slides into view */
}


/* ====================================================================
    6. TESTIMONIALS STYLING (Carousel Look)
==================================================================== */
.testimonial-carousel {
    display: flex;
    justify-content: center;
    gap: 3rem;
    padding: 2rem 0;
}

.testimonial-card {
    background: var(--color-bg-dark);
    border-radius: var(--border-radius);
    padding: 3rem;
    max-width: 500px;
    position: relative;
    border-left: 5px solid var(--color-secondary);
    box-shadow: var(--shadow-light);
}

.quote {
    font-size: 1.2rem;
    font-style: italic;
    color: var(--color-text-main);
    margin-bottom: 1.5rem;
    position: relative;
}

.quote::before {
    content: "\201C"; /* Left double quotation mark */
    font-size: 5rem;
    color: var(--color-secondary);
    position: absolute;
    top: -30px;
    left: -20px;
    opacity: 0.2;
    z-index: 0;
}

.client-info {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-top: 2rem;
}

.client-avatar {
    width: 60px;
    height: 60px;
    background: linear-gradient(45deg, var(--color-primary), var(--color-secondary));
    border-radius: 50%;
    border: 3px solid #fff;
    /* Placeholder - in a real site, this would contain an image */
}

.client-info h4 {
    color: var(--color-primary);
    font-size: 1.1rem;
    margin-bottom: 0.2rem;
}

.client-info p {
    color: var(--color-text-secondary);
    font-size: 0.9rem;
}

/* ====================================================================
    7. CONTACT SECTION STYLING (Form Design)
==================================================================== */
.contact-grid {
    display: grid;
    grid-template-columns: 1fr 1.5fr;
    gap: 4rem;
}

.contact-info h3 {
    font-size: 2rem;
    color: var(--color-primary);
    margin-bottom: 2rem;
}

.contact-info p {
    font-size: 1.1rem;
    color: var(--color-text-secondary);
    margin-bottom: 1rem;
}

.contact-info p i {
    color: var(--color-secondary);
    margin-right: 1rem;
    width: 20px;
}

.social-icons {
    margin-top: 2rem;
    display: flex;
    gap: 1.5rem;
}

.social-icons a {
    font-size: 1.5rem;
    color: var(--color-text-secondary);
}

.social-icons a:hover {
    color: var(--color-primary);
    transform: scale(1.1);
}

.contact-form {
    background: var(--color-bg-light);
    padding: 3rem;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow-light);
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
}

.form-group {
    flex: 1 1 48%; /* Allows two inputs per row */
    display: flex;
    flex-direction: column;
}

.form-group.full-width {
    flex: 1 1 100%;
}

.contact-form label {
    font-weight: 500;
    margin-bottom: 0.5rem;
    color: var(--color-primary);
}

.contact-form input,
.contact-form textarea {
    background: var(--color-bg-dark);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--color-text-main);
    padding: 1rem;
    border-radius: 5px;
    outline: none;
    transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.contact-form input:focus,
.contact-form textarea:focus {
    border-color: var(--color-secondary);
    box-shadow: 0 0 10px rgba(255, 64, 129, 0.5);
}

.contact-form textarea {
    resize: vertical;
}


/* ====================================================================
    8. FOOTER STYLING
==================================================================== */
footer {
    background: var(--color-bg-light);
    padding: 4rem 0 1.5rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-content {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 3rem;
    margin-bottom: 3rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.footer-about p {
    color: var(--color-text-secondary);
    margin-top: 1rem;
}

.copyright {
    margin-top: 2rem;
    font-size: 0.9rem;
    color: var(--color-text-secondary);
}

.footer-links h3 {
    font-size: 1.2rem;
    color: #fff;
    margin-bottom: 1.5rem;
}

.footer-links ul {
    list-style: none;
}

.footer-links li {
    margin-bottom: 0.8rem;
}

.footer-links a {
    color: var(--color-text-secondary);
}

.footer-links a:hover {
    color: var(--color-primary);
    padding-left: 5px;
}

/* ====================================================================
    9. RESPONSIVENESS (Media Queries for High-Level Mobile Design)
==================================================================== */

/* Tablet View */
@media (max-width: 1024px) {
    .container {
        padding: 0 1.5rem;
    }
    
    .nav-links {
        gap: 1.5rem;
    }

    /* Hero Section */
    .hero h1 {
        font-size: 3.5rem;
    }
    .hero h2 {
        font-size: 1.7rem;
    }
    .profile-frame {
        width: 300px;
        height: 400px;
    }

    /* About Section */
    .about-grid {
        grid-template-columns: 1fr;
        gap: 3rem;
    }
    .about-text .btn-primary {
        margin-top: 1rem;
    }
    
    /* Contact Section */
    .contact-grid {
        grid-template-columns: 1fr;
    }
}

/* Mobile View */
@media (max-width: 768px) {
    .section {
        padding: 4rem 0;
    }
    .section-title {
        font-size: 2.5rem;
    }
    
    /* Navbar (Mobile Menu) */
    #navbar .container {
        padding-top: 0.5rem;
        padding-bottom: 0.5rem;
    }

    .menu-toggle {
        display: block;
        cursor: pointer;
    }
    .menu-toggle .bar {
        display: block;
        width: 25px;
        height: 3px;
        margin: 5px auto;
        -webkit-transition: all 0.3s ease-in-out;
        transition: all 0.3s ease-in-out;
        background-color: var(--color-primary);
    }
    
    .nav-links {
        display: none;
        flex-direction: column;
        width: 100%;
        position: absolute;
        top: 100%;
        left: 0;
        background: var(--color-bg-light);
        border-top: 1px solid rgba(255, 255, 255, 0.1);
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
        padding: 1rem 0;
    }

    .nav-links.active {
        display: flex;
    }

    .nav-links li {
        text-align: center;
        margin: 0.5rem 0;
    }

    .nav-links .special-link {
        display: inline-block;
        margin-top: 0.5rem;
    }

    /* Hero Section */
    .hero-content {
        flex-direction: column-reverse;
        text-align: center;
    }
    .hero h1 {
        font-size: 3rem;
    }
    .hero h2 {
        font-size: 1.5rem;
    }
    .hero .intro-text {
        max-width: 100%;
    }
    .hero-actions {
        justify-content: center;
    }
    .profile-frame {
        width: 280px;
        height: 350px;
        margin-bottom: 2rem;
    }

    /* Testimonials */
    .testimonial-carousel {
        flex-direction: column;
        align-items: center;
    }
    .testimonial-card {
        max-width: 100%;
    }

    /* Form */
    .contact-form .form-group {
        flex: 1 1 100%;
    }
    
    /* Footer */
    .footer-content {
        grid-template-columns: 1fr;
        text-align: center;
    }
    .footer-links h3 {
        margin-top: 1.5rem;
    }
}
  .tools-section {
            margin-top: 50px;
            margin-left: 200px;
            margin-right: 200px;
            
        }

        .section-title {
            font-size: 2.2rem;
            text-align: center;
          
            margin-bottom: 30px;
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
        }

        .tool-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 255, 0, 0.1);
            position: relative;
            overflow: hidden;
          
        }

        .tool-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(0, 255, 0, 0.1), transparent);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .tool-item:hover::before {
            opacity: 1;
        }

        .tool-item:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px rgba(0, 255, 0, 0.3);
            border-color: #00ff00;
        }

        .tool-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
        }

        .html-icon { color: #e34f26; }
        .css-icon { color: #1572b6; }
        .js-icon { color: #f7df1e; }
        .react-icon { color: #61dafb; }
        .node-icon { color: #339933; }
        .python-icon { color: #3776ab; }
        .php-icon { color: #777bb4; }
        .git-icon { color: #f05032; }
        .ps-icon { color: #31a8ff; }
        .figma-icon { color: #f24e1e; }
        .mysql-icon { color: #4479a1; }
        .mongodb-icon { color: #47a248; }

        .tool-name {
            font-size: 0.9rem;
            font-weight: 600;
            color: #e0e0e0;
        }
</style>
<body>
   <header id="navbar">
        <nav class="container">
            <a href="#hero" class="logo">Peeru <span>Portfolio</span></a>
            <ul class="nav-links">
                <li><a href="#hero" class="nav-item active">Home</a></li>
                <li><a href="#about" class="nav-item">About</a></li>
                <li><a href="#services" class="nav-item">Services</a></li>
                <li><a href="#portfolio" class="nav-item">Projects</a></li>
                <li><a href="#contact" class="nav-item special-link">Contact Me</a></li>
            </ul>
            <div class="menu-toggle" id="mobile-menu">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>
        </nav>
    </header>

    <section id="hero" class="hero">
        <div class="container hero-content">
            <div class="text-side">
                <p class="greeting">Assalam-o-Alaikum, I'm</p>
                <h1>Umair Haider</h1>
                <h2>A <span class="typed-text">Web Developer</span></h2>
                <p class="intro-text">
                    I build complex web applications using modern technologies, focusing on performance and elegant design.
                    My work is characterized by high-level coding standards and pixel-perfect aesthetics.
                </p>
                <div class="hero-actions">
                    <a href="#portfolio" class="btn btn-primary">View Work <i class="fa-solid fa-arrow-right"></i></a>
                    <a href="#contact" class="btn btn-secondary">Get In Touch</a>
                </div>
            </div>
            <div class="image-side">
                <div class="profile-frame">
                    <img src="pic.JPG" alt="Professional Profile Picture">
                </div>
            </div>
        </div>
        <div class="scroll-indicator">Scroll Down <i class="fa-solid fa-arrow-down"></i></div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <p class="section-subtitle">My journey and expertise in web development.</p>

            <div class="about-grid">
                <div class="about-text">
                    <h3>Years of Experience & Passion</h3>
                    <p>My core philosophy revolves around creating scalable, maintainable, and highly responsive digital experiences. I specialize in front-end development with a strong command over modern JavaScript frameworks.</p>
                    <p>I constantly explore new technologies to keep my skills sharp and deliver future-proof solutions.</p>
                    <a href="#" class="btn btn-primary">Read Full Bio</a>
                </div>
                
                <div class="skills-side">
                    <h3>Technical Skills</h3>
                    <div class="skill-bar">
                        <span class="skill-name">HTML & CSS (SASS/LESS)</span>
                        <div class="progress-bar"><div class="progress" style="width: 95%;"></div></div>
                    </div>
                    <div class="skill-bar">
                        <span class="skill-name">JavaScript (ES6+)</span>
                        <div class="progress-bar"><div class="progress" style="width: 90%;"></div></div>
                    </div>
                    <div class="skill-bar">
                        <span class="skill-name">React / Vue.js</span>
                        <div class="progress-bar"><div class="progress" style="width: 85%;"></div></div>
                    </div>
                    <div class="skill-bar">
                        <span class="skill-name">Node.js / Databases (SQL/NoSQL)</span>
                        <div class="progress-bar"><div class="progress" style="width: 75%;"></div></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section id="services" class="section dark-bg">
        <div class="container">
            <h2 class="section-title">My Services</h2>
            <p class="section-subtitle">Solutions I provide to elevate your business.</p>

            <div class="services-grid">
                <div class="service-card">
                    <i class="fa-solid fa-code icon-big"></i>
                    <h3>Custom Web Development</h3>
                    <p>Building tailor-made, performance-optimized websites from scratch, ensuring perfect alignment with your business goals.</p>
                </div>
                <div class="service-card">
                    <i class="fa-solid fa-mobile-screen-button icon-big"></i>
                    <h3>Responsive Design</h3>
                    <p>Creating designs that look impeccable on all devices—from desktop monitors to mobile phones.</p>
                </div>
                <div class="service-card">
                    <i class="fa-solid fa-object-group icon-big"></i>
                    <h3>UI/UX Prototyping</h3>
                    <p>Designing intuitive and engaging user interfaces to maximize user satisfaction and conversion rates.</p>
                </div>
            </div>
        </div>
    </section>
<!-- Tools & Technologies -->
        <div class="tools-section">
            <h2 class="section-title">Tools & Technologies</h2>
            <div class="tools-grid">
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-html5 tool-icon html-icon"></i>
                    <span class="tool-name">HTML5</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-css3-alt tool-icon css-icon"></i>
                    <span class="tool-name">CSS3</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-js tool-icon js-icon"></i>
                    <span class="tool-name">JavaScript</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-react tool-icon react-icon"></i>
                    <span class="tool-name">React</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-node-js tool-icon node-icon"></i>
                    <span class="tool-name">Node.js</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-python tool-icon python-icon"></i>
                    <span class="tool-name">Python</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-php tool-icon php-icon"></i>
                    <span class="tool-name">PHP</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-git-alt tool-icon git-icon"></i>
                    <span class="tool-name">Git</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fab fa-figma tool-icon figma-icon"></i>
                    <span class="tool-name">Figma</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fas fa-database tool-icon mysql-icon"></i>
                    <span class="tool-name">MySQL</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fas fa-server tool-icon mongodb-icon"></i>
                    <span class="tool-name">MongoDB</span>
                </div>
                <div class="tool-item animate-on-scroll">
                    <i class="fas fa-photo-video tool-icon ps-icon"></i>
                    <span class="tool-name">Photoshop</span>
                </div>
            </div>
        </div>

    <section id="portfolio" class="section">
        <div class="container">
            <h2 class="section-title">Latest Projects</h2>
            <p class="section-subtitle">A showcase of my recent high-level work.</p>

            <div class="project-grid">
                <div class="project-card">
                    <div class="card-image">
                        <img src="https://picsum.photos/600/400?random=1" alt="Project Alpha">
                    </div>
                    <div class="card-overlay">
                        <div class="overlay-content">
                            <h3>Personal Portfolio </h3>
                            <p>I built every type of portfolio.</p>
                            <a href="#" class="btn-project">View Case Study <i class="fa-solid fa-link"></i></a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="card-image">
                        <img src="https://picsum.photos/600/400?random=2" alt="Project Beta">
                    </div>
                    <div class="card-overlay">
                        <div class="overlay-content">
                            <h3>E e-commerce website</h3>
                            <p>An e-commerce solution using React and GraphQL.</p>
                            <a href="#" class="btn-project">View Case Study <i class="fa-solid fa-link"></i></a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="card-image">
                        <img src="https://picsum.photos/600/400?random=3" alt="Project Gamma">
                    </div>
                    <div class="card-overlay">
                        <div class="overlay-content">
                            <h3>c++ Projects</h3>
                            <p>I make games through C++ logics.</p>
                            <a href="#" class="btn-project">View Case Study <i class="fa-solid fa-link"></i></a>
                        </div>
                    </div>
                </div>
            </div>
            <div class="text-center mt-5">
                <a href="#" class="btn btn-secondary">Load More Projects</a>
            </div>
        </div>
    </section>

    <section id="testimonials" class="section dark-bg">
        <div class="container">
            <h2 class="section-title">Client Feedback</h2>
            <p class="section-subtitle">What my high-profile clients say about my work.</p>
            
            <div class="testimonial-carousel">
                <div class="testimonial-card">
                    <p class="quote">"Khan's dedication to detail and commitment to high coding standards is unmatched. They delivered a high-performance solution ahead of schedule."</p>
                    <div class="client-info">
                        <div class="client-avatar"></div>
                        <h4>Mansoor</h4>
                        <p>CEO, TechCorp Solutions</p>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="quote">"The responsive design implemented was flawless. Truly a high-level developer who understands modern UI/UX principles."</p>
                    <div class="client-info">
                        <div class="client-avatar"></div>
                        <h4>Sameer Aslam</h4>
                        <p>Head of Product, Digital Bridge</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <h2 class="section-title">Let's Connect</h2>
            <p class="section-subtitle">Start your next high-level project with me.</p>

            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Contact Details</h3>
                    <p><i class="fa-solid fa-envelope"></i> umairhaidercit@gmail.com</p>
                    <p><i class="fa-solid fa-phone"></i> +92 3491882707</p>
                    <p><i class="fa-solid fa-location-dot"></i> Bhakkar, Pakistan</p>

                    <div class="social-icons">
                        <a href="#" target="_blank"><i class="fa-brands fa-github"></i></a>
                        <a href="#" target="_blank"><i class="fa-brands fa-linkedin"></i></a>
                        <a href="#" target="_blank"><i class="fa-brands fa-twitter"></i></a>
                    </div>
                </div>
                
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Your Name</label>
                        <input type="text" id="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Your Email</label>
                        <input type="email" id="email" required>
                    </div>
                    <div class="form-group full-width">
                        <label for="message">Your Message</label>
                        <textarea id="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary full-width">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <div class="container footer-content">
            <div class="footer-about">
                <a href="#hero" class="logo">Peeru <span>Portfolio</span></a>
                <p>High-level web solutions, designed for the future.</p>
                <p class="copyright">&copy; 2025 All Rights Reserved.</p>
            </div>

            <div class="footer-links">
                <h3>Navigation</h3>
                <ul>
                    <li><a href="#about">About</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#portfolio">Projects</a></li>
                </ul>
            </div>

            <div class="footer-links">
                <h3>Legal</h3>
                <ul>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Terms of Use</a></li>
                    <li><a href="#">Sitemap</a></li>
                </ul>
            </div>
        </div>
    </footer>
    
    <script>
        document.getElementById('mobile-menu').addEventListener('click', function() {
            document.querySelector('.nav-links').classList.toggle('active');
            this.classList.toggle('active');
        });
        
        // Simple Scroll detection for Navbar active state
        window.addEventListener('scroll', () => {
            let current = '';
            document.querySelectorAll('section').forEach(section => {
                const sectionTop = section.offsetTop;
                if (pageYOffset >= sectionTop - 100) {
                    current = section.getAttribute('id');
                }
            });
            document.querySelectorAll('.nav-item').forEach(a => {
                a.classList.remove('active');
                if (a.getAttribute('href').includes(current)) {
                    a.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
