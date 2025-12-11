<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness Designer | Daiki Oikawa & Kokona Tomizawa</title>
    <meta name="description" content="本質から整える健康を。追川大輝と富沢心乙による、経営者・プロフェッショナルのためのウェルネスプログラム。">

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&family=Noto+Sans+JP:wght@400;500;700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* === CSS Variables (色設定を変更) === */
        :root {
            /* 自然で高級感のあるカラーパレットに変更 */
            --bg-black: #1c1c1a;       /* 深い墨色（わずかに温かみのある黒） */
            --bg-dark-gray: #2a2a28;   /* 上記より少し明るい落ち着いたチャコール */
            --bg-light: #f2f0eb;       /* 生成り色（石灰岩のような自然なオフホワイト） */
            --text-white: #f7f7f4;     /* 柔らかな白 */
            --text-black: #3a3a38;     /* 濃いグレー */
            --text-sub: #9e9e9b;       /* 落ち着いたグレー */
            --accent: #bfa588;         /* 落ち着いたブロンズゴールド（高級感と自然感） */
            --accent-hover: #a88f72;   /* アクセントのホバー色 */
            --gradient: linear-gradient(135deg, #1c1c1a 0%, #333330 100%);
            --header-h: 70px;
        }

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
        
        /* Background Classes */
        .bg-black { background-color: var(--bg-black); }
        .bg-dark { background-color: var(--bg-dark-gray); }
        .bg-light { background-color: var(--bg-light); color: var(--text-black); }
        .bg-gradient { background: var(--gradient); }

        /* === Components === */
        /* Buttons */
        .btn {
            display: inline-block; padding: 14px 40px; 
            background-color: var(--accent); color: #1c1c1a; /* 文字色を背景に合わせて調整 */
            font-weight: 700; font-size: 0.95rem; border-radius: 50px; 
            letter-spacing: 0.05em; transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(191, 165, 136, 0.3); /* 影の色もアクセントに合わせる */
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

        /* Titles */
        .section-title { 
            font-size: clamp(1.8rem, 4vw, 2.4rem); margin-bottom: 60px; 
            text-align: center; position: relative; color: inherit;
        }
        .section-title::after { 
            content: ''; display: block; width: 50px; height: 3px; 
            background: var(--accent); margin: 20px auto 0; 
        }

        /* Fixed CTA (Floating Button) */
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

        /* === Header & Navigation === */
        .header {
            position: fixed; top: 0; left: 0; width: 100%; height: var(--header-h);
            display: flex; justify-content: space-between; align-items: center;
            padding: 0 5%; z-index: 1000;
            background: rgba(28, 28, 26
