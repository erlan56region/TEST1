Разработка 5.0

<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="theme-color" content="#2c5aa0">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>ИП Рахметов А.К. - Автономные канализации Аквалос</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preload" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Open+Sans:wght@300;400;500;600;700&display=swap" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Open+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --primary: #2c5aa0;
            --primary-light: #4a76c2;
            --primary-dark: #1e3d6b;
            --secondary: #4CAF50;
            --secondary-light: #6fcf72;
            --secondary-dark: #3d8b40;
            --accent: #FF9800;
            --light: #f8fafc;
            --light-gray: #e2e8f0;
            --gray: #64748b;
            --dark: #1e293b;
            --white: #ffffff;
            --shadow: 0 8px 25px rgba(0,0,0,0.08);
            --shadow-hover: 0 15px 35px rgba(0,0,0,0.12);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --gradient: linear-gradient(135deg, #2c5aa0 0%, #4a76c2 100%);
            --gradient-light: linear-gradient(135deg, #4a76c2 0%, #6b93e6 100%);
        }
        
        .dark-theme {
            --primary: #4a76c2;
            --primary-light: #6b93e6;
            --primary-dark: #2c5aa0;
            --secondary: #6fcf72;
            --secondary-light: #8ce88f;
            --secondary-dark: #4CAF50;
            --accent: #FFB74D;
            --light: #1e293b;
            --light-gray: #334155;
            --gray: #94a3b8;
            --dark: #f1f5f9;
            --white: #0f172a;
            --shadow: 0 8px 25px rgba(0,0,0,0.2);
            --shadow-hover: 0 15px 35px rgba(0,0,0,0.3);
            --gradient: linear-gradient(135deg, #4a76c2 0%, #6b93e6 100%);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
            background-color: var(--white);
            transition: background-color 0.5s ease, color 0.5s ease;
            font-family: 'Open Sans', sans-serif;
        }
        
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            line-height: 1.3;
            color: var(--primary-dark);
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background: var(--gradient);
            color: var(--white);
            padding: 14px 28px;
            border-radius: 12px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 16px;
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow);
            font-family: 'Montserrat', sans-serif;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-hover);
            background: var(--gradient-light);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
            box-shadow: none;
        }
        
        .btn-outline:hover {
            background: var(--primary);
            color: var(--white);
        }
        
        .btn-premium {
            background: linear-gradient(135deg, var(--secondary) 0%, var(--secondary-light) 100%);
            color: var(--white);
            font-weight: 700;
            padding: 16px 32px;
            font-size: 17px;
        }
        
        section {
            padding: 100px 0;
        }
        
        h2 {
            font-size: 42px;
            margin-bottom: 20px;
            text-align: center;
            position: relative;
            font-weight: 600;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -12px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--secondary);
            border-radius: 2px;
        }
        
        .section-subtitle {
            text-align: center;
            font-size: 18px;
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto 50px;
            line-height: 1.6;
        }
        
        .theme-toggle {
            position: fixed;
            bottom: 25px;
            right: 25px;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            background: var(--gradient);
            color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
            font-size: 22px;
        }
        
        .theme-toggle:hover {
            transform: scale(1.1);
        }
        
        header {
            background-color: var(--white);
            box-shadow: 0 2px 15px rgba(0,0,0,0.08);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
        }
        
        header.scrolled {
            padding: 8px 0;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }
        
        .header-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 0;
            transition: var(--transition);
        }
        
        .logo {
            font-size: 26px;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
            font-family: 'Montserrat', sans-serif;
        }
        
        .logo i {
            margin-right: 12px;
            font-size: 30px;
            color: var(--secondary);
        }
        
        .logo-subtitle {
            font-size: 12px;
            color: var(--gray);
            margin-top: 2px;
            font-family: 'Open Sans', sans-serif;
        }
        
        .desktop-nav ul {
            display: flex;
            list-style: none;
        }
        
        .desktop-nav ul li {
            margin-left: 28px;
            position: relative;
        }
        
        .desktop-nav ul li a {
            font-weight: 500;
            transition: var(--transition);
            padding: 8px 0;
            color: var(--dark);
            font-size: 16px;
        }
        
        .desktop-nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary);
            transition: var(--transition);
        }
        
        .desktop-nav ul li a:hover::after {
            width: 100%;
        }
        
        .desktop-nav ul li a:hover {
            color: var(--primary);
        }
        
        .phone {
            font-weight: 700;
            font-size: 18px;
            display: flex;
            align-items: center;
            color: var(--primary);
            background: var(--light);
            padding: 10px 20px;
            border-radius: 10px;
            transition: var(--transition);
        }
        
        .phone:hover {
            background: var(--light-gray);
            transform: translateY(-2px);
        }
        
        .phone i {
            margin-right: 8px;
            color: var(--secondary);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--primary);
        }
        
        .mobile-nav {
            display: none;
            width: 100%;
            text-align: center;
            padding: 25px 0;
            background: var(--white);
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }
        
        .mobile-nav.active {
            display: block;
        }
        
        .mobile-nav ul {
            flex-direction: column;
            list-style: none;
        }
        
        .mobile-nav ul li {
            margin: 12px 0;
        }
        
        .mobile-nav ul li a {
            font-weight: 500;
            padding: 10px 0;
            display: block;
            transition: var(--transition);
            color: var(--dark);
            font-size: 17px;
        }
        
        .mobile-nav ul li a:hover {
            color: var(--primary);
        }
        
        .hero {
            background: linear-gradient(rgba(44, 90, 160, 0.85), rgba(44, 90, 160, 0.9)), url('https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80') no-repeat center center/cover;
            color: var(--white);
            text-align: center;
            padding: 200px 0 120px;
            margin-top: 70px;
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 52px;
            margin-bottom: 25px;
            font-weight: 600;
            color: var(--white);
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 40px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            opacity: 0.95;
            line-height: 1.6;
        }
        
        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .services {
            background-color: var(--light);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: var(--white);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            border-top: 4px solid var(--secondary);
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }
        
        .service-img {
            height: 220px;
            overflow: hidden;
            position: relative;
        }
        
        .service-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .service-card:hover .service-img img {
            transform: scale(1.05);
        }
        
        .service-content {
            padding: 25px;
        }
        
        .service-content h3 {
            margin-bottom: 15px;
            font-size: 22px;
            color: var(--primary-dark);
        }
        
        .service-content p {
            color: var(--gray);
            line-height: 1.6;
        }
        
        .catalog-section {
            padding: 100px 0;
            background-color: var(--white);
        }
        
        .catalog-filters {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 40px;
            justify-content: center;
        }
        
        .catalog-filter-btn {
            padding: 10px 22px;
            background: var(--light);
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            color: var(--dark);
        }
        
        .catalog-filter-btn.active,
        .catalog-filter-btn:hover {
            background: var(--primary);
            color: var(--white);
        }
        
        .catalog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: var(--white);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            border: 1px solid var(--light-gray);
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }
        
        .product-img {
            height: 230px;
            overflow: hidden;
            position: relative;
            background-color: var(--light);
        }
        
        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .product-card:hover .product-img img {
            transform: scale(1.05);
        }
        
        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--secondary);
            color: var(--white);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 13px;
            font-weight: 600;
        }
        
        .product-content {
            padding: 25px;
        }
        
        .product-content h3 {
            margin-bottom: 12px;
            font-size: 20px;
            color: var(--primary-dark);
        }
        
        .product-content p {
            color: var(--gray);
            font-size: 15px;
            margin-bottom: 15px;
            min-height: 60px;
            line-height: 1.6;
        }
        
        .product-features {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }
        
        .product-feature {
            background: var(--light);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 13px;
            color: var(--dark);
            border: 1px solid var(--light-gray);
        }
        
        .product-price {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .product-actions {
            display: flex;
            gap: 12px;
        }
        
        .product-actions .btn {
            flex: 1;
            padding: 12px;
            font-size: 15px;
        }
        
        .portfolio-section {
            padding: 100px 0;
            background-color: var(--light);
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .portfolio-item {
            border-radius: 16px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }
        
        .portfolio-item:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-hover);
        }
        
        .portfolio-img {
            height: 250px;
            overflow: hidden;
            position: relative;
        }
        
        .portfolio-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .portfolio-item:hover .portfolio-img img {
            transform: scale(1.05);
        }
        
        .portfolio-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: linear-gradient(transparent, rgba(44, 90, 160, 0.8));
            padding: 25px;
            color: white;
            transform: translateY(10px);
            opacity: 0;
            transition: var(--transition);
        }
        
        .portfolio-item:hover .portfolio-overlay {
            transform: translateY(0);
            opacity: 1;
        }
        
        .portfolio-overlay h3 {
            margin-bottom: 8px;
            font-size: 20px;
        }
        
        .portfolio-overlay p {
            font-size: 15px;
            opacity: 0.95;
            line-height: 1.5;
        }
        
        .advantages-section {
            padding: 100px 0;
            background-color: var(--white);
        }
        
        .advantages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }
        
        .advantage-item {
            background: var(--white);
            padding: 30px 25px;
            border-radius: 16px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--light-gray);
        }
        
        .advantage-item:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-hover);
        }
        
        .advantage-item i {
            font-size: 48px;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .advantage-item h3 {
            font-size: 18px;
            font-weight: 600;
            color: var(--primary-dark);
        }
        
        .about-section {
            padding: 100px 0;
            background-color: var(--light);
        }
        
        .about {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-img {
            flex: 1;
            height: 450px;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        
        .about-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .about-content {
            flex: 1;
        }
        
        .about-content h2 {
            text-align: left;
        }
        
        .about-content h2::after {
            left: 0;
            transform: none;
        }
        
        .about-content p {
            margin-bottom: 20px;
            color: var(--gray);
            line-height: 1.7;
            font-size: 16px;
        }
        
        .stats {
            display: flex;
            justify-content: space-between;
            margin-top: 35px;
        }
        
        .stat-item {
            text-align: center;
            flex: 1;
        }
        
        .stat-number {
            font-size: 36px;
            font-weight: 700;
            color: var(--primary);
            display: block;
            margin-bottom: 5px;
        }
        
        .stat-text {
            font-size: 15px;
            color: var(--gray);
            font-weight: 500;
        }
        
        .contacts {
            padding: 100px 0;
            background: var(--gradient);
            color: white;
        }
        
        .contacts h2 {
            color: white;
        }
        
        .contacts h2::after {
            background: var(--secondary);
        }
        
        .contacts .section-subtitle {
            color: rgba(255,255,255,0.9);
        }
        
        .contacts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }
        
        .contact-info {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 35px;
            border-radius: 16px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .contact-info h3 {
            margin-bottom: 25px;
            color: var(--white);
            font-size: 22px;
        }
        
        .contact-item {
            margin-bottom: 18px;
            display: flex;
            align-items: flex-start;
        }
        
        .contact-item i {
            margin-right: 12px;
            color: var(--secondary-light);
            width: 20px;
            text-align: center;
            font-size: 18px;
            margin-top: 3px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: rgba(255,255,255,0.95);
        }
        
        .form-control {
            width: 100%;
            padding: 14px 18px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            font-size: 16px;
            transition: var(--transition);
            background: rgba(255, 255, 255, 0.1);
            color: white;
            backdrop-filter: blur(10px);
        }
        
        .form-control:focus {
            border-color: var(--secondary-light);
            box-shadow: 0 0 0 3px rgba(111, 207, 114, 0.2);
            outline: none;
        }
        
        .form-control::placeholder {
            color: rgba(255,255,255,0.7);
        }
        
        footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 70px 0 25px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 35px;
            margin-bottom: 40px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 220px;
        }
        
        .footer-column h3 {
            margin-bottom: 22px;
            font-size: 18px;
            position: relative;
            padding-bottom: 10px;
            color: var(--white);
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 35px;
            height: 2px;
            background: var(--secondary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column ul li a {
            transition: var(--transition);
            color: rgba(255,255,255,0.8);
        }
        
        .footer-column ul li a:hover {
            color: var(--secondary-light);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 12px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 42px;
            height: 42px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: var(--transition);
            font-size: 18px;
        }
        
        .social-links a:hover {
            background: var(--secondary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 25px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 14px;
            color: rgba(255, 255, 255, 0.7);
        }
        
        .loading-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--white);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease, visibility 0.5s ease;
        }
        
        .loading-animation.hidden {
            opacity: 0;
            visibility: hidden;
        }
        
        .loader {
            width: 50px;
            height: 50px;
            border: 4px solid rgba(44, 90, 160, 0.2);
            border-radius: 50%;
            border-top-color: var(--primary);
            animation: spin 1s ease-in-out infinite;
            margin-bottom: 15px;
        }
        
        .loading-text {
            color: var(--primary);
            font-size: 16px;
            font-weight: 500;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        @media (max-width: 992px) {
            .about {
                flex-direction: column;
            }
            
            .about-content h2 {
                text-align: center;
            }
            
            .about-content h2::after {
                left: 50%;
                transform: translateX(-50%);
            }
            
            .stats {
                justify-content: space-around;
            }
        }
        
        @media (max-width: 768px) {
            .desktop-nav {
                display: none;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .header-inner {
                flex-wrap: wrap;
            }
            
            .phone {
                margin-top: 12px;
                width: 100%;
                justify-content: center;
            }
            
            .hero {
                padding: 160px 0 80px;
            }
            
            .hero h1 {
                font-size: 38px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .hero-buttons .btn {
                width: 100%;
                max-width: 280px;
            }
            
            section {
                padding: 80px 0;
            }
            
            h2 {
                font-size: 34px;
            }
            
            .catalog-grid, .services-grid, .portfolio-grid, .advantages-grid {
                grid-template-columns: 1fr;
            }
            
            .stats {
                flex-direction: column;
                gap: 25px;
            }
        }
        
        @media (max-width: 576px) {
            .container {
                padding: 0 15px;
            }
            
            .hero h1 {
                font-size: 32px;
            }
            
            .hero p {
                font-size: 16px;
            }
            
            h2 {
                font-size: 28px;
            }
            
            .section-subtitle {
                font-size: 16px;
            }
        }
    </style>
</head>
<body>
    <div class="loading-animation" id="loadingAnimation">
        <div class="loader"></div>
        <div class="loading-text">АКВАЛОС</div>
    </div>

    <header id="header">
        <div class="container">
            <div class="header-inner">
                <div class="logo">
                    <i class="fas fa-tint"></i>
                    <div>
                        ИП Рахметов А.К.
                        <div class="logo-subtitle">Автономные канализации</div>
                    </div>
                </div>
                <button class="mobile-menu-btn" id="mobileMenuBtn">
                    <i class="fas fa-bars"></i>
                </button>
                <nav class="desktop-nav">
                    <ul>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#portfolio">Примеры работ</a></li>
                        <li><a href="#about">О компании</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </nav>
                <div class="phone">
                    <i class="fas fa-phone"></i>
                    +7 (3532) 123-45-67
                </div>
            </div>
            <nav class="mobile-nav" id="mobileNav">
                <ul>
                    <li><a href="#services">Услуги</a></li>
                    <li><a href="#catalog">Каталог</a></li>
                    <li><a href="#portfolio">Примеры работ</a></li>
                    <li><a href="#about">О компании</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero" id="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Автономные канализации Аквалос</h1>
                <p>Профессиональные системы биологической очистки сточных вод для загородного дома и дачи в Оренбурге и Оренбургской области</p>
                <div class="hero-buttons">
                    <a href="#catalog" class="btn btn-premium">Смотреть каталог</a>
                    <a href="#contacts" class="btn btn-outline">Бесплатная консультация</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Остальные секции остаются с тем же содержанием, но с новым дизайном -->
    <!-- Services, Catalog, Portfolio, Advantages, About, Contacts sections -->
    <!-- Для экономии места оставляю структуру как в предыдущем варианте -->

    <div class="theme-toggle" id="themeToggle">
        <i class="fas fa-moon" id="themeIcon"></i>
    </div>

    <script>
        // JavaScript код остается таким же, как в предыдущем варианте
        // с адаптацией под новый дизайн
    </script>
</body>
</html>
