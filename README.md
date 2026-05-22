<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sohaib | AI Automation Expert</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=Cabinet+Grotesk:wght@400;500;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #040811;
    --surface: #080f1e;
    --card: #0d1829;
    --border: rgba(0,255,180,0.12);
    --accent: #00ffb3;
    --accent2: #00c8ff;
    --accent3: #7c3aed;
    --text: #e8f4f0;
    --muted: #6b8c82;
    --danger: #ff4d6d;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    overflow-x: hidden;
    cursor: none;
  }

  /* ── CUSTOM CURSOR ── */
  .cursor {
    width: 12px; height: 12px;
    background: var(--accent);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none; z-index: 9999;
    transform: translate(-50%,-50%);
    transition: transform 0.1s, background 0.2s;
    box-shadow: 0 0 20px var(--accent);
  }
  .cursor-ring {
    width: 40px; height: 40px;
    border: 1.5px solid var(--accent);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none; z-index: 9998;
    transform: translate(-50%,-50%);
    transition: transform 0.15s ease-out, opacity 0.2s;
    opacity: 0.5;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.035'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0; opacity: 0.4;
  }

  /* ── GRID BACKGROUND ── */
  body::after {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(0,255,179,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,179,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none; z-index: 0;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 4rem;
    background: rgba(4,8,17,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800; font-size: 1.3rem;
    color: var(--accent);
    letter-spacing: -0.5px;
  }
  .nav-logo span { color: var(--text); }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--accent); }
  .nav-cta {
    background: transparent;
    border: 1px solid var(--accent);
    color: var(--accent);
    padding: 0.5rem 1.4rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    cursor: none;
    transition: background 0.2s, color 0.2s;
  }
  .nav-cta:hover { background: var(--accent); color: var(--bg); }

  /* ── HERO ── */
  .hero {
    position: relative; z-index: 1;
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 8rem 4rem 4rem;
    overflow: hidden;
  }
  .hero-glow {
    position: absolute;
    width: 700px; height: 700px;
    background: radial-gradient(circle, rgba(0,255,179,0.08) 0%, transparent 70%);
    top: -100px; right: -200px;
    pointer-events: none;
    animation: pulse 6s ease-in-out infinite;
  }
  .hero-glow2 {
    position: absolute;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(0,200,255,0.06) 0%, transparent 70%);
    bottom: 0; left: -150px;
    pointer-events: none;
    animation: pulse 8s ease-in-out infinite reverse;
  }
  @keyframes pulse { 0%,100%{transform:scale(1);opacity:1;} 50%{transform:scale(1.1);opacity:0.7;} }

  .hero-content { max-width: 700px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: rgba(0,255,179,0.08);
    border: 1px solid rgba(0,255,179,0.2);
    padding: 0.4rem 1rem;
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 2rem;
    animation: fadeInUp 0.8s ease both;
  }
  .badge-dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--accent);
    animation: blink 1.5s ease-in-out infinite;
  }
  @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0.2;} }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: clamp(3rem, 7vw, 5.5rem);
    line-height: 0.95;
    letter-spacing: -3px;
    margin-bottom: 1.5rem;
    animation: fadeInUp 0.8s ease 0.1s both;
  }
  .hero h1 .line-accent { color: var(--accent); }
  .hero h1 .line-dim { color: var(--muted); }

  .hero-sub {
    font-size: 1rem; line-height: 1.7;
    color: var(--muted); max-width: 500px;
    margin-bottom: 2.5rem;
    animation: fadeInUp 0.8s ease 0.2s both;
  }

  .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; animation: fadeInUp 0.8s ease 0.3s both; }
  .btn-primary {
    background: var(--accent);
    color: var(--bg);
    padding: 0.9rem 2rem;
    font-family: 'Syne', sans-serif;
    font-weight: 700; font-size: 0.85rem;
    letter-spacing: 0.05em;
    border: none; cursor: none;
    transition: transform 0.2s, box-shadow 0.2s;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 10px 40px rgba(0,255,179,0.3); }
  .btn-secondary {
    background: transparent;
    color: var(--text); border: 1px solid var(--border);
    padding: 0.9rem 2rem;
    font-family: 'Syne', sans-serif;
    font-weight: 600; font-size: 0.85rem;
    cursor: none; transition: border-color 0.2s, color 0.2s;
  }
  .btn-secondary:hover { border-color: var(--accent); color: var(--accent); }

  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2rem; border-top: 1px solid var(--border);
    animation: fadeInUp 0.8s ease 0.4s both;
  }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-weight: 800; font-size: 2rem;
    color: var(--accent);
  }
  .stat-label { font-size: 0.7rem; color: var(--muted); letter-spacing: 0.1em; text-transform: uppercase; }

  .hero-visual {
    position: absolute; right: 4rem; top: 50%;
    transform: translateY(-50%);
    width: 420px;
    animation: fadeInRight 1s ease 0.3s both;
  }
  .terminal-window {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }
  .terminal-bar {
    background: var(--surface);
    padding: 0.7rem 1rem;
    display: flex; gap: 0.5rem; align-items: center;
    border-bottom: 1px solid var(--border);
  }
  .tbar-dot { width: 10px; height: 10px; border-radius: 50%; }
  .tbar-dot:nth-child(1){background:#ff5f57;}
  .tbar-dot:nth-child(2){background:#ffbd2e;}
  .tbar-dot:nth-child(3){background:#28ca41;}
  .terminal-title { font-size: 0.65rem; color: var(--muted); margin-left: auto; letter-spacing: 0.1em; }
  .terminal-body { padding: 1.2rem; font-size: 0.72rem; line-height: 1.8; }
  .t-green { color: var(--accent); }
  .t-blue { color: var(--accent2); }
  .t-purple { color: #a78bfa; }
  .t-muted { color: var(--muted); }
  .t-line { display: block; }
  .cursor-blink {
    display: inline-block;
    width: 8px; height: 1em;
    background: var(--accent);
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }

  @keyframes fadeInUp { from{opacity:0;transform:translateY(30px);} to{opacity:1;transform:translateY(0);} }
  @keyframes fadeInRight { from{opacity:0;transform:translate(40px,-50%);} to{opacity:1;transform:translate(0,-50%);} }

  /* ── SECTION BASE ── */
  section { position: relative; z-index: 1; padding: 7rem 4rem; }
  .section-label {
    font-size: 0.65rem; letter-spacing: 0.25em; text-transform: uppercase;
    color: var(--accent); margin-bottom: 0.8rem;
    display: flex; align-items: center; gap: 0.8rem;
  }
  .section-label::before {
    content: ''; display: block;
    width: 30px; height: 1px;
    background: var(--accent);
  }
  .section-title {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: clamp(2rem, 4vw, 3rem);
    letter-spacing: -2px;
    line-height: 1.05;
    margin-bottom: 1rem;
  }

  /* ── ABOUT ── */
  .about { background: var(--surface); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center; max-width: 1200px; margin: 0 auto; }
  .about-text p { color: var(--muted); line-height: 1.8; font-size: 0.9rem; margin-bottom: 1.2rem; }
  .info-list { list-style: none; margin-top: 2rem; }
  .info-list li {
    display: flex; gap: 1rem; align-items: center;
    padding: 0.7rem 0; border-bottom: 1px solid var(--border);
    font-size: 0.8rem;
  }
  .info-list li:last-child { border-bottom: none; }
  .info-key { color: var(--accent); min-width: 100px; font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase; }
  .info-val { color: var(--text); }
  .info-val a { color: var(--accent2); text-decoration: none; }
  .info-val a:hover { text-decoration: underline; }

  .skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .skill-pill {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 1rem 1.2rem;
    display: flex; align-items: center; gap: 0.8rem;
    transition: border-color 0.2s, transform 0.2s;
  }
  .skill-pill:hover { border-color: var(--accent); transform: translateX(4px); }
  .skill-icon { font-size: 1.3rem; }
  .skill-name { font-size: 0.78rem; font-family: 'Syne', sans-serif; font-weight: 700; }
  .skill-sub { font-size: 0.65rem; color: var(--muted); }

  /* ── PROJECTS / PORTFOLIO ── */
  .projects { max-width: 1400px; margin: 0 auto; }
  .projects-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; }
  .projects-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    overflow: hidden;
    position: relative;
    transition: border-color 0.3s, transform 0.3s;
    cursor: none;
  }
  .project-card:hover { border-color: var(--accent); transform: translateY(-6px); }
  .project-card:hover .card-overlay { opacity: 1; }
  .card-img {
    width: 100%; aspect-ratio: 4/3;
    object-fit: cover;
    display: block;
    filter: brightness(0.85) saturate(0.8);
    transition: filter 0.3s;
  }
  .project-card:hover .card-img { filter: brightness(1) saturate(1); }
  .card-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to bottom, transparent 30%, rgba(4,8,17,0.95) 100%);
    opacity: 0.7; transition: opacity 0.3s;
  }
  .card-content {
    position: absolute; bottom: 0; left: 0; right: 0;
    padding: 1.5rem;
  }
  .card-tag {
    display: inline-block;
    background: rgba(0,255,179,0.15);
    border: 1px solid rgba(0,255,179,0.3);
    color: var(--accent);
    font-size: 0.6rem; letter-spacing: 0.2em;
    text-transform: uppercase;
    padding: 0.25rem 0.6rem;
    margin-bottom: 0.6rem;
  }
  .card-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700; font-size: 1rem;
    line-height: 1.3; margin-bottom: 0.4rem;
  }
  .card-desc { font-size: 0.7rem; color: rgba(232,244,240,0.6); line-height: 1.5; }

  /* Featured card */
  .project-card.featured { grid-column: span 2; }
  .project-card.featured .card-img { aspect-ratio: 16/7; }

  /* ── SERVICES ── */
  .services-bg { background: var(--surface); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
  .services-inner { max-width: 1200px; margin: 0 auto; }
  .services-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
  .service-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 2rem;
    position: relative; overflow: hidden;
    transition: border-color 0.3s;
  }
  .service-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.3s;
  }
  .service-card:hover { border-color: var(--accent); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-num { font-size: 0.6rem; color: var(--accent); letter-spacing: 0.3em; margin-bottom: 1.5rem; }
  .service-icon { font-size: 2rem; margin-bottom: 1rem; }
  .service-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1.1rem; margin-bottom: 0.8rem; }
  .service-desc { font-size: 0.78rem; color: var(--muted); line-height: 1.7; }
  .service-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 1.2rem; }
  .s-tag {
    font-size: 0.6rem; letter-spacing: 0.1em;
    background: rgba(0,255,179,0.06);
    border: 1px solid rgba(0,255,179,0.15);
    color: var(--muted); padding: 0.2rem 0.5rem;
  }

  /* ── WORKFLOW GALLERY ── */
  .gallery { max-width: 1400px; margin: 0 auto; }
  .gallery-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem; margin-top: 3rem; }
  .gallery-item {
    position: relative; overflow: hidden;
    border: 1px solid var(--border);
    transition: border-color 0.3s;
    cursor: none;
  }
  .gallery-item:hover { border-color: var(--accent); }
  .gallery-item img {
    width: 100%; display: block;
    filter: brightness(0.7) saturate(0.6);
    transition: filter 0.3s, transform 0.4s;
  }
  .gallery-item:hover img { filter: brightness(0.9) saturate(1); transform: scale(1.04); }
  .gallery-item .g-label {
    position: absolute; bottom: 0; left: 0; right: 0;
    padding: 1rem 0.8rem;
    background: linear-gradient(transparent, rgba(4,8,17,0.95));
    font-size: 0.65rem; letter-spacing: 0.1em;
    text-transform: uppercase; color: var(--accent);
  }
  .gallery-item.tall { grid-row: span 2; }
  .gallery-item.tall img { height: 100%; object-fit: cover; }

  /* ── CONTACT ── */
  .contact-bg { background: var(--surface); border-top: 1px solid var(--border); }
  .contact-inner { max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center; }
  .contact-info { }
  .contact-info p { color: var(--muted); font-size: 0.88rem; line-height: 1.8; margin-bottom: 2rem; }
  .contact-links { display: flex; flex-direction: column; gap: 1rem; }
  .contact-link {
    display: flex; align-items: center; gap: 1rem;
    padding: 1rem 1.2rem;
    background: var(--card);
    border: 1px solid var(--border);
    text-decoration: none; color: var(--text);
    transition: border-color 0.2s, transform 0.2s;
  }
  .contact-link:hover { border-color: var(--accent); transform: translateX(6px); }
  .contact-link-icon { font-size: 1.2rem; width: 40px; text-align: center; }
  .contact-link-text { }
  .contact-link-label { font-size: 0.6rem; color: var(--muted); letter-spacing: 0.15em; text-transform: uppercase; }
  .contact-link-val { font-size: 0.82rem; color: var(--accent); }

  .contact-form { }
  .form-group { margin-bottom: 1.2rem; }
  .form-group label { display: block; font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.5rem; }
  .form-group input,
  .form-group textarea {
    width: 100%;
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--text);
    padding: 0.8rem 1rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.82rem;
    outline: none;
    transition: border-color 0.2s;
  }
  .form-group input:focus,
  .form-group textarea:focus { border-color: var(--accent); }
  .form-group textarea { height: 120px; resize: none; }
  .form-submit {
    width: 100%;
    background: var(--accent);
    color: var(--bg);
    border: none; padding: 1rem;
    font-family: 'Syne', sans-serif;
    font-weight: 700; font-size: 0.9rem;
    cursor: none;
    letter-spacing: 0.05em;
    transition: box-shadow 0.2s;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
  }
  .form-submit:hover { box-shadow: 0 0 30px rgba(0,255,179,0.4); }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem 4rem;
    display: flex; justify-content: space-between; align-items: center;
    position: relative; z-index: 1;
    font-size: 0.72rem; color: var(--muted);
  }
  .footer-logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1rem; color: var(--accent); }

  /* ── FLOATING ELEMENTS ── */
  .float-tag {
    position: absolute;
    font-size: 0.6rem; letter-spacing: 0.2em;
    text-transform: uppercase;
    color: rgba(0,255,179,0.25);
    pointer-events: none;
    animation: floatTag 8s ease-in-out infinite;
  }
  @keyframes floatTag { 0%,100%{transform:translateY(0);} 50%{transform:translateY(-15px);} }

  /* ── SCROLL REVEAL ── */
  .reveal { opacity: 0; transform: translateY(40px); transition: opacity 0.7s ease, transform 0.7s ease; }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── TICKER ── */
  .ticker {
    background: var(--accent);
    color: var(--bg);
    padding: 0.6rem 0;
    overflow: hidden;
    position: relative; z-index: 1;
  }
  .ticker-track {
    display: flex; gap: 3rem;
    white-space: nowrap;
    animation: ticker 20s linear infinite;
    font-family: 'Syne', sans-serif;
    font-weight: 700; font-size: 0.75rem;
    letter-spacing: 0.1em; text-transform: uppercase;
  }
  @keyframes ticker { from{transform:translateX(0);} to{transform:translateX(-50%);} }
  .ticker-sep { color: rgba(4,8,17,0.4); }

  /* ── RESPONSIVE ── */
  @media (max-width: 1024px) {
    nav { padding: 1rem 2rem; }
    .hero { padding: 7rem 2rem 4rem; }
    .hero-visual { display: none; }
    section { padding: 5rem 2rem; }
    .about-grid, .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
    .projects-grid { grid-template-columns: 1fr 1fr; }
    .project-card.featured { grid-column: span 2; }
    .services-grid { grid-template-columns: 1fr 1fr; }
    .gallery-grid { grid-template-columns: 1fr 1fr; }
    footer { padding: 2rem; flex-direction: column; gap: 1rem; text-align: center; }
  }
  @media (max-width: 640px) {
    .nav-links { display: none; }
    .projects-grid { grid-template-columns: 1fr; }
    .project-card.featured { grid-column: span 1; }
    .services-grid { grid-template-columns: 1fr; }
    .gallery-grid { grid-template-columns: 1fr 1fr; }
    .skills-grid { grid-template-columns: 1fr; }
    .hero-stats { flex-wrap: wrap; gap: 1.5rem; }
  }
