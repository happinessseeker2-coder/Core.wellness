<head>
    <!-- 以下にプロジェクト説明や使い方を続けてください -->    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness Designer | Daiki Oikawa & munetsugu Tomizawa</title>
    <meta name="description" content="本質から整える健康を。追川大輝と富沢心乙による、経営者・プロフェッショナルのためのウェルネスプログラム。">

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&family=Noto+Sans+JP:wght@400;500;700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* === CSS Variables === */
        :root {
            /* 写真の夕日/朝日に合わせた、温かみのあるカラーパレット */
            --bg-black: #1c1c1a;       /* 墨色 */
            --bg-dark-gray: #2a2a28;   /* チャコール */
            --bg-light: #f2f0eb;       /* 生成り色 */
            --text-white: #f7f7f4;     
            --text-black: #3a3a38;     
            --text-sub: #9e9e9b;       
            --accent: #bfa588;         /* ブロンズゴールド */
            --accent-hover: #a88f72;   
            --gradient: linear-gradient(135deg, #1c1c1a 0%, #333330 100%);
            --header-h: 70px;![代替テキスト](./images/photo.jpg "PH1")}

        /* === Reset & Base === */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }

        body {
            background-color: var(--bg-black);
            color: var(--text-white);
            font-family: 'Noto Sans JP', sans-serif;
            line-height: 1.9;
            letter-spacing: 0.05em;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        h1, h2, h3, h4 { font-family: 'Montserrat', sans-serif; letter-spacing: 0.08em; }
        a { text-decoration: none; color: inherit; transition: 0.3s; }
        img { width: 100%; display: block; }
        ul { list-style: none; }
        p { margin-bottom: 1.5rem; }

        /* === Layout Utilities === */
        .container {
            width: 90%; max-width: 1000px; margin: 0 auto; padding: 0 20px;
            position: relative; z-index: 2;
        }
        .section-padding { padding: 100px 0; }
        
        .bg-black { background-color: var(--bg-black); }
        .bg-dark { background-color: var(--bg-dark-gray); }
        .bg-light { background-color: var(--bg-light); color: var(--text-black); }
        .bg-gradient { background: var(--gradient); }

        /* === Components === */
        .btn {
            display: inline-block; padding: 14px 40px; 
            background-color: var(--accent); color: #1c1c1a;
            font-weight: 700; font-size: 0.95rem; border-radius: 50px; 
            letter-spacing: 0.05em; transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(191, 165, 136, 0.3);
            text-align: center;
        }
        .btn:hover { 
            background-color: var(--accent-hover); 
            transform: translateY(-2px); 
            box-shadow: 0 6px 20px rgba(191, 165, 136, 0.5); 
        }
        .btn-outline {
            background: transparent; border: 1px solid var(--accent); color: var(--accent);
        }
        .btn-outline:hover { background: var(--accent); color: #1c1c1a; }

        .section-title { 
            font-size: clamp(1.8rem, 4vw, 2.4rem); margin-bottom: 60px; 
            text-align: center; position: relative; color: inherit;
        }
        .section-title::after { 
            content: ''; display: block; width: 50px; height: 3px; 
            background: var(--accent); margin: 20px auto 0; 
        }

        /* Fixed CTA */
        .fixed-cta {
            position: fixed; bottom: 30px; right: 30px; z-index: 990;
            background: var(--accent); color: #1c1c1a;
            width: 60px; height: 60px; border-radius: 50%;
            display: flex; justify-content: center; align-items: center;
            box-shadow: 0 5px 20px rgba(191, 165, 136, 0.4);
            font-size: 1.5rem; transition: 0.3s;
        }
        .fixed-cta:hover { transform: scale(1.1); }
        @media (min-width: 768px) {
            .fixed-cta {
                width: auto; height: auto; padding: 12px 30px; border-radius: 50px; font-size: 1rem; font-weight: 700;
            }
            .fixed-cta i { margin-right: 8px; }
            .fixed-cta::after { content: '無料相談'; }
        }

        /* === Header === */
        .header {
            position: fixed; top: 0; left: 0; width: 100%; height: var(--header-h);
            display: flex; justify-content: space-between; align-items: center;
            padding: 0 5%; z-index: 1000;
            background: rgba(28, 28, 26, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .logo { font-size: 1.4rem; font-weight: 700; color: var(--text-white); }
        .logo span { color: var(--accent); }

        .menu-toggle { display: none; font-size: 1.5rem; color: var(--text-white); cursor: pointer; z-index: 1001; }
        
        .nav-menu { display: flex; gap: 30px; }
        .nav-link { font-size: 0.9rem; font-weight: 500; position: relative; }
        .nav-link:hover { color: var(--accent); }

        @media (max-width: 900px) {
            .menu-toggle { display: block; }
            .nav-menu {
                position: fixed; top: 0; right: -100%;
                width: 70%; height: 100vh;
                background: rgba(28, 28, 26, 0.95);
                backdrop-filter: blur(15px);
                flex-direction: column; justify-content: center; align-items: center;
                gap: 40px; transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1);
                box-shadow: -10px 0 30px rgba(0,0,0,0.5);
            }
            .nav-menu.active { right: 0; }
            .nav-link { font-size: 1.2rem; }
        }

        /* === Hero Section (自然背景設定) === */
        .hero {
            height: 100vh; position: relative; display: flex; align-items: center; justify-content: center; text-align: center;
            background-image: url('hero.jpg'); /* ここで画像を指定 */
            background-size: cover; background-position: center;
            background-color: var(--bg-black);
        }
        .hero::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            /* 写真が明るいため、文字が見えるように少し濃いめのグラデーションをかけています */
            background: linear-gradient(to bottom, rgba(0,0,0,0.4), rgba(28,28,26,0.95));
        }
        .hero-content { position: relative; z-index: 1; padding: 0 20px; max-width: 800px; }
        .hero-sub { color: var(--accent); font-weight: 600; letter-spacing: 0.2em; display: block; margin-bottom: 20px; text-transform: uppercase; }
        .hero-title { 
            font-size: clamp(2rem, 5vw, 3.8rem); line-height: 1.4; font-weight: 700; margin-bottom: 30px;
            text-shadow: 0 5px 20px rgba(0,0,0,0.9); /* 文字の影を強化して読みやすく */
        }
        
        /* === Profile Section === */
        .person-card {
            display: grid; grid-template-columns: 0.8fr 1.2fr; gap: 50px; align-items: center; margin-bottom: 80px;
        }
        .about-img img { 
            height: 450px; object-fit: cover; border-radius: 4px; 
            filter: grayscale(20%); transition: 0.5s; 
            background-color: #222;
        }
        .about-img:hover img { filter: grayscale(0%); }
        .role { color: var(--accent); font-size: 0.85rem; font-weight: 700; letter-spacing: 0.15em; display: block; margin-bottom: 15px; }
        .person-card h3 { font-size: 1.8rem; margin-bottom: 20px; }
        
        .person-card.reverse { grid-template-columns: 1.2fr 0.8fr; }
        .person-card.reverse .about-img { order: 2; }
        .person-card.reverse .about-text { order: 1; }

        @media (max-width: 768px) {
            .person-card, .person-card.reverse { grid-template-columns: 1fr; gap: 30px; }
            .person-card.reverse .about-img { order: 0; }
            .about-img img { height: 350px; }
        }

        /* === Philosophy === */
        .philosophy-text { text-align: center; max-width: 700px; margin: 0 auto; font-size: 1.1rem; }
        .philosophy-text strong { color: var(--accent); font-weight: 500; }

        /* === Merit === */
        .merit-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
        .merit-card {
            background: var(--text-white); padding: 40px 30px; border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05); text-align: center;
        }
        .merit-icon { font-size: 2.2rem; color: var(--accent); margin-bottom: 20px; }
        .merit-card h3 { font-size: 1.2rem; margin-bottom: 15px; color: var(--text-black); }
        .merit-card p { font-size: 0.9rem; color: #666; line-height: 1.8; margin-bottom: 0; }

        /* === Voices === */
        .voice-card {
            background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.08);
            padding: 40px; border-radius: 8px; max-width: 800px; margin: 0 auto;
        }
        .voice-header { display: flex; align-items: center; gap: 20px; margin-bottom: 20px; }
        .voice-avt { 
            width: 60px; height: 60px; background: #333; border-radius: 50%; 
            display: flex; align-items: center; justify-content: center; color: #fff;
        }
        .voice-meta h4 { font-size: 1.1rem; margin-bottom: 5px; }
        .voice-meta span { color: var(--text-sub); font-size: 0.85rem; }
        .voice-body { font-style: italic; color: var(--text-white); opacity: 0.9; }

        /* === Flow & Price === */
        .flow-step { 
            border-left: 2px solid var(--accent); padding-left: 30px; position: relative; margin-bottom: 40px; 
            max-width: 600px; margin-left: auto; margin-right: auto;
        }
        .flow-step::before {
            content: ''; position: absolute; left: -9px; top: 0; width: 16px; height: 16px; 
            background: var(--accent); border-radius: 50%;
        }
        .flow-step h4 { font-size: 1.2rem; margin-bottom: 10px; color: var(--text-white); }
        
        .price-container { display: flex; justify-content: center; gap: 30px; flex-wrap: wrap; }
        .price-card {
            background: var(--text-white); color: var(--text-black); padding: 40px; border-radius: 16px; text-align: center;
            flex: 1; min-width: 300px; max-width: 450px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.08); border: 1px solid #eee;
            position: relative; display: flex; flex-direction: column;
        }
        .price-card.advance { border: 2px solid var(--accent); transform: scale(1.05); z-index: 10; }
        @media (max-width: 800px) { .price-card.advance { transform: scale(1); } }

        .price-tag { 
            display: inline-block; background: var(--text-black); color: var(--text-white); padding: 5px 15px; 
            border-radius: 20px; font-size: 0.8rem; margin-bottom: 20px; 
        }
        .price-card.advance .price-tag { background: var(--accent); color: var(--bg-black); font-weight: bold; }

        .price-amount { font-size: 2.5rem; font-weight: 700; font-family: 'Montserrat', sans-serif; color: var(--text-black); }
        .price-sub { font-size: 0.9rem; color: #777; margin-bottom: 30px; display: block; }
        .price-list { text-align: left; margin-bottom: 40px; padding: 0 10px; flex-grow: 1; }
        .price-list li { margin-bottom: 12px; border-bottom: 1px solid #eee; padding-bottom: 8px; font-size: 0.95rem; }
        .price-list i { color: var(--accent); margin-right: 10px; }

        /* === Footer === */
        .footer { background: var(--bg-black); padding: 80px 0 30px; border-top: 1px solid rgba(255,255,255,0.05); text-align: center; }
        .footer-sns a { color: var(--text-sub); font-size: 1.5rem; margin: 0 15px; }
        .footer-sns a:hover { color: var(--accent); }
        .copyright { margin-top: 40px; color: var(--text-sub); font-size: 0.75rem; }

        /* Animation */
        .fade-in { opacity: 0; transform: translateY(30px); transition: 1s ease; }
        .fade-in.visible { opacity: 1; transform: translateY(0); }

    </style>
</head>
<body>

    <!-- Floating CTA -->
    <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="fixed-cta"><i class="far fa-envelope"></i></a>

    <!-- Header -->
    <header class="header">
        <a href="#" class="logo">Wellness<span>Designer</span></a>
        
        <div class="menu-toggle" id="menuToggle">
            <i class="fas fa-bars"></i>
        </div>

        <nav class="nav-menu" id="navMenu">
            <a href="#about" class="nav-link">About</a>
            <a href="#merit" class="nav-link">Concept</a>
            <a href="#voice" class="nav-link">Voices</a>
            <a href="#price" class="nav-link">Plan</a>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="nav-link">Contact</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <span class="hero-sub fade-in">Holistic Wellness Program</span>
            <h1 class="hero-title fade-in">
                あなたの体と心の<br>
                根本にアプローチし<br>
                “本質から整える健康” をつくります。
            </h1>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn fade-in">無料カウンセリングを予約</a>
        </div>
    </section>

    <!-- Profile Section (Dark) -->
    <section id="about" class="section-padding bg-dark">
        <div class="container">
            <h2 class="section-title fade-in">Professionals</h2>
            
            <div class="person-card fade-in">
                <div class="about-img">
                    <img src="profile1.jpg" alt="Daiki Oikawa">
                </div>
                <div class="about-text">
                    <h3>追川 大輝</h3>
                    <span class="role">BODY ARCHITECT</span>
                    <p>
                        「なぜその不調が起きるのか？」を解剖学的に紐解き、感覚ではなく論理で身体を再構築します。
                        ビジネスパフォーマンスを最大化させるための、疲れない姿勢と機能的な動作を獲得させます。
                    </p>
                </div>
            </div>

            <div class="person-card reverse fade-in">
                <div class="about-img">
                    <img src="profile2.jpg" alt="Kokona Tomizawa">
                </div>
                <div class="about-text">
                    <h3>富沢 心乙</h3>
                    <span class="role">MIND & LIFE STYLIST</span>
                    <p>
                        栄養学とメンタルヘルスを融合。一時的なダイエットではなく、
                        「何を食べるか」「どう休息するか」という生活習慣の根本からアプローチし、
                        内側から溢れ出るエネルギーを引き出します。
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Philosophy -->
    <section class="section-padding bg-gradient">
        <div class="container fade-in">
            <h2 class="section-title">Philosophy</h2>
            <div class="philosophy-text">
                <p>
                    私たちが提供するのは、単なるトレーニングや食事指導ではありません。<br>
                    それは、<strong>生涯の資産となる「自己管理能力」</strong>です。
                </p>
                <p>
                    都市生活の中で乱れがちな自律神経を整え、<br>
                    本来の自分を取り戻すための時間を、私たちがデザインします。
                </p>
            </div>
        </div>
    </section>

    <!-- Merit -->
    <section id="merit" class="section-padding bg-light">
        <div class="container">
            <h2 class="section-title fade-in">Our Value</h2>
            <div class="merit-grid">
                <div class="merit-card fade-in">
                    <div class="merit-icon"><i class="fas fa-cubes"></i></div>
                    <h3>Dual Approach</h3>
                    <p>身体のプロと心のプロ。二つの視点から多角的に分析し、最短距離で理想の状態へ導きます。</p>
                </div>
                <div class="merit-card fade-in">
                    <div class="merit-icon"><i class="fas fa-fingerprint"></i></div>
                    <h3>Hyper Personalized</h3>
                    <p>マニュアルは存在しません。あなたのライフスタイル、骨格、嗜好に合わせた完全オーダーメイド。</p>
                </div>
                <div class="merit-card fade-in">
                    <div class="merit-icon"><i class="fas fa-infinity"></i></div>
                    <h3>Sustainable</h3>
                    <p>一過性の結果ではなく、プログラム終了後も一生続く「習慣」を定着させます。</p>
                </div>
            </div>
            <div class="text-center" style="margin-top: 50px;">
                <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">詳細を聞いてみる</a>
            </div>
        </div>
    </section>

    <!-- Voices -->
    <section id="voice" class="section-padding bg-black">
        <div class="container">
            <h2 class="section-title fade-in">Client Voices</h2>
            <div class="voice-card fade-in">
                <div class="voice-header">
                    <div class="voice-avt"><i class="fas fa-user"></i></div>
                    <div class="voice-meta">
                        <h4>M.S 様（28歳）</h4>
                        <span>ピラティストレーナー / 女性</span>
                    </div>
                </div>
                <div class="voice-body">
                    <p>
                        「同業として身体の使い方は分かっているつもりでしたが、追川さんのロジカルな指導には目から鱗でした。
                        自分の癖を根本から修正できたことで、クライアントへの指導の質も上がりました。
                        また富沢さんの食事指導のおかげで、忙しい時期のメンタルブレも減り、仕事に集中できています。」
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Price -->
    <section id="price" class="section-padding bg-dark">
        <div class="container">
            <h2 class="section-title fade-in">Flow & Price</h2>
            
            <div style="margin-bottom: 80px;" class="fade-in">
                <div class="flow-step">
                    <h4>Step 1. カウンセリング</h4>
                    <p style="font-size: 0.9rem; color: var(--text-sub);">現状の課題と目標をヒアリングし、プランを策定します。</p>
                </div>
                <div class="flow-step">
                    <h4>Step 2. プログラム開始</h4>
                    <p style="font-size: 0.9rem; color: var(--text-sub);">週1回のセッションと、毎日のLINEサポートで伴走します。</p>
                </div>
                <div class="flow-step">
                    <h4>Step 3. 卒業・自走</h4>
                    <p style="font-size: 0.9rem; color: var(--text-sub);">ご自身でコントロールできる状態を目指し、卒業となります。</p>
                </div>
            </div>

            <div class="price-container fade-in">
                
                <div class="price-card">
                    <span class="price-tag">Normal Plan</span>
                    <div class="price-amount">200,000<span style="font-size:1rem; font-weight:400;">yen〜</span></div>
                    <span class="price-sub">スタンダードサポート</span>
                    <ul class="price-list">
                        <li><i class="fas fa-check"></i> パーソナルトレーニング</li>
                        <li><i class="fas fa-check"></i> 食事・栄養アドバイス</li>
                        <li><i class="fas fa-check"></i> LINE相談サポート</li>
                    </ul>
                    <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">無料相談に申し込む</a>
                </div>

                <div class="price-card advance">
                    <span class="price-tag">Advance Plan</span>
                    <div class="price-amount">300,000<span style="font-size:1rem; font-weight:400;">yen〜</span></div>
                    <span class="price-sub">3ヶ月集中トータルサポート</span>
                    <ul class="price-list">
                        <li><i class="fas fa-check"></i> パーソナルトレーニング (全12回)</li>
                        <li><i class="fas fa-check"></i> 毎日の食事・栄養徹底管理</li>
                        <li><i class="fas fa-check"></i> マインドセットコーチング</li>
                        <li><i class="fas fa-check"></i> LINE相談 無制限</li>
                    </ul>
                    <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">無料相談に申し込む</a>
                </div>

            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact" class="footer">
        <div class="container fade-in">
            <h2 class="section-title" style="margin-bottom: 30px;">Contact</h2>
            <p style="margin-bottom: 30px; color: var(--text-sub);">
                まずは無料カウンセリングにて、あなたのお悩みをお聞かせください。<br>
                無理な勧誘は一切いたしません。
            </p>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn btn-outline">フォームから問い合わせる</a>
            
            <div class="footer-sns" style="margin-top: 50px;">
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-line"></i></a>
            </div>
            <p class="copyright">&copy; 2024 Wellness Designer. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        const menuToggle = document.getElementById('menuToggle');
        const navMenu = document.getElementById('navMenu');
        const navLinks = document.querySelectorAll('.nav-link');

        menuToggle.addEventListener('click', () => {
            navMenu.classList.toggle('active');
            const icon = menuToggle.querySelector('i');
            icon.classList.toggle('fa-bars');
            icon.classList.toggle('fa-times');
        });

        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
                menuToggle.querySelector('i').classList.add('fa-bars');
                menuToggle.querySelector('i').classList.remove('fa-times');
            });
        });

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
    </script>
</body>
</html># Wellness Designer

![チーム写真](./images/hero.jpg "チーム写真")

本質から整える健康を。追川大輝と富沢心乙による、経営者・プロフェッショナルのためのウェルネスプログラム。

<!-- 以下にプロジェクト説明や使い方を続けてください -->
