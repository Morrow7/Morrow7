<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Morrow · dev profile</title>
  <!-- Font Awesome (icons) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <!-- AOS (animate on scroll) -->
  <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0a0c10;
      font-family: 'Inter', sans-serif;
      color: #e9edf5;
      line-height: 1.6;
      overflow-x: hidden;
      position: relative;
      padding: 2rem 1.5rem;
    }

    /* dynamic animated gradient background */
    body::before {
      content: '';
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 30%, rgba(110, 84, 148, 0.25) 0%, transparent 35%),
                  radial-gradient(circle at 80% 70%, rgba(0, 180, 255, 0.18) 0%, transparent 40%),
                  radial-gradient(circle at 40% 80%, rgba(255, 120, 200, 0.12) 0%, transparent 45%),
                  #0a0c10;
      z-index: -2;
      animation: bgPulse 12s ease-in-out infinite alternate;
    }

    /* subtle noise / stars */
    body::after {
      content: '';
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI4MCIgaGVpZ2h0PSI4MCIgdmlld0JveD0iMCAwIDgwIDgwIj48cGF0aCBkPSJNMzAgMTBhMiAyIDAgMSAwIDAgNCAyIDIgMCAwIDAgMC00Wk00MCAyMGEyIDIgMCAxIDAgMCA0IDIgMiAwIDAgMCAwLTRaTTUwIDUwYTIgMiAwIDEgMCAwIDQgMiAyIDAgMCAwIDAtNFpNMjAgNjBhMiAyIDAgMSAwIDAgNCAyIDIgMCAwIDAgMC00Wk02MCAzMGEyIDIgMCAxIDAgMCA0IDIgMiAwIDAgMCAwLTRaTTEwIDUwYTIgMiAwIDEgMCAwIDQgMiAyIDAgMCAwIDAtNFoiIGZpbGw9InJnYmEoMjU1LDI1NSwyNTUsMC4wNCkiLz48L3N2Zz4=');
      background-repeat: repeat;
      opacity: 0.4;
      pointer-events: none;
      z-index: -1;
    }

    @keyframes bgPulse {
      0% { opacity: 0.8; transform: scale(1); }
      100% { opacity: 1; transform: scale(1.05); }
    }

    .container {
      max-width: 1100px;
      margin: 0 auto;
      position: relative;
      z-index: 2;
    }

    /* glass card */
    .glass-card {
      background: rgba(18, 22, 32, 0.65);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.06);
      border-radius: 32px;
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(255, 255, 255, 0.02) inset;
      padding: 2rem 2.2rem;
      transition: all 0.3s ease;
    }

    .glass-card:hover {
      border-color: rgba(140, 120, 255, 0.25);
      box-shadow: 0 30px 60px -15px rgba(100, 70, 255, 0.3), 0 0 0 1px rgba(200, 180, 255, 0.1) inset;
    }

    /* typography */
    h1, h2, h3 {
      font-weight: 700;
      letter-spacing: -0.02em;
    }

    h1 {
      font-size: 3.2rem;
      background: linear-gradient(135deg, #fff 0%, #c7b3ff 45%, #96b9ff 80%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      line-height: 1.2;
      text-shadow: 0 0 30px rgba(150, 130, 255, 0.4);
    }

    h2 {
      font-size: 1.8rem;
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 1.5rem;
      color: #f0f3ff;
    }

    h2 i {
      color: #a78bfa;
      font-size: 1.8rem;
      filter: drop-shadow(0 0 8px rgba(167, 139, 250, 0.6));
    }

    h3 {
      font-size: 1.3rem;
      margin-bottom: 0.75rem;
      color: #d6e2ff;
    }

    .subhead {
      font-size: 1.2rem;
      color: #b9c8e0;
      font-weight: 400;
      margin-bottom: 2rem;
      border-left: 4px solid #a78bfa;
      padding-left: 1.5rem;
      background: linear-gradient(90deg, rgba(167, 139, 250, 0.15), transparent);
      border-radius: 0 12px 12px 0;
    }

    /* badges */
    .badge-container {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      justify-content: center;
      margin: 1.8rem 0 0.5rem;
    }

    .badge {
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 100px;
      padding: 0.5rem 1.2rem;
      font-size: 0.9rem;
      font-weight: 500;
      color: #ced9f0;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.2s;
      backdrop-filter: blur(4px);
    }

    .badge i {
      color: #a78bfa;
    }

    .badge:hover {
      border-color: #a78bfa;
      background: rgba(167, 139, 250, 0.1);
      transform: translateY(-2px);
    }

    /* quote block */
    .quote-block {
      background: rgba(10, 14, 23, 0.7);
      border-left: 6px solid #a78bfa;
      border-radius: 18px;
      padding: 1.8rem 2rem;
      font-style: italic;
      font-weight: 400;
      color: #d0dcf5;
      box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.7);
      backdrop-filter: blur(8px);
      line-height: 1.8;
      position: relative;
      overflow: hidden;
    }

    .quote-block::after {
      content: '"';
      position: absolute;
      bottom: -20px;
      right: 20px;
      font-size: 8rem;
      font-weight: 900;
      color: rgba(167, 139, 250, 0.08);
      font-family: serif;
      line-height: 1;
      pointer-events: none;
    }

    .quote-block span {
      display: block;
      margin-bottom: 0.6rem;
      font-style: normal;
      font-weight: 500;
      color: #b9a9ff;
      letter-spacing: 0.3px;
    }

    /* tech stack grid */
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      justify-content: center;
      margin: 2rem 0;
    }

    .tech-item {
      background: rgba(255, 255, 255, 0.03);
      border-radius: 20px;
      padding: 0.7rem 1.4rem;
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 500;
      border: 1px solid rgba(255, 255, 255, 0.05);
      transition: all 0.25s;
      font-size: 0.95rem;
    }

    .tech-item i {
      font-size: 1.4rem;
      width: 24px;
      color: #a78bfa;
    }

    .tech-item:hover {
      background: rgba(167, 139, 250, 0.12);
      border-color: #a78bfa;
      transform: scale(1.05);
      box-shadow: 0 0 20px rgba(167, 139, 250, 0.2);
    }

    /* stats cards */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
      margin: 2rem 0;
    }

    .stat-card {
      background: rgba(0, 0, 0, 0.4);
      border-radius: 24px;
      padding: 1rem 1.5rem;
      border: 1px solid rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(4px);
      transition: 0.2s;
      flex: 1 1 200px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .stat-card img {
      max-width: 100%;
      height: auto;
      border-radius: 12px;
      filter: drop-shadow(0 0 12px rgba(120, 90, 255, 0.3));
    }

    /* snake graph */
    .snake-container {
      display: flex;
      justify-content: center;
      padding: 1rem 0;
    }

    .snake-container picture img {
      max-width: 100%;
      height: auto;
      border-radius: 24px;
      box-shadow: 0 0 40px rgba(120, 90, 255, 0.2);
      border: 1px solid rgba(255, 255, 255, 0.05);
      background: rgba(0, 0, 0, 0.3);
      padding: 8px;
    }

    /* contact section */
    .contact-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      justify-content: center;
      margin-top: 1.5rem;
    }

    .contact-link {
      display: flex;
      align-items: center;
      gap: 10px;
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 100px;
      padding: 0.8rem 1.8rem;
      text-decoration: none;
      color: #dfe7ff;
      font-weight: 500;
      transition: all 0.25s;
      backdrop-filter: blur(4px);
    }

    .contact-link i {
      font-size: 1.3rem;
      color: #a78bfa;
    }

    .contact-link:hover {
      background: rgba(167, 139, 250, 0.15);
      border-color: #a78bfa;
      transform: translateY(-4px);
      box-shadow: 0 15px 25px -10px rgba(167, 139, 250, 0.4);
    }

    /* footer */
    .footer-note {
      text-align: center;
      margin-top: 3rem;
      color: #95a6c9;
      font-size: 0.95rem;
      letter-spacing: 0.3px;
    }

    .footer-note strong {
      color: #c7b3ff;
      font-weight: 600;
    }

    /* avatar decoration */
    .avatar-glow {
      display: flex;
      justify-content: center;
      margin-bottom: 1rem;
    }

    .avatar-glow img {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid rgba(167, 139, 250, 0.6);
      box-shadow: 0 0 40px rgba(167, 139, 250, 0.4);
      transition: 0.3s;
    }

    .avatar-glow img:hover {
      transform: scale(1.02);
      box-shadow: 0 0 60px rgba(167, 139, 250, 0.8);
    }

    /* responsive */
    @media (max-width: 680px) {
      body { padding: 1rem; }
      h1 { font-size: 2.2rem; }
      h2 { font-size: 1.5rem; }
      .glass-card { padding: 1.5rem; }
      .badge-container { justify-content: center; }
      .subhead { font-size: 1rem; padding-left: 1rem; }
      .stats-row { gap: 1rem; }
      .contact-link { padding: 0.6rem 1.2rem; font-size: 0.9rem; }
    }

    /* scroll reveal */
    [data-aos] {
      transition-timing-function: cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    /* separator line gradient */
    .glow-sep {
      height: 2px;
      background: linear-gradient(90deg, transparent, #a78bfa, #6e8aff, #a78bfa, transparent);
      margin: 2.5rem 0;
      border: none;
      opacity: 0.5;
      border-radius: 100%;
      filter: blur(0.5px);
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- main card -->
    <div class="glass-card" data-aos="fade-up" data-aos-duration="800">
      <!-- avatar optional: if you have an avatar, uncomment and set src -->
      <!--
      <div class="avatar-glow">
        <img src="https://github.com/Morrow7.png" alt="Morrow avatar" />
      </div>
      -->
      <div style="text-align: center;">
        <h1>Hi, I'm Morrow <span style="display: inline-block; animation: wave 1.5s infinite; transform-origin: 70% 70%;">👋</span></h1>
        <div class="subhead" style="margin-top: 1rem;">
          A 19-year-old developer passionate about coding, self-learning, and building meaningful things.
        </div>
      </div>

      <!-- badge row -->
      <div class="badge-container">
        <span class="badge"><i class="fab fa-github"></i> GitHub followers · 1.2k</span>
        <span class="badge"><i class="fas fa-star"></i> Stars · 340</span>
        <span class="badge"><i class="far fa-eye"></i> Profile views · 12k</span>
      </div>

      <hr class="glow-sep" />

      <!-- about me -->
      <h2 data-aos="fade-right"><i class="fas fa-user-astronaut"></i> About Me</h2>
      <ul style="list-style: none; display: flex; flex-direction: column; gap: 0.9rem; margin-bottom: 2rem;">
        <li style="display: flex; gap: 12px;"><span style="color: #a78bfa; font-size: 1.2rem;">🎂</span> <strong>19 years old</strong> · Continuous Learner & Tech Enthusiast.</li>
        <li style="display: flex; gap: 12px;"><span style="color: #a78bfa; font-size: 1.2rem;">💻</span> Focused on <strong>Front-end / Full-stack Development</strong> and exploring <strong>CS Fundamentals</strong>.</li>
        <li style="display: flex; gap: 12px;"><span style="color: #a78bfa; font-size: 1.2rem;">🌱</span> Passionate about <strong>clean code, open source, and elegant UI/UX design</strong>.</li>
        <li style="display: flex; gap: 12px;"><span style="color: #a78bfa; font-size: 1.2rem;">🚀</span> Currently diving deep into <strong>Next.js</strong>, <strong>NestJS</strong>, and AI-driven development.</li>
        <li style="display: flex; gap: 12px;"><span style="color: #a78bfa; font-size: 1.2rem;">🤝</span> Always excited to connect with developers who love building cool, real-world things.</li>
      </ul>

      <!-- quote -->
      <div class="quote-block" data-aos="fade-left">
        <span>✨ A FEW WORDS I LIKE</span>
        > Open your soul to welcome another soul.<br>
        > Money can't buy natural elegance, and status doesn't always bestow noble qualities.<br>
        > Good upbringing will naturally shine through; external deficiencies are secondary.<br>
        > Hold the torch in your hand tightly.<br>
        > Illuminate your own soul first, understand your depth and shallowness, your vanity and generosity, and discover your own meaning.
      </div>

      <hr class="glow-sep" />

      <!-- featured project -->
      <h2 data-aos="fade-right"><i class="fas fa-rocket"></i> Featured Project & Learning</h2>
      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 1.5rem; margin-bottom: 1.8rem;">
        <div class="glass-card" style="padding: 1.5rem; border-radius: 24px; background: rgba(255,255,255,0.02);">
          <h3><i class="fab fa-react" style="color: #61dafb; margin-right: 8px;"></i> ⚡ Frameworks & Engineering</h3>
          <ul style="list-style: none; margin-top: 1rem;">
            <li style="margin-bottom: 0.7rem;"><strong>Next.js</strong> — high-performance full-stack React framework.</li>
            <li><strong>NestJS</strong> — TypeScript backend with modular architecture.</li>
          </ul>
        </div>
        <div class="glass-card" style="padding: 1.5rem; border-radius: 24px; background: rgba(255,255,255,0.02);">
          <h3><i class="fas fa-code-branch" style="color: #42b883; margin-right: 8px;"></i> 👥 Open Source</h3>
          <ul style="list-style: none; margin-top: 1rem;">
            <li><strong>Vue-Bits</strong> — ported React-bits components to Vue, with comprehensive examples & docs.</li>
          </ul>
        </div>
      </div>

      <hr class="glow-sep" />

      <!-- github stats & languages -->
      <h2 data-aos="fade-right"><i class="fas fa-chart-line"></i> GitHub Activity</h2>
      <div class="stats-row">
        <div class="stat-card" data-aos="zoom-in">
          <img src="https://github-readme-stats.vercel.app/api?username=Morrow7&show_icons=true&theme=dracula&hide_border=true&bg_color=0a0c10&title_color=a78bfa&icon_color=a78bfa&text_color=c9d1d9" alt="GitHub Stats" />
        </div>
        <div class="stat-card" data-aos="zoom-in" data-aos-delay="100">
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Morrow7&layout=compact&theme=dracula&hide_border=true&bg_color=0a0c10&title_color=a78bfa&text_color=c9d1d9" alt="Top Languages" />
        </div>
      </div>

      <hr class="glow-sep" />

      <!-- tech stack -->
      <h2 data-aos="fade-right"><i class="fas fa-microchip"></i> Tech Stack</h2>
      <div class="tech-grid">
        <div class="tech-item"><i class="fab fa-js"></i> JavaScript</div>
        <div class="tech-item"><i class="fab fa-ts"></i> TypeScript</div>
        <div class="tech-item"><i class="fab fa-vuejs"></i> Vue</div>
        <div class="tech-item"><i class="fab fa-react"></i> React</div>
        <div class="tech-item"><i class="fas fa-n"></i> Next.js</div>
        <div class="tech-item"><i class="fab fa-tailwind"></i> Tailwind</div>
        <div class="tech-item"><i class="fab fa-python"></i> Python</div>
        <div class="tech-item"><i class="fab fa-java"></i> Java</div>
        <div class="tech-item"><i class="fas fa-c"></i> C++</div>
        <div class="tech-item"><i class="fas fa-cat"></i> NestJS</div>
        <div class="tech-item"><i class="fas fa-leaf"></i> Spring</div>
        <div class="tech-item"><i class="fab fa-node-js"></i> Node.js</div>
        <div class="tech-item"><i class="fas fa-database"></i> MySQL</div>
        <div class="tech-item"><i class="fas fa-bolt"></i> Supabase</div>
        <div class="tech-item"><i class="fas fa-cloud"></i> Railway</div>
        <div class="tech-item"><i class="fas fa-memory"></i> Redis</div>
        <div class="tech-item"><i class="fab fa-git-alt"></i> Git</div>
        <div class="tech-item"><i class="fab fa-github"></i> GitHub</div>
        <div class="tech-item"><i class="fas fa-code"></i> VS Code</div>
        <div class="tech-item"><i class="fas fa-laptop-code"></i> IntelliJ</div>
        <div class="tech-item"><i class="fab fa-linux"></i> Linux</div>
        <div class="tech-item"><i class="fab fa-docker"></i> Docker</div>
        <div class="tech-item"><i class="fas fa-robot"></i> OpenAI</div>
        <div class="tech-item"><i class="fas fa-wand-magic-sparkles"></i> AI Tools</div>
      </div>

      <hr class="glow-sep" />

      <!-- snake contribution -->
      <h2 data-aos="fade-right"><i class="fas fa-snake"></i> Contribution Graph</h2>
      <div class="snake-container" data-aos="fade-up">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="./assets/contribution-snake-dark.svg" />
          <source media="(prefers-color-scheme: light)" srcset="./assets/contribution-snake.svg" />
          <img alt="github-snake" src="./assets/contribution-snake.svg" style="max-width: 100%; border-radius: 16px;" />
        </picture>
      </div>
      <p style="text-align: center; font-size: 0.9rem; color: #8b9bc2; margin-top: 0.5rem;"><i class="fas fa-arrow-up"></i> snake eating my contributions</p>

      <hr class="glow-sep" />

      <!-- contact -->
      <h2 data-aos="fade-right"><i class="fas fa-paper-plane"></i> Get in Touch</h2>
      <div class="contact-links">
        <a href="mailto:susu997y@gmail.com" class="contact-link"><i class="fas fa-envelope"></i> susu997y@gmail.com</a>
        <a href="https://x.com/Morrow992887" target="_blank" class="contact-link"><i class="fab fa-twitter"></i> @Morrow992887</a>
        <a href="https://github.com/Morrow7" target="_blank" class="contact-link"><i class="fab fa-github"></i> @Morrow7</a>
      </div>

      <div class="footer-note">
        <i class="fas fa-code"></i> <strong>Thanks for visiting my profile ✨</strong> <br>
        Let's grow, collaborate, and build a better world of code 🚀
      </div>
    </div>
  </div>

  <!-- AOS script -->
  <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
  <script>
    AOS.init({
      duration: 700,
      once: true,
      offset: 40,
      easing: 'ease-out-quad'
    });
  </script>
  <!-- add wave animation for emoji -->
  <style>
    @keyframes wave {
      0% { transform: rotate(0deg); }
      20% { transform: rotate(14deg); }
      40% { transform: rotate(-8deg); }
      60% { transform: rotate(14deg); }
      80% { transform: rotate(-4deg); }
      100% { transform: rotate(0deg); }
    }
    .glow-sep {
      transition: opacity 0.3s;
    }
  </style>
</body>
</html>
