

<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness Designer | For Pilates Instructors</title>
    <meta name="description" content="ピラティスインストラクターのための栄養・ウェルネスプログラム。スキル向上と顧客獲得、そして自身の健康を叶える。">

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&family=Noto+Sans+JP:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* === CSS Variables (New Palette) === */
        :root {
            /* ベース：深遠・安定・知性 */
            --bg-base: #1A1F1D; 
            --bg-card: #232926; /* ベースより少し明るい、カード用 */
            
            /* テキスト：清潔・明瞭（可読性重視） */
            --text-main: #E6E6E6;
            --text-sub: #B0B5B2; /* 少し緑がかったグレー */
            --text-dark: #1A1F1D; /* ゴールド背景用の濃い文字 */

            /* アクセント（金）：富・成功・高品質 */
            --gold-gradient: linear-gradient(135deg, #BF953F 0%, #FCF6BA 50%, #B38728 100%);
            --gold-text: #D4AF37; /* 文字として使う場合の単色ゴールド */

            /* サブアクセント（セージグリーン）：調和・自然 */
            --sage-green: #5D7266;
            
            --header-h: 70px;
        }

        /* === Reset & Base === */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }

        body {
            background-color: var(--bg-base);
            color: var(--text-main);
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
        
        /* 背景クラスの再定義 */
        .bg-base { background-color: var(--bg-base); }
        .bg-card { background-color: var(--bg-card); }
        
        /* === Components === */
        
        /* Gold Button (CTA) */
        .btn {
            display: inline-block; padding: 16px 45px; 
            background: var(--gold-gradient); 
            color: var(--text-dark); /* 金背景には黒文字で可読性と高級感を */
            font-weight: 700; font-size: 1rem; border-radius: 50px; 
            letter-spacing: 0.05em; transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(191, 149, 63, 0.3);
            text-align: center; border: none; position: relative; overflow: hidden;
        }
        .btn:hover { 
            transform: translateY(-2px); 
            box-shadow: 0 6px 25px rgba(191, 149, 63, 0.5); 
            filter: brightness(1.1); /* ホバー時に少し輝く */
        }

        /* Outline Button (gold-gradient)*/
        .btn-outline {
            background: transparent; border: 1px solid var(--sage-green); color: var(--text-main);
            padding: 14px 40px; font-weight: 700; border-radius: 50px;
        }
        .btn-outline:hover { background: var(--sage-green); color: var(--text-main); }

        /* Section Titles */
        .section-title { 
            font-size: clamp(1.8rem, 4vw, 2.4rem); margin-bottom: 60px; 
            text-align: center; position: relative; color: var(--text-main);
        }
        /* 金色のアンダーライン */
        .section-title::after { 
            content: ''; display: block; width: 60px; height: 3px; 
            background: var(--gold-gradient); margin: 20px auto 0; 
        }

        /* Fixed CTA */
        .fixed-cta {
            position: fixed; bottom: 30px; right: 30px; z-index: 990;
            background: var(--gold-gradient); color: var(--text-dark);
            width: 60px; height: 60px; border-radius: 50%;
            display: flex; justify-content: center; align-items: center;
            box-shadow: 0 5px 20px rgba(191, 149, 63, 0.4);
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
            background: rgba(26, 31, 29, 0.9); /* Base color semi-transparent */
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .logo { font-size: 1.4rem; font-weight: 700; color: var(--text-main); }
        .logo span { color: var(--sage-green); /* アクセントにセージグリーン */ }

        .menu-toggle { display: none; font-size: 1.5rem; color: var(--text-main); cursor: pointer; z-index: 1001; }
        
        .nav-menu { display: flex; gap: 30px; }
        .nav-link { font-size: 0.9rem; font-weight: 500; position: relative; color: var(--text-main); }
        .nav-link:hover { color: var(--gold-text); }

        @media (max-width: 900px) {
            .menu-toggle { display: block; }
            .nav-menu {
                position: fixed; top: 0; right: -100%;
                width: 70%; height: 100vh;
                background: rgba(26, 31, 29, 0.98);
                backdrop-filter: blur(15px);
                flex-direction: column; justify-content: center; align-items: center;
                gap: 40px; transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1);
                box-shadow: -10px 0 30px rgba(0,0,0,0.5);
                border-left: 1px solid var(--sage-green);
            }
            .nav-menu.active { right: 0; }
            .nav-link { font-size: 1.2rem; }
        }

        /* === Hero Section === */
        .hero {
            height: 100vh; position: relative; display: flex; align-items: center; justify-content: center; text-align: center;
            background-image: url('hero.jpg'); 
            background-size: cover; background-position: center;
            background-color: var(--bg-base);
        }
        .hero::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            /* Deep Green Black Gradient Overlay */
            background: linear-gradient(to bottom, rgba(26, 31, 29, 0.3), rgba(26, 31, 29, 0.95));
        }
        .hero-content { position: relative; z-index: 1; padding: 0 20px; max-width: 900px; }
        
        .hero-sub { 
            color: var(--sage-green); /* 自然・調和 */
            font-weight: 600; letter-spacing: 0.15em; display: block; margin-bottom: 20px; font-size: 1.1rem; 
            text-transform: uppercase;
        }
        .hero-title { 
            font-size: clamp(1.6rem, 4vw, 2.8rem); line-height: 1.7; font-weight: 700; margin-bottom: 40px;
            text-shadow: 0 10px 30px rgba(0,0,0,0.8); text-align: left;
        }
        .hero-title span { display: block; margin-bottom: 15px; }
        
        /* === Profile Section === */
        .person-card {
            display: grid; grid-template-columns: 0.8fr 1.2fr; gap: 50px; align-items: center; margin-bottom: 80px;
            background: rgba(255,255,255,0.02); /* わずかに背景を入れてカード化 */
            padding: 30px; border-radius: 12px; border: 1px solid rgba(93, 114, 102, 0.2); /* セージグリーンの薄い枠 */
        }
        .about-img img { 
            height: 450px; object-fit: cover; border-radius: 4px; 
            filter: grayscale(20%); transition: 0.5s; 
            background-color: #222;
        }
        .about-img:hover img { filter: grayscale(0%); }
        .role { color: var(--sage-green); font-size: 0.85rem; font-weight: 700; letter-spacing: 0.15em; display: block; margin-bottom: 15px; }
        .person-card h3 { font-size: 1.8rem; margin-bottom: 20px; color: var(--gold-text); } /* 名前を金文字に */
        
        .person-card.reverse { grid-template-columns: 1.2fr 0.8fr; }
        .person-card.reverse .about-img { order: 2; }
        .person-card.reverse .about-text { order: 1; }

        @media (max-width: 768px) {
            .person-card, .person-card.reverse { grid-template-columns: 1fr; gap: 30px; }
            .person-card.reverse .about-img { order: 0; }
            .about-img img { height: 350px; }
            .hero-title { text-align: center; }
        }

        /* === Philosophy === */
        .philosophy-text { text-align: center; max-width: 700px; margin: 0 auto; font-size: 1.1rem; }
        .philosophy-text strong { 
            background: var(--gold-gradient); 
            -webkit-background-clip: text; 
            -webkit-text-fill-color: transparent;
            font-weight: 700; 
        }

        /* === Merit (Detail Section) === */
        .merit-layout {
            display: grid; grid-template-columns: 1fr 1fr; gap: 50px; align-items: center;
        }
        .merit-img img {
            width: 100%; height: 400px; object-fit: cover; border-radius: 12px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3); border: 1px solid var(--sage-green);
        }
        .merit-list { display: flex; flex-direction: column; gap: 30px; }
        .merit-item { 
            display: flex; gap: 20px; align-items: flex-start; 
            padding: 20px; border-radius: 8px;
            transition: 0.3s;
        }
        .merit-item:hover { background: rgba(93, 114, 102, 0.1); } /* セージグリーンの背景ホバー */
        
        .merit-icon { 
            width: 60px; height: 60px; 
            background: var(--bg-card); /* カード色 */
            border: 1px solid var(--sage-green); /* セージグリーンの枠 */
            border-radius: 50%; 
            display: flex; align-items: center; justify-content: center;
            font-size: 1.5rem; color: var(--sage-green); flex-shrink: 0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        .merit-content h3 { font-size: 1.2rem; margin-bottom: 10px; color: var(--text-main); }
        .merit-content p { font-size: 0.95rem; color: var(--text-sub); line-height: 1.7; margin-bottom: 0; }

        @media (max-width: 900px) {
            .merit-layout { grid-template-columns: 1fr; }
            .merit-img { order: 2; }
            .merit-list { order: 1; }
        }

        /* === Voices (Grid Layout) === */
        .voices-grid {
            display: grid; 
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }
        .voice-card {
            background: var(--bg-card); 
            border: 1px solid rgba(255,255,255,0.05); /* 控えめな枠線 */
            padding: 30px; border-radius: 8px; height: 100%;
            transition: 0.3s;
        }
        .voice-card:hover { border-color: var(--sage-green); }

        .voice-header { display: flex; align-items: center; gap: 15px; margin-bottom: 15px; }
        .voice-avt { 
            width: 50px; height: 50px; background: #111; border-radius: 50%; 
            display: flex; align-items: center; justify-content: center; color: var(--sage-green);
            border: 1px solid var(--sage-green);
        }
        .voice-meta h4 { font-size: 1rem; margin-bottom: 3px; color: var(--text-main); }
        .voice-meta span { color: var(--text-sub); font-size: 0.8rem; }
        .voice-body { font-style: italic; color: var(--text-main); opacity: 0.8; font-size: 0.9rem; }

        /* === Flow & Price === */
        .flow-step { 
            border-left: 3px solid var(--sage-green); padding-left: 30px; position: relative; margin-bottom: 40px; 
            max-width: 600px; margin-left: auto; margin-right: auto;
        }
        .flow-step::before {
            content: ''; position: absolute; left: -10px; top: 0; width: 16px; height: 16px; 
            background: var(--sage-green); border-radius: 50%;
            border: 2px solid var(--bg-base); /* 穴あき効果 */
        }
        .flow-step h4 { font-size: 1.2rem; margin-bottom: 10px; color: var(--gold-text); }
        
        .price-container { display: flex; justify-content: center; gap: 30px; flex-wrap: wrap; }
        .price-card {
            background: var(--bg-card); color: var(--text-main); padding: 40px; border-radius: 16px; text-align: center;
            flex: 1; min-width: 300px; max-width: 450px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2); border: 1px solid rgba(255,255,255,0.05);
            position: relative; display: flex; flex-direction: column;
        }
        /* アドバンスプラン（金枠） */
        .price-card.advance { 
            border: 2px solid transparent;
            background-image: linear-gradient(var(--bg-card), var(--bg-card)), var(--gold-gradient);
            background-origin: border-box;
            background-clip: content-box, border-box;
            transform: scale(1.03); z-index: 10; 
        }
        @media (max-width: 800px) { .price-card.advance { transform: scale(1); } }

        .price-tag { 
            display: inline-block; background: var(--sage-green); color: #fff; padding: 5px 15px; 
            border-radius: 20px; font-size: 0.8rem; margin-bottom: 20px; 
        }
        .price-card.advance .price-tag { background: var(--gold-gradient); color: var(--text-dark); font-weight: bold; }

        .price-name { font-size: 1.4rem; font-weight: 700; margin-bottom: 10px; color: var(--text-main); }
        
        .price-amount { 
            font-size: 2.2rem; font-weight: 700; font-family: 'Montserrat', sans-serif; 
            margin-bottom: 20px;
            /* 数字を金グラデーションに */
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .price-list { text-align: left; margin-bottom: 40px; padding: 0 10px; flex-grow: 1; }
        .price-list li { margin-bottom: 12px; border-bottom: 1px solid rgba(255,255,255,0.05); padding-bottom: 8px; font-size: 0.95rem; color: var(--text-sub); }
        .price-list i { color: var(--sage-green); margin-right: 10px; }
        .price-card.advance .price-list i { color: var(--gold-text); } /* アドバンスのチェックは金 */

        /* === Footer === */
        .footer { background: #111; padding: 80px 0 30px; border-top: 1px solid var(--sage-green); text-align: center; }
        .footer-sns a { color: var(--text-sub); font-size: 1.8rem; margin: 0 15px; transition: 0.3s; }
        .footer-sns a:hover { color: var(--gold-text); }
        .copyright { margin-top: 40px; color: var(--text-sub); font-size: 0.75rem; }

        /* Animation */
        .fade-in { opacity: 0; transform: translateY(30px); transition: 1s ease; }
        .fade-in.visible { opacity: 1; transform: translateY(0); }

    </style>
</head>
<body>

   <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="fixed-cta"><i class="far fa-envelope"></i></a>

<header class="header">
    <a href="#" class="logo">Wellness<span>Designer</span></a>
    
    <div class="menu-toggle" id="menuToggle">
        <i class="fas fa-bars"></i>
    </div>

    <nav class="nav-menu" id="navMenu">
        <a href="#about" class="nav-link">About</a>
        <a href="#merit" class="nav-link">Service</a>
        <a href="#voice" class="nav-link">Voices</a>
        <a href="#price" class="nav-link">Plan</a>
        <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="nav-link">Contact</a>
    </nav>
</header>

<section class="hero">
    <div class="hero-content" style="text-align: center;">
        
        <span class="hero-sub fade-in" style="display: inline-block;">For Pilates Instructors</span>
        
        <h1 class="hero-title fade-in" style="text-align: center;">
            ピラティスインストラクターの皆様へ。<br><br>
            <span style="display: inline-block; border: 2px solid #c5a47e; padding: 30px; margin-top: 10px; font-size: 0.6em; font-weight: 600; line-height: 1.8; color: var(--text-main);">
                3ヶ月で、栄養の基礎から“本質の応用”まで確実に身につく<br>
                点の知識ではなく、何を選び、なぜ選ぶかまで説明できるインストラクターへ<br>
                動きと栄養を一貫して導ける力を手に入れる<br>
                より多くの顧客を手に入れましょう。
            </span>
        </h1>

        <div style="margin-top: 30px;">
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn fade-in">
                無料カウンセリングを予約
            </a>
        </div>

    </div>
</section>
       
    <!-- Profile Section -->
    <section id="about" class="section-padding bg-base">
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
                        解剖学に基づいたロジカルなアプローチで、インストラクター自身の身体の使い方の癖を修正。
                        「指導者としての説得力」を持つ身体作りと、長く働き続けるためのメンテナンス法を伝授します。
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
                        クライアントへの食事アドバイスに自信はありますか？
                        栄養学に基づいた指導法を習得し、あなた自身の内面も整えることで、
                        選ばれるインストラクターへと導きます。
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Philosophy -->
    <section class="section-padding bg-card">
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

    <!-- Merit (Detail Section) -->
    <section id="merit" class="section-padding bg-base">
        <div class="container">
            <h2 class="section-title fade-in">Our Value</h2>
            
            <div class="merit-layout fade-in">
                <!-- Detailed List -->
                <div class="merit-list">
                    <div class="merit-item">
                        <div class="merit-icon"><i class="fas fa-utensils"></i></div>
                        <div class="merit-content">
                            <h3>Nutritional Expertise</h3>
                            <p>
                                <strong>「食事指導力」の向上</strong><br>
                                運動だけでは解決できないクライアントの悩みに、栄養面からアプローチ可能に。ダイエットや体質改善の成果が出やすくなり、信頼度が向上します。
                            </p>
                        </div>
                    </div>
                    <div class="merit-item">
                        <div class="merit-icon"><i class="fas fa-user-plus"></i></div>
                        <div class="merit-content">
                            <h3>Client Acquisition</h3>
                            <p>
                                <strong>差別化による集客アップ</strong><br>
                                ピラティス×栄養指導のトータルサポートができるインストラクターは希少です。高単価でも選ばれる強みとなります。
                            </p>
                        </div>
                    </div>
                    <div class="merit-item">
                        <div class="merit-icon"><i class="fas fa-heart"></i></div>
                        <div class="merit-content">
                            <h3>Self Wellness</h3>
                            <p>
                                <strong>あなた自身の健康美</strong><br>
                                忙しいレッスンの合間でも実践できる栄養管理法を習得。疲れにくい身体と安定したメンタルを手に入れ、長く活躍できる基盤を作ります。
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Nutrition Image -->
                <div class="merit-img">
                    <img src="nutrition.jpg" alt="栄養指導と健康的な食事のイメージ" style="background-color: var(--bg-card);">
                </div>
            </div>

            <div class="text-center" style="margin-top: 60px;">
                <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">詳細を聞いてみる</a>
            </div>
        </div>
    </section>

    <!-- Voices (Grid Layout) -->
    <section id="voice" class="section-padding bg-card">
        <div class="container">
            <h2 class="section-title fade-in">Client Voices</h2>
            <div class="voices-grid fade-in">
                
                <!-- Client 1 -->
                <div class="voice-card">
                    <div class="voice-header">
                        <div class="voice-avt"><i class="fas fa-user"></i></div>
                        <div class="voice-meta">
                            <h4>M.S 様（28歳）</h4>
                            <span>ピラティストレーナー</span>
                        </div>
                    </div>
                    <div class="voice-body">
                        「身体の使い方は分かっているつもりでしたが、追川さんの指導で自分の癖を根本から修正できました。クライアントへのキューイングの質も上がり、自信がつきました。」
                    </div>
                </div>

                <!-- Client 2 -->
                <div class="voice-card">
                    <div class="voice-header">
                        <div class="voice-avt"><i class="fas fa-user"></i></div>
                        <div class="voice-meta">
                            <h4>K.T 様（32歳）</h4>
                            <span>ヨガ・ピラティス講師</span>
                        </div>
                    </div>
                    <div class="voice-body">
                        「食事指導が苦手でしたが、富沢さんのおかげで理論的にアドバイスできるようになりました。生徒さんのダイエット成功率が上がり、継続率もアップしています！」
                    </div>
                </div>

                <!-- Client 3 -->
                <div class="voice-card">
                    <div class="voice-header">
                        <div class="voice-avt"><i class="fas fa-user"></i></div>
                        <div class="voice-meta">
                            <h4>A.Y 様（30歳）</h4>
                            <span>スタジオ経営者</span>
                        </div>
                    </div>
                    <div class="voice-body">
                        「経営とレッスンの忙しさで自分の食事が疎かになっていましたが、手軽な栄養管理法を学び体調が劇的に良くなりました。肌艶も良くなり生徒さんに褒められます。」
                    </div>
                </div>

                <!-- Client 4 -->
                <div class="voice-card">
                    <div class="voice-header">
                        <div class="voice-avt"><i class="fas fa-user"></i></div>
                        <div class="voice-meta">
                            <h4>R.N 様（26歳）</h4>
                            <span>フリーランスインストラクター</span>
                        </div>
                    </div>
                    <div class="voice-body">
                        「ただの講習ではなく、私のライフスタイルに合わせた実践的な内容でした。LINEでいつでも相談できる安心感があり、モチベーションを維持できました。」
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Flow & Price -->
    <section id="price" class="section-padding bg-base">
        <div class="container">
            <h2 class="section-title fade-in">Flow & Price</h2>
            
            <div style="margin-bottom: 80px;" class="fade-in">
                <div class="flow-step">
                    <h4>Step 1. カウンセリング</h4>
                    <p style="font-size: 0.9rem; color: var(--text-sub);">現状の課題（指導スキル・集客・自身の健康）をヒアリング。</p>
                </div>
                <div class="flow-step">
                    <h4>Step 2. プログラム開始</h4>
                    <p style="font-size: 0.9rem; color: var(--text-sub);">週1回のセッションと、毎日のLINEサポートで伴走します。</p>
                </div>
                <div class="flow-step">
                    <h4>Step 3. スキル習得・卒業</h4>
                    <p style="font-size: 0.9rem; color: var(--text-sub);">一生モノの知識と習慣を身につけ、さらに活躍できる状態へ。</p>
                </div>
            </div>

            <div class="price-container fade-in">
                
                <!-- Plan 1 -->
                <div class="price-card">
                    <span class="price-tag">Basic Plan</span>
                    <h3 class="price-name">パーソナル栄養<br>コーチングプラン</h3>
                    <div class="price-amount">200,000<span style="font-size:1rem; font-weight:400; color:var(--text-main);">yen〜</span></div>
                    <ul class="price-list">
                        <li><i class="fas fa-check"></i> 食事・栄養コーチング</li>
                        <li><i class="fas fa-check"></i> 週1回オンラインセッション</li>
                        <li><i class="fas fa-check"></i> 期間：3ヶ月継続</li>
                        <li><i class="fas fa-check"></i> 自身の健康管理と指導力UP</li>
                    </ul>
                    <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn">無料相談に申し込む</a>
                </div>

                <!-- Plan 2 -->
                <div class="price-card advance">
                    <span class="price-tag">Advance Plan</span>
                    <h3 class="price-name">アドバンスプラン<br>トータルサポート</h3>
                    <div class="price-amount">300,000<span style="font-size:1rem; font-weight:400; color:var(--text-main);">yen〜</span></div>
                    <ul class="price-list">
                        <li><i class="fas fa-check"></i> <strong>毎日の食事栄養 徹底管理</strong></li>
                        <li><i class="fas fa-check"></i> 3ヶ月継続コーチング</li>
                        <li><i class="fas fa-check"></i> 週1回 Zoom相談</li>
                        <li><i class="fas fa-check"></i> <strong>LINE相談 無制限</strong></li>
                        <li><i class="fas fa-check"></i> パーソナルトレーニング連携</li>
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
            <a href="https://docs.google.com/forms/d/e/1FAIpQLScIAD-W3wwlx3-h5BYWnTISMvaoD_p2huWuIAT3mQ6KkWsFjA/viewform?usp=header" target="_blank" class="btn-outline">フォームから問い合わせる</a>
            
            <div class="footer-sns" style="margin-top: 50px;">
                <!-- Instagram -->
                <a href="https://www.instagram.com/core.wellness.official?igsh=MW0yNnRpNzFsMmtrcA%3D%3D&utm_source=qr" target="_blank"><i class="fab fa-instagram"></i></a>
                <!-- LINE -->
                <a href="https://line.me/R/ti/p/@Vo8zA80" target="_blank"><i class="fab fa-line"></i></a>
            </div>
            <p class="copyright">&copy; 2024 Wellness Designer. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- JavaScript -->
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
</html>
