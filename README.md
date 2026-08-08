<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sadiq Aliquliyev — Data Analyst</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a;
    --surface: #111827;
    --surface2: #1a2235;
    --accent: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #10b981;
    --text: #e2e8f0;
    --muted: #64748b;
    --border: rgba(255,255,255,0.07);
    --glow: 0 0 40px rgba(0, 212, 255, 0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    overflow-x: hidden;
  }

  /* GRID BACKGROUND */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* NAVBAR */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 60px;
    background: rgba(10,14,26,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: 'Space Mono', monospace;
    font-size: 1rem;
    color: var(--accent);
    letter-spacing: 2px;
  }

  .nav-links {
    display: flex;
    gap: 36px;
    list-style: none;
  }

  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.85rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--accent); }

  /* HERO */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 120px 60px 80px;
    z-index: 1;
  }

  .hero-content { max-width: 760px; }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 0.78rem;
    color: var(--accent);
    background: rgba(0,212,255,0.08);
    border: 1px solid rgba(0,212,255,0.2);
    padding: 6px 16px;
    border-radius: 100px;
    margin-bottom: 32px;
    letter-spacing: 1px;
  }

  .hero-tag::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(0.8); }
  }

  .hero h1 {
    font-size: clamp(2.8rem, 6vw, 5rem);
    font-weight: 700;
    line-height: 1.05;
    letter-spacing: -2px;
    margin-bottom: 8px;
  }

  .hero h1 .name {
    background: linear-gradient(135deg, #ffffff 0%, #00d4ff 50%, #7c3aed 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-role {
    font-family: 'Space Mono', monospace;
    font-size: 1rem;
    color: var(--accent2);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 28px;
    opacity: 0.9;
  }

  .hero-desc {
    font-size: 1.1rem;
    color: var(--muted);
    line-height: 1.75;
    max-width: 560px;
    margin-bottom: 44px;
  }

  .hero-desc strong { color: var(--text); }

  .hero-cta {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }

  .btn-primary {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--accent);
    color: #0a0e1a;
    padding: 14px 28px;
    border-radius: 8px;
    font-weight: 600;
    font-size: 0.9rem;
    text-decoration: none;
    letter-spacing: 0.5px;
    transition: all 0.2s;
    box-shadow: 0 0 30px rgba(0,212,255,0.3);
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 50px rgba(0,212,255,0.5);
  }

  .btn-secondary {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: transparent;
    color: var(--text);
    padding: 14px 28px;
    border-radius: 8px;
    font-weight: 500;
    font-size: 0.9rem;
    text-decoration: none;
    border: 1px solid var(--border);
    transition: all 0.2s;
  }

  .btn-secondary:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  /* FLOATING STATS */
  .hero-stats {
    position: absolute;
    right: 80px;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 20px 24px;
    text-align: center;
    min-width: 130px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s;
  }

  .stat-card:hover { transform: translateX(-6px); }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
  }

  .stat-card:nth-child(1)::before { background: var(--accent); }
  .stat-card:nth-child(2)::before { background: var(--accent2); }
  .stat-card:nth-child(3)::before { background: var(--accent3); }

  .stat-num {
    font-family: 'Space Mono', monospace;
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--text);
    display: block;
  }

  .stat-label {
    font-size: 0.72rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-top: 4px;
  }

  /* SECTIONS */
  section {
    position: relative;
    z-index: 1;
    padding: 100px 60px;
    max-width: 1200px;
    margin: 0 auto;
  }

  .section-eyebrow {
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .section-title {
    font-size: clamp(1.8rem, 3vw, 2.6rem);
    font-weight: 700;
    letter-spacing: -1px;
    margin-bottom: 60px;
    color: var(--text);
  }

  .section-title span { color: var(--accent); }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 16px;
  }

  .skill-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 20px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    transition: all 0.25s;
    cursor: default;
  }

  .skill-item:hover {
    border-color: var(--accent);
    background: var(--surface2);
    transform: translateY(-4px);
    box-shadow: var(--glow);
  }

  .skill-icon {
    font-size: 1.6rem;
  }

  .skill-name {
    font-weight: 600;
    font-size: 0.95rem;
    color: var(--text);
  }

  .skill-bar {
    height: 3px;
    background: rgba(255,255,255,0.07);
    border-radius: 2px;
    overflow: hidden;
  }

  .skill-fill {
    height: 100%;
    border-radius: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }

  /* CERTS */
  .certs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 24px;
  }

  .cert-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 32px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
  }

  .cert-card:hover {
    transform: translateY(-6px);
    border-color: rgba(0,212,255,0.4);
    box-shadow: 0 20px 60px rgba(0,0,0,0.4), var(--glow);
  }

  .cert-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at top right, rgba(0,212,255,0.05), transparent 60%);
    pointer-events: none;
  }

  .cert-org {
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .cert-card:nth-child(1) .cert-org { color: var(--accent); }
  .cert-card:nth-child(2) .cert-org { color: var(--accent3); }
  .cert-card:nth-child(3) .cert-org { color: var(--accent2); }

  .cert-name {
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 12px;
    line-height: 1.3;
  }

  .cert-desc {
    font-size: 0.875rem;
    color: var(--muted);
    line-height: 1.65;
  }

  .cert-badge {
    position: absolute;
    top: 20px; right: 20px;
    font-size: 1.8rem;
  }

  /* EDUCATION */
  .edu-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 40px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 20px;
    align-items: start;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .edu-card::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 3px;
    background: linear-gradient(180deg, var(--accent), var(--accent2));
  }

  .edu-card:hover {
    border-color: rgba(0,212,255,0.3);
    box-shadow: var(--glow);
  }

  .edu-uni {
    font-size: 0.8rem;
    color: var(--accent);
    letter-spacing: 2px;
    text-transform: uppercase;
    font-family: 'Space Mono', monospace;
    margin-bottom: 8px;
  }

  .edu-degree {
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 8px;
  }

  .edu-detail {
    color: var(--muted);
    font-size: 0.9rem;
    line-height: 1.6;
  }

  .edu-status {
    background: rgba(16,185,129,0.1);
    border: 1px solid rgba(16,185,129,0.3);
    color: var(--accent3);
    padding: 6px 16px;
    border-radius: 100px;
    font-size: 0.78rem;
    font-family: 'Space Mono', monospace;
    white-space: nowrap;
  }

  /* CONTACT */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
  }

  .contact-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 28px;
    display: flex;
    align-items: center;
    gap: 18px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.25s;
  }

  .contact-card:hover {
    border-color: var(--accent);
    transform: translateY(-3px);
    box-shadow: var(--glow);
  }

  .contact-icon {
    width: 48px; height: 48px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.3rem;
    flex-shrink: 0;
  }

  .contact-icon.blue { background: rgba(0,212,255,0.1); }
  .contact-icon.purple { background: rgba(124,58,237,0.1); }
  .contact-icon.green { background: rgba(16,185,129,0.1); }

  .contact-label {
    font-size: 0.75rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 4px;
  }

  .contact-value {
    font-size: 0.9rem;
    font-weight: 500;
    word-break: break-all;
  }

  /* DATA VISUAL */
  .data-visual {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 32px;
    margin-bottom: 60px;
    font-family: 'Space Mono', monospace;
    font-size: 0.8rem;
    color: var(--accent3);
    line-height: 1.8;
    overflow: hidden;
    position: relative;
  }

  .data-visual::after {
    content: '';
    position: absolute;
    right: 0; top: 0; bottom: 0;
    width: 200px;
    background: linear-gradient(90deg, transparent, var(--surface));
  }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: var(--border);
    margin: 0 60px;
  }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 40px 60px;
    color: var(--muted);
    font-size: 0.82rem;
    font-family: 'Space Mono', monospace;
    position: relative;
    z-index: 1;
  }

  footer span { color: var(--accent); }

  /* SCROLL ANIMATIONS */
  .fade-up {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-up.visible {
    opacity: 1;
    transform: translateY(0);
  }

  @media (max-width: 900px) {
    nav { padding: 18px 24px; }
    .nav-links { display: none; }
    .hero { padding: 100px 24px 60px; flex-direction: column; }
    .hero-stats {
      position: static;
      transform: none;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 40px;
    }
    section { padding: 70px 24px; }
    .divider { margin: 0 24px; }
    footer { padding: 30px 24px; }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo">SA_PORTFOLIO</div>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#certs">Certificates</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<div class="hero">
  <div class="hero-content">
    <div class="hero-tag">Available · Data Analyst</div>
    <h1><span class="name">Sadiq<br>Aliquliyev</span></h1>
    <p class="hero-role">// Data Analyst · Computer Engineer</p>
    <p class="hero-desc">
      Computer Engineering student at <strong>Azerbaijan University</strong>.
      A passionate junior data analyst who turns raw data into meaningful insights.
      Graduate of Code Academy's Data Analytics program, certified by <strong>Google</strong> and <strong>Meta</strong>.
    </p>
    <div class="hero-cta">
      <a href="https://www.linkedin.com/in/sadig-aliguliyev-6b2562420" target="_blank" class="btn-primary">
        LinkedIn Profile →
      </a>
      <a href="#contact" class="btn-secondary">Get In Touch</a>
    </div>
  </div>

  <div class="hero-stats">
    <div class="stat-card">
      <span class="stat-num">2</span>
      <div class="stat-label">Certificates</div>
    </div>
    <div class="stat-card">
      <span class="stat-num">6+</span>
      <div class="stat-label">Technical Skills</div>
    </div>
    <div class="stat-card">
      <span class="stat-num">∞</span>
      <div class="stat-label">Drive to Learn</div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- SKILLS -->
<section id="skills">
  <div class="fade-up">
    <div class="section-eyebrow">// 01 — technical arsenal</div>
    <h2 class="section-title">Skills & <span>Tools</span></h2>
  </div>

  <div class="data-visual fade-up">
    SELECT skill, proficiency FROM sadiq_profile WHERE category = 'data_analytics' ORDER BY power DESC;
  </div>

  <div class="skills-grid fade-up">
    <div class="skill-item">
      <div class="skill-icon">📊</div>
      <div class="skill-name">Excel</div>
      <div class="skill-bar"><div class="skill-fill" style="width:90%"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-icon">🗄️</div>
      <div class="skill-name">MySQL</div>
      <div class="skill-bar"><div class="skill-fill" style="width:82%"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-icon">📈</div>
      <div class="skill-name">R Language</div>
      <div class="skill-bar"><div class="skill-fill" style="width:78%"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-icon">📐</div>
      <div class="skill-name">Statistics</div>
      <div class="skill-bar"><div class="skill-fill" style="width:85%"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-icon">🧹</div>
      <div class="skill-name">Data Cleaning</div>
      <div class="skill-bar"><div class="skill-fill" style="width:88%"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-icon">⚙️</div>
      <div class="skill-name">Data Manipulation</div>
      <div class="skill-bar"><div class="skill-fill" style="width:84%"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-icon">🔍</div>
      <div class="skill-name">Data Analytics</div>
      <div class="skill-bar"><div class="skill-fill" style="width:87%"></div></div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CERTS -->
<section id="certs">
  <div class="fade-up">
    <div class="section-eyebrow">// 02 — certifications</div>
    <h2 class="section-title">Professional <span>Recognition</span></h2>
  </div>

  <div class="certs-grid fade-up">
    <div class="cert-card">
      <div class="cert-badge">🏅</div>
      <div class="cert-org">Google</div>
      <div class="cert-name">AI Essentials Certificate</div>
      <div class="cert-desc">
        Google's official certification covering the fundamentals of artificial intelligence, generative AI tools, and practical AI usage in professional environments.
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-badge">🎖️</div>
      <div class="cert-org">Meta</div>
      <div class="cert-name">Data Analytics Professional Certificate</div>
      <div class="cert-desc">
        Meta's professional certification covering data analysis, visualization, statistical methods, and business intelligence insights.
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-badge">🎓</div>
      <div class="cert-org">Code Academy Azerbaijan</div>
      <div class="cert-name">Data Analytics Program</div>
      <div class="cert-desc">
        Successfully completed an intensive data analytics program at Azerbaijan's leading technology academy.
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- EDUCATION -->
<section id="education">
  <div class="fade-up">
    <div class="section-eyebrow">// 03 — education</div>
    <h2 class="section-title">Academic <span>Journey</span></h2>
  </div>

  <div class="edu-card fade-up">
    <div>
      <div class="edu-uni">Azerbaijan University</div>
      <div class="edu-degree">Computer Engineering</div>
      <p class="edu-detail">
        Bachelor's degree program in Computer Engineering. Building expertise in programming, algorithms,
        database systems, and data science through rigorous academic coursework.
      </p>
    </div>
    <div class="edu-status">In Progress</div>
  </div>
</section>

<div class="divider"></div>

<!-- ABOUT -->
<section id="about">
  <div class="fade-up">
    <div class="section-eyebrow">// 04 — about me</div>
    <h2 class="section-title">Who <span>Am I?</span></h2>
  </div>

  <div class="fade-up" style="display:flex; flex-direction:column; gap: 28px;">
    <div style="background:var(--surface); border:1px solid var(--border); border-left: 3px solid var(--accent); border-radius:16px; padding:44px 48px; position:relative; overflow:hidden;">
      <div style="position:absolute; top:24px; right:28px; font-size:3rem; opacity:0.08;">❝</div>
      <h3 style="font-size:1rem; font-family:'Space Mono',monospace; color:var(--accent); letter-spacing:2px; text-transform:uppercase; margin-bottom:20px;">My Story</h3>
      <p style="color:#cbd5e1; line-height:2; font-size:1.05rem; max-width:860px;">
        My relationship with data began with a simple question: <em style="color:var(--accent);">"What do these numbers actually mean?"</em> — While studying Computer Engineering at Azerbaijan University, I realized that technology is not just about writing code — it's about reading data correctly, asking the right questions, and finding real answers. That realization led me to data analytics. I successfully completed Code Academy's intensive data analytics program and earned both Google's AI Essentials and Meta's Data Analytics certifications. These aren't just credentials — behind each one stand dozens of hours of hands-on work, analyses on real datasets, and problems I solved from scratch. From Excel to MySQL, from R programming to statistical modeling, every tool is a language to me — a way to speak the language of data fluently.
      </p>
    </div>

    <div style="background:var(--surface); border:1px solid var(--border); border-left: 3px solid var(--accent2); border-radius:16px; padding:44px 48px; position:relative; overflow:hidden;">
      <div style="position:absolute; top:24px; right:28px; font-size:3rem; opacity:0.08;">🎯</div>
      <h3 style="font-size:1rem; font-family:'Space Mono',monospace; color:var(--accent2); letter-spacing:2px; text-transform:uppercase; margin-bottom:20px;">Why Me?</h3>
      <p style="color:#cbd5e1; line-height:2; font-size:1.05rem; max-width:860px;">
        Being young means many things — a high learning velocity, fast adaptation to new technologies, and most importantly, the ability to approach every problem with fresh eyes. I'm not just someone who knows the tools; I'm someone who understands <em style="color:var(--accent2);">why</em> to use them. From data cleaning to data manipulation, my goal at every step is the same: separate the signal from the noise, turn complexity into clarity. I thrive working in teams, asking questions, and seeing answers make a difference not just in a spreadsheet — but in the real world. Every new project is not just a task to me — it's an opportunity to grow. If you're looking to turn data into something meaningful together, reach out — I'm ready.
      </p>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CONTACT -->
<section id="contact">
  <div class="fade-up">
    <div class="section-eyebrow">// 05 — contact</div>
    <h2 class="section-title">Get In <span>Touch</span></h2>
  </div>

  <div class="contact-grid fade-up">
    <a href="https://www.linkedin.com/in/sadig-aliguliyev-6b2562420" target="_blank" class="contact-card">
      <div class="contact-icon purple">💼</div>
      <div>
        <div class="contact-label">LinkedIn</div>
        <div class="contact-value">Sadiq Aliquliyev</div>
      </div>
    </a>
    <a href="mailto:sadigra@code.edu.az" class="contact-card">
      <div class="contact-icon blue">📧</div>
      <div>
        <div class="contact-label">Email</div>
        <div class="contact-value">sadigra@code.edu.az</div>
      </div>
    </a>
    <a href="tel:+994708765363" class="contact-card">
      <div class="contact-icon green">📱</div>
      <div>
        <div class="contact-label">Phone</div>
        <div class="contact-value">+994 70 876 53 63</div>
      </div>
    </a>
  </div>
</section>

<footer>
  <p>© 2025 <span>Sadiq Aliquliyev</span> · Data Analyst · Azerbaijan</p>
  <p style="margin-top:8px; opacity:0.5;">From data to insight</p>
</footer>

<script>
  // Intersection Observer for fade-up animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => {
          entry.target.classList.add('visible');
        }, i * 100);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Animate skill bars on scroll
  const skillObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.querySelectorAll('.skill-fill').forEach(bar => {
          const w = bar.style.width;
          bar.style.width = '0%';
          setTimeout(() => { bar.style.transition = 'width 1s ease'; bar.style.width = w; }, 200);
        });
        skillObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.3 });

  const skillGrid = document.querySelector('.skills-grid');
  if (skillGrid) skillObserver.observe(skillGrid);
</script>
</body>
</html>
