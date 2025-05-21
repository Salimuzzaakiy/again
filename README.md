<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website Modern</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #3a86ff;
            --secondary-color: #8338ec;
            --accent-color: #ff006e;
            --text-color: #2b2d42;
            --light-text: #8d99ae;
            --background: #f8f9fa;
            --white: #ffffff;
            --section-padding: 80px 0;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--background);
            overflow-x: hidden;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header & Navigation */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
        }
        
        header.scrolled {
            padding: 5px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-color);
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--accent-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            position: relative;
            font-weight: 500;
            transition: var(--transition);
            padding: 5px 0;
        }
        
        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary-color);
            transition: var(--transition);
        }
        
        nav ul li a:hover {
            color: var(--primary-color);
        }
        
        nav ul li a:hover::after,
        nav ul li a.active::after {
            width: 100%;
        }
        
        .menu-toggle {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
            background: linear-gradient(135deg, rgba(58, 134, 255, 0.1) 0%, rgba(131, 56, 236, 0.1) 100%);
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: url('/api/placeholder/1200/800') center/cover no-repeat;
            opacity: 0.05;
            z-index: -1;
        }
        
        .hero-content {
            max-width: 600px;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            line-height: 1.2;
            color: var(--text-color);
            animation: fadeInUp 1s ease;
        }
        
        .hero h1 span {
            color: var(--primary-color);
        }
        
        .hero p {
            font-size: 1.1rem;
            margin-bottom: 30px;
            color: var(--light-text);
            animation: fadeInUp 1s ease 0.2s;
            animation-fill-mode: both;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 28px;
            background-color: var(--primary-color);
            color: var(--white);
            border-radius: 30px;
            font-weight: 500;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 1rem;
            text-align: center;
            box-shadow: 0 4px 15px rgba(58, 134, 255, 0.3);
        }
        
        .btn:hover {
            background-color: var(--secondary-color);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(131, 56, 236, 0.4);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
        }
        
        .btn-outline:hover {
            background-color: var(--primary-color);
            color: var(--white);
        }
        
        .hero-btns {
            display: flex;
            gap: 15px;
            animation: fadeInUp 1s ease 0.4s;
            animation-fill-mode: both;
        }
        
        .hero-image {
            position: absolute;
            right: -100px;
            bottom: -100px;
            width: 650px;
            height: 650px;
            background: url('/api/placeholder/650/650') center/contain no-repeat;
            animation: floatImage 6s ease-in-out infinite;
        }
        
        /* About Section */
        .about {
            padding: var(--section-padding);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 70px;
            height: 3px;
            background-color: var(--primary-color);
        }
        
        .section-title p {
            color: var(--light-text);
            max-width: 600px;
            margin: 0 auto;
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-image {
            flex: 1;
            position: relative;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: var(--transition);
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--text-color);
        }
        
        .about-text p {
            margin-bottom: 25px;
            color: var(--light-text);
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 30px;
        }
        
        .feature-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }
        
        .feature-icon {
            width: 40px;
            height: 40px;
            background-color: rgba(58, 134, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-color);
        }
        
        .feature-text h4 {
            margin-bottom: 5px;
            font-size: 1.1rem;
        }
        
        .feature-text p {
            font-size: 0.9rem;
            margin-bottom: 0;
        }
        
        /* Services Section */
        .services {
            padding: var(--section-padding);
            background-color: var(--white);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: var(--white);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 0;
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            transition: var(--transition);
            z-index: -1;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .service-card:hover::before {
            height: 100%;
        }
        
        .service-card:hover .service-icon,
        .service-card:hover h3,
        .service-card:hover p {
            color: var(--white);
        }
        
        .service-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            transition: var(--transition);
        }
        
        .service-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            transition: var(--transition);
        }
        
        .service-card p {
            transition: var(--transition);
        }
        
        /* Contact Section */
        .contact {
            padding: var(--section-padding);
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }
        
        .contact-icon {
            width: 50px;
            height: 50px;
            background-color: rgba(58, 134, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-color);
            font-size: 1.2rem;
        }
        
        .contact-details h4 {
            margin-bottom: 5px;
            font-size: 1.1rem;
        }
        
        .contact-details p {
            color: var(--light-text);
        }
        
        .contact-form {
            background-color: var(--white);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #e5e7eb;
            border-radius: 5px;
            font-size: 1rem;
            transition: var(--transition);
        }
        
        .form-control:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 0 3px rgba(58, 134, 255, 0.1);
        }
        
        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background-color: #2b2d42;
            color: var(--white);
            padding: 60px 0 20px;
        }
        
        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-col h4 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-col h4::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary-color);
        }
        
        .footer-col ul {
            list-style: none;
        }
        
        .footer-col ul li {
            margin-bottom: 10px;
        }
        
        .footer-col ul li a {
            color: #b7b9c7;
            transition: var(--transition);
        }
        
        .footer-col ul li a:hover {
            color: var(--white);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .social-link {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            transition: var(--transition);
        }
        
        .social-link:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
        }
        
        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 20px;
            text-align: center;
            color: #b7b9c7;
        }
        
        /* Back to top button */
        .back-to-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 40px;
            height: 40px;
            background-color: var(--primary-color);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 99;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }
        
        .back-to-top.active {
            opacity: 1;
            visibility: visible;
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes floatImage {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        /* Responsive */
        @media screen and (max-width: 992px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .hero-image {
                width: 500px;
                height: 500px;
                right: -150px;
                bottom: -150px;
            }
        }
        
        @media screen and (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
            
            nav ul {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                flex-direction: column;
                background-color: var(--white);
                box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
                transition: var(--transition);
                padding: 20px 0;
                z-index: 999;
            }
            
            nav ul.active {
                left: 0;
            }
            
            nav ul li {
                margin: 0;
                width: 100%;
                text-align: center;
            }
            
            nav ul li a {
                display: block;
                padding: 10px 0;
            }
            
            .hero-content {
                text-align: center;
                max-width: 100%;
            }
            
            .hero-btns {
                justify-content: center;
            }
            
            .hero-image {
                opacity: 0.2;
                width: 400px;
                height: 400px;
                right: -100px;
                bottom: -100px;
            }
            
            .feature-item {
                margin-bottom: 10px;
            }
            
            .features {
                grid-template-columns: 1fr;
            }
        }
        
        @media screen and (max-width: 576px) {
            .section-title h2 {
                font-size: 2rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .about-text h3 {
                font-size: 1.5rem;
            }
            
            .hero-btns {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-cube"></i>
                <span>Modern</span>
            </a>
            <div class="menu-toggle">
                <i class="fas fa-bars"></i>
            </div>
            <nav>
                <ul id="nav-menu">
                    <li><a href="#hero" class="active">Beranda</a></li>
                    <li><a href="#about">Tentang</a></li>
                    <li><a href="#services">Layanan</a></li>
                    <li><a href="#contact">Kontak</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Design Website <span>Modern</span> & Profesional</h1>
                <p>Website modern dengan tampilan yang menarik dan responsif. Dibuat untuk memberikan pengalaman pengguna yang optimal pada semua perangkat.</p>
                <div class="hero-btns">
                    <a href="#services" class="btn">Layanan Kami</a>
                    <a href="#contact" class="btn btn-outline">Hubungi Kami</a>
                </div>
            </div>
            <div class="hero-image"></div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-title">
                <h2>Tentang Kami</h2>
                <p>Kami menyediakan solusi digital terbaik untuk membantu bisnis Anda tumbuh dan berkembang di era digital.</p>
            </div>
            <div class="about-content">
                <div class="about-image">
                    <img src="/api/placeholder/600/400" alt="Tentang Kami">
                </div>
                <div class="about-text">
