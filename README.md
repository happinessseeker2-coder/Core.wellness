[ai_studio_code.html](https://github.com/user-attachments/files/24073390/ai_studio_code.html)
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness Designer | 追川大輝</title>
    <meta name="description" content="あなたの悩みに寄り添い、内側から健康をデザインする。Wellness Designer 追川大輝の公式サイト。">
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Noto+Sans+JP:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <!-- Font Awesome (アイコン用) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- CSS (外部ファイルにする場合は linkタグに変更してください) -->
    <style>
        /* === CSS Variables === */
        :root {
            --bg-color: #000000;
            --text-color: #ffffff;
            --text-sub: #cccccc;
            --accent-color: #40E0D0; /* Turquoise */
            --accent-hover: #33b2a6;
            --silver: #C0C0C0;
            --font-heading: 'Montserrat', sans-serif;
            --font-body: 'Noto Sans JP', sans-serif;
            --header-height: 80px;
        }

        /* === Reset & Base === */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: var(--font-body);
            line-height: 1.8;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: 0.3s;
        }

        ul {
            list-style: none;
        }

        h1, h2, h3 {
            font-family: var(--font-heading);
            letter-spacing: 0.05em;
        }

        img {
            max-width: 100%;
            height: auto;
            display: block;
        }

        /* === Utilities === */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-padding {
            padding: 120px 0;
        }

        .text-center {
            text-align: center;
        }

        .btn {
            display: inline-block;
            padding: 14px 32px;
            background-color: var(--accent-color);
            color: #000;
            font-weight: 700;
            font-size: 1rem;
            border-radius: 50px; /* 丸みを帯びたモダンな形状 */
            letter-spacing: 0.05em;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(64, 224, 208, 0.3);
        }

        .btn:hover {
            background-color: var(--accent-hover);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(64, 224, 208, 0.5);
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--silver);
            text-align: center;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 2px;
            background: var(--accent-color);
            margin: 15px auto 0;
        }

        /* === Animation Classes === */
        .fade-in-section {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
            will-change: opacity, visibility;
        }

        .fade-in-section.is-visible {
            opacity: 1;
            transform: none;
        }

        /* === Header === */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: var(--header-height);
            background-color: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 4%;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .logo {
            font-family: var(--font-heading);
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--text-color);
            letter-spacing: 0.05em;
        }

        .logo span {
            color: var(--accent-color);
        }

        .nav-wrapper {
            display: flex;
            align-items: center;
            gap: 40px;
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--text-sub);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .header-btn {
            padding: 10px 24px;
            font-size: 0.85rem;
        }

        .header-sns {
            display: flex;
            gap: 15px;
        }

        .header-sns a {
            color: var(--text-sub);
            font-size: 1.2rem;
        }

        .header-sns a:hover {
            color: var(--accent-color);
        }

        /* Mobile Menu Button */
        .menu-toggle {
            display: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* === Hero Section === */
        .hero {
            height: 100vh;
            width: 100%;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            /* Placeholder Image for Fitness/Wellness */
            background-image: url('https://images.unsplash.com/photo-1517836357463-d25dfeac3438?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6); /* Overlay for text readability */
        }

        .hero-content {
            position: relative;
            z-index: 1;
            padding: 0 20px;
            max-width: 800px;
        }

        .hero-title {
            font-size: 3rem; /* PC size */
            font-weight: 700;
            margin-bottom: 2rem;
            line-height: 1.4;
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--silver);
            margin-bottom: 1rem;
            font-weight: 300;
            letter-spacing: 0.1em;
        }

        /* === Self Introduction === */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-img {
            width: 100%;
            height: 500px; /* Adjust as needed */
            object-fit: cover;
            border-radius: 4px;
            filter: grayscale(30%); /* Slightly desaturated for mood */
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
            color: var(--accent-color);
        }

        .about-role {
            display: block;
            font-size: 1rem;
            color: var(--silver);
            margin-bottom: 2rem;
            font-family: var(--font-heading);
            letter-spacing: 0.1em;
        }

        .about-desc {
            font-size: 1rem;
            line-height: 2;
            color: var(--text-sub);
            margin-bottom: 2.5rem;
        }

        /* === Philosophy === */
        .philosophy-card {
            max-width: 800px;
            margin: 0 auto;
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 60px 40px;
            background: linear-gradient(145deg, #0a0a0a, #000000);
        }

        .philosophy-text {
            font-size: 1.2rem;
            line-height: 2.2;
            font-weight: 300;
        }

        /* === Benefits === */
        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .benefit-item {
            background: #0a0a0a;
            padding: 40px 30px;
            text-align: center;
            border: 1px solid #222;
            transition: 0.3s;
            border-radius: 8px;
        }

        .benefit-item:hover {
            border-color: var(--accent-color);
            transform: translateY(-5px);
        }

        .benefit-icon {
            font-size: 3rem;
            color: var(--accent-color);
            margin-bottom: 20px;
        }

        .benefit-text {
            font-size: 1.1rem;
            font-weight: 500;
        }

        /* === Footer === */
        .footer {
            background-color: #050505;
            padding: 60px 0 30px;
            border-top: 1px solid #111;
            text-align: center;
        }

        .footer-sns {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-bottom: 30px;
        }

        .footer-sns a {
            font-size: 1.5rem;
            color: var(--silver);
            transition: 0.3s;
        }

        .footer-sns a:hover {
            color: var(--accent-color);
        }

        .footer-links {
            margin-bottom: 20px;
        }

        .footer-links a {
            font-size: 0.9rem;
            color: var(--text-sub);
            margin: 0 10px;
        }

        .copyright {
            color: #555;
            font-size: 0.8rem;
            font-family: var(--font-heading);
        }

        /* === Responsive Design === */
        @media (max-width: 992px) {
            .header {
                padding: 0 20px;
            }
            
            .nav-wrapper {
                position: fixed;
                top: 0;
                right: -100%;
                width: 70%;
                height: 100vh;
                background: #000;
                flex-direction: column;
                justify-content: center;
                padding: 40px;
                transition: 0.4s ease;
                border-left: 1px solid #222;
            }

            .nav-wrapper.active {
                right: 0;
            }

            .nav-links {
                flex-direction: column;
                align-items: center;
                gap: 40px;
                margin-bottom: 40px;
            }

            .nav-links a {
                font-size: 1.2rem;
            }

            .header-actions {
                flex-direction: column;
            }

            .menu-toggle {
                display: block;
                z-index: 1001;
            }

            .about-grid {
                grid-template-columns: 1fr;
            }

            .about-img {
                height: 350px;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 2rem;
            }
            
            .section-padding {
                padding: 80px 0;
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="header">
        <a href="#" class="logo">Wellness <span>Designer</span></a>
        
        <div class="menu-toggle" id="mobile-menu">
            <i class="fa-solid fa-bars"></i>
        </div>

        <div class="nav-wrapper" id="nav-wrapper">
            <nav>
                <ul class="nav-links">
                    <li><a href="#about" class="nav-link-item">自己紹介</a></li>
                    <li><a href="#philosophy" class="nav-link-item">経営理念</a></li>
                    <li><a href="#benefits" class="nav-link-item">学ぶメリット</a></li>
                </ul>
            </nav>
            <div class="header-actions">
                <a href="#contact" class="btn header-btn">お問い合わせ</a>
                <div class="header-sns">
                    <a href="#"><i class="fa-brands fa-instagram"></i></a>
                    <a href="#"><i class="fa-brands fa-x-twitter"></i></a> <!-- X icon -->
                    <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content fade-in-section">
            <p class="hero-subtitle">WELLNESS DESIGNER</p>
            <h1 class="hero-title">あなたの悩みに寄り添い、<br>内側から健康をデザインする</h1>
            <a href="#contact" class="btn">無料カウンセリングを予約する</a>
        </div>
    </section>

    <!-- Self Introduction Section -->
    <section class="section-padding" id="about">
        <div class="container">
            <div class="about-grid">
                <div class="fade-in-section">
                    <!-- Placeholder for Oikawa's photo -->
                    <img src="https://images.unsplash.com/photo-1571019614242-c5c5dee9f50b?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="追川大輝" class="about-img">
                </div>
                <div class="about-text fade-in-section">
                    <h3>追川大輝</h3>
                    <span class="about-role">Wellness Designer</span>
                    <p class="about-desc">
                        もともとパーソナルトレーナーをしていたが、お客様の悩みの種の改善が真の目的だと気づきました。<br><br>
                        表面的な身体作りだけでなく、内面からのアプローチが不可欠であると感じ、ここから私はWellness Designerとして活動していくことにしました。
                    </p>
                    <a href="#contact" class="btn">お問い合わせ</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Philosophy Section -->
    <section class="section-padding" id="philosophy">
        <div class="container">
            <h2 class="section-title fade-in-section">経営理念</h2>
            <div class="philosophy-card text-center fade-in-section">
                <p class="philosophy-text">
                    お客様一人ひとりの課題に深く寄り添い、<br>
                    持続可能な健康と幸福をデザインし、<br>
                    内側から真のウェルネスを実現するサポートを提供します。
                </p>
            </div>
        </div>
    </section>

    <!-- Benefits Section -->
    <section class="section-padding" id="benefits">
        <div class="container">
            <h2 class="section-title fade-in-section">Wellness Designerスクールで<br>学ぶメリット</h2>
            
            <div class="benefits-grid">
                <!-- Merit 1 -->
                <div class="benefit-item fade-in-section">
                    <div class="benefit-icon">
                        <i class="fa-solid fa-clipboard-user"></i>
                    </div>
                    <p class="benefit-text">あなただけの<br>オーダーメイド栄養プラン</p>
                </div>
                
                <!-- Merit 2 -->
                <div class="benefit-item fade-in-section">
                    <div class="benefit-icon">
                        <i class="fa-solid fa-heart-pulse"></i>
                    </div>
                    <p class="benefit-text">内側から変わる<br>体と心の健康</p>
                </div>
                
                <!-- Merit 3 -->
                <div class="benefit-item fade-in-section">
                    <div class="benefit-icon">
                        <i class="fa-solid fa-infinity"></i>
                    </div>
                    <p class="benefit-text">継続できる<br>実践的なライフスタイル指導</p>
                </div>
                
                <!-- Merit 4 -->
                <div class="benefit-item fade-in-section">
                    <div class="benefit-icon">
                        <i class="fa-solid fa-handshake"></i>
                    </div>
                    <p class="benefit-text">個別サポートで<br>確実な目標達成</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer" id="contact">
        <div class="container">
            <div class="footer-sns">
                <a href="#"><i class="fa-brands fa-instagram"></i></a>
                <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
                <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
            </div>
            <div class="footer-links">
                <a href="#">プライバシーポリシー</a>
                <a href="#">お問い合わせ</a>
            </div>
            <p class="copyright">© 2023 Wellness Designer. All rights reserved.</p>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // === スクロールアニメーション (Intersection Observer) ===
        document.addEventListener('DOMContentLoaded', () => {
            const observerOptions = {
                root: null, // ビューポート
                rootMargin: '0px',
                threshold: 0.1 // 10%見えたら発火
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('is-visible');
                        observer.unobserve(entry.target); // 一度発火したら監視をやめる
                    }
                });
            }, observerOptions);

            const fadeElements = document.querySelectorAll('.fade-in-section');
            fadeElements.forEach(el => observer.observe(el));
        });

        // === モバイルメニューのトグル機能 ===
        const menuToggle = document.getElementById('mobile-menu');
        const navWrapper = document.getElementById('nav-wrapper');
        const navLinks = document.querySelectorAll('.nav-link-item');
        const icon = menuToggle.querySelector('i');

        menuToggle.addEventListener('click', () => {
            navWrapper.classList.toggle('active');
            
            // アイコンの切り替え (ハンバーガー <-> バツ)
            if (navWrapper.classList.contains('active')) {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-xmark');
            } else {
                icon.classList.remove('fa-xmark');
                icon.classList.add('fa-bars');
            }
        });

        // メニューリンクをクリックしたら閉じる
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                navWrapper.classList.remove('active');
                icon.classList.remove('fa-xmark');
                icon.classList.add('fa-bars');
            });
        });
    </script>
</body>
</html>
