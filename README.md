ওকে! এই নাও পুরো কোড — **এটা পুরোটা কপি করো** (`<!DOCTYPE html>` থেকে `</html>` পর্যন্ত):

```html
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ইসলাম নগর আলো প্রদীপ যুব সংগঠন</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        :root {
            --primary: #1a7a4c;
            --primary-dark: #145e3a;
            --accent: #f59e0b;
            --bg: #f8faf9;
            --text: #1a1a2e;
            --text-light: #555;
            --white: #ffffff;
            --shadow: 0 4px 20px rgba(0,0,0,0.08);
            --radius: 12px;
        }
        body { font-family: 'Noto Sans Bengali', sans-serif; background: var(--bg); color: var(--text); line-height: 1.7; }
        nav { position: fixed; top: 0; width: 100%; background: rgba(255,255,255,0.95); backdrop-filter: blur(10px); z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.06); }
        .nav-container { max-width: 1200px; margin: 0 auto; padding: 0 20px; display: flex; justify-content: space-between; align-items: center; height: 70px; }
        .nav-logo { font-size: 1.2rem; font-weight: 700; color: var(--primary); text-decoration: none; }
        .nav-logo span { color: var(--accent); }
        .nav-links { display: flex; list-style: none; gap: 8px; }
        .nav-links a { text-decoration: none; color: var(--text); padding: 8px 16px; border-radius: 8px; font-size: 0.95rem; font-weight: 600; transition: all 0.3s; }
        .nav-links a:hover, .nav-links a.active { background: var(--primary); color: var(--white); }
        .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; padding: 5px; }
        .hamburger span { width: 25px; height: 3px; background: var(--text); border-radius: 3px; transition: 0.3s; }
        .hero { min-height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; background: linear-gradient(135deg, var(--primary) 0%, #0f4c30 100%); color: var(--white); padding: 100px 20px 60px; position: relative; overflow: hidden; }
        .hero::before { content: ''; position: absolute; top: -50%; right: -20%; width: 600px; height: 600px; background: rgba(245, 158, 11, 0.1); border-radius: 50%; }
        .hero::after { content: ''; position: absolute; bottom: -30%; left: -10%; width: 400px; height: 400px; background: rgba(255,255,255,0.05); border-radius: 50%; }
        .hero-content { position: relative; z-index: 1; max-width: 800px; }
        .hero-icon { font-size: 4rem; margin-bottom: 20px; animation: glow 2s ease-in-out infinite alternate; }
        @keyframes glow { from { filter: drop-shadow(0 0 5px rgba(245,158,11,0.3)); } to { filter: drop-shadow(0 0 20px rgba(245,158,11,0.6)); } }
        .hero h1 { font-size: 2.8rem; font-weight: 700; margin-bottom: 16px; line-height: 1.3; }
        .hero h1 span { color: var(--accent); }
        .hero p { font-size: 1.15rem; opacity: 0.9; max-width: 600px; margin: 0 auto 30px; }
        .hero-btn { display: inline-block; padding: 14px 36px; background: var(--accent); color: var(--text); text-decoration: none; border-radius: 50px; font-weight: 700; font-size: 1rem; transition: transform 0.3s, box-shadow 0.3s; }
        .hero-btn:hover { transform: translateY(-3px); box-shadow: 0 10px 30px rgba(245,158,11,0.3); }
        section { padding: 80px 20px; }
        .container { max-width: 1100px; margin: 0 auto; }
        .section-title { text-align: center; margin-bottom: 50px; }
        .section-title h2 { font-size: 2rem; color: var(--primary); margin-bottom: 10px; }
        .section-title p { color: var(--text-light); font-size: 1rem; }
        .section-title .line { width: 60px; height: 4px; background: var(--accent); margin: 12px auto 0; border-radius: 2px; }
        .about-content { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: center; }
        .about-text p { color: var(--text-light); margin-bottom: 16px; font-size: 1rem; }
        .about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        .stat-card { background: var(--white); padding: 24px; border-radius: var(--radius); text-align: center; box-shadow: var(--shadow); transition: transform 0.3s; }
        .stat-card:hover { transform: translateY(-5px); }
        .stat-card .number { font-size: 2.2rem; font-weight: 700; color: var(--primary); }
        .stat-card .label { font-size: 0.9rem; color: var(--text-light); margin-top: 4px; }
        #activities { background: var(--white); }
        .activities-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 24px; }
        .activity-card { background: var(--bg); border-radius: var(--radius); padding: 30px; text-align: center; transition: transform 0.3s, box-shadow 0.3s; border: 1px solid rgba(26,122,76,0.1); }
        .activity-card:hover { transform: translateY(-5px); box-shadow: var(--shadow); }
        .activity-card .icon { font-size: 2.5rem; margin-bottom: 16px; }
        .activity-card h3 { font-size: 1.15rem; color: var(--primary); margin-bottom: 10px; }
        .activity-card p { color: var(--text-light); font-size: 0.92rem; }
        .gallery-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 16px; }
        .gallery-item { aspect-ratio: 4/3; border-radius: var(--radius); overflow: hidden; background: linear-gradient(135deg, #e0f2e9, #d1e8d9); display: flex; align-items: center; justify-content: center; font-size: 3rem; cursor: pointer; transition: transform 0.3s; position: relative; }
        .gallery-item:hover { transform: scale(1.03); }
        .gallery-item .overlay { position: absolute; bottom: 0; left: 0; right: 0; padding: 12px; background: linear-gradient(transparent, rgba(0,0,0,0.6)); color: white; font-size: 0.85rem; opacity: 0; transition: opacity 0.3s; }
        .gallery-item:hover .overlay { opacity: 1; }
        .gallery-note { text-align: center; margin-top: 24px; color: var(--text-light); font-size: 0.9rem; padding: 16px; background: var(--white); border-radius: var(--radius); border: 2px dashed rgba(26,122,76,0.2); }
        #contact { background: var(--white); }
        .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; }
        .contact-info-card { display: flex; align-items: flex-start; gap: 16px; margin-bottom: 24px; }
        .contact-info-card .icon { width: 48px; height: 48px; background: var(--bg); border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.3rem; flex-shrink: 0; }
        .contact-info-card h4 { font-size: 0.95rem; color: var(--primary); margin-bottom: 2px; }
        .contact-info-card p { color: var(--text-light); font-size: 0.9rem; }
        .contact-form { display: flex; flex-direction: column; gap: 16px; }
        .contact-form input, .contact-form textarea { padding: 14px 18px; border: 2px solid #e5e5e5; border-radius: 10px; font-family: inherit; font-size: 0.95rem; transition: border-color 0.3s; outline: none; }
        .contact-form input:focus, .contact-form textarea:focus { border-color: var(--primary); }
        .contact-form textarea { resize: vertical; min-height: 120px; }
        .submit-btn { padding: 14px; background: var(--primary); color: var(--white); border: none; border-radius: 10px; font-family: inherit; font-size: 1rem; font-weight: 600; cursor: pointer; transition: background 0.3s, transform 0.3s; }
        .submit-btn:hover { background: var(--primary-dark); transform: translateY(-2px); }
        footer { background: var(--text); color: rgba(255,255,255,0.7); text-align: center; padding: 30px 20px; font-size: 0.9rem; }
        footer span { color: var(--accent); }
        @media (max-width: 768px) {
            .hamburger { display: flex; }
            .nav-links { display: none; position: absolute; top: 70px; left: 0; right: 0; background: var(--white); flex-direction: column; padding: 20px; box-shadow: 0 10px 20px rgba(0,0,0,0.1); }
            .nav-links.open { display: flex; }
            .hero h1 { font-size: 2rem; }
            .about-content, .contact-grid { grid-template-columns: 1fr; }
            .activities-grid { grid-template-columns: 1fr; }
        }
        .fade-in { opacity: 0; transform: translateY(30px); transition: opacity 0.6s, transform 0.6s; }
        .fade-in.visible { opacity: 1; transform: translateY(0); }
    </style>
</head>
<body>
    <nav>
        <div class="nav-container">
            <a href="#home" class="nav-logo">আলো <span>প্রদীপ</span></a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home" class="active">হোম</a></li>
                <li><a href="#about">পরিচিতি</a></li>
                <li><a href="#activities">কার্যক্রম</a></li>
                <li><a href="#gallery">গ্যালারি</a></li>
                <li><a href="#contact">যোগাযোগ</a></li>
            </ul>
            <button class="hamburger" id="hamburger" aria-label="Menu">
                <span></span><span></span><span></span>
            </button>
        </div>
    </nav>
    <section class="hero" id="home">
        <div class="hero-content">
            <div class="hero-icon">🕌</div>
            <h1>ইসলাম নগর <span>আলো প্রদীপ</span><br>যুব সংগঠন</h1>
            <p>সমাজের উন্নয়নে নিবেদিত তরুণদের একটি প্ল্যাটফর্ম। একসাথে গড়ি আলোকিত সমাজ।</p>
            <a href="#activities" class="hero-btn">আমাদের কার্যক্রম দেখুন →</a>
        </div>
    </section>
    <section id="about">
        <div class="container">
            <div class="section-title fade-in">
                <h2>আমাদের পরিচিতি</h2>
                <p>সমাজসেবা ও যুব উন্নয়নে প্রতিশ্রুতিবদ্ধ</p>
                <div class="line"></div>
            </div>
            <div class="about-content">
                <div class="about-text fade-in">
                    <p><strong>ইসলাম নগর আলো প্রদীপ যুব সংগঠন</strong> একটি অলাভজনক সামাজিক সংগঠন যা এলাকার তরুণদের নিয়ে গঠিত। আমরা বিশ্বাস করি, তরুণদের সঠিক পথে পরিচালনা করতে পারলে একটি সুন্দর ও আলোকিত সমাজ গড়ে তোলা সম্ভব।</p>
                    <p>শিক্ষা, সংস্কৃতি, খেলাধুলা ও সমাজসেবার মাধ্যমে আমরা এলাকার উন্নয়নে কাজ করে যাচ্ছি। প্রতিটি সদস্যের অংশগ্রহণ ও সহযোগিতায় আমরা এগিয়ে চলেছি।</p>
                    <p>আমাদের লক্ষ্য — একটি সুশিক্ষিত, সচেতন ও আত্মনির্ভরশীল যুব সমাজ গড়ে তোলা।</p>
                </div>
                <div class="about-stats fade-in">
                    <div class="stat-card"><div class="number">৫০+</div><div class="label">সক্রিয় সদস্য</div></div>
                    <div class="stat-card"><div class="number">২০+</div><div class="label">সম্পন্ন প্রকল্প</div></div>
                    <div class="stat-card"><div class="number">১০০+</div><div class="label">সেবা গ্রহীতা</div></div>
                    <div class="stat-card"><div class="number">🏆</div><div class="label">পুরস্কার প্রাপ্ত</div></div>
                </div>
            </div>
        </div>
    </section>
    <section id="activities">
        <div class="container">
            <div class="section-title fade-in">
                <h2>আমাদের কার্যক্রম</h2>
                <p>সমাজের বিভিন্ন ক্ষেত্রে আমাদের কাজ</p>
                <div class="line"></div>
            </div>
            <div class="activities-grid">
                <div class="activity-card fade-in"><div class="icon">📚</div><h3>শিক্ষা কার্যক্রম</h3><p>বিনামূল্যে কোচিং, বই বিতরণ, এবং শিক্ষা উপকরণ সরবরাহের মাধ্যমে শিক্ষার আলো ছড়িয়ে দেওয়া।</p></div>
                <div class="activity-card fade-in"><div class="icon">🏥</div><h3>স্বাস্থ্যসেবা</h3><p>ফ্রি স্বাস্থ্য ক্যাম্প, রক্তদান কর্মসূচি এবং স্বাস্থ্য সচেতনতা প্রচারণা পরিচালনা।</p></div>
                <div class="activity-card fade-in"><div class="icon">⚽</div>
...(truncated)...