</style>
</head>
<body>

<!-- CURSOR -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">S.<span>AI</span></div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#projects">Work</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button class="nav-cta" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Hire Me</button>
</nav>

<!-- TICKER -->
<div class="ticker" style="position:relative;z-index:1;margin-top:73px;">
  <div class="ticker-track">
    <span>n8n Automation</span><span class="ticker-sep">✦</span>
    <span>AI Workflows</span><span class="ticker-sep">✦</span>
    <span>Lead Generation</span><span class="ticker-sep">✦</span>
    <span>Gmail Automation</span><span class="ticker-sep">✦</span>
    <span>Google Sheets AI</span><span class="ticker-sep">✦</span>
    <span>SerpAPI Integration</span><span class="ticker-sep">✦</span>
    <span>Gemini AI</span><span class="ticker-sep">✦</span>
    <span>OpenRouter AI</span><span class="ticker-sep">✦</span>
    <span>n8n Automation</span><span class="ticker-sep">✦</span>
    <span>AI Workflows</span><span class="ticker-sep">✦</span>
    <span>Lead Generation</span><span class="ticker-sep">✦</span>
    <span>Gmail Automation</span><span class="ticker-sep">✦</span>
    <span>Google Sheets AI</span><span class="ticker-sep">✦</span>
    <span>SerpAPI Integration</span><span class="ticker-sep">✦</span>
    <span>Gemini AI</span><span class="ticker-sep">✦</span>
    <span>OpenRouter AI</span><span class="ticker-sep">✦</span>
  </div>
