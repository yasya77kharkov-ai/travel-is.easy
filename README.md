<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TravelEase - Премиум туристические услуги</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, sans-serif;
        }
        
        :root {
            --primary: #2563eb;
            --primary-light: #3b82f6;
            --secondary: #64748b;
            --accent: #f59e0b;
            --light: #f8fafc;
            --dark: #1e293b;
            --text: #334155;
            --white: #ffffff;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            --radius: 12px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        body {
            background-color: var(--light);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ШАПКА - АДАПТИВНАЯ */
        header {
            background-color: var(--white);
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 15px 0;
            backdrop-filter: blur(10px);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 60px;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 12px;
            transition: var(--transition);
        }
        
        .logo:hover {
            transform: translateY(-2px);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 40px;
            margin: 0;
            padding: 0;
        }
        
        nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            font-size: 1.1rem;
            transition: var(--transition);
            position: relative;
            padding: 8px 0;
        }
        
        nav a:hover {
            color: var(--primary);
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        nav a:hover::after {
            width: 100%;
        }
        
        .btn {
            display: inline-block;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            color: var(--white);
            padding: 12px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(37, 99, 235, 0.4);
        }

        /* ГЕРОЙ СЕКЦИЯ - АДАПТИВНАЯ */
        .hero {
            background: linear-gradient(135deg, rgba(37, 99, 235, 0.9) 0%, rgba(59, 130, 246, 0.8) 100%), 
                        url('https://images.unsplash.com/photo-1488646953014-85cb44e25828?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            padding: 120px 0;
            text-align: center;
            min-height: 100vh;
            display: flex;
            align-items: center;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            color: var(--white);
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            font-weight: 800;
            line-height: 1.2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .hero p {
            font-size: 1.3rem;
            margin: 0 auto 3rem;
            opacity: 0.95;
            max-width: 600px;
            line-height: 1.8;
        }
        
        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            align-items: center;
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--white);
            color: var(--white);
            backdrop-filter: blur(10px);
        }
        
        .btn-outline:hover {
            background: var(--white);
            color: var(--primary);
            transform: translateY(-3px);
        }

        /* СЕКЦИИ - АДАПТИВНЫЕ */
        .section {
            padding: 100px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 4rem;
        }
        
        .section-title h2 {
            font-size: 2.8rem;
            color: var(--dark);
            margin-bottom: 1.5rem;
            font-weight: 700;
        }
        
        .section-title p {
            max-width: 700px;
            margin: 0 auto;
            color: var(--secondary);
            font-size: 1.2rem;
            line-height: 1.8;
        }

        /* УСЛУГИ - АДАПТИВНЫЕ */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background: var(--white);
            border-radius: var(--radius);
            padding: 3rem 2rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            text-align: center;
            border: 1px solid rgba(0, 0, 0, 0.05);
            position: relative;
            overflow: hidden;
        }
        
        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            transform: scaleX(0);
            transition: var(--transition);
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }
        
        .service-card:hover::before {
            transform: scaleX(1);
        }
        
        .service-icon {
            font-size: 3.5rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
            transition: var(--transition);
        }
        
        .service-card:hover .service-icon {
            transform: scale(1.1);
        }
        
        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }
        
        .service-card p {
            color: var(--secondary);
            line-height: 1.7;
        }

        /* НАПРАВЛЕНИЯ - АДАПТИВНЫЕ */
        .destinations-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }
        
        .destination-card {
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            position: relative;
            height: 400px;
            transition: var(--transition);
        }
        
        .destination-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
        }
        
        .destination-img {
            height: 100%;
            background-size: cover;
            background-position: center;
            transition: transform 0.8s ease;
        }
        
        .destination-card:hover .destination-img {
            transform: scale(1.1);
        }
        
        .destination-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.9));
            color: var(--white);
            padding: 2rem;
            transform: translateY(20px);
            transition: var(--transition);
        }
        
        .destination-card:hover .destination-overlay {
            transform: translateY(0);
        }
        
        .destination-overlay h3 {
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
        }

        /* ОТЗЫВЫ - АДАПТИВНЫЕ */
        .testimonials {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: var(--white);
            position: relative;
        }
        
        .testimonials::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://images.unsplash.com/photo-1523531294919-4bcd7c65e216?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');
            background-size: cover;
            background-position: center;
            opacity: 0.1;
        }
        
        .testimonials .section-title h2 {
            color: var(--white);
        }
        
        .testimonials .section-title p {
            color: rgba(255, 255, 255, 0.9);
        }
        
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            position: relative;
            z-index: 1;
        }
        
        .testimonial-card {
            background: rgba(255, 255, 255, 0.95);
            padding: 2.5rem;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }
        
        .testimonial-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 1);
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 2rem;
            position: relative;
            color: var(--dark);
            line-height: 1.8;
        }
        
        .testimonial-text::before {
            content: """;
            font-size: 5rem;
            color: var(--primary-light);
            opacity: 0.2;
            position: absolute;
            top: -2rem;
            left: -1rem;
            font-family: Georgia, serif;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }
        
        .author-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: bold;
            font-size: 1.2rem;
            flex-shrink: 0;
        }

        /* ПРИЗЫВ К ДЕЙСТВИЮ - АДАПТИВНЫЙ */
        .cta {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: var(--white);
            text-align: center;
            padding: 6rem 0;
            border-radius: var(--radius);
            position: relative;
            overflow: hidden;
        }
        
        .cta::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://images.unsplash.com/photo-1469474968028-56623f02e42e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');
            background-size: cover;
            background-position: center;
            opacity: 0.2;
        }
        
        .cta-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .cta h2 {
            color: var(--white);
            margin-bottom: 1.5rem;
            font-size: 2.5rem;
        }
        
        .cta p {
            max-width: 600px;
            margin: 0 auto 3rem;
            font-size: 1.2rem;
            opacity: 0.95;
        }

        /* КОНТАКТЫ - АДАПТИВНЫЕ */
        .contact-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: start;
        }
        
        .contact-info {
            background: var(--white);
            padding: 3rem;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            height: fit-content;
        }
        
        .contact-info h3 {
            color: var(--dark);
            margin-bottom: 2rem;
            font-size: 1.8rem;
        }
        
        .contact-details {
            list-style: none;
        }
        
        .contact-details li {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
            padding: 1rem;
            border-radius: var(--radius);
            transition: var(--transition);
        }
        
        .contact-details li:hover {
            background: var(--light);
            transform: translateX(10px);
        }
        
        .contact-details i {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 1.2rem;
        }
        
        .contact-form {
            background: var(--white);
            padding: 3rem;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
        }
        
        .form-group {
            margin-bottom: 2rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.8rem;
            font-weight: 600;
            color: var(--dark);
            font-size: 1.1rem;
        }
        
        .form-control {
            width: 100%;
            padding: 1rem 1.5rem;
            border: 2px solid #e2e8f0;
            border-radius: var(--radius);
            font-size: 1rem;
            transition: var(--transition);
            background: var(--light);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            background: var(--white);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* ПОДВАЛ - АДАПТИВНЫЙ */
        footer {
            background: linear-gradient(135deg, var(--dark) 0%, #0f172a 100%);
            color: var(--white);
            padding: 5rem 0 2rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }
        
        .footer-column h3 {
            color: var(--white);
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
            position: relative;
            padding-bottom: 0.8rem;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--primary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column a {
            color: #cbd5e1;
            text-decoration: none;
            transition: var(--transition);
            display: inline-block;
        }
        
        .footer-column a:hover {
            color: var(--white);
            transform: translateX(5px);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--white);
            transition: var(--transition);
            font-size: 1.2rem;
        }
        
        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px) rotate(5deg);
        }
        
        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #94a3b8;
            font-size: 0.9rem;
        }

        /* АДАПТИВНОСТЬ ДЛЯ МОБИЛЬНЫХ УСТРОЙСТВ */
        @media (max-width: 1200px) {
            .container {
                max-width: 1140px;
            }
            
            .hero h1 {
                font-size: 3rem;
            }
        }

        @media (max-width: 992px) {
            .container {
                max-width: 960px;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .section-title h2 {
                font-size: 2.2rem;
            }
            
            .contact-section {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            
            nav ul {
                gap: 25px;
            }
        }

        @media (max-width: 768px) {
            .container {
                max-width: 720px;
            }
            
            .header-content {
                flex-direction: column;
                height: auto;
                gap: 20px;
                padding: 10px 0;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
                gap: 15px;
            }
            
            .hero {
                padding: 80px 0;
                min-height: auto;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .hero-buttons {
                flex-direction: column;
                gap: 15px;
            }
            
            .section {
                padding: 60px 0;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .service-card {
                padding: 2rem 1.5rem;
            }
            
            .destination-card {
                height: 350px;
            }
        }

        @media (max-width: 576px) {
            .container {
                width: 95%;
                padding: 0 15px;
            }
            
            .logo {
                font-size: 1.5rem;
            }
            
            nav ul {
                gap: 10px;
            }
            
            nav a {
                font-size: 0.9rem;
            }
            
            .btn {
                padding: 10px 25px;
                font-size: 0.9rem;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .section-title p {
                font-size: 1rem;
            }
            
            .service-card {
                padding: 1.5rem;
            }
            
            .service-icon {
                font-size: 2.5rem;
            }
            
            .contact-info,
            .contact-form {
                padding: 2rem 1.5rem;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
        }

        /* АНИМАЦИИ */
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

        .fade-in {
            animation: fadeInUp 0.8s ease-out;
        }

        /* СКРОЛЛБАР */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: var(--light);
        }
        
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary);
        }
    </style>
</head>
<body>
    <!-- ШАПКА -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-globe-americas"></i>
                    TravelEase
                </div>
                <nav>
                    <ul>
                        <li><a href="#home">Главная</a></li>
                        <li><a href="#services">Услуги</a></li>
                        <li><a href="#destinations">Направления</a></li>
                        <li><a href="#testimonials">Отзывы</a></li>
                        <li><a href="#contact">Контакты</a></li>
                    </ul>
                </nav>
                <a href="#contact" class="btn">Начать путешествие</a>
            </div>
        </div>
    </header>

    <!-- ГЕРОЙ СЕКЦИЯ -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content fade-in">
                <h1>Откройте мир с TravelEase</h1>
                <p>Премиум туристические услуги для самых требовательных путешественников. Мы создаем незабываемые впечатления по всему миру.</p>
                <div class="hero-buttons">
                    <a href="#services" class="btn">Наши услуги</a>
                    <a href="#destinations" class="btn btn-outline">Эксклюзивные направления</a>
                </div>
            </div>
        </div>
    </section>

    <!-- УСЛУГИ -->
    <section class="section" id="services">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Наши премиум услуги</h2>
                <p>Полный спектр туристических услуг высшего класса для вашего комфорта и удовольствия</p>
            </div>
            <div class="services-grid">
                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-plane-first-class"></i>
                    </div>
                    <h3>Бизнес-класс</h3>
                    <p>Перелеты бизнес-классом с максимальным комфортом и премиум обслуживанием на борту.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-hotel"></i>
                    </div>
                    <h3>Люкс отели</h3>
                    <p>Размещение в лучших отелях 5* по всему миру с эксклюзивными условиями бронирования.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-route"></i>
                    </div>
                    <h3>Индивидуальные туры</h3>
                    <p>Разработка персональных маршрутов с учетом всех ваших пожеланий и предпочтений.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-concierge-bell"></i>
                    </div>
                    <h3>VIP сервис</h3>
                    <p>Персональный менеджер, трансферы, гиды и эксклюзивные экскурсии по всему миру.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- НАПРАВЛЕНИЯ -->
    <section class="section" id="destinations">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Эксклюзивные направления</h2>
                <p>Откройте для себя самые роскошные и уникальные места для путешествий</p>
            </div>
            <div class="destinations-grid">
                <div class="destination-card fade-in">
                    <div class="destination-img" style="background-image: url('https://images.unsplash.com/photo-1543349689-9a4d426bee8e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');"></div>
                    <div class="destination-overlay">
                        <h3>Мальдивы</h3>
                        <p>От 350 000 руб.</p>
                    </div>
                </div>
                <div class="destination-card fade-in">
                    <div class="destination-img" style="background-image: url('https://images.unsplash.com/photo-1533050487297-09b450131914?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');"></div>
                    <div class="destination-overlay">
                        <h3>Санторини</h3>
                        <p>От 280 000 руб.</p>
                    </div>
                </div>
                <div class="destination-card fade-in">
                    <div class="destination-img" style="background-image: url('https://images.unsplash.com/photo-1539650116574-75c0c6d73f6e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');"></div>
                    <div class="destination-overlay">
                        <h3>Бора-Бора</h3>
                        <p>От 420 000 руб.</p>
                    </div>
                </div>
                <div class="destination-card fade-in">
                    <div class="destination-img" style="background-image: url('https://images.unsplash.com/photo-1590523741831-ab7e8b8f9c7f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');"></div>
                    <div class="destination-overlay">
                        <h3>Дубай</h3>
                        <p>От 320 000 руб.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ОТЗЫВЫ -->
    <section class="section testimonials" id="testimonials">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Отзывы наших клиентов</h2>
                <p>Что говорят путешественники о своем опыте с TravelEase</p>
            </div>
            <div class="testimonials-grid">
                <div class="testimonial-card fade-in">
                    <div class="testimonial-text">
                        Невероятный сервис! Организовали нам свадебное путешествие на Мальдивы. Каждая деталь была продумана до мелочей. Спасибо команде TravelEase за незабываемые впечатления!
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">АП</div>
                        <div class="author-info">
                            <h4>Анна Петрова</h4>
                            <p>Путешествовала на Мальдивы</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card fade-in">
                    <div class="testimonial-text">
                        Бронировали через TravelEase тур в Дубай для всей семьи. Все было организовано на высшем уровне: отель, экскурсии, трансферы. Дети в восторге, мы с женой довольны!
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">ИС</div>
                        <div class="author-info">
                            <h4>Иван Сидоров</h4>
                            <p>Путешествовал в Дубай</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card fade-in">
                    <div class="testimonial-text">
                        Премиум сервис на всех этапах! От консультации до возвращения домой. Персональный менеджер решал все вопросы 24/7. Теперь только с TravelEase!
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">ОК</div>
                        <div class="author-info">
                            <h4>Ольга Козлова</h4>
                            <p>Путешествовала в Санторини</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ПРИЗЫВ К ДЕЙСТВИЮ -->
    <section class="section">
        <div class="container">
            <div class="cta">
                <div class="cta-content fade-in">
                    <h2>Готовы к роскошному путешествию?</h2>
                    <p>Свяжитесь с нами сегодня и получите персональное предложение для вашего идеального отпуска</p>
                    <a href="#contact" class="btn">Забронировать консультацию</a>
                </div>
            </div>
        </div>
    </section>

    <!-- КОНТАКТЫ -->
    <section class="section" id="contact">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Свяжитесь с нами</h2>
                <p>Наша команда экспертов готова создать для вас идеальное путешествие</p>
            </div>
            <div class="contact-section">
                <div class="contact-info fade-in">
                    <h3>Наши контакты</h3>
                    <ul class="contact-details">
                        <li>
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <strong>Адрес</strong>
                                <p>Москва, ул. Тверская, 15</p>
                            </div>
                        </li>
                        <li>
                            <i class="fas fa-phone"></i>
                            <div>
                                <strong>Телефон</strong>
                                <p>+7 (495) 123-45-67</p>
                            </div>
                        </li>
                        <li>
                            <i class="fas fa-envelope"></i>
                            <div>
                                <strong>Email</strong>
                                <p>vip@travelease.ru</p>
                            </div>
                        </li>
                        <li>
                            <i class="fas fa-clock"></i>
                            <div>
                                <strong>Часы работы</strong>
                                <p>Пн-Вс: 9:00-22:00</p>
                            </div>
                        </li>
                    </ul>
                </div>
                <div class="contact-form fade-in">
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Ваше имя</label>
                            <input type="text" id="name" class="form-control" placeholder="Введите ваше имя" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" class="form-control" placeholder="Введите ваш email" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Телефон</label>
                            <input type="tel" id="phone" class="form-control" placeholder="Введите ваш телефон">
                        </div>
                        <div class="form-group">
                            <label for="message">Сообщение</label>
                            <textarea id="message" class="form-control" placeholder="Расскажите о ваших планах путешествия" required></textarea>
                        </div>
                        <button type="submit" class="btn" style="width: 100%;">Отправить запрос</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- ПОДВАЛ -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>TravelEase</h3>
                    <p>Премиум туристические услуги для самых требовательных клиентов. Мы создаем незабываемые впечатления и гарантируем высочайший уровень сервиса.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-vk"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Услуги</h3>
                    <ul>
                        <li><a href="#">Бизнес-класс</a></li>
                        <li><a href="#">Люкс отели</a></li>
                        <li><a href="#">Индивидуальные туры</a></li>
                        <li><a href="#">VIP сервис</a></li>
                        <li><a href="#">Яхтинг</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Направления</h3>
                    <ul>
                        <li><a href="#">Мальдивы</a></li>
                        <li><a href="#">Санторини</a></li>
                        <li><a href="#">Бора-Бора</a></li>
                        <li><a href="#">Дубай</a></li>
                        <li><a href="#">Сейшелы</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul>
                        <li><i class="fas fa-map-marker-alt"></i> Москва, ул. Тверская, 15</li>
                        <li><i class="fas fa-phone"></i> +7 (495) 123-45-67</li>
                        <li><i class="fas fa-envelope"></i> vip@travelease.ru</li>
                        <li><i class="fas fa-clock"></i> Пн-Вс: 9:00-22:00</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 TravelEase Premium. Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Плавная прокрутка для якорных ссылок
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Обработка формы
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Благодарим за ваш запрос! Наш менеджер свяжется с вами в ближайшее время для обсуждения деталей вашего путешествия.');
            this.reset();
        });
        
        // Анимация появления элементов при скролле
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        // Применяем анимацию к элементам
        document.querySelectorAll('.fade-in').forEach(element => {
            element.style.opacity = '0';
            element.style.transform = 'translateY(30px)';
            element.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
            observer.observe(element);
        });
    </script>
</body>
</html>
