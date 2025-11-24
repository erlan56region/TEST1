РАЗРАБОТКА 4.0
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="theme-color" content="#0c1a2a">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>ИП Рахметов А.К. - Премиум автономные канализации Аквалос</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preload" href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --primary: #0c1a2a;
            --primary-dark: #081220;
            --primary-light: #1a2d45;
            --secondary: #c9a96e;
            --secondary-dark: #b89450;
            --accent: #2a5a78;
            --dark: #0a0f17;
            --light: #f8f9fa;
            --gray: #8a8f98;
            --white: #ffffff;
            --black: #05080f;
            --shadow: 0 10px 30px rgba(0,0,0,0.15);
            --transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --gradient: linear-gradient(135deg, #0c1a2a 0%, #1a2d45 50%, #2a5a78 100%);
            --gold-gradient: linear-gradient(135deg, #c9a96e 0%, #e6c260 50%, #f7d87c 100%);
        }
        
        .dark-theme {
            --primary: #1a2d45;
            --primary-dark: #0c1a2a;
            --primary-light: #2a4466;
            --secondary: #e6c260;
            --secondary-dark: #d4af37;
            --accent: #3a7a9a;
            --dark: #0a0f17;
            --light: #1a1f2a;
            --gray: #a0a5b0;
            --white: #e8e8e8;
            --black: #05080f;
            --shadow: 0 10px 30px rgba(0,0,0,0.3);
            --gradient: linear-gradient(135deg, #1a2d45 0%, #2a4466 50%, #3a7a9a 100%);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            color: var(--dark);
            line-height: 1.7;
            overflow-x: hidden;
            background-color: var(--white);
            transition: background-color 0.5s ease, color 0.5s ease;
            font-family: 'Inter', sans-serif;
        }
        
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Playfair Display', serif;
            font-weight: 600;
            line-height: 1.3;
        }
        
        .container {
            width: 100%;
            max-width: 1400px;
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
            background: var(--gold-gradient);
            color: var(--primary);
            padding: 16px 32px;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 16px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(201, 169, 110, 0.3);
            font-family: 'Inter', sans-serif;
            letter-spacing: 0.5px;
        }
        
        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(201, 169, 110, 0.4);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--secondary);
            color: var(--secondary);
            box-shadow: none;
        }
        
        .btn-outline:hover {
            background: var(--secondary);
            color: var(--primary);
        }
        
        .btn-premium {
            background: var(--gold-gradient);
            color: var(--primary);
            font-weight: 700;
            padding: 18px 36px;
            font-size: 18px;
            box-shadow: 0 10px 25px rgba(201, 169, 110, 0.4);
        }
        
        section {
            padding: 120px 0;
        }
        
        h2 {
            font-size: 48px;
            margin-bottom: 20px;
            text-align: center;
            position: relative;
            font-weight: 700;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: var(--gold-gradient);
            border-radius: 2px;
        }
        
        .section-subtitle {
            text-align: center;
            font-size: 20px;
            color: var(--gray);
            max-width: 800px;
            margin: 0 auto 60px;
            line-height: 1.6;
        }
        
        .theme-toggle {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--gold-gradient);
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
            font-size: 24px;
        }
        
        .theme-toggle:hover {
            transform: scale(1.1) rotate(15deg);
        }
        
        header {
            background-color: rgba(12, 26, 42, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
            border-bottom: 1px solid rgba(201, 169, 110, 0.2);
        }
        
        header.scrolled {
            padding: 5px 0;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }
        
        .header-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            transition: var(--transition);
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--white);
            display: flex;
            align-items: center;
            font-family: 'Playfair Display', serif;
        }
        
        .logo i {
            margin-right: 12px;
            font-size: 32px;
            color: var(--secondary);
        }
        
        .logo-subtitle {
            font-size: 12px;
            color: var(--gray);
            margin-top: 2px;
            letter-spacing: 1px;
            font-family: 'Inter', sans-serif;
        }
        
        .desktop-nav ul {
            display: flex;
            list-style: none;
        }
        
        .desktop-nav ul li {
            margin-left: 30px;
            position: relative;
        }
        
        .desktop-nav ul li a {
            font-weight: 500;
            transition: var(--transition);
            padding: 8px 0;
            color: var(--white);
            font-size: 16px;
            letter-spacing: 0.5px;
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
            color: var(--secondary);
        }
        
        .phone {
            font-weight: 700;
            font-size: 18px;
            display: flex;
            align-items: center;
            color: var(--white);
            background: rgba(201, 169, 110, 0.1);
            padding: 10px 20px;
            border-radius: 50px;
            border: 1px solid rgba(201, 169, 110, 0.3);
            transition: var(--transition);
        }
        
        .phone:hover {
            background: rgba(201, 169, 110, 0.2);
            transform: translateY(-2px);
        }
        
        .phone i {
            margin-right: 10px;
            color: var(--secondary);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--white);
        }
        
        .mobile-nav {
            display: none;
            width: 100%;
            text-align: center;
            padding: 30px 0;
            background: var(--primary);
            box-shadow: 0 5px 10px rgba(0,0,0,0.1);
        }
        
        .mobile-nav.active {
            display: block;
        }
        
        .mobile-nav ul {
            flex-direction: column;
            list-style: none;
        }
        
        .mobile-nav ul li {
            margin: 15px 0;
        }
        
        .mobile-nav ul li a {
            font-weight: 500;
            padding: 12px 0;
            display: block;
            transition: var(--transition);
            color: var(--white);
            font-size: 18px;
        }
        
        .mobile-nav ul li a:hover {
            color: var(--secondary);
        }
        
        .hero {
            background: linear-gradient(rgba(12, 26, 42, 0.9), rgba(12, 26, 42, 0.95)), url('https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80') no-repeat center center/cover;
            color: var(--white);
            text-align: center;
            padding: 240px 0 160px;
            margin-top: 80px;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" opacity="0.03"><polygon fill="white" points="0,1000 1000,0 1000,1000"/></svg>');
            background-size: cover;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 68px;
            margin-bottom: 30px;
            font-weight: 700;
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 24px;
            margin-bottom: 50px;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
            opacity: 0.9;
            line-height: 1.6;
        }
        
        .hero-buttons {
            display: flex;
            gap: 25px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .services {
            background-color: var(--light);
            position: relative;
        }
        
        .services::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.02"><polygon fill="%230c1a2a" points="50,0 100,50 50,100 0,50"/></svg>');
            background-size: 200px;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            position: relative;
            z-index: 2;
        }
        
        .service-card {
            background-color: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            border-top: 5px solid var(--secondary);
        }
        
        .service-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.15);
        }
        
        .service-img {
            height: 240px;
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
            transform: scale(1.1);
        }
        
        .service-content {
            padding: 30px;
        }
        
        .service-content h3 {
            margin-bottom: 15px;
            font-size: 24px;
            color: var(--primary);
        }
        
        .service-content p {
            color: var(--gray);
            line-height: 1.6;
        }
        
        .catalog-section {
            padding: 120px 0;
            background: var(--gradient);
            color: white;
            position: relative;
        }
        
        .catalog-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.03"><circle fill="white" cx="50" cy="50" r="2"/></svg>');
            background-size: 50px;
        }
        
        .catalog-section h2 {
            color: white;
        }
        
        .catalog-section h2::after {
            background: var(--gold-gradient);
        }
        
        .catalog-section .section-subtitle {
            color: rgba(255,255,255,0.8);
        }
        
        .catalog-filters {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 50px;
            justify-content: center;
        }
        
        .catalog-filter-btn {
            padding: 12px 24px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 50px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            color: white;
            backdrop-filter: blur(10px);
        }
        
        .catalog-filter-btn.active,
        .catalog-filter-btn:hover {
            background: var(--gold-gradient);
            color: var(--primary);
            border-color: transparent;
        }
        
        .catalog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 40px;
            position: relative;
            z-index: 2;
        }
        
        .product-card {
            background: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            border: 1px solid rgba(0,0,0,0.05);
        }
        
        .product-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.2);
        }
        
        .product-img {
            height: 250px;
            overflow: hidden;
            position: relative;
            background-color: #f8f9fa;
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
            top: 20px;
            right: 20px;
            background: var(--gold-gradient);
            color: var(--primary);
            padding: 8px 16px;
            border-radius: 50px;
            font-size: 14px;
            font-weight: 700;
            box-shadow: 0 5px 15px rgba(201, 169, 110, 0.3);
        }
        
        .product-content {
            padding: 30px;
        }
        
        .product-content h3 {
            margin-bottom: 15px;
            font-size: 22px;
            color: var(--primary);
        }
        
        .product-content p {
            color: var(--gray);
            font-size: 16px;
            margin-bottom: 20px;
            min-height: 60px;
            line-height: 1.6;
        }
        
        .product-features {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .product-feature {
            background: var(--light);
            padding: 8px 16px;
            border-radius: 50px;
            font-size: 14px;
            color: var(--primary);
            border: 1px solid rgba(0,0,0,0.05);
        }
        
        .product-price {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 25px;
            display: flex;
            align-items: center;
        }
        
        .product-price::before {
            content: '';
            display: inline-block;
            width: 30px;
            height: 2px;
            background: var(--gold-gradient);
            margin-right: 15px;
        }
        
        .product-actions {
            display: flex;
            gap: 15px;
        }
        
        .product-actions .btn {
            flex: 1;
            padding: 14px;
            font-size: 16px;
        }
        
        .portfolio-section {
            padding: 120px 0;
            background-color: var(--light);
            position: relative;
        }
        
        .portfolio-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.02"><polygon fill="%230c1a2a" points="50,0 100,50 50,100 0,50"/></svg>');
            background-size: 150px;
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
            gap: 40px;
            position: relative;
            z-index: 2;
        }
        
        .portfolio-item {
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }
        
        .portfolio-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.15);
        }
        
        .portfolio-img {
            height: 300px;
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
            background: linear-gradient(transparent, rgba(12, 26, 42, 0.9));
            padding: 30px;
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
            margin-bottom: 10px;
            font-size: 22px;
        }
        
        .portfolio-overlay p {
            font-size: 16px;
            opacity: 0.9;
            line-height: 1.6;
        }
        
        .advantages-section {
            padding: 120px 0;
            background: var(--gradient);
            color: white;
            position: relative;
        }
        
        .advantages-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.03"><circle fill="white" cx="50" cy="50" r="2"/></svg>');
            background-size: 50px;
        }
        
        .advantages-section h2 {
            color: white;
        }
        
        .advantages-section h2::after {
            background: var(--gold-gradient);
        }
        
        .advantages-section .section-subtitle {
            color: rgba(255,255,255,0.8);
        }
        
        .advantages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 60px;
            position: relative;
            z-index: 2;
        }
        
        .advantage-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 40px 30px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .advantage-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
            background: rgba(255, 255, 255, 0.15);
        }
        
        .advantage-item i {
            font-size: 54px;
            color: var(--secondary);
            margin-bottom: 25px;
        }
        
        .advantage-item h3 {
            font-size: 20px;
            font-weight: 600;
            color: var(--white);
        }
        
        .about-section {
            padding: 120px 0;
            background-color: var(--light);
            position: relative;
        }
        
        .about-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.02"><polygon fill="%230c1a2a" points="50,0 100,50 50,100 0,50"/></svg>');
            background-size: 200px;
        }
        
        .about {
            display: flex;
            align-items: center;
            gap: 60px;
            position: relative;
            z-index: 2;
        }
        
        .about-img {
            flex: 1;
            height: 500px;
            border-radius: 20px;
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
            margin-bottom: 25px;
            color: var(--gray);
            line-height: 1.7;
            font-size: 17px;
        }
        
        .stats {
            display: flex;
            justify-content: space-between;
            margin-top: 40px;
        }
        
        .stat-item {
            text-align: center;
            flex: 1;
        }
        
        .stat-number {
            font-size: 42px;
            font-weight: 700;
            color: var(--primary);
            display: block;
            margin-bottom: 5px;
        }
        
        .stat-text {
            font-size: 16px;
            color: var(--gray);
            font-weight: 500;
        }
        
        .contacts {
            padding: 120px 0;
            background: var(--gradient);
            color: white;
            position: relative;
        }
        
        .contacts::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.03"><circle fill="white" cx="50" cy="50" r="2"/></svg>');
            background-size: 50px;
        }
        
        .contacts h2 {
            color: white;
        }
        
        .contacts h2::after {
            background: var(--gold-gradient);
        }
        
        .contacts .section-subtitle {
            color: rgba(255,255,255,0.8);
        }
        
        .contacts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            position: relative;
            z-index: 2;
        }
        
        .contact-info {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .contact-info h3 {
            margin-bottom: 25px;
            color: var(--secondary);
            font-size: 24px;
        }
        
        .contact-item {
            margin-bottom: 20px;
            display: flex;
            align-items: flex-start;
        }
        
        .contact-item i {
            margin-right: 15px;
            color: var(--secondary);
            width: 20px;
            text-align: center;
            font-size: 20px;
            margin-top: 3px;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: rgba(255,255,255,0.9);
        }
        
        .form-control {
            width: 100%;
            padding: 15px 20px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            font-size: 16px;
            transition: var(--transition);
            background: rgba(255, 255, 255, 0.1);
            color: white;
            backdrop-filter: blur(10px);
        }
        
        .form-control:focus {
            border-color: var(--secondary);
            box-shadow: 0 0 0 3px rgba(201, 169, 110, 0.2);
            outline: none;
        }
        
        .form-control::placeholder {
            color: rgba(255,255,255,0.6);
        }
        
        footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 80px 0 30px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
            margin-bottom: 50px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-column h3 {
            margin-bottom: 25px;
            font-size: 20px;
            position: relative;
            padding-bottom: 10px;
            color: var(--secondary);
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background: var(--secondary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 12px;
        }
        
        .footer-column ul li a {
            transition: var(--transition);
            color: rgba(255,255,255,0.7);
        }
        
        .footer-column ul li a:hover {
            color: var(--secondary);
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 25px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: var(--transition);
            font-size: 18px;
        }
        
        .social-links a:hover {
            background: var(--secondary);
            color: var(--primary);
            transform: translateY(-5px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 15px;
            color: rgba(255, 255, 255, 0.6);
        }
        
        .loading-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--primary);
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
            width: 60px;
            height: 60px;
            border: 5px solid rgba(201, 169, 110, 0.2);
            border-radius: 50%;
            border-top-color: var(--secondary);
            animation: spin 1s ease-in-out infinite;
            margin-bottom: 20px;
        }
        
        .loading-text {
            color: var(--secondary);
            font-size: 18px;
            letter-spacing: 2px;
            font-weight: 500;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        @media (max-width: 1200px) {
            .container {
                max-width: 1140px;
            }
            
            h2 {
                font-size: 42px;
            }
            
            .hero h1 {
                font-size: 58px;
            }
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
            
            .hero h1 {
                font-size: 48px;
            }
            
            .hero p {
                font-size: 20px;
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
                margin-top: 15px;
                width: 100%;
                justify-content: center;
            }
            
            .hero {
                padding: 180px 0 100px;
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
                max-width: 300px;
            }
            
            section {
                padding: 80px 0;
            }
            
            h2 {
                font-size: 36px;
            }
            
            .catalog-grid, .services-grid, .portfolio-grid, .advantages-grid {
                grid-template-columns: 1fr;
            }
            
            .stats {
                flex-direction: column;
                gap: 30px;
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
                font-size: 30px;
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
        <div class="loading-text">АКВАЛОС ПРЕМИУМ</div>
    </div>

    <header id="header">
        <div class="container">
            <div class="header-inner">
                <div class="logo">
                    <i class="fas fa-tint"></i>
                    <div>
                        ИП Рахметов А.К.
                        <div class="logo-subtitle">ПРЕМИУМ АВТОНОМНЫЕ КАНАЛИЗАЦИИ</div>
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
                <h1>АВТОНОМНЫЕ КАНАЛИЗАЦИИ АКВАЛОС ПРЕМИУМ</h1>
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
            <p class="section-subtitle">Мы предлагаем полный комплекс услуг по установке и обслуживанию автономных канализационных систем премиум-класса</p>
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
            <p class="section-subtitle">Выберите оптимальное решение для вашего объекта из нашего каталога элитных автономных канализационных систем</p>
            <div class="catalog-filters">
                <button class="catalog-filter-btn active" data-filter="all">Все модели</button>
                <button class="catalog-filter-btn" data-filter="vertical">Вертикальные станции</button>
                <button class="catalog-filter-btn" data-filter="horizontal">Горизонтальные станции</button>
                <button class="catalog-filter-btn" data-filter="premium">Премиум решения</button>
            </div>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары будут загружены через JavaScript -->
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
                        <img src="https://images.unsplash.com/photo-1600585154340-6f09c190bafe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Загородный дом">
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
                    <i class="fas fa-ruble-sign"></i>
                    <h3>Оптимальное соотношение цена - качество</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-warehouse"></i>
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
                    <i class="fas fa-power-off"></i>
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
                    <img src="https://images.unsplash.com/photo-1560518883-ce09059eeffa?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="О компании">
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
                        <i class="fas fa-phone"></i>
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

    <div class="theme-toggle" id="themeToggle">
        <i class="fas fa-moon" id="themeIcon"></i>
    </div>

    <script>
        // Данные товаров
        const products = [
            {
                id: 1,
                name: "АКВАЛОС 2 Un*",
                description: "Автономная канализация для дома и дачи",
                price: "101 000 ₽",
                image: "https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Производительность: 400л/сут", "Залповый сброс: 120л", "Глубина подводящей трубы: до 30 см"],
                category: "vertical",
                badge: "Универсальная"
            },
            {
                id: 2,
                name: "АКВАЛОС 3 Un*",
                description: "Автономная канализация для частного дома",
                price: "113 000 ₽",
                image: "https://images.unsplash.com/photo-1581094794358-1b3d2b48f54f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Производительность: 600л/сут", "Залповый сброс: 200л", "Глубина подводящей трубы: до 50 см"],
                category: "vertical",
                badge: "Универсальная"
            },
            {
                id: 3,
                name: "АКВАЛОС 10 Un*",
                description: "Промышленная автономная канализация",
                price: "237 000 ₽",
                image: "https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Производительность: 2000л/сут", "Залповый сброс: 800л", "Глубина подводящей трубы: до 60 см"],
                category: "vertical",
                badge: "Универсальная"
            },
            {
                id: 4,
                name: "АКВАЛОС ПРЕМИУМ",
                description: "Элитная система для резиденций",
                price: "10 000 000 ₽",
                image: "https://images.unsplash.com/photo-1600585154340-6f09c190bafe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Неограниченная производительность", "Полная автоматизация", "Умное управление"],
                category: "premium",
                badge: "ПРЕМИУМ"
            }
        ];

        document.addEventListener('DOMContentLoaded', function() {
            const loadingAnimation = document.getElementById('loadingAnimation');
            if (loadingAnimation) {
                setTimeout(() => {
                    loadingAnimation.classList.add('hidden');
                }, 2000);
            }
            
            initCatalog();
            initCounters();
            initBaseFunctionality();
        });

        function initCatalog() {
            const catalogGrid = document.getElementById('catalogGrid');
            if (!catalogGrid) return;
            
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
                            ${product.features.map(feature => `<span class="product-feature">${feature}</span>`).join('')}
                        </div>
                        <div class="product-price">${product.price}</div>
                        <div class="product-actions">
                            <button class="btn" data-product-id="${product.id}">Подробнее</button>
                            <button class="btn ${product.category === 'premium' ? 'btn-premium' : 'btn-outline'}" data-product-id="${product.id}">Заказать</button>
                        </div>
                    </div>
                `;
                catalogGrid.appendChild(productCard);
            });
            
            initCatalogFilters();
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
                animateCounter(yearsCounter, 0, 15, 2500);
                animateCounter(projectsCounter, 0, 1200, 3000);
                animateCounter(clientsCounter, 0, 98, 2800);
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
            
            document.querySelectorAll('.social-links a').forEach(link => {
                link.setAttribute('target', '_blank');
                link.setAttribute('rel', 'noopener noreferrer');
            });
            
            document.querySelectorAll('.phone').forEach(phoneElement => {
                phoneElement.addEventListener('click', (e) => {
                    e.preventDefault();
                    window.location.href = 'tel:+735321234567';
                });
            });
            
            window.addEventListener('resize', () => {
                if (window.innerWidth > 768 && mobileNav) {
                    mobileNav.classList.remove('active');
                    if (mobileMenuBtn) {
                        mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                    }
                }
            });

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
