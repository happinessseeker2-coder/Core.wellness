<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness Designer | 追川大輝</title>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Noto+Sans+JP:wght@300;400;500;700&display=swap" rel="stylesheet">

    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* === CSS Variables === */
        :root {
            --bg-color: #050505; /* 真っ黒より少し目に優しい黒 */
            --bg-secondary: #0f0f0f; 
            --bg-tertiary: #1a1a1a;
            --text-color: #f0f0f0;
            --text-sub: #b0b0b0;
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
            line-height: 1.9;
            letter-spacing: 0.5px;
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

        h1, h2, h3, h4 {
            font-family: var(--font-heading);
            letter-spacing: 0.08em;
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
            padding: 100px 0 120px;
        }
        
        #about, #benefits {
            background-color: var(--bg-secondary);
        }
        #philosophy, #flow {
            background-color: var(--bg-tertiary);
        }
        #reviews {
            background-color: var(--bg-color);
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
            border-radius: 50px;
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
            font-size: 2.2rem;
            margin-bottom: 4rem;
            color: var(--silver);
            text-align: center;
            position: relative;
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
            transition: opacity 1.0s ease-out, transform 1.0s ease-out;
            will-change: opacity, transform;
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
            background-color: rgba(5, 5, 5, 0.9);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 5%;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            font-family: var(--font-heading);
            color: var(--text-color);
            z-index: 1001; /* モバイルメニューより上に */
        }
        .logo span {
            color: var(--accent-color);
        }

        .nav-wrapper {
            display: flex;
            align-items: center;
            gap: 30px;
        }

        .nav-links {
            display: flex;
            gap: 25px;
        }

        .nav-link-item {
            font-size: 0.95rem;
            font-weight: 500;
            position: relative;
        }

        .nav-link-item::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0%;
            height: 1px;
            background-color: var(--accent-color);
            transition: width 0.3s;
        }

        .nav-link-item:hover::after {
            width: 100%;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .header-btn {
            padding: 10px 24px;
            font-size: 0.9rem;
        }

        .header-sns {
            display: flex;
            gap: 15px;
        }
        .header-sns a {
            font-size: 1.1rem;
            color: var(--text-sub);
        }
        .header-sns a:hover {
            color: var(--accent-color);
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 1001;
        }

        /* === Hero Section === */
        .hero {
            height: 100vh;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background-color: #000; /* フォールバック */
            /* 画像がある場合は以下を有効化 */
            background-image: url('hero-bg.jpg'); 
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0,0,0,0.4) 0%, rgba(0,0,0,0.8) 100%);
        }

        .hero-content {
            position: relative;
            z-index: 1;
            padding: 0 20px;
        }

        .hero-subtitle {
            color: var(--accent-color);
            font-weight: 600;
            letter-spacing: 0.2em;
            margin-bottom: 1rem;
            font-family: var(--font-heading);
        }

        .hero-title {
            font-size: clamp(2rem, 5vw, 3.5rem);
            margin-bottom: 2rem;
            line-height: 1.4;
        }

        /* === Self Introduction === */
        .about-grid {
            display: grid;
            grid-template-columns: 0.8fr 1.2fr;
            gap: 60px;
            align-items: center;
        }

        .about-img {
            width: 100%;
            height: 450px; 
            object-fit: cover;
            border-radius: 4px;
            /* 画像パス */
            /* src="tomizawa.jpg" */
            background-color: #333; /* 仮のプレースホルダー */
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
        }

        .about-role {
            display: block;
            color: var(--accent-color);
            font-family: var(--font-heading);
            margin-bottom: 1.5rem;
            font-weight: 600;
        }

        .about-desc {
            color: var(--text-sub);
            margin-bottom: 2rem;
            text-align: justify;
        }

        /* === Philosophy === */
        .philosophy-card {
            max-width: 800px;
            margin: 0 auto;
            padding: 60px 40px;
            background: radial-gradient(circle at center, #222 0%, #000 100%);
            border: 1px solid rgba(255,255,255,0.05);
        }

        .philosophy-english {
            font-size: clamp(2.5rem, 6vw, 4rem);
            line-height: 1.1;
            margin-bottom: 20px;
            background: linear-gradient(to right, #fff, #999);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .philosophy-japanese {
            font-size: 1.2rem;
            color: var(--accent-color);
            margin-bottom: 30px;
            font-weight: 500;
        }

        .philosophy-text {
            color: var(--text-sub);
        }

        /* === Reviews/Results Section === */
        .reviews-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 3rem;
        }
        .review-card {
            background-color: rgba(255,255,255,0.03);
            padding: 30px;
            border-radius: 8px;
            border-top: 3px solid var(--accent-color);
            transition: 0.3s;
        }
        .review-card:hover {
            background-color: rgba(255,255,255,0.06);
        }
        .review-card p {
            font-style: italic;
            color: var(--text-sub);
            line-height: 1.8;
            margin-bottom: 20px;
        }
        .review-card span {
            display: block;
            font-weight: 700;
            color: var(--text-color);
            font-size: 0.9rem;
            text-align: right;
        }

        /* === Flow/Pricing Section === */
        .flow-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
            margin-bottom: 5rem;
        }
        .flow-item {
            text-align: center;
            position: relative;
        }
        /* 矢印のような装飾 (PCのみ) */
        .flow-item:not(:last-child)::after {
            content: '\f054'; /* FontAwesome right arrow */
            font-family: "Font Awesome 6 Free";
            font-weight: 900;
            position: absolute;
            top: 20%;
            right: -25px;
            color: #333;
            font-size: 1.2rem;
        }

        .flow-number {
            font-size: 3.5rem;
            font-family: var(--font-heading);
            color: rgba(64, 224, 208, 0.2); /* アクセントカラーの薄い版 */
            line-height: 1;
            margin-bottom: -20px;
            position: relative;
            z-index: 0;
        }
        .flow-title {
            font-size: 1.1rem;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }
        .flow-item p {
            font-size: 0.9rem;
            color: var(--text-sub);
        }
        
        .pricing-card {
            max-width: 500px;
            margin: 0 auto;
            background-color: var(--bg-secondary);
            padding: 50px 30px;
            border-radius: 12px;
            border: 1px solid var(--accent-color);
            box-shadow: 0 0 30px rgba(64, 224, 208, 0.05);
        }
        .pricing-card h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--accent-color);
        }
        .price {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 10px;
        }
        
        /* === Benefits (ここが抜けていました) === */
        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); /* レスポンシブグリッド */
            gap: 40px;
            margin-top: 40px;
        }

        .benefit-item {
            text-align: center;
            padding: 30px 20px;
            background: rgba(255,255,255,0.02);
            border-radius: 8px;
            transition: 0.3s;
        }

        .benefit-item:hover {
            transform: translateY(-5px);
            background: rgba(255,255,255,0.05);
        }

        .benefit-icon {
            font-size: 2.5rem;
            color: var(--accent-color);
            margin-bottom: 20px;
        }

        .benefit-text {
            font-weight: 600;
            line-height: 1.6;
        }
        
        /* === Footer === */
        .footer {
            padding: 60px 0 30px;
            background-color: #000;
            text-align: center;
            border-top: 1px solid #222;
        }
        .footer-sns {
            margin-bottom: 30px;
        }
        .footer-sns a {
            margin: 0 15px;
            font-size: 1.5rem;
            color: var(--silver);
        }
        .footer-sns a:hover {
            color: var(--accent-color);
        }
        .footer-links {
            margin-bottom: 30px;
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
        }
        .footer-links a {
            font-size: 0.9rem;
            color: var(--text-sub);
        }
        .footer-links a[href^="mailto:"] {
            color: var(--accent-color);
            border-bottom: 1px dashed var(--accent-color);
        }
        .copyright {
            color: #444;
            font-size: 0.8rem;
        }

        /* === Floating CTA === */
        .floating-cta {
            position: fixed;
            right: 30px;
            bottom: 30px;
            z-index: 999;
            background-color: var(--accent-color);
            border-radius: 50%;
            width: 65px;
            height: 65px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 20px rgba(64, 224, 208, 0.4);
            animation: pulse 2s infinite;
            transition: 0.3s;
        }
        .floating-cta:hover {
            transform: scale(1.1);
        }
        .floating-cta i {
            color: #000;
            font-size: 1.8rem;
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(64, 224, 208, 0.7); }
            70% { box-shadow: 0 0 0 15px rgba(64, 224, 208, 0); }
            100% { box-shadow: 0 0 0 0 rgba(64, 224, 208, 0); }
        }

        /* === Responsive Design (修正版) === */
        @media (max-width: 992px) {
            .menu-toggle {
                display: block;
                color: #fff;
            }

            .nav-wrapper {
                position: fixed;
                top: 0;
                right: -100%; /* 初期状態は画面外 */
                width: 75%;
                height: 100vh;
                background: rgba(10, 10, 10, 0.98);
                backdrop-filter: blur(15px);
                flex-direction: column;
                justify-content: center;
                transition: right 0.4s ease-in-out;
                border-left: 1px solid #333;
                z-index: 1000;
                padding: 20px;
            }

            /* ここが重要：activeクラスがついたら画面内へ */
            .nav-wrapper.active {
                right: 0;
            }

            .nav-links {
                flex-direction: column;
                text-align: center;
                margin-bottom: 40px;
            }
            .nav-link-item {
                font-size: 1.2rem;
            }

            .header-actions {
                flex-direction: column;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            .about-img {
                height: 350px;
            }

            .flow-grid {
                grid-template-columns: 1fr; /* スマホでは縦並び */
                gap: 50px;
            }
            .flow-item:not(:last-child)::after {
                content: '\f078'; /* 下矢印に変更 */
                top: auto;
                bottom: -35px;
                right: 50%;
                transform: translateX(50%);
            }
        }
        
        @media (max-width: 576px) {
            .hero-title {
                font-size: 2.2rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .philosophy-english {
                font-size: 2.5rem;
            }
            .floating-cta {
                width: 55px;
                height: 55px;
                right: 20px;
                bottom: 20px;
            }
            .floating-cta i {
                font-size: 1.4rem;
            }
        }
    </style>
</head>
<body>

<header class="header">
    <a href="#home" class="logo">Wellness <span>Designer</span></a>
    
    <div class="menu-toggle" id="mobile-menu">
        <i class="fa-solid fa-bars"></i>
    </div>

    <!-- id="nav-wrapper" を追加 -->
    <div class="nav-wrapper" id="nav-wrapper">
        <nav>
            <ul class="nav-links">
                <li><a href="#about" class="nav-link-item">自己紹介</a></li>
                <li><a href="#philosophy" class="nav-link-item">経営理念</a></li>
                <li><a href="#reviews" class="nav-link-item">実績・声</a></li>
                <li><a href="#flow" class="nav-link-item">サポート</a></li>
                <li><a href="#benefits" class="nav-link-item">学ぶメリット</a></li>
            </ul>
        </nav>
        <div class="header-actions">
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn header-btn">無料相談予約</a>
            <div class="header-sns">
                <a href="#"><i class="fa-brands fa-instagram"></i></a>
                <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
                <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
            </div>
        </div>
    </div>
</header>

<section class="hero" id="home">
    <div class="hero-content fade-in-section">
        <p class="hero-subtitle">WELLNESS DESIGNER</p>
        <h1 class="hero-title">あなたの悩みに寄り添い、<br>内側から健康をデザインする</h1>
        <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">無料カウンセリングを予約する</a>
    </div>
</section>

<section class="section-padding" id="about">
    <div class="container">
        <h2 class="section-title fade-in-section">自己紹介</h2>
        <div class="about-grid">
            <div class="fade-in-section">
                <!-- 画像ファイル名は適切なものに変更してください -->
                <img src="tomizawa.jpg" alt="追川大輝" class="<img width="645" height="1398" alt="IMG_6992 (1)" src="https://github.com/user-attachments/assets/e484dd9a-4241-4961-8c1c-8ddee7a10deb" />
">
            </div>
            <div class="about-text fade-in-section">
                <h3>富沢心乙 <a href="https://profu.link/u/corewellness" target="_blank" style="font-size: 0.6em; color: var(--accent-color); margin-left: 10px; vertical-align: middle; border-bottom: 1px dashed var(--accent-color);">詳細プロフィールへ</a></h3>
                <span class="about-role">Wellness Designer</span>
                <p class="about-desc">
                    もともとパーソナルトレーナーをしていたが、お客様の悩みの種の改善が真の目的だと気づきました。<br><br>
                    表面的な身体作りだけでなく、内面からのアプローチが不可欠であると感じ、ここから私はWellness Designerとして活動していくことにしました。
                </p>
                <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">無料相談を申し込む</a>
            </div>
        </div>
    </div>
</section>

<section class="section-padding" id="philosophy">
    <div class="container">
        <h2 class="section-title fade-in-section">経営理念</h2>
        <div class="philosophy-card text-center fade-in-section">
            <h3 class="philosophy-english">
                True Health<br>True Happiness
            </h3>
            <p class="philosophy-japanese">
                真の健康と真の幸福
            </p>
            <p class="philosophy-text">
                お客様一人ひとりの課題に深く寄り添い、<br>
                持続可能な健康と幸福をデザインし、<br>
                内側から真のウェルネスを実現するサポートを提供します。
            </p>
        </div>
    </div>
</section>

<section class="section-padding" id="reviews">
    <div class="container">
        <h2 class="section-title fade-in-section">実績・お客様の声</h2>
        <div class="reviews-grid">
            <div class="review-card fade-in-section">
                <p>「長年のダイエットの悩みが解消し、食事に対する考え方が根本から変わりました。体の変化だけでなく、心の安定も得られたことに感謝しています。」</p>
                <span>- M.S 様 (30代 女性)</span>
            </div>
            <div class="review-card fade-in-section">
                <p>「パーソナルトレーナー時代の経験に基づいた指導は説得力が違います。食事と運動を両面からサポートしてもらえたことで、目標体重を達成できました。」</p>
                <span>- T.K 様 (40代 男性)</span>
            </div>
            <div class="review-card fade-in-section">
                <p>「以前のトレーナーでは教えてもらえなかった栄養学の知識が深まりました。卒業後も自分で健康をコントロールできる自信がついたのが一番の収穫です。」</p>
                <span>- A.I 様 (20代 女性)</span>
            </div>
        </div>
        <div class="text-center fade-in-section">
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">実績に基づく無料相談はこちら</a>
        </div>
    </div>
</section>

<section class="section-padding" id="flow">
    <div class="container">
        <h2 class="section-title fade-in-section">サポートの流れと料金</h2>
        
        <div class="flow-grid fade-in-section">
            <div class="flow-item">
                <div class="flow-number">1</div>
                <h4 class="flow-title">無料カウンセリング</h4>
                <p>現状の課題や目標をヒアリングし、最適なウェルネスデザインを提案します。</p>
            </div>
            <div class="flow-item">
                <div class="flow-number">2</div>
                <h4 class="flow-title">オーダーメイドプラン</h4>
                <p>栄養・運動・ライフスタイルを統合した、あなただけの専用プランを作成。</p>
            </div>
            <div class="flow-item">
                <div class="flow-number">3</div>
                <h4 class="flow-title">実践と個別指導</h4>
                <p>週次/隔週のセッションで進捗を確認し、メンタル面も含めて細かく指導。</p>
            </div>
            <div class="flow-item">
                <div class="flow-number">4</div>
                <h4 class="flow-title">継続的なサポート</h4>
                <p>プログラム終了後も、自立して継続できるようアフターフォローを提供。</p>
            </div>
        </div>

        <div class="pricing-card text-center fade-in-section">
            <h3>料金プラン (例)</h3>
            <p class="price">¥180,000〜 <span style="font-size: 0.5em; font-weight: 400;">(税込)</span></p>
            <p style="margin-bottom: 20px;"><strong>3ヶ月集中コース</strong></p>
            <p style="margin-top: 15px; color: var(--text-sub); font-size: 0.85rem;">
                ※詳細なプラン内容、6ヶ月・12ヶ月コースについては、無料カウンセリングでお伝えいたします。
            </p>
        </div>
        
        <div class="text-center" style="margin-top: 50px;">
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">今すぐ無料カウンセリングを予約</a>
        </div>
    </div>
</section>

<section class="section-padding" id="benefits">
    <div class="container">
        <h2 class="section-title fade-in-section">Wellness Designerスクールで<br>学ぶメリット</h2>
        
        <div class="benefits-grid">
            <div class="benefit-item fade-in-section">
                <div class="benefit-icon">
                    <i class="fa-solid fa-clipboard-user"></i>
                </div>
                <p class="benefit-text">あなただけの<br>オーダーメイド栄養プラン</p>
            </div>
            
            <div class="benefit-item fade-in-section">
                <div class="benefit-icon">
                    <i class="fa-solid fa-seedling"></i>
                </div>
                <p class="benefit-text">体と心の健康は<br>栄養と生活習慣から変わる</p>
            </div>
            
            <div class="benefit-item fade-in-section">
                <div class="benefit-icon">
                    <i class="fa-solid fa-infinity"></i>
                </div>
                <p class="benefit-text">一生モノの知識と<br>継続できる実践力</p>
            </div>
            
            <div class="benefit-item fade-in-section">
                <div class="benefit-icon">
                    <i class="fa-solid fa-handshake-angle"></i>
                </div>
                <p class="benefit-text">個別サポートで<br>確実な目標達成</p>
            </div>
        </div>
    </div>
</section>

<footer class="footer">
    <div class="container">
        <div class="footer-sns">
            <a href="#"><i class="fa-brands fa-instagram"></i></a>
            <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
            <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
        </div>
        <div class="footer-links">
            <a href="#">プライバシーポリシー</a>
            <a href="mailto:Happiness.seeker2@gmail.com">Happiness.seeker2@gmail.com</a>
        </div>
        <p class="copyright">© 2023 Wellness Designer. All rights reserved.</p>
    </div>
</footer>

<a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="floating-cta">
    <i class="fa-solid fa-calendar-check"></i>
</a>

<script>
    // === スクロールアニメーション (Intersection Observer) ===
    document.addEventListener('DOMContentLoaded', () => {
        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.1 
        };

        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                    observer.unobserve(entry.target);
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
        
        // アイコンの切り替え
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
