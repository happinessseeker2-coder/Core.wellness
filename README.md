<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellness Designer | 追川大輝 & 富沢心乙</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Noto+Sans+JP:wght@300;400;500;700&display=swap" rel="stylesheet">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* === CSS Variables === */
        :root {
            --bg-color: #050505;
            --bg-secondary: rgba(15, 15, 15, 0.9); /* 半透明にして背景画像を透過させる */
            --bg-tertiary: rgba(26, 26, 26, 0.9);
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
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: var(--font-body);
            line-height: 1.9;
            letter-spacing: 0.5px;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }
        a { text-decoration: none; color: inherit; transition: 0.3s; }
        ul { list-style: none; }
        h1, h2, h3, h4 { font-family: var(--font-heading); letter-spacing: 0.08em; }
        img { max-width: 100%; height: auto; display: block; }

        /* === 背景画像のパララックス設定エリア === */
        /* 各セクションの背景として固定表示させるためのクラス */
        .bg-fixed {
            position: relative;
            background-attachment: fixed;
            background-position: center;
            background-size: cover;
            background-repeat: no-repeat;
        }

        /* 背景画像1 (PH1.jpg) */
        .bg-image-1 {
            background-image: url('PH1.jpg');
        }

        /* 背景画像2 (PH2.jpg) */
        .bg-image-2 {
            background-image: url('PH2.jpg');
        }

        /* 背景画像3 (PH3.jpeg) */
        .bg-image-3 {
            background-image: url('PH3.jpeg');
        }
        
        /* コンテンツを見やすくするためのオーバーレイ */
        .bg-overlay {
            background-color: rgba(0, 0, 0, 0.75); /* 背景を暗くする */
            width: 100%;
            height: 100%;
            padding: 100px 0 120px; /* section-paddingの代わり */
        }

        /* === Utilities === */
        .container { width: 90%; max-width: 1200px; margin: 0 auto; padding: 0 20px; position: relative; z-index: 2; }
        .text-center { text-align: center; }

        .btn {
            display: inline-block; padding: 14px 32px; background-color: var(--accent-color); color: #000;
            font-weight: 700; font-size: 1rem; border-radius: 50px; letter-spacing: 0.05em; transition: all 0.3s ease;
            border: none; cursor: pointer; box-shadow: 0 4px 15px rgba(64, 224, 208, 0.3);
        }
        .btn:hover { background-color: var(--accent-hover); transform: translateY(-3px); box-shadow: 0 6px 20px rgba(64, 224, 208, 0.5); }

        .section-title { font-size: 2.2rem; margin-bottom: 4rem; color: var(--silver); text-align: center; position: relative; }
        .section-title::after { content: ''; display: block; width: 60px; height: 2px; background: var(--accent-color); margin: 15px auto 0; }

        .fade-in-section { opacity: 0; transform: translateY(30px); transition: opacity 1.0s ease-out, transform 1.0s ease-out; will-change: opacity, transform; }
        .fade-in-section.is-visible { opacity: 1; transform: none; }

        /* === Header === */
        .header {
            position: fixed; top: 0; left: 0; width: 100%; height: var(--header-height);
            background-color: rgba(5, 5, 5, 0.9); backdrop-filter: blur(10px); display: flex; align-items: center;
            justify-content: space-between; padding: 0 5%; z-index: 1000; border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }
        .logo { font-size: 1.5rem; font-weight: 700; font-family: var(--font-heading); color: var(--text-color); z-index: 1001; }
        .logo span { color: var(--accent-color); }

        .nav-wrapper { display: flex; align-items: center; gap: 30px; }
        .nav-links { display: flex; gap: 25px; }
        .nav-link-item { font-size: 0.95rem; font-weight: 500; position: relative; }
        .nav-link-item::after { content: ''; position: absolute; bottom: -5px; left: 0; width: 0%; height: 1px; background-color: var(--accent-color); transition: width 0.3s; }
        .nav-link-item:hover::after { width: 100%; }

        .header-actions { display: flex; align-items: center; gap: 20px; }
        .header-btn { padding: 10px 24px; font-size: 0.9rem; }
        .header-sns { display: flex; gap: 15px; }
        .header-sns a { font-size: 1.1rem; color: var(--text-sub); }
        .header-sns a:hover { color: var(--accent-color); }
        .menu-toggle { display: none; font-size: 1.5rem; cursor: pointer; z-index: 1001; color: #fff; }

        /* === Hero Section === */
        .
