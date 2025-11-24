Разработка 1.5
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="theme-color" content="#27ae60">
    <meta name="msapplication-TileColor" content="#27ae60">
    <title>ИП Рахметов А.К. - Автономная канализация Аквалос</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --primary: #27ae60;
            --primary-dark: #219653;
            --primary-light: #6fcf97;
            --secondary: #2d9cdb;
            --dark: #343a40;
            --light: #f8f9fa;
            --gray: #6c757d;
            --white: #ffffff;
            --black: #0a0a0a;
            --shadow: 0 5px 15px rgba(0,0,0,0.08);
            --transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--white);
            overflow-x: hidden;
            transition: var(--transition);
            min-height: 100vh;
            min-height: -webkit-fill-available;
        }
        
        /* Фикс для мобильного Safari */
        @supports (-webkit-touch-callout: none) {
            body {
                min-height: -webkit-fill-available;
            }
        }
        
        body.dark-theme {
            --dark: #f8f9fa;
            --light: #343a40;
            --white: #1a1a1a;
            --black: #f8f9fa;
            --gray: #adb5bd;
            --shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Анимация загрузки */
        .loading-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--white);
            display: flex;
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
            border: 5px solid var(--primary-light);
            border-top: 5px solid var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Шапка */
        header {
            background: var(--white);
            box-shadow: var(--shadow);
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            transition: var(--transition);
            -webkit-backdrop-filter: blur(10px);
            backdrop-filter: blur(10px);
        }
        
        header.scrolled {
            padding: 5px 0;
            background: rgba(255, 255, 255, 0.95);
        }
        
        .dark-theme header.scrolled {
            background: rgba(26, 26, 26, 0.95);
        }
        
        .header-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            transition: var(--transition);
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }
        
        .logo i {
            font-size: 2rem;
            margin-right: 10px;
            color: var(--primary);
        }
        
        .logo-subtitle {
            font-size: 0.8rem;
            font-weight: 400;
            color: var(--gray);
        }
        
        .desktop-nav ul {
            display: flex;
            list-style: none;
        }
        
        .desktop-nav li {
            margin: 0 15px;
        }
        
        .desktop-nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            padding: 5px 0;
        }
        
        .desktop-nav a:hover {
            color: var(--primary);
        }
        
        .desktop-nav a:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        .desktop-nav a:hover:after {
            width: 100%;
        }
        
        .phone {
            display: flex;
            align-items: center;
            font-weight: 600;
            color: var(--dark);
            transition: var(--transition);
            cursor: pointer;
            text-decoration: none;
            padding: 8px 16px;
            border-radius: 5px;
        }
        
        .phone:hover {
            color: var(--primary);
            background: var(--primary-light);
            color: var(--white);
        }
        
        .phone i {
            margin-right: 8px;
            color: var(--primary);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
            transition: var(--transition);
            padding: 10px;
            border-radius: 5px;
        }
        
        .mobile-menu-btn:hover {
            color: var(--primary);
            background: var(--primary-light);
        }
        
        .mobile-nav {
            display: none;
            background: var(--white);
            box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            transform: translateY(-10px);
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }
        
        .mobile-nav.active {
            transform: translateY(0);
            opacity: 1;
            visibility: visible;
        }
        
        .mobile-nav ul {
            list-style: none;
            padding: 20px;
        }
        
        .mobile-nav li {
            margin: 10px 0;
        }
        
        .mobile-nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            display: block;
            padding: 12px 15px;
            border-radius: 5px;
            transition: var(--transition);
        }
        
        .mobile-nav a:hover {
            background: var(--primary-light);
            color: var(--white);
        }
        
        /* Герой секция */
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: var(--white);
            padding: 180px 0 100px;
            text-align: center;
            position: relative;
            overflow: hidden;
            min-height: 100vh;
            display: flex;
            align-items: center;
        }
        
        .hero .container {
            width: 100%;
        }
        
        .hero:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.1" d="M0,96L48,112C96,128,192,160,288,186.7C384,213,480,235,576,213.3C672,192,768,128,864,128C960,128,1056,192,1152,192C1248,192,1344,128,1392,96L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-size: cover;
            background-position: center;
        }
        
        .hero h1 {
            font-size: clamp(2rem, 5vw, 3rem);
            margin-bottom: 20px;
            position: relative;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: clamp(1rem, 3vw, 1.2rem);
            max-width: 700px;
            margin: 0 auto 30px;
            position: relative;
            line-height: 1.5;
        }
        
        .btn {
            display: inline-block;
            background: var(--white);
            color: var(--primary);
            padding: 14px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            border: 2px solid var(--white);
            transition: var(--transition);
            cursor: pointer;
            position: relative;
            overflow: hidden;
            font-size: 1rem;
            min-height: 50px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }
        
        .btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: var(--transition);
        }
        
        .btn:hover:before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        .btn-outline {
            background: transparent;
            color: var(--white);
            border-color: var(--white);
        }
        
        .btn-outline:hover {
            background: var(--white);
            color: var(--primary);
        }
        
        /* Секции */
        section {
            padding: 80px 0;
        }
        
        h2 {
            text-align: center;
            font-size: clamp(1.8rem, 4vw, 2.5rem);
            margin-bottom: 50px;
            color: var(--dark);
            position: relative;
            line-height: 1.3;
        }
        
        h2:after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }
        
        /* Услуги */
        .services {
            background: var(--light);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .service-img {
            background: var(--primary);
            height: 150px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--white);
            font-size: 3rem;
        }
        
        .service-content {
            padding: 25px;
        }
        
        .service-content h3 {
            margin-bottom: 15px;
            color: var(--dark);
            font-size: 1.3rem;
        }
        
        /* Каталог */
        .catalog-filters {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 40px;
        }
        
        .catalog-filter-btn {
            background: var(--light);
            color: var(--dark);
            border: none;
            padding: 12px 24px;
            border-radius: 50px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            font-size: 1rem;
            min-height: 44px;
        }
        
        .catalog-filter-btn.active,
        .catalog-filter-btn:hover {
            background: var(--primary);
            color: var(--white);
        }
        
        .catalog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            cursor: pointer;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .product-img {
            background: var(--primary-light);
            height: 200px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--white);
            font-size: 4rem;
            position: relative;
        }
        
        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--primary);
            color: var(--white);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .product-content {
            padding: 25px;
        }
        
        .product-content h3 {
            margin-bottom: 10px;
            color: var(--dark);
            font-size: 1.3rem;
        }
        
        .product-features {
            margin: 15px 0;
        }
        
        .product-feature {
            display: block;
            padding: 5px 0;
            color: var(--gray);
            font-size: 0.9rem;
            position: relative;
            padding-left: 15px;
        }
        
        .product-feature:before {
            content: '•';
            position: absolute;
            left: 0;
            color: var(--primary);
        }
        
        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            margin: 15px 0;
        }
        
        .product-actions {
            display: flex;
            gap: 10px;
        }
        
        .product-actions .btn {
            flex: 1;
            padding: 12px 20px;
            font-size: 0.9rem;
            min-height: 44px;
        }
        
        /* Преимущества */
        .advantages-section {
            background: var(--light);
        }
        
        .advantages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }
        
        .advantage-item {
            background: var(--white);
            padding: 30px 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .advantage-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .advantage-item i {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        .advantage-item h3 {
            font-size: 1rem;
            color: var(--dark);
            line-height: 1.4;
        }
        
        /* О компании */
        .about {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }
        
        .about-img {
            background: var(--primary-light);
            height: 400px;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--white);
            font-size: 8rem;
        }
        
        .about-content h2 {
            text-align: left;
        }
        
        .about-content h2:after {
            left: 0;
            transform: none;
        }
        
        .about-content p {
            margin-bottom: 20px;
            color: var(--gray);
            line-height: 1.6;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 30px;
        }
        
        .stat-item {
            text-align: center;
            padding: 20px;
            background: var(--light);
            border-radius: 10px;
            transition: var(--transition);
        }
        
        .stat-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }
        
        .stat-number {
            display: block;
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .stat-text {
            color: var(--gray);
            font-size: 0.9rem;
        }
        
        /* Контакты */
        .contacts-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }
        
        .contact-info h3 {
            margin-bottom: 20px;
            color: var(--dark);
            font-size: 1.5rem;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 15px;
        }
        
        .contact-item i {
            color: var(--primary);
            margin-right: 10px;
            margin-top: 3px;
            width: 20px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 44px;
            height: 44px;
            background: var(--primary);
            color: var(--white);
            border-radius: 50%;
            text-decoration: none;
            transition: var(--transition);
            font-size: 1.2rem;
        }
        
        .social-links a:hover {
            transform: translateY(-5px);
            background: var(--primary-dark);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-control {
            width: 100%;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: 'Inter', sans-serif;
            transition: var(--transition);
            background: var(--white);
            color: var(--dark);
            font-size: 16px; /* Предотвращает масштабирование в iOS */
            min-height: 50px;
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(39, 174, 96, 0.2);
        }
        
        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--dark);
        }
        
        /* Подвал */
        footer {
            background: var(--dark);
            color: var(--white);
            padding: 60px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            margin-bottom: 20px;
            color: var(--white);
            font-size: 1.3rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column li {
            margin-bottom: 10px;
            line-height: 1.5;
        }
        
        .footer-column a {
            color: #adb5bd;
            text-decoration: none;
            transition: var(--transition);
        }
        
        .footer-column a:hover {
            color: var(--primary);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #495057;
            color: #adb5bd;
            font-size: 0.9rem;
            line-height: 1.5;
        }
        
        /* Переключатель темы */
        .theme-toggle {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--primary);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            box-shadow: var(--shadow);
            transition: var(--transition);
            z-index: 100;
            border: none;
        }
        
        .theme-toggle:hover {
            transform: scale(1.1);
        }
        
        /* Модальное окно */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            padding: 20px;
        }
        
        .modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-content {
            background: var(--white);
            border-radius: 10px;
            padding: 30px;
            max-width: 500px;
            width: 100%;
            position: relative;
            transform: scale(0.9);
            transition: var(--transition);
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .modal.active .modal-content {
            transform: scale(1);
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--gray);
            cursor: pointer;
            transition: var(--transition);
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .close-modal:hover {
            color: var(--primary);
        }
        
        /* Модальное окно товара */
        .product-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            padding: 20px;
        }
        
        .product-modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .product-modal-content {
            background: var(--white);
            border-radius: 10px;
            max-width: 900px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            transform: scale(0.9);
            transition: var(--transition);
        }
        
        .product-modal.active .product-modal-content {
            transform: scale(1);
        }
        
        .product-modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--gray);
            cursor: pointer;
            transition: var(--transition);
            z-index: 10;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .product-modal-close:hover {
            color: var(--primary);
        }
        
        .product-modal-body {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            padding: 30px;
        }
        
        .product-modal-img {
            background: var(--primary-light);
            height: 300px;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--white);
            font-size: 6rem;
        }
        
        .product-modal-price {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            margin: 15px 0;
        }
        
        .product-modal-description {
            margin-bottom: 20px;
            color: var(--gray);
            line-height: 1.6;
        }
        
        .specs-list {
            list-style: none;
            margin-bottom: 20px;
        }
        
        .specs-list li {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid #eee;
        }
        
        .spec-name {
            font-weight: 500;
        }
        
        .spec-value {
            color: var(--gray);
        }
        
        .product-modal-actions {
            display: flex;
            gap: 10px;
        }
        
        .product-modal-actions .btn {
            flex: 1;
            min-height: 50px;
        }
        
        /* Уведомление */
        .notification {
            position: fixed;
            top: 100px;
            right: 30px;
            background: var(--primary);
            color: var(--white);
            padding: 15px 25px;
            border-radius: 5px;
            box-shadow: var(--shadow);
            transform: translateX(150%);
            transition: transform 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            z-index: 3000;
            max-width: 300px;
        }
        
        .notification.show {
            transform: translateX(0);
        }
        
        /* Адаптивность */
        @media (max-width: 992px) {
            .about,
            .contacts-grid,
            .product-modal-body {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr 1fr;
            }
            
            .about-img {
                height: 300px;
                font-size: 6rem;
            }
        }
        
        @media (max-width: 768px) {
            .header-inner {
                padding: 10px 0;
            }
            
            .desktop-nav,
            .phone {
                display: none;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .mobile-nav {
                display: block;
            }
            
            .hero {
                padding: 150px 0 80px;
                min-height: 80vh;
            }
            
            h2 {
                font-size: 2rem;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
            
            .stats {
                grid-template-columns: 1fr;
            }
            
            .product-modal-body {
                padding: 20px;
            }
            
            .modal-content {
                padding: 25px;
            }
        }
        
        @media (max-width: 576px) {
            .services-grid,
            .catalog-grid {
                grid-template-columns: 1fr;
            }
            
            .advantages-grid {
                grid-template-columns: 1fr;
            }
            
            .catalog-filters {
                flex-direction: column;
                align-items: center;
            }
            
            .catalog-filter-btn {
                width: 100%;
                max-width: 250px;
            }
            
            .product-actions,
            .product-modal-actions {
                flex-direction: column;
            }
            
            .hero {
                padding: 130px 0 60px;
            }
            
            section {
                padding: 60px 0;
            }
            
            .container {
                padding: 0 15px;
            }
            
            .product-modal-body,
            .modal-content {
                padding: 20px 15px;
            }
            
            .theme-toggle {
                bottom: 20px;
                right: 20px;
                width: 45px;
                height: 45px;
            }
        }
        
        @media (max-width: 400px) {
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .btn {
                padding: 12px 24px;
                font-size: 0.9rem;
            }
        }
        
        /* Фиксы для конкретных браузеров */
        /* Safari iOS */
        @media not all and (min-resolution:.001dpcm) { 
            @supports (-webkit-appearance:none) {
                .hero {
                    -webkit-backface-visibility: hidden;
                }
            }
        }
        
        /* Firefox */
        @-moz-document url-prefix() {
            .header-inner {
                padding: 12px 0;
            }
        }
        
        /* Edge */
        @supports (-ms-ime-align:auto) {
            .hero {
                background: var(--primary);
            }
        }
    </style>
</head>
<body>
    <!-- Анимация загрузки -->
    <div class="loading-animation" id="loadingAnimation">
        <div class="loader"></div>
    </div>

    <!-- Шапка -->
    <header id="header">
        <div class="container">
            <div class="header-inner">
                <a href="#hero" class="logo">
                    <i class="fas fa-tint"></i>
                    <div>
                        ИП Рахметов А.К.
                        <div class="logo-subtitle">ИНН 561902398552</div>
                    </div>
                </a>
                <button class="mobile-menu-btn" id="mobileMenuBtn" aria-label="Открыть меню">
                    <i class="fas fa-bars"></i>
                </button>
                <nav class="desktop-nav">
                    <ul>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
                        <li><a href="#about">О компании</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </nav>
                <a href="tel:+735321234567" class="phone">
                    <i class="fas fa-phone"></i>
                    +7 (3532) 123-45-67
                </a>
            </div>
            <nav class="mobile-nav" id="mobileNav">
                <ul>
                    <li><a href="#services">Услуги</a></li>
                    <li><a href="#catalog">Каталог</a></li>
                    <li><a href="#about">О компании</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero" id="hero">
        <div class="container">
            <h1>Автономная канализация Аквалос</h1>
            <p>Профессиональные системы биологической очистки сточных вод для загородного дома и дачи в Оренбурге и Оренбургской области</p>
            <a href="#catalog" class="btn" id="catalogBtn">Смотреть каталог</a>
        </div>
    </section>

    <!-- Услуги -->
    <section id="services" class="services">
        <div class="container">
            <h2>Наши услуги</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-recycle"></i>
                    </div>
                    <div class="service-content">
                        <h3>Монтаж автономной канализации</h3>
                        <p>Профессиональная установка септиков Аквалос для частных домов, дач и коммерческих объектов в Оренбурге и области.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-tools"></i>
                    </div>
                    <div class="service-content">
                        <h3>Обслуживание септиков</h3>
                        <p>Регулярное обслуживание, чистка и ремонт автономных канализационных систем Аквалос.</p>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-img">
                        <i class="fas fa-truck"></i>
                    </div>
                    <div class="service-content">
                        <h3>Доставка и установка</h3>
                        <p>Быстрая доставка и профессиональный монтаж септиков Аквалос в Оренбурге и Оренбургской области.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Каталог -->
    <section id="catalog" class="catalog-section">
        <div class="container">
            <h2>Каталог автономных канализаций Аквалос</h2>
            <div class="catalog-filters">
                <button class="catalog-filter-btn active" data-filter="all">Все модели</button>
                <button class="catalog-filter-btn" data-filter="vertical">Вертикальные станции</button>
                <button class="catalog-filter-btn" data-filter="horizontal">Горизонтальные станции</button>
            </div>
            <div class="catalog-grid" id="catalogGrid">
                <!-- Товары будут загружены через JavaScript -->
            </div>
        </div>
    </section>

    <!-- Преимущества -->
    <section class="advantages-section">
        <div class="container">
            <h2>17 преимуществ септика Аквалос</h2>
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

    <!-- Модальное окно товара -->
    <div class="product-modal" id="productModal">
        <div class="product-modal-content">
            <button class="product-modal-close" id="productModalClose" aria-label="Закрыть">&times;</button>
            <div class="product-modal-body">
                <div class="product-modal-img">
                    <i class="fas fa-recycle" id="modalProductIcon"></i>
                </div>
                <div class="product-modal-info">
                    <h3 id="modalProductName"></h3>
                    <div class="product-modal-price" id="modalProductPrice"></div>
                    <div class="product-modal-description" id="modalProductDescription"></div>
                    <div class="product-modal-specs">
                        <h4>Характеристики</h4>
                        <ul class="specs-list" id="modalProductSpecs">
                            <!-- Спецификации будут добавлены через JavaScript -->
                        </ul>
                    </div>
                    <div class="product-modal-actions">
                        <button class="btn" id="modalProductOrder">Заказать</button>
                        <button class="btn btn-outline" id="modalProductConsult">Консультация</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- О компании -->
    <section id="about" class="about-section">
        <div class="container">
            <div class="about">
                <div class="about-img">
                    <i class="fas fa-building"></i>
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

    <!-- Контакты -->
    <section id="contacts" class="contacts">
        <div class="container">
            <h2>Контакты</h2>
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
                        <div><a href="tel:+735321234567" style="color: inherit; text-decoration: none;">+7 (3532) 123-45-67</a></div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div><a href="mailto:info@rahmetov-orenburg.ru" style="color: inherit; text-decoration: none;">info@rahmetov-orenburg.ru</a></div>
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
                        <a href="https://vk.com" target="_blank" aria-label="ВКонтакте"><i class="fab fa-vk"></i></a>
                        <a href="https://t.me" target="_blank" aria-label="Telegram"><i class="fab fa-telegram"></i></a>
                        <a href="https://wa.me/735321234567" target="_blank" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                        <a href="https://instagram.com" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
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
                        <button type="submit" class="btn">Отправить</button>
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
                    <h3>Компания</h3>
                    <ul>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#catalog">Каталог</a></li>
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
                        <li><a href="tel:+735321234567" style="color: inherit; text-decoration: none;">+7 (3532) 123-45-67</a></li>
                        <li><a href="mailto:info@rahmetov-orenburg.ru" style="color: inherit; text-decoration: none;">info@rahmetov-orenburg.ru</a></li>
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

    <!-- Переключатель темы -->
    <div class="theme-toggle" id="themeToggle" aria-label="Переключить тему">
        <i class="fas fa-moon" id="themeIcon"></i>
    </div>

    <!-- Модальное окно -->
    <div class="modal" id="modal">
        <div class="modal-content">
            <button class="close-modal" id="closeModal" aria-label="Закрыть">&times;</button>
            <h3>Быстрая консультация</h3>
            <form id="quick-form">
                <div class="form-group">
                    <label for="quick-name">Ваше имя</label>
                    <input type="text" id="quick-name" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="quick-phone">Ваш телефон</label>
                    <input type="tel" id="quick-phone" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="quick-location">Ваш населенный пункт</label>
                    <input type="text" id="quick-location" class="form-control" placeholder="Оренбург или область">
                </div>
                <button type="submit" class="btn">Позвоните мне</button>
            </form>
        </div>
    </div>

    <!-- Уведомление -->
    <div class="notification" id="notification">
        Сообщение отправлено успешно!
    </div>

    <script>
        // Данные товаров
        const products = [
            {
                id: 1,
                name: "АКВАЛОС 2 Un*",
                description: "Автономная канализация для дома и дачи",
                price: "101 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 400л/сут", "Залповый сброс: 120л", "Глубина подводящей трубы: до 30 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 2 Un* предназначена для использования в частных домах и на дачах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "400л/сут" },
                    { name: "Залповый сброс", value: "120л" },
                    { name: "Глубина подводящей трубы", value: "До 30 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "860*860*1500" }
                ]
            },
            {
                id: 2,
                name: "АКВАЛОС 3 Un*",
                description: "Автономная канализация для частного дома",
                price: "113 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 600л/сут", "Залповый сброс: 200л", "Глубина подводящей трубы: до 50 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 3 Un* предназначена для использования в частных домах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "600л/сут" },
                    { name: "Залповый сброс", value: "200л" },
                    { name: "Глубина подводящей трубы", value: "До 50 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "860*860*1850" }
                ]
            },
            {
                id: 3,
                name: "АКВАЛОС 4 Un*",
                description: "Автономная канализация для большого дома",
                price: "128 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 800л/сут", "Залповый сброс: 280л", "Глубина подводящей трубы: до 70 см"],
                category: "vertical",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 4 Un* предназначена для использования в больших частных домах. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "800л/сут" },
                    { name: "Залповый сброс", value: "280л" },
                    { name: "Глубина подводящей трубы", value: "До 70 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "1060*1060*1850" }
                ]
            },
            {
                id: 4,
                name: "АКВАЛОС 5 Un*",
                description: "Автономная канализация для нескольких домов",
                price: "148 000 ₽",
                icon: "fas fa-recycle",
                features: ["Производительность: 1000л/сут", "Залповый сброс: 350л", "Глубина подводящей трубы: до 90 см"],
                category: "horizontal",
                badge: "Универсальная",
                fullDescription: "Автономная канализация АКВАЛОС 5 Un* предназначена для использования несколькими домами или небольшими коммерческими объектами. Способ отведения воды: универсальная.",
                specifications: [
                    { name: "Способ отведения воды", value: "Универсальная" },
                    { name: "Производительность", value: "1000л/сут" },
                    { name: "Залповый сброс", value: "350л" },
                    { name: "Глубина подводящей трубы", value: "До 90 см" },
                    { name: "Габаритные размеры Д*Ш*В", value: "1500*1060*1500" }
                ]
            }
        ];

        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            // Скрытие анимации загрузки
            const loadingAnimation = document.getElementById('loadingAnimation');
            setTimeout(() => {
                if (loadingAnimation) {
                    loadingAnimation.classList.add('hidden');
                }
            }, 1000);

            // Инициализация базовой функциональности
            initBaseFunctionality();
            
            // Инициализация каталога
            initCatalog();
            
            // Инициализация анимаций
            setTimeout(() => {
                initAnimations();
                initCounters();
            }, 100);
        });

        // Базовая функциональность
        function initBaseFunctionality() {
            // Мобильное меню
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
            
            // Плавная прокрутка для всех ссылок с якорями
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    // Исключаем ссылки, которые не ведут к секциям (например, телефонные номера)
                    if (this.getAttribute('href') === '#') return;
                    
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        const headerHeight = document.getElementById('header').offsetHeight;
                        const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - headerHeight;
                        
                        window.scrollTo({
                            top: targetPosition,
                            behavior: 'smooth'
                        });
                        
                        // Закрытие мобильного меню
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
                
                // Анимация переключателя
                if (themeToggle && typeof gsap !== 'undefined') {
                    gsap.fromTo(themeToggle, {
                        scale: 1
                    }, {
                        scale: 1.2,
                        duration: 0.2,
                        yoyo: true,
                        repeat: 1
                    });
                }
            }
            
            if (themeToggle && themeIcon) {
                themeToggle.addEventListener('click', toggleTheme);
                applyTheme();
            }
            
            // Модальное окно
            const catalogBtn = document.getElementById('catalogBtn');
            const closeModal = document.getElementById('closeModal');
            const modal = document.getElementById('modal');
            
            if (catalogBtn) {
                catalogBtn.addEventListener('click', (e) => {
                    e.preventDefault();
                    if (modal) {
                        modal.classList.add('active');
                        document.body.style.overflow = 'hidden';
                    }
                });
            }
            
            if (closeModal && modal) {
                closeModal.addEventListener('click', () => {
                    modal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                });
            }
            
            // Закрытие по клику вне модального окна
            if (modal) {
                modal.addEventListener('click', (e) => {
                    if (e.target === modal) {
                        modal.classList.remove('active');
                        document.body.style.overflow = 'auto';
                    }
                });
            }
            
            // Формы
            const contactForm = document.getElementById('contact-form');
            const quickForm = document.getElementById('quick-form');
            
            if (contactForm) {
                contactForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const data = {
                        name: document.getElementById('name').value,
                        phone: document.getElementById('phone').value,
                        location: document.getElementById('location').value,
                        message: document.getElementById('message').value
                    };
                    
                    console.log('Данные формы обратной связи:', data);
                    
                    setTimeout(() => {
                        contactForm.reset();
                        showNotification("Заявка отправлена! Мы свяжемся с вами в ближайшее время.");
                    }, 500);
                });
            }
            
            if (quickForm) {
                quickForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const data = {
                        name: document.getElementById('quick-name').value,
                        phone: document.getElementById('quick-phone').value,
                        location: document.getElementById('quick-location').value
                    };
                    
                    console.log('Данные формы быстрой консультации:', data);
                    
                    setTimeout(() => {
                        quickForm.reset();
                        if (modal) {
                            modal.classList.remove('active');
                            document.body.style.overflow = 'auto';
                        }
                        showNotification("Заявка на консультацию отправлена! Мы перезвоним вам в течение 15 минут.");
                    }, 500);
                });
            }
            
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
            
            // Закрытие мобильного меню при ресайзе
            window.addEventListener('resize', () => {
                if (window.innerWidth > 768 && mobileNav) {
                    mobileNav.classList.remove('active');
                    if (mobileMenuBtn) {
                        mobileMenuBtn.querySelector('i').className = 'fas fa-bars';
                    }
                }
            });
            
            // Предотвращение масштабирования на iOS при фокусе
            document.addEventListener('touchstart', function() {}, {passive: true});
        }

        // Инициализация каталога
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
                        <i class="${product.icon}"></i>
                        ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
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
                            <button class="btn btn-outline" data-product-id="${product.id}">Заказать</button>
                        </div>
                    </div>
                `;
                catalogGrid.appendChild(productCard);
            });
            
            // Инициализация фильтров каталога
            initCatalogFilters();
            
            // Инициализация обработчиков событий для кнопок товаров
            initProductButtons();
            
            // Инициализация модального окна товара
            initProductModal();
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
                    // Анимация появления
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
                    }
                } else {
                    // Анимация скрытия
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
        
        // Инициализация обработчиков событий для кнопок товаров
        function initProductButtons() {
            const productCards = document.querySelectorAll('.product-card');
            productCards.forEach(card => {
                const buttons = card.querySelectorAll('.btn');
                buttons.forEach(button => {
                    button.addEventListener('click', (e) => {
                        e.stopPropagation();
                        const productId = parseInt(button.getAttribute('data-product-id'));
                        if (button.classList.contains('btn-outline')) {
                            // Заказ товара
                            orderProduct(productId);
                        } else {
                            // Просмотр подробной информации
                            viewProductDetails(productId);
                        }
                    });
                });
                
                // Клик по карточке товара
                card.addEventListener('click', () => {
                    const productId = parseInt(card.querySelector('.btn').getAttribute('data-product-id'));
                    viewProductDetails(productId);
                });
            });
        }
        
        // Просмотр детальной информации о товаре
        function viewProductDetails(productId) {
            const product = products.find(p => p.id === productId);
            if (product) {
                const modal = document.getElementById('productModal');
                const modalIcon = document.getElementById('modalProductIcon');
                const modalName = document.getElementById('modalProductName');
                const modalPrice = document.getElementById('modalProductPrice');
                const modalDescription = document.getElementById('modalProductDescription');
                const modalSpecs = document.getElementById('modalProductSpecs');
                
                if (!modal || !modalIcon || !modalName || !modalPrice || !modalDescription || !modalSpecs) return;
                
                // Заполнение модального окна данными товара
                modalIcon.className = product.icon;
                modalName.textContent = product.name;
                modalPrice.textContent = product.price;
                modalDescription.textContent = product.fullDescription;
                
                // Очистка и заполнение спецификаций
                modalSpecs.innerHTML = '';
                product.specifications.forEach(spec => {
                    const li = document.createElement('li');
                    li.innerHTML = `
                        <span class="spec-name">${spec.name}</span>
                        <span class="spec-value">${spec.value}</span>
                    `;
                    modalSpecs.appendChild(li);
                });
                
                // Анимация открытия модального окна
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
                
                // Анимация появления контента в модальном окне
                if (typeof gsap !== 'undefined') {
                    gsap.fromTo('.product-modal-content', {
                        scale: 0.8,
                        opacity: 0
                    }, {
                        scale: 1,
                        opacity: 1,
                        duration: 0.3,
                        ease: "back.out(1.7)"
                    });
                }
            }
        }
        
        // Заказ товара
        function orderProduct(productId) {
            const product = products.find(p => p.id === productId);
            if (product) {
                // Открытие модального окна заказа
                const modal = document.getElementById('modal');
                if (modal) {
                    modal.classList.add('active');
                    document.body.style.overflow = 'hidden';
                }
            }
        }
        
        // Инициализация модального окна товара
        function initProductModal() {
            const modal = document.getElementById('productModal');
            const closeButton = document.getElementById('productModalClose');
            const orderButton = document.getElementById('modalProductOrder');
            const consultButton = document.getElementById('modalProductConsult');
            
            if (!modal || !closeButton || !orderButton || !consultButton) return;
            
            // Закрытие модального окна
            closeButton.addEventListener('click', () => {
                closeProductModal();
            });
            
            // Заказ товара из модального окна
            orderButton.addEventListener('click', () => {
                closeProductModal();
                const modal = document.getElementById('modal');
                if (modal) {
                    modal.classList.add('active');
                    document.body.style.overflow = 'hidden';
                }
            });
            
            // Консультация по товару
            consultButton.addEventListener('click', () => {
                closeProductModal();
                const modal = document.getElementById('modal');
                if (modal) {
                    modal.classList.add('active');
                    document.body.style.overflow = 'hidden';
                }
            });
            
            // Закрытие по клику вне модального окна
            modal.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeProductModal();
                }
            });
            
            // Закрытие по клавише Escape
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && modal.classList.contains('active')) {
                    closeProductModal();
                }
            });
        }

        // Закрытие модального окна товара
        function closeProductModal() {
            const modal = document.getElementById('productModal');
            if (modal) {
                // Анимация закрытия модального окна
                if (typeof gsap !== 'undefined') {
                    gsap.to(modal.querySelector('.product-modal-content'), {
                        scale: 0.8,
                        opacity: 0,
                        duration: 0.2,
                        ease: "power2.in",
                        onComplete: () => {
                            modal.classList.remove('active');
                            document.body.style.overflow = 'auto';
                        }
                    });
                } else {
                    modal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            }
        }

        // Показать уведомление
        function showNotification(message = "Сообщение отправлено успешно!") {
            const notification = document.getElementById('notification');
            if (!notification) return;
            
            notification.textContent = message;
            notification.classList.add('show');
            
            // Анимация появления уведомления
            if (typeof gsap !== 'undefined') {
                gsap.fromTo(notification, {
                    x: 150
                }, {
                    x: 0,
                    duration: 0.5,
                    ease: "back.out(1.7)"
                });
            }
            
            setTimeout(() => {
                // Анимация скрытия уведомления
                if (typeof gsap !== 'undefined') {
                    gsap.to(notification, {
                        x: 150,
                        duration: 0.3,
                        ease: "power2.in",
                        onComplete: () => {
                            notification.classList.remove('show');
                        }
                    });
                } else {
                    notification.classList.remove('show');
                }
            }, 3000);
        }

        // Инициализация GSAP анимаций
        function initAnimations() {
            // Проверяем, загружена ли GSAP
            if (typeof gsap === 'undefined') {
                console.warn('GSAP не загружен');
                return;
            }
            
            // Инициализация ScrollTrigger
            if (typeof ScrollTrigger !== 'undefined') {
                gsap.registerPlugin(ScrollTrigger);
            } else {
                console.warn('ScrollTrigger не загружен');
                return;
            }
            
            // Анимация появления секций при скролле
            const sections = document.querySelectorAll('section');
            if (sections.length > 0) {
                sections.forEach(section => {
                    gsap.fromTo(section, {
                        opacity: 0,
                        y: 50
                    }, {
                        opacity: 1,
                        y: 0,
                        duration: 1,
                        ease: "power2.out",
                        scrollTrigger: {
                            trigger: section,
                            start: "top 80%",
                            toggleActions: "play none none none"
                        }
                    });
                });
            }
            
            // Анимация карточек услуг
            const serviceCards = document.querySelectorAll('.service-card');
            if (serviceCards.length > 0) {
                serviceCards.forEach((card, i) => {
                    gsap.fromTo(card, {
                        opacity: 0,
                        y: 50
                    }, {
                        opacity: 1,
                        y: 0,
                        duration: 0.8,
                        delay: i * 0.1,
                        ease: "power2.out",
                        scrollTrigger: {
                            trigger: card,
                            start: "top 85%",
                            toggleActions: "play none none none"
                        }
                    });
                });
            }
            
            // Анимация карточек товаров
            const productCards = document.querySelectorAll('.product-card');
            if (productCards.length > 0) {
                productCards.forEach((card, i) => {
                    gsap.fromTo(card, {
                        opacity: 0,
                        y: 50
                    }, {
                        opacity: 1,
                        y: 0,
                        duration: 0.8,
                        delay: i * 0.1,
                        ease: "power2.out",
                        scrollTrigger: {
                            trigger: card,
                            start: "top 85%",
                            toggleActions: "play none none none"
                        }
                    });
                });
            }
            
            // Анимация преимуществ
            const advantageItems = document.querySelectorAll('.advantage-item');
            if (advantageItems.length > 0) {
                advantageItems.forEach((item, i) => {
                    gsap.fromTo(item, {
                        opacity: 0,
                        y: 30
                    }, {
                        opacity: 1,
                        y: 0,
                        duration: 0.8,
                        delay: i * 0.1,
                        ease: "power2.out",
                        scrollTrigger: {
                            trigger: '.advantages-grid',
                            start: "top 85%",
                            toggleActions: "play none none none"
                        }
                    });
                });
            }
            
            // Анимация элементов "О компании"
            const aboutImg = document.querySelector('.about-img');
            const aboutContent = document.querySelector('.about-content');
            if (aboutImg && aboutContent) {
                gsap.fromTo(aboutImg, {
                    opacity: 0,
                    x: -50
                }, {
                    opacity: 1,
                    x: 0,
                    duration: 1,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: '.about',
                        start: "top 80%",
                        toggleActions: "play none none none"
                    }
                });
                
                gsap.fromTo(aboutContent, {
                    opacity: 0,
                    x: 50
                }, {
                    opacity: 1,
                    x: 0,
                    duration: 1,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: '.about',
                        start: "top 80%",
                        toggleActions: "play none none none"
                    }
                });
            }
            
            // Анимация статистики
            const statItems = document.querySelectorAll('.stat-item');
            if (statItems.length > 0) {
                statItems.forEach((item, i) => {
                    gsap.fromTo(item, {
                        opacity: 0,
                        y: 30
                    }, {
                        opacity: 1,
                        y: 0,
                        duration: 0.8,
                        delay: i * 0.2,
                        ease: "power2.out",
                        scrollTrigger: {
                            trigger: '.stats',
                            start: "top 80%",
                            toggleActions: "play none none none"
                        }
                    });
                });
            }
            
            // Анимация контактных блоков
            const contactInfos = document.querySelectorAll('.contact-info');
            if (contactInfos.length > 0) {
                contactInfos.forEach((info, i) => {
                    gsap.fromTo(info, {
                        opacity: 0,
                        y: 50
                    }, {
                        opacity: 1,
                        y: 0,
                        duration: 0.8,
                        delay: i * 0.2,
                        ease: "power2.out",
                        scrollTrigger: {
                            trigger: '.contacts-grid',
                            start: "top 80%",
                            toggleActions: "play none none none"
                        }
                    });
                });
            }
        }

        // Анимация счетчиков
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

        // Функция анимации счетчика
        function animateCounter(element, start, end, duration) {
            if (!element) return;
            
            const obj = { value: start };
            if (typeof gsap !== 'undefined') {
                gsap.to(obj, {
                    value: end,
                    duration: duration / 1000,
                    ease: "power2.out",
                    onUpdate: function() {
                        if (element.id === 'clientsCounter') {
                            element.textContent = Math.floor(obj.value) + '%';
                        } else {
                            element.textContent = Math.floor(obj.value).toLocaleString();
                        }
                    }
                });
            } else {
                // Fallback если GSAP не загружен
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
        }
    </script>
</body>
</html>