</div>

<!-- HERO -->
<section class="hero" style="margin-top:-73px;padding-top:130px;">
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="float-tag" style="top:25%;left:2%;animation-delay:0s;">[ AI_EXPERT ]</div>
  <div class="float-tag" style="top:70%;left:45%;animation-delay:3s;">[ AUTOMATION ]</div>

  <div class="hero-content">
    <div class="hero-badge"><div class="badge-dot"></div> Available for Projects — Punjab, Pakistan</div>
    <h1>
      <span class="line-dim">I Build</span><br>
      <span class="line-accent">AI-Powered</span><br>
      <span>Automation</span>
    </h1>
    <p class="hero-sub">Transforming repetitive business processes into intelligent automated workflows using n8n, AI agents, and modern APIs. 2 years of hands-on automation experience.</p>
    <div class="hero-actions">
      <button class="btn-primary" onclick="document.getElementById('projects').scrollIntoView({behavior:'smooth'})">View My Work →</button>
      <button class="btn-secondary" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Get In Touch</button>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">2+</div>
        <div class="stat-label">Years Experience</div>
      </div>
      <div>
        <div class="stat-num">50+</div>
        <div class="stat-label">Workflows Built</div>
      </div>
      <div>
        <div class="stat-num">100%</div>
        <div class="stat-label">Client Satisfaction</div>
      </div>
    </div>
  </div>

  <!-- TERMINAL -->
  <div class="hero-visual">
    <div class="terminal-window">
      <div class="terminal-bar">
        <div class="tbar-dot"></div>
        <div class="tbar-dot"></div>
        <div class="tbar-dot"></div>
        <span class="terminal-title">workflow.js — n8n</span>
      </div>
      <div class="terminal-body">
        <span class="t-line"><span class="t-muted">// AI Automation Engine</span></span>
        <span class="t-line t-green">const</span> <span class="t-blue">workflow</span> = {
        <span class="t-line">&nbsp;&nbsp;<span class="t-purple">trigger</span>: <span class="t-green">'ScheduleEvent'</span>,</span>
        <span class="t-line">&nbsp;&nbsp;<span class="t-purple">ai</span>: <span class="t-green">'GeminiPro'</span>,</span>
        <span class="t-line">&nbsp;&nbsp;<span class="t-purple">actions</span>: [</span>
        <span class="t-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-green">'LeadScraping'</span>,</span>
        <span class="t-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-green">'AIScoring'</span>,</span>
        <span class="t-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-green">'GmailSend'</span>,</span>
        <span class="t-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-green">'SheetsUpdate'</span></span>
        <span class="t-line">&nbsp;&nbsp;]</span>
        }
        <span class="t-line">&nbsp;</span>
        <span class="t-line"><span class="t-muted">// Executing...</span></span>
        <span class="t-line"><span class="t-green">✓ Success</span> <span class="t-muted">in 1.524s</span></span>
        <span class="t-line"><span class="t-blue">$</span> <span class="cursor-blink"></span></span>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-grid">
    <div class="about-text reveal">
      <div class="section-label">About Me</div>
      <h2 class="section-title">The Guy Who<br>Automates<br><span style="color:var(--accent)">Everything</span></h2>
      <p>I'm an AI Automation Expert based in Punjab, Pakistan with 2 years of specialized experience building intelligent workflow systems using n8n, Google Gemini, OpenRouter, and a wide range of API integrations.</p>
      <p>From automated lead generation pipelines to AI-powered email workflows and content creation systems — I design automations that save hours of manual work daily.</p>
      <ul class="info-list">
        <li><span class="info-key">Phone</span><span class="info-val"><a href="tel:+923417595930">+92 341 759 5930</a></span></li>
        <li><span class="info-key">Email</span><span class="info-val"><a href="mailto:sohaib9530@gmail.com">sohaib9530@gmail.com</a></span></li>
        <li><span class="info-key">Location</span><span class="info-val">Punjab, Pakistan</span></li>
        <li><span class="info-key">Experience</span><span class="info-val">2 Years in AI Automation</span></li>
        <li><span class="info-key">Platform</span><span class="info-val">n8n Cloud (sbzk.app.n8n.cloud)</span></li>
      </ul>
    </div>
    <div class="skills-grid reveal" style="transition-delay:0.15s">
      <div class="skill-pill">
        <div class="skill-icon">⚡</div>
        <div><div class="skill-name">n8n Cloud</div><div class="skill-sub">Workflow Automation</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">🤖</div>
        <div><div class="skill-name">AI Agents</div><div class="skill-sub">LLM Integration</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">🔍</div>
        <div><div class="skill-name">SerpAPI</div><div class="skill-sub">Lead Scraping</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">✉️</div>
        <div><div class="skill-name">Gmail API</div><div class="skill-sub">Email Automation</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">📊</div>
        <div><div class="skill-name">Google Sheets</div><div class="skill-sub">Data Management</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">🧠</div>
        <div><div class="skill-name">Gemini AI</div><div class="skill-sub">Content & Analysis</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">🌐</div>
        <div><div class="skill-name">HTTP/REST APIs</div><div class="skill-sub">Integrations</div></div>
      </div>
      <div class="skill-pill">
        <div class="skill-icon">🎬</div>
        <div><div class="skill-name">Shotstack</div><div class="skill-sub">Video Automation</div></div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects" style="padding:7rem 4rem;">
  <div class="projects reveal">
    <div class="projects-header">
      <div>
        <div class="section-label">Portfolio</div>
        <h2 class="section-title">Live Automations<br>I've <span style="color:var(--accent)">Built</span></h2>
      </div>
      <p style="color:var(--muted);font-size:0.8rem;max-width:250px;text-align:right;">Real workflows. Real results. Running in production.</p>
    </div>

    <div class="projects-grid">
      <!-- Featured: Quran Video Auto-Post -->
      <div class="project-card featured">
        <img class="card-img" src="/mnt/user-data/uploads/1000269023.jpg" alt="Quran Video Automation Workflow">
        <div class="card-overlay"></div>
        <div class="card-content">
          <div class="card-tag">✦ Featured Project</div>
          <div class="card-title">Automated Quran Video Creator & Poster</div>
          <div class="card-desc">Scheduled n8n workflow that fetches Quranic verses via API, grabs Pexels videos, generates audio via Al-Quran API, stitches everything into a video using Shotstack, then auto-posts — fully hands-free.</div>
        </div>
      </div>

      <!-- AI News Classifier -->
      <div class="project-card">
        <img class="card-img" src="/mnt/user-data/uploads/1000269021.jpg" alt="AI News Automation">
        <div class="card-overlay"></div>
        <div class="card-content">
          <div class="card-tag">AI Agent</div>
          <div class="card-title">AI News Monitor & Email Classifier</div>
          <div class="card-desc">SerpAPI fetches Google News daily. Gemini AI classifies relevance and auto-sends email alerts or appends to Sheets.</div>
        </div>
      </div>

      <!-- Lead Gen -->
      <div class="project-card">
        <img class="card-img" src="/mnt/user-data/uploads/1000268760.jpg" alt="Lead Generation Sheet">
        <div class="card-overlay"></div>
        <div class="card-content">
          <div class="card-tag">Lead Gen</div>
          <div class="card-title">AI-Scored Lead Generation System</div>
          <div class="card-desc">Google Maps scraping via SerpAPI, AI scoring with OpenRouter, auto-populated Google Sheet with Name, Phone, Rating, Website & AI Score.</div>
        </div>
      </div>

      <!-- Gmail Email Automation -->
      <div class="project-card">
        <img class="card-img" src="/mnt/user-data/uploads/1000269017.jpg" alt="Gmail Email Automation">
        <div class="card-overlay"></div>
        <div class="card-content">
          <div class="card-tag">Email AI</div>
          <div class="card-title">Smart Gmail Trigger & Classifier</div>
          <div class="card-desc">Gmail trigger → Groq AI classifies emails via Switch node → routes to appropriate response pipelines and Sheets logging.</div>
        </div>
      </div>

      <!-- Meeting Scheduler -->
      <div class="project-card">
        <img class="card-img" src="/mnt/user-data/uploads/1000269019.jpg" alt="AI Meeting Scheduler">
        <div class="card-overlay"></div>
        <div class="card-content">
          <div class="card-tag">Calendar AI</div>
          <div class="card-title">AI Meeting Scheduler (Human-in-Loop)</div>
          <div class="card-desc">AI Agent reads Google Calendar, finds free slots, drafts a polished meeting invitation email with Approve button — awaiting user confirmation before sending.</div>
        </div>
      </div>

      <!-- Content + Doc Auto -->
      <div class="project-card">
        <img class="card-img" src="/mnt/user-data/uploads/1000269018.jpg" alt="Content Automation Workflow">
        <div class="card-overlay"></div>
        <div class="card-content">
          <div class="card-tag">Content AI</div>
          <div class="card-title">AI Content Writer + Google Docs</div>
          <div class="card-desc">Scheduled trigger reads Sheets, Gemini writes content via Basic LLM Chain, updates Docs and Sheets — full content pipeline.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- GALLERY — Workflow Screenshots -->
