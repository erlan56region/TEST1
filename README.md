<!DOCTYPE html>
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
            font-size: 24px;
            font-weight: 700;
            font-family: 'Montserrat', sans-serif;
            letter-spacing: 2px;
        }
        
        .progress-bar {
            width: 200px;
            height: 4px;
            background: var(--light-gray);
            border-radius: 2px;
            margin-top: 15px;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background: var(--primary);
            width: 0%;
            transition: width 0.3s ease;
        }
        
        /* Модальное окно для детального просмотра */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        
        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal {
            background: var(--white);
            border-radius: 16px;
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            transform: translateY(30px);
            opacity: 0;
            transition: transform 0.4s ease, opacity 0.4s ease;
        }
        
        .modal-overlay.active .modal {
            transform: translateY(0);
            opacity: 1;
        }
        
        .modal-header {
            padding: 25px 30px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--light-gray);
            padding-bottom: 20px;
        }
        
        .modal-title {
            font-size: 24px;
            color: var(--primary-dark);
            margin: 0;
        }
        
        .modal-close {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--gray);
            transition: var(--transition);
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .modal-close:hover {
            background: var(--light-gray);
            color: var(--primary);
        }
        
        .modal-body {
            padding: 30px;
        }
        
        .modal-product {
            display: flex;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .modal-product-img {
            flex: 1;
            border-radius: 12px;
            overflow: hidden;
            max-height: 300px;
        }
        
        .modal-product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .modal-product-info {
            flex: 1;
        }
        
        .modal-product-price {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary);
            margin: 15px 0;
        }
        
        .modal-description {
            margin-top: 30px;
        }
        
        .modal-features {
            margin-top: 20px;
        }
        
        .modal-features h4 {
            margin-bottom: 15px;
            color: var(--primary-dark);
        }
        
        .modal-features ul {
            list-style-type: none;
            padding-left: 0;
        }
        
        .modal-features li {
            padding: 8px 0;
            border-bottom: 1px solid var(--light-gray);
            display: flex;
        }
        
        .modal-features li:last-child {
            border-bottom: none;
        }
        
        .modal-features li i {
            color: var(--secondary);
            margin-right: 10px;
            margin-top: 3px;
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
            
            .modal-product {
                flex-direction: column;
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
            
            .modal-header {
                padding: 20px 20px 15px;
            }
            
            .modal-body {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="loading-animation" id="loadingAnimation">
        <div class="loader"></div>
        <div class="loading-text">АКВАЛОС</div>
        <div class="progress-bar">
            <div class="progress" id="loadingProgress"></div>
        </div>
    </div>

    <header id="header">
        <div class="container">
            <div class="header-inner">
                <div class="logo">
                    <i class="fas fa-water"></i>
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
                    <i class="fas fa-phone-alt"></i>
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

    <section id="services" class="services">
        <div class="container">
            <h2>Наши услуги</h2>
            <p class="section-subtitle">Мы предлагаем полный комплекс услуг по установке и обслуживанию автономных канализационных систем</p>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-img">
                        <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Монтаж автономной канализации">
                    </div>
                    <div class="service-content">
                        <h3>Монтаж автономной канализации</h3>
                        <p>Профессиональная установка септиков Аквалос для частных домов, дач и коммерческих объектов в Оренбурге и области.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <img src="https://images.unsplash.com/photo-1581094794358-1b3d2b48f54f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Обслуживание септиков">
                    </div>
                    <div class="service-content">
                        <h3>Обслуживание септиков</h3>
                        <p>Регулярное обслуживание, чистка и ремонт автономных канализационных систем Аквалос.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <img src="https://images.unsplash.com/photo-1581094794368-3fbb8f2e7b38?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Доставка и установка">
                    </div>
                    <div class="service-content">
                        <h3>Доставка и установка</h3>
                        <p>Быстрая доставка и профессиональный монтаж септиков Аквалос в Оренбурге и Оренбургской области.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="catalog" class="catalog-section">
        <div class="container">
            <h2>Каталог автономных канализаций Аквалос</h2>
            <p class="section-subtitle">Выберите оптимальное решение для вашего объекта из нашего каталога</p>
            <div class="catalog-filters">
                <button class="catalog-filter-btn active" data-filter="all">Все модели</button>
                <button class="catalog-filter-btn" data-filter="vertical">Вертикальные станции</button>
                <button class="catalog-filter-btn" data-filter="horizontal">Горизонтальные станции</button>
                <button class="catalog-filter-btn" data-filter="large">Более 10 человек</button>
            </div>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары загружаются через JavaScript -->
            </div>
        </div>
    </section>

    <section id="portfolio" class="portfolio-section">
        <div class="container">
            <h2>Примеры выполненных работ</h2>
            <p class="section-subtitle">Реализованные проекты автономных канализационных систем для частных домов и коммерческих объектов</p>
            <div class="portfolio-grid">
                <div class="portfolio-item">
                    <div class="portfolio-img">
                        <img src="https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg" alt="Загородный дом">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Загородный дом в Оренбурге</h3>
                        <p>Установка АКВАЛОС 10 Un* для дома площадью 250 м²</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <div class="portfolio-img">
                        <img src="https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Коттедж">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Коттеджный поселок</h3>
                        <p>Комплексное решение для 8 домов в Оренбургской области</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <div class="portfolio-img">
                        <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Ресторан">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>Ресторан в Оренбурге</h3>
                        <p>Установка промышленной системы очистки</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="advantages-section">
        <div class="container">
            <h2>17 преимуществ септика Аквалос</h2>
            <p class="section-subtitle">Почему наши клиенты выбирают автономные канализации Аквалос для своих объектов</p>
            <div class="advantages-grid">
                <div class="advantage-item">
                    <i class="fas fa-money-bill-wave"></i>
                    <h3>Оптимальное соотношение цена - качество</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-boxes"></i>
                    <h3>Постоянное наличие на складе</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-calendar-check"></i>
                    <h3>Три рабочих дня до пользования станцией</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-bolt"></i>
                    <h3>Малое электропотребление</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-cogs"></i>
                    <h3>Отсутствие часто ломающихся устройств</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-plug"></i>
                    <h3>Работает при отсутствии электроэнергии (до 7 суток)</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-wind"></i>
                    <h3>Полное отсутствие запаха</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-snowflake"></i>
                    <h3>Работа при любых экстремальных погодных условиях</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-shield-alt"></i>
                    <h3>Гарантия на корпус 50 лет</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-tint"></i>
                    <h3>Нечувствительность к пиковым потокам</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-filter"></i>
                    <h3>Степень очистки 96-98%</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-flask"></i>
                    <h3>Не используются химические вещества</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-user-cog"></i>
                    <h3>Самостоятельное обслуживание</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-volume-mute"></i>
                    <h3>Низкий уровень шума</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-hand-holding-usd"></i>
                    <h3>Возможность оплаты после сдачи объекта</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-truck-loading"></i>
                    <h3>Не нужна ассенизаторская машина</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-exchange-alt"></i>
                    <h3>Простота переоборудования</h3>
                </div>
            </div>
        </div>
    </section>

    <section id="about" class="about-section">
        <div class="container">
            <div class="about">
                <div class="about-img">
                    <img src="https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg" alt="О компании">
                </div>
                <div class="about-content">
                    <h2>О компании</h2>
                    <p><strong>ИП Рахметов А.К.</strong> (ИНН 561902398552) специализируется на установке автономных канализационных систем с 2010 года. Мы являемся официальными дилерами систем Аквалос в Оренбурге и Оренбургской области.</p>
                    <p>Наша команда состоит из опытных специалистов, которые используют современное оборудование и материалы для обеспечения высокого качества работ.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number" id="yearsCounter">0</span>
                            <span class="stat-text">Лет опыта</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="projectsCounter">0</span>
                            <span class="stat-text">Установленных систем</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="clientsCounter">0</span>
                            <span class="stat-text">Довольных клиентов</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contacts" class="contacts">
        <div class="container">
            <h2>Контакты</h2>
            <p class="section-subtitle">Свяжитесь с нами для получения бесплатной консультации и расчета стоимости автономной канализации для вашего объекта</p>
            <div class="contacts-grid">
                <div class="contact-info">
                    <h3>Контактная информация</h3>
                    <div class="contact-item">
                        <i class="fas fa-user-tie"></i>
                        <div><strong>ИП Рахметов А.К.</strong></div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-id-card"></i>
                        <div>ИНН: 561902398552</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div>г. Оренбург, ул. Примерная, д. 123</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone-alt"></i>
                        <div>+7 (3532) 123-45-67</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div>info@rahmetov-orenburg.ru</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-clock"></i>
                        <div>Пн-Пт: 9:00-18:00</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marked-alt"></i>
                        <div>Работаем по всему Оренбургу и области</div>
                    </div>
                    <div class="social-links">
                        <a href="https://vk.com" target="_blank"><i class="fab fa-vk"></i></a>
                        <a href="https://t.me" target="_blank"><i class="fab fa-telegram"></i></a>
                        <a href="https://wa.me/735321234567" target="_blank"><i class="fab fa-whatsapp"></i></a>
                        <a href="https://instagram.com" target="_blank"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div class="contact-info">
                    <h3>Форма обратной связи</h3>
                    <form id="contact-form">
                        <div class="form-group">
                            <label for="name">Ваше имя</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Ваш телефон</label>
                            <input type="tel" id="phone" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="location">Ваш населенный пункт</label>
                            <input type="text" id="location" class="form-control" placeholder="Оренбург или область">
                        </div>
                        <div class="form-group">
                            <label for="message">Сообщение</label>
                            <textarea id="message" class="form-control" rows="4" placeholder="Интересует автономная канализация Аквалос..."></textarea>
                        </div>
                        <button type="submit" class="btn btn-premium">Отправить</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Компания</h3>
                    <ul>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#portfolio">Примеры работ</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Услуги</h3>
                    <ul>
                        <li><a href="#services">Автономная канализация</a></li>
                        <li><a href="#services">Монтаж септиков</a></li>
                        <li><a href="#services">Обслуживание</a></li>
                        <li><a href="#services">Консультации</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul>
                        <li><strong>ИП Рахметов А.К.</strong></li>
                        <li>ИНН: 561902398552</li>
                        <li>+7 (3532) 123-45-67</li>
                        <li>info@rahmetov-orenburg.ru</li>
                        <li>г. Оренбург, ул. Примерная, д. 123</li>
                        <li>Работаем по Оренбургу и области</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2025 ИП Рахметов А.К. (ИНН 561902398552). Все права защищены. Обслуживаем Оренбург и Оренбургскую область.
            </div>
        </div>
    </footer>

    <!-- Модальное окно для детального просмотра товара -->
    <div class="modal-overlay" id="productModal">
        <div class="modal">
            <div class="modal-header">
                <h3 class="modal-title" id="modalProductTitle">Название товара</h3>
                <button class="modal-close" id="modalClose">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="modal-body" id="modalProductBody">
                <!-- Содержимое модального окна загружается через JavaScript -->
            </div>
        </div>
    </div>

    <div class="theme-toggle" id="themeToggle">
        <i class="fas fa-moon" id="themeIcon"></i>
    </div>

    <script>
        // Ускоренная загрузка - максимум 3 секунды
        document.addEventListener('DOMContentLoaded', function() {
            const loadingAnimation = document.getElementById('loadingAnimation');
            const loadingProgress = document.getElementById('loadingProgress');
            const startTime = Date.now();
            const maxLoadTime = 3000; // 3 секунды максимум
            let progress = 0;
            
            // Быстрая симуляция загрузки с прогресс-баром
            const progressInterval = setInterval(() => {
                const elapsed = Date.now() - startTime;
                progress = Math.min(100, (elapsed / maxLoadTime) * 100);
                loadingProgress.style.width = progress + '%';
                
                // Если прошло больше 3 секунд или загрузка завершена, скрываем прелоадер
                if (elapsed >= maxLoadTime) {
                    clearInterval(progressInterval);
                    setTimeout(() => {
                        loadingAnimation.classList.add('hidden');
                        // Инициализация остального функционала
                        initCatalog();
                        initCounters();
                        initBaseFunctionality();
                    }, 300);
                }
            }, 30);
        });

        function initCatalog() {
            const catalogGrid = document.getElementById('catalogGrid');
            if (!catalogGrid) return;
            
            const products = [
                {
                    id: 1,
                    name: "АКВАЛОС 2 Un*",
                    description: "Автономная канализация для дома и дачи",
                    detailedDescription: "Компактная станция биологической очистки для небольшого дома или дачи. Идеально подходит для сезонного использования. Обеспечивает высокую степень очистки сточных вод до 98%. Простая в обслуживании и эксплуатации.",
                    price: "101 000 ₽",
                    image: "https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg",
                    features: ["Производительность: 400л/сут", "Залповый сброс: 120л", "Глубина подводящей трубы: до 30 см", "Количество пользователей: 1-2 чел", "Габариты: 1000×1000×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 2,
                    name: "АКВАЛОС 3 Un*",
                    description: "Автономная канализация для частного дома",
                    detailedDescription: "Надежная система очистки для постоянного проживания 3 человек. Отличается энергоэффективностью и стабильной работой в любое время года. Не требует частого обслуживания.",
                    price: "113 000 ₽",
                    image: "https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg",
                    features: ["Производительность: 600л/сут", "Залповый сброс: 200л", "Глубина подводящей трубы: до 50 см", "Количество пользователей: 2-3 чел", "Габариты: 1000×1000×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 3,
                    name: "АКВАЛОС 4 Un*",
                    description: "Автономная канализация для загородного дома",
                    detailedDescription: "Оптимальное решение для семьи из 4 человек. Обеспечивает комфортную эксплуатацию без запахов и шума. Устойчива к перепадам нагрузки.",
                    price: "129 000 ₽",
                    image: "https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg",
                    features: ["Производительность: 800л/сут", "Залповый сброс: 230л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 3-4 чел", "Габариты: 1000×1000×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 4,
                    name: "АКВАЛОС 5 Un*",
                    description: "Автономная канализация для большого дома",
                    detailedDescription: "Мощная система для дома с постоянным проживанием 5 человек. Справляется с пиковыми нагрузками и обеспечивает стабильную работу даже при одновременном использовании нескольких сантехнических приборов.",
                    price: "141 000 ₽",
                    image: "https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg",
                    features: ["Производительность: 900л/сут", "Залповый сброс: 320л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 4-5 чел", "Габариты: 1500×1000×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 5,
                    name: "АКВАЛОС 7 Un*",
                    description: "Автономная канализация повышенной производительности",
                    detailedDescription: "Профессиональное решение для большого загородного дома или небольшого гостевого комплекса. Обеспечивает бесперебойную работу при постоянной нагрузке.",
                    price: "171 000 ₽",
                    image: "https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg",
                    features: ["Производительность: 1200л/сут", "Залповый сброс: 500л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 6-7 чел", "Габариты: 1500×1500×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 6,
                    name: "АКВАЛОС 8 Un*",
                    description: "Профессиональная автономная канализация",
                    detailedDescription: "Надежная система для коммерческого использования или большого семейного дома. Отличается увеличенным ресурсом и устойчивостью к экстремальным нагрузкам.",
                    price: "181 000 ₽",
                    image: "https://static.tildacdn.com/stor3931-3032-4137-b631-393138316364/42248305.jpg",
                    features: ["Производительность: 1600л/сут", "Залповый сброс: 630л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 7-8 чел", "Габариты: 1500×1500×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 7,
                    name: "АКВАЛОС 10 Un*",
                    description: "Промышленная автономная канализация",
                    detailedDescription: "Мощная система для коттеджных поселков, небольших гостиниц или ресторанов. Обеспечивает высокую степень очистки при значительных объемах стоков.",
                    price: "237 000 ₽",
                    image: "https://static.tildacdn.com/stor3933-6432-4866-a261-333863346337/41217855.png",
                    features: ["Производительность: 2000л/сут", "Залповый сброс: 800л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 9-10 чел", "Габариты: 2000×1500×2000 мм"],
                    category: "vertical",
                    badge: "Универсальная"
                },
                {
                    id: 8,
                    name: "Горизонтальная станция АКВАЛОС 4",
                    description: "Горизонтальная автономная канализация",
                    detailedDescription: "Идеальное решение для участков с высоким уровнем грунтовых вод. Горизонтальная компоновка позволяет устанавливать станцию на небольшой глубине.",
                    price: "148 000 ₽",
                    image: "https://static.tildacdn.com/stor3933-6432-4866-a261-333863346337/41217855.png",
                    features: ["Производительность: 800 л/сут", "Залповый сброс: 200 л", "Глубина подводящей трубы: до 30 см", "Количество пользователей: 3-4 чел", "Габариты: 2000×1000×1500 мм"],
                    category: "horizontal",
                    badge: "Горизонтальная"
                },
                {
                    id: 9,
                    name: "Горизонтальная станция АКВАЛОС 5",
                    description: "Горизонтальная автономная канализация",
                    detailedDescription: "Надежная горизонтальная система для семьи из 5 человек. Особенно подходит для участков с ограниченной глубиной установки.",
                    price: "158 000 ₽",
                    image: "https://static.tildacdn.com/stor3933-6432-4866-a261-333863346337/41217855.png",
                    features: ["Производительность: 900 л/сут", "Залповый сброс: 300 л", "Глубина подводящей трубы: до 30 см", "Количество пользователей: 4-5 чел", "Габариты: 2000×1000×1500 мм"],
                    category: "horizontal",
                    badge: "Горизонтальная"
                },
                {
                    id: 10,
                    name: "Горизонтальная станция АКВАЛОС 7",
                    description: "Горизонтальная автономная канализация",
                    detailedDescription: "Производительная горизонтальная система для большого дома или небольшого коммерческого объекта. Обеспечивает стабильную работу при неравномерной нагрузке.",
                    price: "194 000 ₽",
                    image: "https://static.tildacdn.com/stor3933-6432-4866-a261-333863346337/41217855.png",
                    features: ["Производительность: 1200 л/сут", "Залповый сброс: 550 л", "Глубина подводящей трубы: до 30 см", "Количество пользователей: 6-7 чел", "Габариты: 2500×1000×1500 мм"],
                    category: "horizontal",
                    badge: "Горизонтальная"
                },
                {
                    id: 11,
                    name: "Горизонтальная станция АКВАЛОС 10",
                    description: "Горизонтальная автономная канализация",
                    detailedDescription: "Мощная горизонтальная система для объектов с большим водопотреблением. Идеально подходит для гостиниц, кафе и других коммерческих объектов.",
                    price: "246 000 ₽",
                    image: "https://static.tildacdn.com/stor3933-6432-4866-a261-333863346337/41217855.png",
                    features: ["Производительность: 2000 л/сут", "Залповый сброс: 800 л", "Глубина подводящей трубы: до 30 см", "Количество пользователей: 9-10 чел", "Габариты: 3000×1000×1500 мм"],
                    category: "horizontal",
                    badge: "Горизонтальная"
                },
                // Модели для более 10 человек
                {
                    id: 12,
                    name: "АКВАЛОС 15 Un*",
                    description: "Промышленная автономная канализация для больших объектов",
                    detailedDescription: "Профессиональная система для коттеджных поселков, небольших гостиниц или производственных объектов. Обеспечивает высокую степень очистки при значительных объемах стоков.",
                    price: "310 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 3000л/сут", "Залповый сброс: 1025л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 14-15 чел", "Габариты: 1750×1750×2280 мм"],
                    category: "large",
                    badge: "Промышленная"
                },
                {
                    id: 13,
                    name: "АКВАЛОС 20 Un*",
                    description: "Промышленная автономная канализация повышенной производительности",
                    detailedDescription: "Мощная система для объектов с постоянным высоким водопотреблением. Отличается увеличенным ресурсом и устойчивостью к экстремальным нагрузкам.",
                    price: "377 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 4000л/сут", "Залповый сброс: 1250л", "Глубина подводящей трубы: до 60 см", "Количество пользователей: 19-20 чел", "Габариты: 2000×2000×2280 мм"],
                    category: "large",
                    badge: "Промышленная"
                },
                {
                    id: 14,
                    name: "АКВАЛОС 30 Un*",
                    description: "Профессиональная автономная канализация",
                    detailedDescription: "Высокопроизводительная система для коммерческих и промышленных объектов. Обеспечивает бесперебойную работу при постоянной высокой нагрузке.",
                    price: "584 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 6000л/сут", "Залповый сброс: 1700л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 29-30 чел", "Габариты: 2250×2250×2500 мм"],
                    category: "large",
                    badge: "Профессиональная"
                },
                {
                    id: 15,
                    name: "АКВАЛОС 40",
                    description: "Промышленная автономная канализация",
                    detailedDescription: "Мощная система для объектов с большим водопотреблением. Идеально подходит для гостиниц, ресторанов и других коммерческих объектов с высокой нагрузкой.",
                    price: "676 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 8000л/сут", "Залповый сброс: 2250л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 39-40 чел", "Габариты: 2660×2000×2500 мм"],
                    category: "large",
                    badge: "Промышленная"
                },
                {
                    id: 16,
                    name: "АКВАЛОС 50",
                    description: "Промышленная автономная канализация",
                    detailedDescription: "Высокопроизводительная система для крупных коммерческих и промышленных объектов. Обеспечивает стабильную работу при неравномерной нагрузке.",
                    price: "882 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 9000л/сут", "Залповый сброс: 2700л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 49-50 чел", "Габариты: 3160×2000×2500 мм"],
                    category: "large",
                    badge: "Промышленная"
                },
                {
                    id: 17,
                    name: "АКВАЛОС 75",
                    description: "Промышленная автономная канализация высокой производительности",
                    detailedDescription: "Мощная система для объектов с очень высоким водопотреблением. Отличается увеличенным ресурсом и устойчивостью к экстремальным нагрузкам.",
                    price: "1 092 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 12000л/сут", "Залповый сброс: 3600л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 74-75 чел", "Габариты: 4160×2000×2500 мм"],
                    category: "large",
                    badge: "Высокая производительность"
                },
                {
                    id: 18,
                    name: "АКВАЛОС 100",
                    description: "Промышленная автономная канализация для крупных объектов",
                    detailedDescription: "Профессиональная система для крупных коммерческих и промышленных объектов. Обеспечивает бесперебойную работу при постоянной высокой нагрузке.",
                    price: "1 642 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 18000л/сут", "Залповый сброс: 4500л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 99-100 чел", "Габариты: 5160×2000×2500 мм"],
                    category: "large",
                    badge: "Для крупных объектов"
                },
                {
                    id: 19,
                    name: "АКВАЛОС 150",
                    description: "Промышленная автономная канализация для промышленных объектов",
                    detailedDescription: "Высокопроизводительная система для промышленных объектов и крупных коммерческих комплексов. Отличается увеличенным ресурсом и устойчивостью к экстремальным нагрузкам.",
                    price: "2 378 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 24000л/сут", "Залповый сброс: 6100л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 149-150 чел", "Габариты: 4160×4000×2500 мм"],
                    category: "large",
                    badge: "Промышленная"
                },
                {
                    id: 20,
                    name: "АКВАЛОС 200",
                    description: "Промышленная автономная канализация максимальной производительности",
                    detailedDescription: "Мощнейшая система для объектов с максимальным водопотреблением. Обеспечивает стабильную работу при постоянной экстремальной нагрузке.",
                    price: "2 949 000 ₽",
                    image: "https://static.tildacdn.com/stor3634-3237-4432-b631-363163336630/67448824.png",
                    features: ["Производительность: 35000л/сут", "Залповый сброс: 9000л", "Глубина подводящей трубы: до 85 см", "Количество пользователей: 199-200 чел", "Габариты: 4160×4000×2500 мм"],
                    category: "large",
                    badge: "Максимальная производительность"
                }
            ];
            
            catalogGrid.innerHTML = '';
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.setAttribute('data-category', product.category);
                productCard.innerHTML = `
                    <div class="product-img">
                        <img src="${product.image}" alt="${product.name}">
                        <div class="product-badge">${product.badge}</div>
                    </div>
                    <div class="product-content">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <div class="product-features">
                            ${product.features.slice(0, 3).map(feature => `<span class="product-feature">${feature}</span>`).join('')}
                        </div>
                        <div class="product-price">${product.price}</div>
                        <div class="product-actions">
                            <button class="btn btn-details" data-product-id="${product.id}">Подробнее</button>
                            <button class="btn btn-outline btn-order" data-product-id="${product.id}">Заказать</button>
                        </div>
                    </div>
                `;
                catalogGrid.appendChild(productCard);
            });
            
            // Добавляем обработчики для кнопок
            document.querySelectorAll('.btn-details').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = this.getAttribute('data-product-id');
                    showProductDetails(productId);
                });
            });
            
            document.querySelectorAll('.btn-order').forEach(button => {
                button.addEventListener('click', function() {
                    const productId = this.getAttribute('data-product-id');
                    orderProduct(productId);
                });
            });
            
            initCatalogFilters();
        }
        
        function showProductDetails(productId) {
            const products = [
                // Здесь должен быть тот же массив products, что и в initCatalog
                // Для краткости не дублируем его полностью
            ];
            
            const product = products.find(p => p.id == productId);
            if (!product) return;
            
            const modal = document.getElementById('productModal');
            const modalTitle = document.getElementById('modalProductTitle');
            const modalBody = document.getElementById('modalProductBody');
            
            modalTitle.textContent = product.name;
            modalBody.innerHTML = `
                <div class="modal-product">
                    <div class="modal-product-img">
                        <img src="${product.image}" alt="${product.name}">
                    </div>
                    <div class="modal-product-info">
                        <p>${product.detailedDescription}</p>
                        <div class="modal-product-price">${product.price}</div>
                        <button class="btn btn-premium btn-order-modal" data-product-id="${product.id}">Заказать</button>
                    </div>
                </div>
                <div class="modal-features">
                    <h4>Характеристики</h4>
                    <ul>
                        ${product.features.map(feature => `<li><i class="fas fa-check"></i> ${feature}</li>`).join('')}
                    </ul>
                </div>
            `;
            
            // Добавляем обработчик для кнопки заказа в модальном окне
            modalBody.querySelector('.btn-order-modal').addEventListener('click', function() {
                const productId = this.getAttribute('data-product-id');
                orderProduct(productId);
                closeModal();
            });
            
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }
        
        function closeModal() {
            const modal = document.getElementById('productModal');
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }
        
        function orderProduct(productId) {
            // Перенаправляем к форме заказа с предзаполненным полем
            const productName = document.querySelector(`[data-product-id="${productId}"]`).closest('.product-card').querySelector('h3').textContent;
            document.getElementById('message').value = `Интересует ${productName}`;
            
            // Плавная прокрутка к форме заказа
            document.getElementById('contacts').scrollIntoView({ behavior: 'smooth' });
        }
        
        function initCatalogFilters() {
            const filterButtons = document.querySelectorAll('.catalog-filter-btn');
            filterButtons.forEach(button => {
                button.addEventListener('click', () => {
                    filterButtons.forEach(btn => btn.classList.remove('active'));
                    button.classList.add('active');
                    
                    const filter = button.getAttribute('data-filter');
                    filterCatalog(filter);
                });
            });
        }
        
        function filterCatalog(filter) {
            const productCards = document.querySelectorAll('.product-card');
            productCards.forEach(card => {
                if (filter === 'all' || card.getAttribute('data-category') === filter) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        function initCounters() {
            const yearsCounter = document.getElementById('yearsCounter');
            const projectsCounter = document.getElementById('projectsCounter');
            const clientsCounter = document.getElementById('clientsCounter');
            
            if (yearsCounter && projectsCounter && clientsCounter) {
                animateCounter(yearsCounter, 0, 15, 2000);
                animateCounter(projectsCounter, 0, 1200, 2500);
                animateCounter(clientsCounter, 0, 98, 1800);
            }
        }

        function animateCounter(element, start, end, duration) {
            if (!element) return;
            
            let current = start;
            const increment = (end - start) / (duration / 16);
            const timer = setInterval(() => {
                current += increment;
                if (current >= end) {
                    current = end;
                    clearInterval(timer);
                }
                if (element.id === 'clientsCounter') {
                    element.textContent = Math.floor(current) + '%';
                } else {
                    element.textContent = Math.floor(current).toLocaleString();
                }
            }, 16);
        }

        function initBaseFunctionality() {
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const mobileNav = document.getElementById('mobileNav');
            
            if (mobileMenuBtn && mobileNav) {
                mobileMenuBtn.addEventListener('click', () => {
                    mobileNav.classList.toggle('active');
                    const icon = mobileMenuBtn.querySelector('i');
                    if (mobileNav.classList.contains('active')) {
                        icon.className = 'fas fa-times';
                    } else {
                        icon.className = 'fas fa-bars';
                    }
                });
            }
            
            // Закрытие модального окна
            const modalClose = document.getElementById('modalClose');
            const modalOverlay = document.getElementById('productModal');
            
            if (modalClose && modalOverlay) {
                modalClose.addEventListener('click', closeModal);
                modalOverlay.addEventListener('click', function(e) {
                    if (e.target === modalOverlay) {
                        closeModal();
                    }
                });
            }
            
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - 80;
                        window.scrollTo({
                            top: targetPosition,
                            behavior: 'smooth'
                        });
                        
                        if (mobileNav) {
                            mobileNav.classList.remove('active');
                            if (mobileMenuBtn) {
                                mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                            }
                        }
                    }
                });
            });
            
            const themeToggle = document.getElementById('themeToggle');
            const themeIcon = document.getElementById('themeIcon');
            let isDarkTheme = localStorage.getItem('darkTheme') === 'true';
            
            function applyTheme() {
                if (isDarkTheme) {
                    document.body.classList.add('dark-theme');
                    if (themeIcon) themeIcon.className = 'fas fa-sun';
                } else {
                    document.body.classList.remove('dark-theme');
                    if (themeIcon) themeIcon.className = 'fas fa-moon';
                }
            }
            
            function toggleTheme() {
                isDarkTheme = !isDarkTheme;
                localStorage.setItem('darkTheme', isDarkTheme);
                applyTheme();
            }
            
            if (themeToggle && themeIcon) {
                themeToggle.addEventListener('click', toggleTheme);
                applyTheme();
            }
            
            const contactForm = document.getElementById('contact-form');
            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const data = {
                        name: document.getElementById('name').value,
                        phone: document.getElementById('phone').value,
                        location: document.getElementById('location').value,
                        message: document.getElementById('message').value
                    };
                    
                    setTimeout(() => {
                        contactForm.reset();
                        alert("Ваш запрос отправлен! Мы свяжемся с вами в ближайшее время.");
                    }, 500);
                });
            }
            
            const header = document.getElementById('header');
            if (header) {
                window.addEventListener('scroll', () => {
                    if (window.scrollY > 50) {
                        header.classList.add('scrolled');
                    } else {
                        header.classList.remove('scrolled');
                    }
                });
            }
        }
    </script>
</body>
</html>
