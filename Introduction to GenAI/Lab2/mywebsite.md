İşte belirttiğin 3 ana bölümü (Kimim, Yeteneklerim, Kariyer Hedefim) net bir şekilde ayıran, modern, duyarlı (responsive) ve açık mavi tonlarının hakim olduğu tam bir HTML/CSS web sitesi kodu.

Bu kodu bir `.html` dosyası olarak kaydedip (örneğin `index.html`) tarayıcında doğrudan açabilirsin. Görseller de tasarıma şık bir şekilde entegre edilmiştir.

```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Murat Ertik | Kişisel Web Sitesi</title>
    <style>
        /* Modern ve Açık Mavi Temalı CSS Değişkenleri */
        :root {
            --bg-color: #f0f7fc;
            --card-bg: #ffffff;
            --primary-blue: #0077b6;
            --accent-blue: #00b4d8;
            --light-blue: #90e0ef;
            --text-color: #1d3557;
            --text-muted: #4a5568;
        }

        /* Genel Ayarlar */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* Navigasyon Barı */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 119, 182, 0.1);
            z-index: 1000;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-blue);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            font-weight: 600;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--accent-blue);
        }

        /* Giriş (Hero) Alanı */
        .hero {
            padding: 160px 20px 100px;
            text-align: center;
            background: linear-gradient(180deg, #e2effa 0%, var(--bg-color) 100%);
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 15px;
            color: var(--primary-blue);
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--text-muted);
            max-width: 600px;
            margin: 0 auto;
        }

        /* Ortak Bölüm Düzeni */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 80px 20px;
        }

        .section-title {
            font-size: 2.2rem;
            text-align: center;
            margin-bottom: 50px;
            position: relative;
            color: var(--primary-blue);
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background-color: var(--accent-blue);
            margin: 10px auto 0;
            border-radius: 2px;
        }

        /* İki Sütunlu Grid Yapısı (Görsel + Metin için) */
        .content-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        @media (max-width: 768px) {
            .content-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            .hero h1 { font-size: 2.2rem; }
            nav ul { display: none; } /* Mobil için basit tutuldu */
        }

        .text-content h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
        }

        /* Web Sitesi Görselleri */
        .section-image {
            width: 100%;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0, 119, 182, 0.15);
            transition: transform 0.3s;
        }

        .section-image:hover {
            transform: translateY(-5px);
        }

        /* Yetenekler Bölümü Kart Tasarımları */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .skill-card {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 119, 182, 0.05);
            border-top: 4px solid var(--accent-blue);
            transition: all 0.3s;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 119, 182, 0.1);
        }

        .skill-card h4 {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: var(--primary-blue);
        }

        .skill-card p {
            font-size: 0.95rem;
            color: var(--text-muted);
        }

        /* Footer */
        footer {
            background-color: #1d3557;
            color: #ffffff;
            text-align: center;
            padding: 30px;
            margin-top: 60px;
            font-size: 0.95rem;
        }
    </style>
</head>
<body>

    <header>
        <div class="nav-container">
            <div class="logo">Murat Ertik</div>
            <nav>
                <ul>
                    <li><a href="#who-i-am">Kimim</a></li>
                    <li><a href="#my-skills">Yeteneklerim</a></li>
                    <li><a href="#my-future-goal">Kariyer Hedefim</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero">
        <h1>Merhaba, Ben Murat</h1>
        <p>Geleceğin Akıllı Sistemlerini İnşa Eden Backend Geliştiricisi</p>
    </section>

    <section id="who-i-am">
        <h2 class="section-title">Who I Am (Kimim)</h2>
        <div class="content-grid">
            <div class="text-content">
                <h3>Akademik Altyapı ve Tutku</h3>
                <p>Kocaeli Üniversitesi Bilişim Sistemleri Mühendisliği bölümünden 2026 yılı Haziran ayında mezun olmuş, tutkulu bir <strong>Backend Geliştiricisiyim</strong>. Pratik projeler üretme, sürekli öğrenme ve yeni teknolojilere hızla adapte olma konusunda her zaman yüksek motivasyona sahibim.</p>
            </div>
            <div class="image-content">
                <img src="http://googleusercontent.com/image_generation_content/317" alt="Murat'ın Mezuniyeti ve Temelleri" class="section-image">
            </div>
        </div>
    </section>

    <section id="my-skills" style="background-color: rgba(255, 255, 255, 0.6); border-radius: 20px;">
        <h2 class="section-title">My Skills (Yeteneklerim)</h2>
        <div class="content-grid">
            <div class="image-content">
                <img src="http://googleusercontent.com/image_generation_content/322" alt="Backend Geliştirme Süreçleri" class="section-image">
            </div>
            <div class="text-content">
                <h3>Teknik Uzmanlık Alanlarım</h3>
                <p>Karmaşık gereksinimleri temiz koda dönüştürmekten ve veri tutarlılığını sağlamaktan keyif alıyorum.</p>
                
                <div class="skills-grid">
                    <div class="skill-card">
                        <h4>Ana Teknolojiler</h4>
                        <p>Java ve Spring Boot ekosisteminde sağlam bir bilgi birikimi.</p>
                    </div>
                    <div class="skill-card">
                        <h4>Mimari Tasarım</h4>
                        <p>Ölçeklenebilir mikroservisler ve dağıtık sistemler geliştirme odağı.</p>
                    </div>
                    <div class="skill-card">
                        <h4>Temiz Kod</h4>
                        <p>İş gereksinimlerini sürdürülebilir ve temiz koda (Clean Code) dönüştürme.</p>
                    </div>
                    <div class="skill-card">
                        <h4>Veri ve Optimizasyon</h4>
                        <p>Veritabanı optimizasyonu ve mikroservis tasarım desenlerinin uygulanması.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="my-future-goal">
        <h2 class="section-title">My Future Goal (Kariyer Hedefim)</h2>
        <div class="content-grid">
            <div class="text-content">
                <h3>Yapay Zeka Entegreli Altyapılar</h3>
                <p>Öncelikli hedefim, mikroservis mimarilerindeki uzmanlığımı sürekli pratik yaparak daha da derinleştirmek.</p>
                <br>
                <p>Aynı zamanda, <strong>Derin Öğrenme</strong> ve <strong>RAG (Geri Getirmeyle Zenginleştirilmiş Üretim)</strong> gibi modern yapay zeka yeteneklerini backend çözümlerine entegre etmeyi öğrenerek yenilikçi, akıllı ve vizyoner altyapılar inşa etmeyi amaçlıyorum.</p>
            </div>
            <div class="image-content">
                <img src="http://googleusercontent.com/image_generation_content/328" alt="Yapay Zeka ve Mikroservis Geleceği" class="section-image">
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Murat Ertik. Tüm Hakları Saklıdır.</p>
    </footer>

</body>
</html>

```