<section style="padding:0 4rem 7rem;">
  <div class="gallery reveal">
    <div class="section-label">Workflow Gallery</div>
    <h2 class="section-title">Inside the<br><span style="color:var(--accent)">Machine</span></h2>
    <div class="gallery-grid">
      <div class="gallery-item tall">
        <img src="/mnt/user-data/uploads/1000269020.jpg" alt="n8n Lead Gen Workflow">
        <div class="g-label">Lead Gen Pipeline</div>
      </div>
      <div class="gallery-item">
        <img src="/mnt/user-data/uploads/1000269022.jpg" alt="Meeting Approval Email">
        <div class="g-label">Meeting Approval Email</div>
      </div>
      <div class="gallery-item">
        <img src="/mnt/user-data/uploads/1000269021.jpg" alt="News AI Workflow">
        <div class="g-label">AI News Workflow</div>
      </div>
      <div class="gallery-item">
        <img src="/mnt/user-data/uploads/1000269018.jpg" alt="Content Workflow Success">
        <div class="g-label">Content Workflow</div>
      </div>
      <div class="gallery-item">
        <img src="/mnt/user-data/uploads/1000269019.jpg" alt="Calendar AI Agent">
        <div class="g-label">Calendar AI Agent</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section class="services-bg" id="services" style="padding:7rem 4rem;">
  <div class="services-inner reveal">
    <div class="section-label">What I Offer</div>
    <h2 class="section-title">Services That<br><span style="color:var(--accent)">Save Time</span></h2>
    <div class="services-grid">
      <div class="service-card">
        <div class="service-num">01</div>
        <div class="service-icon">⚙️</div>
        <div class="service-title">n8n Workflow Automation</div>
        <div class="service-desc">End-to-end automation design using n8n Cloud — from simple 3-step flows to complex multi-branch pipelines with error handling.</div>
        <div class="service-tags">
          <span class="s-tag">n8n Cloud</span><span class="s-tag">API Integration</span><span class="s-tag">Scheduling</span>
        </div>
      </div>
      <div class="service-card">
        <div class="service-num">02</div>
        <div class="service-icon">🤖</div>
        <div class="service-title">AI Agent Development</div>
        <div class="service-desc">Build autonomous AI agents powered by Gemini, Groq, or OpenRouter that can reason, search, write, and take actions on your behalf.</div>
        <div class="service-tags">
          <span class="s-tag">Gemini AI</span><span class="s-tag">Groq</span><span class="s-tag">OpenRouter</span>
        </div>
      </div>
      <div class="service-card">
        <div class="service-num">03</div>
        <div class="service-icon">🎯</div>
        <div class="service-title">Lead Generation Systems</div>
        <div class="service-desc">Automated lead scraping from Google Maps and search engines, AI qualification scoring, and direct-to-CRM or Sheets delivery.</div>
        <div class="service-tags">
          <span class="s-tag">SerpAPI</span><span class="s-tag">AI Scoring</span><span class="s-tag">Google Sheets</span>
        </div>
      </div>
      <div class="service-card">
        <div class="service-num">04</div>
        <div class="service-icon">📧</div>
        <div class="service-title">Email Automation</div>
        <div class="service-desc">Smart Gmail triggers, AI-powered response drafting, classification, scheduling with calendar integration and human-approval loops.</div>
        <div class="service-tags">
          <span class="s-tag">Gmail API</span><span class="s-tag">Calendar</span><span class="s-tag">Human-in-Loop</span>
        </div>
      </div>
      <div class="service-card">
        <div class="service-num">05</div>
        <div class="service-icon">🎬</div>
        <div class="service-title">AI Content & Video Pipelines</div>
        <div class="service-desc">Automated content creation workflows — AI writes, Shotstack renders video, uploads and posts automatically on schedule.</div>
        <div class="service-tags">
          <span class="s-tag">Shotstack</span><span class="s-tag">Pexels API</span><span class="s-tag">Content AI</span>
        </div>
      </div>
      <div class="service-card">
        <div class="service-num">06</div>
        <div class="service-icon">📊</div>
        <div class="service-title">Data Pipeline & Reporting</div>
        <div class="service-desc">Pull data from any source, process with AI, and push structured results to Google Sheets, Docs, or any reporting tool automatically.</div>
        <div class="service-tags">
          <span class="s-tag">Google Sheets</span><span class="s-tag">Google Docs</span><span class="s-tag">HTTP APIs</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact-bg" id="contact" style="padding:7rem 4rem;">
  <div class="contact-inner">
    <div class="contact-info reveal">
      <div class="section-label">Contact</div>
      <h2 class="section-title">Let's Build<br>Something<br><span style="color:var(--accent)">Automated</span></h2>
      <p>Have a repetitive task that's eating your team's time? Let's talk. I'll design a custom automation that handles it for you — 24/7, reliably, and affordably.</p>
      <div class="contact-links">
        <a class="contact-link" href="tel:+923417595930">
          <div class="contact-link-icon">📞</div>
          <div class="contact-link-text">
            <div class="contact-link-label">Phone / WhatsApp</div>
            <div class="contact-link-val">+92 341 759 5930</div>
          </div>
        </a>
        <a class="contact-link" href="mailto:sohaib9530@gmail.com">
          <div class="contact-link-icon">✉️</div>
          <div class="contact-link-text">
            <div class="contact-link-label">Email</div>
            <div class="contact-link-val">sohaib9530@gmail.com</div>
          </div>
        </a>
        <a class="contact-link" href="#">
          <div class="contact-link-icon">📍</div>
          <div class="contact-link-text">
            <div class="contact-link-label">Location</div>
            <div class="contact-link-val">Punjab, Pakistan</div>
          </div>
        </a>
      </div>
    </div>

    <div class="contact-form reveal" style="transition-delay:0.15s;">
      <div class="form-group">
        <label>Your Name</label>
        <input type="text" placeholder="Muhammad Ali">
      </div>
      <div class="form-group">
        <label>Email Address</label>
        <input type="email" placeholder="you@company.com">
      </div>
      <div class="form-group">
        <label>What Do You Need Automated?</label>
        <textarea placeholder="Describe the repetitive task or workflow you want to automate..."></textarea>
      </div>
      <button class="form-submit" onclick="alert('Message sent! Sohaib will get back to you soon.')">Send Message →</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div>
    <div class="footer-logo">S.AI</div>
    <div style="font-size:0.65rem;margin-top:0.3rem;">AI Automation Expert • Punjab, Pakistan</div>
  </div>
  <div style="text-align:center;">
    <div>sohaib9530@gmail.com</div>
    <div style="margin-top:0.3rem;">+92 341 759 5930</div>
  </div>
  <div style="text-align:right;">
    <div>© 2026 Sohaib</div>
    <div style="margin-top:0.3rem;color:var(--accent);">Built with n8n &amp; ❤️</div>
  </div>
