Bir İnsan Kaynakları (İK) profesyonelinin veya teknik işe alım uzmanının dikkatini çekmek için web sitesinin **"taranabilir" (scannable)** olması çok önemlidir. İK uzmanları genellikle bir profile ortalama 10-15 saniye ayırır. Bu yüzden anahtar kelimelerin, teknoloji yığınının (tech stack) ve iletişim bilgilerinin anında göze çarpması gerekir.

Bu doğrultuda tasarımı şu şekilde güncelledim:

1. **Hızlı İletişim & Sosyal Kanıt:** İletişim, GitHub ve LinkedIn linklerini hemen sayfanın en üstüne (Hero bölümüne) çarpıcı butonlar ve ikonlar ile ekledim. Ayrıca en alta detaylı bir "İletişim" bölümü kurguladım.
2. **İK İçin Anahtar Kelime Optimizasyonu (Tech Stack):** İK uzmanlarının aradığı teknolojileri (Java, Spring Boot, Hibernate, Docker, PostgreSQL, Kafka, Redis vb.) yetenekler bölümünde **"etiketler (badges)"** halinde görselleştirdim. Bu, okunabilirliği inanılmaz artırır.
3. **Modern ve Profesyonel UI:** FontAwesome ikonları entegre edildi ve açık mavi (güven veren kurumsal renk) paleti daha profesyonel bir kontrasta kavuşturuldu.

İşte doğrudan kullanabileceğin yeni HTML kodun:

```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Murat Ertik | Backend Developer</title>
    <!-- İkonlar için FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-color: #f4f9fd;
            --card-bg: #ffffff;
            --primary-blue: #023e8a;
            --accent-blue: #0077b6;
            --light-blue: #ade8f4;
            --text-color: #2b2d42;
            --text-muted: #6c757d;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }
        body { font-family: 'Segoe UI', system-ui, sans-serif; background-color: var(--bg-color); color: var(--text-color); line-height: 1.6; }
        a { text-decoration: none; color: inherit; }

        /* Navbar */
        header { position: fixed; top: 0; width: 100%; background-color: rgba(255, 255, 255, 0.95); box-shadow: 0 2px 10px rgba(0,0,0,0.05); z-index: 1000; }
        .nav-container { max-width: 1200px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center; padding: 15px 20px; }
        .logo { font-size: 1.5rem; font-weight: 800; color: var(--primary-blue); letter-spacing: -0.5px; }
        nav ul { display: flex; list-style: none; gap: 25px; }
        nav a { font-weight: 600; color: var(--text-muted); transition: color 0.3s; }
        nav a:hover { color: var(--accent-blue); }

        /* Hero / Giriş - İK Odaklı */
        .hero { padding: 180px 20px 120px; text-align: center; background: linear-gradient(135deg, #e0fbfc 0%, #c1e7ff 100%); }
        .hero h1 { font-size: 3.5rem; margin-bottom: 10px; color: var(--primary-blue); font-weight: 800; }
        .hero h2 { font-size: 1.5rem; color: var(--accent-blue); margin-bottom: 25px; font-weight: 600; }
        .hero p { font-size: 1.1rem; color: var(--text-color); max-width: 600px; margin: 0 auto 30px; }
        
        /* Sosyal Butonlar */
        .social-links { display: flex; justify-content: center; gap: 15px; margin-top: 20px; }
        .btn { display: flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; font-weight: 600; transition: all 0.3s; }
        .btn-primary { background-color: var(--primary-blue); color: white; box-shadow: 0 4px 15px rgba(2, 62, 138, 0.3); }
        .btn-primary:hover { background-color: #03045e; transform: translateY(-2px); }
        .btn-outline { background-color: white; border: 2px solid var(--primary-blue); color: var(--primary-blue); }
        .btn-outline:hover { background-color: var(--primary-blue); color: white; transform: translateY(-2px); }

        /* Bölüm Standartları */
        section { max-width: 1200px; margin: 0 auto; padding: 80px 20px; }
        .section-title { font-size: 2.2rem; margin-bottom: 40px; color: var(--primary-blue); display: flex; align-items: center; gap: 10px; }
        .section-title::after { content: ''; flex: 1; height: 2px; background-color: var(--light-blue); margin-left: 20px; }
        .content-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 50px; align-items: center; }
        @media (max-width: 768px) { .content-grid { grid-template-columns: 1fr; gap: 30px; } nav ul { display: none; } }
        .text-content p { font-size: 1.1rem; color: var(--text-muted); margin-bottom: 15px; }
        .section-image { width: 100%; border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); }

        /* Yetenekler ve Tech Stack */
        .tech-stack { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 20px; }
        .tech-badge { background-color: var(--light-blue); color: #03045e; padding: 8px 16px; border-radius: 20px; font-size: 0.9rem; font-weight: 700; display: flex; align-items: center; gap: 5px; }
        
        .skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 30px; }
        .skill-card { background: var(--card-bg); padding: 20px; border-radius: 10px; border-left: 4px solid var(--accent-blue); box-shadow: 0 4px 6px rgba(0,0,0,0.04); }
        .skill-card h4 { color: var(--primary-blue); margin-bottom: 5px; }

        /* İletişim Bölümü */
        .contact-section { background-color: var(--card-bg); padding: 60px 20px; border-radius: 16px; text-align: center; margin: 60px auto; max-width: 800px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); border-top: 5px solid var(--primary-blue); }
        .contact-info { display: flex; flex-direction: column; gap: 20px; margin-top: 30px; align-items: center; }
        .contact-item { display: flex; align-items: center; gap: 15px; font-size: 1.2rem; font-weight: 500; color: var(--text-color); }
        .contact-item i { font-size: 1.5rem; color: var(--accent-blue); }
        .contact-item a:hover { color: var(--accent-blue); text-decoration: underline; }

        footer { text-align: center; padding: 30px; background-color: var(--primary-blue); color: white; margin-top: 40px; }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <div class="nav-container">
            <div class="logo">Murat Ertik</div>
            <nav>
                <ul>
                    <li><a href="#who-i-am">Kimim</a></li>
                    <li><a href="#my-skills">Yeteneklerim</a></li>
                    <li><a href="#my-future-goal">Kariyer Hedefim</a></li>
                    <li><a href="#contact">İletişim</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section (İK'nın ilk gördüğü yer) -->
    <section class="hero">
        <h1>Murat Ertik</h1>
        <h2>Backend Geliştirici (Java & Spring Boot)</h2>
        <p>Ölçeklenebilir mikroservisler tasarlayan, veri odaklı ve yapay zeka entegrasyonlarına meraklı yazılım mühendisi.</p>
        
        <div class="social-links">
            <a href="mailto:dmuratertik1@gmail.com" class="btn btn-primary">
                <i class="fa-solid fa-envelope"></i> E-posta Gönder
            </a>
            <a href="https://www.linkedin.com/in/murat-ertik" target="_blank" class="btn btn-outline">
                <i class="fa-brands fa-linkedin"></i> LinkedIn
            </a>
            <a href="https://github.com/MuratErtik" target="_blank" class="btn btn-outline">
                <i class="fa-brands fa-github"></i> GitHub
            </a>
        </div>
    </section>

    <!-- 1. Who I Am -->
    <section id="who-i-am">
        <h2 class="section-title"><i class="fa-solid fa-user-tie"></i> Who I Am</h2>
        <div class="content-grid">
            <div class="text-content">
                <p>Kocaeli Üniversitesi Bilişim Sistemleri Mühendisliği bölümünden <strong>2026 yılı Haziran ayında mezun oldum</strong>. Ölçeklenebilir mikroservisler ve dağıtık sistemler geliştirmeye odaklanan, Java ve Spring Boot ekosisteminde güçlü bir temele sahip tutkulu bir Backend Geliştiricisiyim.</p>
                <p>Karmaşık iş gereksinimlerini temiz, sürdürülebilir koda dönüştürmeyi ve sistem genelinde veri tutarlılığını sağlamayı bir standart olarak benimsiyorum.</p>
            </div>
            <div class="image-content">
                <img src="http://googleusercontent.com/image_generation_content/317" alt="Mezuniyet" class="section-image">
            </div>
        </div>
    </section>

    <!-- 2. My Skills -->
    <section id="my-skills">
        <h2 class="section-title"><i class="fa-solid fa-code"></i> My Skills</h2>
        <div class="content-grid">
            <div class="image-content">
                <img src="http://googleusercontent.com/image_generation_content/322" alt="Backend Development" class="section-image">
            </div>
            <div class="text-content">
                <p>Modern backend mimarilerinin gerektirdiği teknolojilere hakimim ve sürekli öğrenme motivasyonumla araç setimi genişletiyorum.</p>
                
                <!-- İK için taramayı kolaylaştıran etiketler -->
                <div class="tech-stack">
                    <span class="tech-badge"><i class="fa-brands fa-java"></i> Java</span>
                    <span class="tech-badge"><i class="fa-solid fa-leaf"></i> Spring Boot</span>
                    <span class="tech-badge"><i class="fa-solid fa-database"></i> PostgreSQL</span>
                    <span class="tech-badge"><i class="fa-brands fa-docker"></i> Docker</span>
                    <span class="tech-badge"><i class="fa-solid fa-network-wired"></i> Kafka / RabbitMQ</span>
                    <span class="tech-badge"><i class="fa-solid fa-memory"></i> Redis</span>
                    <span class="tech-badge"><i class="fa-solid fa-cubes"></i> Microservices</span>
                    <span class="tech-badge"><i class="fa-solid fa-code-branch"></i> Hibernate (JPA)</span>
                </div>

                <div class="skills-grid">
                    <div class="skill-card">
                        <h4>Mimari Tasarım</h4>
                        <p style="font-size: 0.9rem; margin:0;">Mikroservisler ve Dağıtık Sistemler</p>
                    </div>
                    <div class="skill-card">
                        <h4>Yazılım Prensipleri</h4>
                        <p style="font-size: 0.9rem; margin:0;">Temiz Kod (Clean Code) & SOLID</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 3. My Future Goal -->
    <section id="my-future-goal">
        <h2 class="section-title"><i class="fa-solid fa-rocket"></i> My Future Goal</h2>
        <div class="content-grid">
            <div class="text-content">
                <p>Hedefim, mikroservis mimarilerindeki pratik uzmanlığımı derinleştirirken, geleceğin teknolojilerine yön vermek.</p>
                <p>Özellikle <strong>Derin Öğrenme (Deep Learning)</strong> ve <strong>RAG (Geri Getirmeyle Zenginleştirilmiş Üretim)</strong> gibi yapay zeka yeteneklerini backend çözümlerine entegre ederek, veri odaklı ve akıllı kurumsal sistemler inşa etmeyi amaçlıyorum.</p>
            </div>
            <div class="image-content">
                <img src="http://googleusercontent.com/image_generation_content/328" alt="AI & Microservices" class="section-image">
            </div>
        </div>
    </section>

    <!-- İletişim Bölümü (Yeni Eklendi) -->
    <section id="contact">
        <div class="contact-section">
            <h2 style="color: var(--primary-blue); font-size: 2rem; margin-bottom: 10px;">Birlikte Çalışalım</h2>
            <p style="color: var(--text-muted); font-size: 1.1rem;">Projeler, iş fırsatları veya teknoloji üzerine sohbet etmek için bana ulaşabilirsiniz.</p>
            
            <div class="contact-info">
                <div class="contact-item">
                    <i class="fa-solid fa-envelope"></i>
                    <a href="mailto:dmuratertik1@gmail.com">dmuratertik1@gmail.com</a>
                </div>
                <div class="contact-item">
                    <i class="fa-brands fa-linkedin"></i>
                    <a href="https://www.linkedin.com/in/murat-ertik" target="_blank">linkedin.com/in/murat-ertik</a>
                </div>
                <div class="contact-item">
                    <i class="fa-brands fa-github"></i>
                    <a href="https://github.com/MuratErtik" target="_blank">github.com/MuratErtik</a>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Murat Ertik. Tüm Hakları Saklıdır.</p>
    </footer>

</body>
</html>

```