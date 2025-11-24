Разработка 3.0
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="theme-color" content="#0c1a2a">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>AquaLux Elite - Премиум автономные канализации для элитной недвижимости</title>
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
        
        /* Темная тема */
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
        
        .btn-premium:hover {
            transform: translateY(-5px);
            box-shadow: 0 18px 35px rgba(201, 169, 110, 0.5);
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
        
        /* Переключатель темы */
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
        
        /* Шапка */
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
        
        /* Мобильная навигация */
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
        
        /* Герой секция */
        .hero {
            background: linear-gradient(rgba(12, 26, 42, 0.9), rgba(12, 26, 42, 0.95)), url('https://images.unsplash.com/photo-1600585154340-6f09c190bafe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80') no-repeat center center/cover;
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
        
        /* Услуги */
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
        
        /* Каталог */
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
        
        /* Примеры работ */
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
        
        /* Секция преимуществ */
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
        
        /* О компании */
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
        
        /* Контакты */
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
        
        /* Подвал */
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
        
        /* Анимация загрузки */
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
        
        /* Адаптивность */
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
            
            .product-modal-body {
                flex-direction: column;
            }
            
            .product-modal-img {
                height: 200px;
                min-width: 100%;
            }
            
            .product-modal-info {
                min-width: 100%;
                padding: 20px;
            }
            
            .product-modal-actions {
                flex-direction: column;
            }
            
            .contact-item {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .contact-item i {
                margin-bottom: 5px;
            }
        }
    </style>
</head>
<body>
    <!-- Анимация загрузки -->
    <div class="loading-animation" id="loadingAnimation">
        <div class="loader"></div>
        <div class="loading-text">AQUALUX ELITE</div>
    </div>

    <!-- Шапка -->
    <header id="header">
        <div class="container">
            <div class="header-inner">
                <div class="logo">
                    <i class="fas fa-water"></i>
                    <div>
                        AquaLux Elite
                        <div class="logo-subtitle">ПРЕМИУМ РЕШЕНИЯ ДЛЯ ЭЛИТНОЙ НЕДВИЖИМОСТИ</div>
                    </div>
                </div>
                <button class="mobile-menu-btn" id="mobileMenuBtn" aria-label="Открыть меню">
                    <i class="fas fa-bars"></i>
                </button>
                <nav class="desktop-nav">
                    <ul>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#portfolio">Проекты</a></li>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </nav>
                <div class="phone">
                    <i class="fas fa-phone"></i>
                    +7 (495) 123-45-67
                </div>
            </div>
            <nav class="mobile-nav" id="mobileNav">
                <ul>
                    <li><a href="#services">Услуги</a></li>
                    <li><a href="#catalog">Каталог</a></li>
                    <li><a href="#portfolio">Проекты</a></li>
                    <li><a href="#about">О нас</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero" id="hero">
        <div class="container">
            <div class="hero-content">
                <h1>ЭКСКЛЮЗИВНЫЕ АВТОНОМНЫЕ КАНАЛИЗАЦИИ ДЛЯ ВАШЕЙ РЕЗИДЕНЦИИ</h1>
                <p>Инженерные решения премиум-класса для загородных резиденций, элитных коттеджей и коммерческих объектов. Бескомпромиссное качество и полная автоматизация.</p>
                <div class="hero-buttons">
                    <a href="#catalog" class="btn btn-premium">СМОТРЕТЬ КАТАЛОГ</a>
                    <a href="#contacts" class="btn btn-outline">КОНСУЛЬТАЦИЯ ЭКСПЕРТА</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Услуги -->
    <section id="services" class="services">
        <div class="container">
            <h2>ЭКСКЛЮЗИВНЫЕ УСЛУГИ</h2>
            <p class="section-subtitle">Мы предлагаем полный комплекс премиальных услуг по проектированию, установке и обслуживанию автономных канализационных систем для объектов высшего класса</p>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-img">
                        <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Проектирование и монтаж">
                    </div>
                    <div class="service-content">
                        <h3>ИНДИВИДУАЛЬНОЕ ПРОЕКТИРОВАНИЕ</h3>
                        <p>Разработка эксклюзивных инженерных решений с учетом архитектурных особенностей вашей резиденции и ландшафта территории.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <img src="https://images.unsplash.com/photo-1581094794358-1b3d2b48f54f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="VIP обслуживание">
                    </div>
                    <div class="service-content">
                        <h3>VIP ОБСЛУЖИВАНИЕ</h3>
                        <p>Круглосуточный сервис премиум-класса с выездом специалистов в течение 2 часов и гарантией на все виды работ.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <img src="https://images.unsplash.com/photo-1581094794368-3fbb8f2e7b38?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Умные системы">
                    </div>
                    <div class="service-content">
                        <h3>УМНЫЕ ТЕХНОЛОГИИ</h3>
                        <p>Интеграция систем в умный дом с возможностью удаленного мониторинга и управления через мобильное приложение.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Каталог -->
    <section id="catalog" class="catalog-section">
        <div class="container">
            <h2>ЭКСКЛЮЗИВНЫЕ РЕШЕНИЯ</h2>
            <p class="section-subtitle">Индивидуально разработанные системы для объектов высшего класса с безупречной эстетикой и максимальной эффективностью</p>
            <div class="catalog-filters">
                <button class="catalog-filter-btn active" data-filter="all">ВСЕ СИСТЕМЫ</button>
                <button class="catalog-filter-btn" data-filter="residential">ДЛЯ РЕЗИДЕНЦИЙ</button>
                <button class="catalog-filter-btn" data-filter="commercial">ДЛЯ КОММЕРЦИИ</button>
                <button class="catalog-filter-btn" data-filter="premium">ПРЕМИУМ КОЛЛЕКЦИЯ</button>
            </div>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- Примеры работ -->
    <section id="portfolio" class="portfolio-section">
        <div class="container">
            <h2>РЕАЛИЗОВАННЫЕ ПРОЕКТЫ</h2>
            <p class="section-subtitle">Эксклюзивные решения для самых требовательных клиентов — от частных резиденций до коммерческих объектов премиум-класса</p>
            <div class="portfolio-grid">
                <div class="portfolio-item">
                    <div class="portfolio-img">
                        <img src="https://images.unsplash.com/photo-1600585154340-6f09c190bafe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Резиденция на Рублевке">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>РЕЗИДЕНЦИЯ НА РУБЛЕВКЕ</h3>
                        <p>Полностью автоматизированная система для особняка площадью 1200 м² с интеграцией в умный дом</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <div class="portfolio-img">
                        <img src="https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Загородный клуб">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>ЗАГОРОДНЫЙ КЛУБ PREMIUM</h3>
                        <p>Комплексное решение для объекта площадью 5 га с рестораном, спа-комплексом и гостиницей</p>
                    </div>
                </div>
                <div class="portfolio-item">
                    <div class="portfolio-img">
                        <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="Эко-резорт">
                    </div>
                    <div class="portfolio-overlay">
                        <h3>ЭКО-РЕЗОРТ "ЗОЛОТОЙ БЕРЕГ"</h3>
                        <p>Система с рециркуляцией воды для премиального курорта на 50 гостевых вилл</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Преимущества -->
    <section class="advantages-section">
        <div class="container">
            <h2>ПРЕИМУЩЕСТВА AQUALUX ELITE</h2>
            <p class="section-subtitle">Технологии, которые устанавливают новые стандарты в области автономных канализационных систем для элитной недвижимости</p>
            <div class="advantages-grid">
                <div class="advantage-item">
                    <i class="fas fa-microchip"></i>
                    <h3>ПОЛНАЯ АВТОМАТИЗАЦИЯ</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-mobile-alt"></i>
                    <h3>УДАЛЕННОЕ УПРАВЛЕНИЕ</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-recycle"></i>
                    <h3>РЕЦИРКУЛЯЦИЯ ВОДЫ</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-shield-alt"></i>
                    <h3>МНОГОУРОВНЕВАЯ ЗАЩИТА</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-leaf"></i>
                    <h3>ЭКОЛОГИЧЕСКАЯ БЕЗОПАСНОСТЬ</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-tachometer-alt"></i>
                    <h3>ВЫСОКАЯ ПРОИЗВОДИТЕЛЬНОСТЬ</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-infinity"></i>
                    <h3>ПОЖИЗНЕННАЯ ГАРАНТИЯ</h3>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-user-cog"></i>
                    <h3>ПЕРСОНАЛЬНЫЙ ИНЖЕНЕР</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- О компании -->
    <section id="about" class="about-section">
        <div class="container">
            <div class="about">
                <div class="about-img">
                    <img src="https://images.unsplash.com/photo-1560518883-ce09059eeffa?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" alt="О компании">
                </div>
                <div class="about-content">
                    <h2>О КОМПАНИИ AQUALUX ELITE</h2>
                    <p><strong>AquaLux Elite</strong> — эксклюзивный поставщик инженерных решений для элитной недвижимости. Мы специализируемся на создании автономных канализационных систем премиум-класса для загородных резиденций, коммерческих объектов и гостиничных комплексов высшей категории.</p>
                    <p>Наша команда состоит из ведущих инженеров и технологов, которые используют передовые разработки и материалы для обеспечения безупречного качества работ. Каждый проект — это уникальное решение, разработанное с учетом архитектурных особенностей объекта и пожеланий клиента.</p>
                    <div class="stats">
                        <div class="stat-item">
                            <span class="stat-number" id="yearsCounter">0</span>
                            <span class="stat-text">ЛЕТ НА РЫНКЕ</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="projectsCounter">0</span>
                            <span class="stat-text">РЕАЛИЗОВАННЫХ ПРОЕКТОВ</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number" id="clientsCounter">0</span>
                            <span class="stat-text">ДОВОЛЬНЫХ КЛИЕНТОВ</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Контакты -->
    <section id="contacts" class="contacts">
        <div class="container">
            <h2>КОНТАКТЫ</h2>
            <p class="section-subtitle">Свяжитесь с нами для получения персональной консультации и расчета стоимости эксклюзивного решения для вашего объекта</p>
            <div class="contacts-grid">
                <div class="contact-info">
                    <h3>КОНТАКТНАЯ ИНФОРМАЦИЯ</h3>
                    <div class="contact-item">
                        <i class="fas fa-user-tie"></i>
                        <div><strong>AquaLux Elite</strong></div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div>Москва, Рублевское шоссе, д. 28</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <div>+7 (495) 123-45-67</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div>info@aqualux-elite.ru</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-clock"></i>
                        <div>Пн-Пт: 9:00-20:00, Сб: 10:00-18:00</div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marked-alt"></i>
                        <div>Работаем по всей России и СНГ</div>
                    </div>
                    <div class="social-links">
                        <a href="https://vk.com" target="_blank" aria-label="ВКонтакте"><i class="fab fa-vk"></i></a>
                        <a href="https://t.me" target="_blank" aria-label="Telegram"><i class="fab fa-telegram"></i></a>
                        <a href="https://wa.me/74951234567" target="_blank" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                        <a href="https://instagram.com" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div class="contact-info">
                    <h3>ЗАПРОС КОНСУЛЬТАЦИИ</h3>
                    <form id="contact-form">
                        <div class="form-group">
                            <label for="name">Ваше имя</label>
                            <input type="text" id="name" class="form-control" required placeholder="Иван Иванов">
                        </div>
                        <div class="form-group">
                            <label for="phone">Ваш телефон</label>
                            <input type="tel" id="phone" class="form-control" required placeholder="+7 (XXX) XXX-XX-XX">
                        </div>
                        <div class="form-group">
                            <label for="location">Местоположение объекта</label>
                            <input type="text" id="location" class="form-control" placeholder="Московская область">
                        </div>
                        <div class="form-group">
                            <label for="message">Дополнительная информация</label>
                            <textarea id="message" class="form-control" rows="4" placeholder="Площадь объекта, особенности участка, пожелания..."></textarea>
                        </div>
                        <button type="submit" class="btn btn-premium">ОТПРАВИТЬ ЗАПРОС</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Подвал -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>КОМПАНИЯ</h3>
                    <ul>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#portfolio">Проекты</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>УСЛУГИ</h3>
                    <ul>
                        <li><a href="#services">Проектирование</a></li>
                        <li><a href="#services">Монтаж систем</a></li>
                        <li><a href="#services">Обслуживание</a></li>
                        <li><a href="#services">Консультации</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>КОНТАКТЫ</h3>
                    <ul>
                        <li><strong>AquaLux Elite</strong></li>
                        <li>Москва, Рублевское шоссе, д. 28</li>
                        <li>+7 (495) 123-45-67</li>
                        <li>info@aqualux-elite.ru</li>
                        <li>Пн-Пт: 9:00-20:00</li>
                        <li>Сб: 10:00-18:00</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2025 AquaLux Elite. Все права защищены. Эксклюзивные инженерные решения для элитной недвижимости.
            </div>
        </div>
    </footer>

    <!-- Переключатель темы -->
    <div class="theme-toggle" id="themeToggle" aria-label="Переключить тему">
        <i class="fas fa-moon" id="themeIcon"></i>
    </div>

    <script>
        // Данные товаров для премиум сайта
        const products = [
            {
                id: 1,
                name: "AQUALUX RESIDENCE 500",
                description: "Автономная система для резиденций до 500 м²",
                price: "5 800 000 ₽",
                image: "https://images.unsplash.com/photo-1600585154340-6f09c190bafe?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Производительность: 5000л/сут", "Умное управление", "Рециркуляция воды"],
                category: "residential",
                badge: "РЕЗИДЕНЦИЯ",
                fullDescription: "AQUALUX RESIDENCE 500 — это премиальное решение для загородных резиденций площадью до 500 м². Система обеспечивает полную автономность и интеграцию в умный дом.",
                specifications: [
                    { name: "Производительность", value: "5000 л/сут" },
                    { name: "Управление", value: "Умная система с приложением" },
                    { name: "Рециркуляция", value: "До 80% воды" },
                    { name: "Гарантия", value: "10 лет" },
                    { name: "Обслуживание", value: "VIP сервис 24/7" }
                ]
            },
            {
                id: 2,
                name: "AQUALUX COMMERCIAL 1000",
                description: "Промышленная система для коммерческих объектов",
                price: "12 500 000 ₽",
                image: "https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Производительность: 10000л/сут", "Промышленная очистка", "Мониторинг онлайн"],
                category: "commercial",
                badge: "КОММЕРЦИЯ",
                fullDescription: "AQUALUX COMMERCIAL 1000 предназначена для гостиниц, ресторанов и бизнес-центров. Обеспечивает бесперебойную работу при пиковых нагрузках.",
                specifications: [
                    { name: "Производительность", value: "10000 л/сут" },
                    { name: "Очистка", value: "Многоступенчатая промышленная" },
                    { name: "Мониторинг", value: "Онлайн 24/7" },
                    { name: "Гарантия", value: "7 лет" },
                    { name: "Обслуживание", value: "Техническая поддержка" }
                ]
            },
            {
                id: 3,
                name: "AQUALUX ELITE ULTIMATE",
                description: "Эксклюзивная система для объектов премиум-класса",
                price: "25 000 000 ₽",
                image: "https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Неограниченная производительность", "Полная автоматизация", "Эксклюзивный дизайн"],
                category: "premium",
                badge: "ЭКСКЛЮЗИВ",
                fullDescription: "AQUALUX ELITE ULTIMATE — это вершина инженерной мысли для самых требовательных клиентов. Полностью автоматизированная система с уникальным дизайном и максимальной эффективностью.",
                specifications: [
                    { name: "Производительность", value: "Неограниченная" },
                    { name: "Автоматизация", value: "Полная с ИИ" },
                    { name: "Дизайн", value: "Индивидуальный" },
                    { name: "Гарантия", value: "Пожизненная" },
                    { name: "Обслуживание", value: "Персональный инженер" }
                ]
            },
            {
                id: 4,
                name: "AQUALUX ELITE SIGNATURE",
                description: "Система для элитных загородных резиденций",
                price: "10 000 000 ₽",
                image: "https://images.unsplash.com/photo-1600566753190-17f0baa2a6c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
                features: ["Производительность: 8000л/сут", "Бесшумная работа", "Интеграция в умный дом"],
                category: "premium",
                badge: "ПРЕМИУМ",
                fullDescription: "AQUALUX ELITE SIGNATURE создана для владельцев элитной недвижимости, ценящих безупречное качество и современные технологии. Бесшумная работа и полная интеграция в систему умного дома.",
                specifications: [
                    { name: "Производительность", value: "8000 л/сут" },
                    { name: "Уровень шума", value: "Менее 25 дБ" },
                    { name: "Интеграция", value: "Умный дом + приложение" },
                    { name: "Гарантия", value: "15 лет" },
                    { name: "Обслуживание", value: "VIP сервис" }
                ]
            }
        ];

        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            // Скрытие анимации загрузки
            const loadingAnimation = document.getElementById('loadingAnimation');
            if (loadingAnimation) {
                setTimeout(() => {
                    loadingAnimation.classList.add('hidden');
                }, 2000);
            }
            
            // Инициализация каталога
            initCatalog();
            
            // Инициализация счетчиков
            initCounters();
            
            // Инициализация базовой функциональности
            initBaseFunctionality();
        });

        // Инициализация каталога
        function initCatalog() {
            const catalogGrid = document.getElementById('catalogGrid');
            
            if (!catalogGrid) return;
            
            // Очистка контейнера
            catalogGrid.innerHTML = '';
            
            // Создание карточек товаров
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
                            <button class="btn" data-product-id="${product.id}">ПОДРОБНЕЕ</button>
                            <button class="btn btn-premium" data-product-id="${product.id}">КОНСУЛЬТАЦИЯ</button>
                        </div>
                    </div>
                `;
                catalogGrid.appendChild(productCard);
            });
            
            // Инициализация фильтров каталога
            initCatalogFilters();
        }
        
        // Инициализация фильтров каталога
        function initCatalogFilters() {
            const filterButtons = document.querySelectorAll('.catalog-filter-btn');
            filterButtons.forEach(button => {
                button.addEventListener('click', () => {
                    // Убираем активный класс у всех кнопок
                    filterButtons.forEach(btn => btn.classList.remove('active'));
                    // Добавляем активный класс текущей кнопке
                    button.classList.add('active');
                    
                    const filter = button.getAttribute('data-filter');
                    filterCatalog(filter);
                });
            });
        }
        
        // Фильтрация каталога
        function filterCatalog(filter) {
            const productCards = document.querySelectorAll('.product-card');
            productCards.forEach(card => {
                if (filter === 'all' || card.getAttribute('data-category') === filter) {
                    card.style.display = 'block';
                    // Анимация появления отфильтрованных карточек
                    if (typeof gsap !== 'undefined') {
                        gsap.fromTo(card, {
                            opacity: 0,
                            scale: 0.8
                        }, {
                            opacity: 1,
                            scale: 1,
                            duration: 0.5,
                            ease: "power2.out"
                        });
                    } else {
                        card.style.opacity = '1';
                    }
                } else {
                    // Анимация скрытия карточек
                    if (typeof gsap !== 'undefined') {
                        gsap.to(card, {
                            opacity: 0,
                            scale: 0.8,
                            duration: 0.3,
                            ease: "power2.in",
                            onComplete: () => {
                                card.style.display = 'none';
                            }
                        });
                    } else {
                        card.style.display = 'none';
                    }
                }
            });
        }

        // Функция для запуска счетчиков
        function initCounters() {
            const yearsCounter = document.getElementById('yearsCounter');
            const projectsCounter = document.getElementById('projectsCounter');
            const clientsCounter = document.getElementById('clientsCounter');
            
            if (yearsCounter && projectsCounter && clientsCounter) {
                // Запускаем счетчики
                animateCounter(yearsCounter, 0, 12, 2500);
                animateCounter(projectsCounter, 0, 150, 3000);
                animateCounter(clientsCounter, 0, 120, 2800);
            }
        }

        // Улучшенная функция для анимации счетчика
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
                element.textContent = Math.floor(current).toLocaleString();
            }, 16);
        }

        // Базовая функциональность
        function initBaseFunctionality() {
            // Мобильное меню
            const mobileMenuBtn = document.getElementById('mobileMenuBtn');
            const mobileNav = document.getElementById('mobileNav');
            
            if (mobileMenuBtn && mobileNav) {
                mobileMenuBtn.addEventListener('click', () => {
                    mobileNav.classList.toggle('active');
                    
                    // Анимация иконки меню
                    const icon = mobileMenuBtn.querySelector('i');
                    if (mobileNav.classList.contains('active')) {
                        icon.className = 'fas fa-times';
                    } else {
                        icon.className = 'fas fa-bars';
                    }
                });
            }
            
            // Плавная прокрутка
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        // Нативная плавная прокрутка
                        const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - 80;
                        window.scrollTo({
                            top: targetPosition,
                            behavior: 'smooth'
                        });
                        
                        // Закрытие мобильного меню после клика
                        if (mobileNav) {
                            mobileNav.classList.remove('active');
                            if (mobileMenuBtn) {
                                mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                            }
                        }
                    }
                });
            });
            
            // Переключение темы
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
            
            // Обработка формы
            const contactForm = document.getElementById('contact-form');
            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    
                    // Получаем данные формы
                    const data = {
                        name: document.getElementById('name').value,
                        phone: document.getElementById('phone').value,
                        location: document.getElementById('location').value,
                        message: document.getElementById('message').value
                    };
                    
                    // В реальном приложении здесь будет отправка на сервер
                    console.log('Данные формы:', data);
                    
                    // Имитация отправки
                    setTimeout(() => {
                        contactForm.reset();
                        alert("Ваш запрос отправлен! Наш специалист свяжется с вами в ближайшее время.");
                    }, 500);
                });
            }
            
            // Социальные сети - открытие в новом окне
            document.querySelectorAll('.social-links a').forEach(link => {
                link.setAttribute('target', '_blank');
                link.setAttribute('rel', 'noopener noreferrer');
            });
            
            // Телефонный номер
            document.querySelectorAll('.phone').forEach(phoneElement => {
                phoneElement.addEventListener('click', (e) => {
                    e.preventDefault();
                    window.location.href = 'tel:+74951234567';
                });
            });
            
            // Закрытие мобильного меню при ресайзе
            window.addEventListener('resize', () => {
                if (window.innerWidth > 768 && mobileNav) {
                    mobileNav.classList.remove('active');
                    if (mobileMenuBtn) {
                        mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                    }
                }
            });

            // Обработка скролла для шапки
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