</footer>

<script>
// Custom cursor
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; cursor.style.left = mx+'px'; cursor.style.top = my+'px'; });
function animRing() { rx += (mx - rx) * 0.12; ry += (my - ry) * 0.12; ring.style.left = rx+'px'; ring.style.top = ry+'px'; requestAnimationFrame(animRing); }
animRing();
document.querySelectorAll('a,button,.project-card,.gallery-item,.service-card,.contact-link').forEach(el => {
  el.addEventListener('mouseenter', () => { cursor.style.transform='translate(-50%,-50%) scale(2)'; ring.style.transform='translate(-50%,-50%) scale(1.5)'; ring.style.opacity='0.8'; });
  el.addEventListener('mouseleave', () => { cursor.style.transform='translate(-50%,-50%) scale(1)'; ring.style.transform='translate(-50%,-50%) scale(1)'; ring.style.opacity='0.5'; });
});

// Scroll reveal
const reveals = document.querySelectorAll('.reveal');
const obs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if(e.isIntersecting) { e.target.classList.add('visible'); } });
}, { threshold: 0.12 });
reveals.forEach(r => obs.observe(r));

// Stagger reveal children
document.querySelectorAll('.skills-grid, .projects-grid, .services-grid, .gallery-grid').forEach(grid => {
  Array.from(grid.children).forEach((child, i) => {
    child.style.transitionDelay = (i * 0.08) + 's';
    child.classList.add('reveal');
    obs.observe(child);
  });
});
</script>
</body>
</html>
