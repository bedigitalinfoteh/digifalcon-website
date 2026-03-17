<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digifalcon Agency – Digital Marketing & Web Solutions</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #0a0a0f;
    --paper: #f5f2ec;
    --gold: #e8b84b;
    --gold-dark: #c49a2a;
    --electric: #1a6bff;
    --smoke: #1c1c26;
    --mist: #e8e4dc;
    --text-muted: #6b6860;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--paper);
    color: var(--ink);
    overflow-x: hidden;
  }

  /* ─── NOISE TEXTURE ─── */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 5%;
    background: rgba(245,242,236,0.88);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(10,10,15,0.08);
  }

  .nav-logo {
    display: flex; align-items: center; gap: 0.6rem;
    text-decoration: none;
  }
  .logo-mark {
    width: 38px; height: 38px;
    background: var(--ink);
    clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }
  .logo-mark::after {
    content: '🦅';
    font-size: 18px; line-height: 1;
    filter: brightness(0) invert(1);
  }
  .logo-text {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 0.05em;
    color: var(--ink);
  }
  .logo-text span { color: var(--gold); }

  .nav-links {
    display: flex; gap: 2rem; list-style: none;
  }
  .nav-links a {
    font-family: 'Syne', sans-serif;
    font-size: 0.82rem; font-weight: 600;
    text-transform: uppercase; letter-spacing: 0.12em;
    text-decoration: none; color: var(--ink);
    position: relative; padding-bottom: 2px;
  }
  .nav-links a::after {
    content: ''; position: absolute; bottom: 0; left: 0;
    width: 0; height: 2px; background: var(--gold);
    transition: width 0.3s ease;
  }
  .nav-links a:hover::after { width: 100%; }

  .nav-cta {
    font-family: 'Syne', sans-serif;
    font-size: 0.82rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.1em;
    background: var(--ink); color: var(--paper);
    border: none; padding: 0.7rem 1.5rem;
    cursor: pointer; text-decoration: none;
    transition: background 0.25s, color 0.25s;
  }
  .nav-cta:hover { background: var(--gold); color: var(--ink); }

  /* ─── HERO ─── */
  #hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 8rem 5% 4rem;
    position: relative; overflow: hidden;
  }

  .hero-bg-shape {
    position: absolute;
    right: -10%;
    top: 10%;
    width: 55%;
    height: 80%;
    background: var(--smoke);
    clip-path: polygon(15% 0%, 100% 0%, 100% 100%, 0% 100%);
    z-index: 0;
  }

  .hero-bg-grid {
    position: absolute; inset: 0; z-index: 0;
    background-image:
      linear-gradient(rgba(10,10,15,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(10,10,15,0.05) 1px, transparent 1px);
    background-size: 60px 60px;
  }

  .hero-content { position: relative; z-index: 2; }

  .hero-eyebrow {
    font-family: 'Syne', sans-serif;
    font-size: 0.75rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.2em;
    color: var(--gold-dark);
    display: flex; align-items: center; gap: 0.8rem;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.8s ease both;
  }
  .hero-eyebrow::before {
    content: ''; display: block;
    width: 40px; height: 2px; background: var(--gold);
  }

  .hero-h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3.5rem, 7vw, 6rem);
    line-height: 0.95;
    letter-spacing: 0.02em;
    color: var(--ink);
    animation: fadeUp 0.8s 0.15s ease both;
  }
  .hero-h1 .accent { color: var(--gold); }
  .hero-h1 .outline {
    -webkit-text-stroke: 2px var(--ink);
    color: transparent;
  }

  .hero-sub {
    font-size: 1rem; font-weight: 300; line-height: 1.7;
    color: var(--text-muted); max-width: 440px;
    margin: 1.5rem 0 2.5rem;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .hero-btns {
    display: flex; gap: 1rem; flex-wrap: wrap;
    animation: fadeUp 0.8s 0.45s ease both;
  }
  .btn-primary {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.1em;
    background: var(--gold); color: var(--ink);
    border: none; padding: 0.9rem 2.2rem;
    cursor: pointer; text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(232,184,75,0.4); }

  .btn-secondary {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.1em;
    background: transparent; color: var(--ink);
    border: 2px solid var(--ink); padding: 0.9rem 2.2rem;
    cursor: pointer; text-decoration: none;
    transition: background 0.2s, color 0.2s;
  }
  .btn-secondary:hover { background: var(--ink); color: var(--paper); }

  .hero-right {
    position: relative; z-index: 2;
    display: flex; align-items: center; justify-content: center;
  }

  .hero-visual {
    width: 380px; height: 380px;
    position: relative;
  }

  .falcon-ring {
    position: absolute; inset: 0;
    border: 1px solid rgba(232,184,75,0.3);
    border-radius: 50%;
    animation: spin 20s linear infinite;
  }
  .falcon-ring::before {
    content: ''; position: absolute;
    top: -4px; left: 50%; transform: translateX(-50%);
    width: 8px; height: 8px;
    background: var(--gold); border-radius: 50%;
  }

  .falcon-ring-2 {
    position: absolute; inset: 30px;
    border: 1px dashed rgba(232,184,75,0.2);
    border-radius: 50%;
    animation: spin 14s linear infinite reverse;
  }

  .falcon-center {
    position: absolute; inset: 60px;
    background: var(--smoke);
    border-radius: 50%;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    gap: 0.3rem;
  }
  .falcon-emoji { font-size: 4.5rem; }
  .falcon-tagline {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1rem; letter-spacing: 0.2em;
    color: var(--gold);
  }

  .hero-stat {
    position: absolute;
    background: var(--paper);
    border: 1px solid var(--mist);
    padding: 0.9rem 1.2rem;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
  }
  .hero-stat .num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem; color: var(--gold);
  }
  .hero-stat .lbl {
    font-size: 0.7rem; font-weight: 500;
    text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--text-muted);
  }
  .stat-1 { bottom: 20px; left: -20px; animation: fadeUp 1s 0.6s both; }
  .stat-2 { top: 20px; right: -20px; animation: fadeUp 1s 0.8s both; }

  /* ─── MARQUEE ─── */
  .marquee-wrap {
    background: var(--ink);
    overflow: hidden; padding: 1rem 0;
    position: relative; z-index: 2;
  }
  .marquee-track {
    display: flex; gap: 0; width: max-content;
    animation: marquee 20s linear infinite;
  }
  .marquee-item {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem; letter-spacing: 0.15em;
    color: var(--paper); padding: 0 2rem;
    white-space: nowrap; opacity: 0.7;
  }
  .marquee-item span { color: var(--gold); margin-right: 2rem; }

  /* ─── SERVICES ─── */
  #services {
    padding: 7rem 5%;
    position: relative;
  }

  .section-label {
    font-family: 'Syne', sans-serif;
    font-size: 0.72rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.25em;
    color: var(--gold-dark);
    display: flex; align-items: center; gap: 0.8rem;
    margin-bottom: 1rem;
  }
  .section-label::before {
    content: ''; width: 30px; height: 2px; background: var(--gold);
  }

  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 5vw, 4rem);
    line-height: 1;
    margin-bottom: 1rem;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5px;
    background: var(--ink);
    margin-top: 4rem;
    border: 1.5px solid var(--ink);
  }

  .service-card {
    background: var(--paper);
    padding: 2.5rem 2rem;
    position: relative; overflow: hidden;
    transition: background 0.3s;
    cursor: default;
  }
  .service-card::after {
    content: ''; position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 3px;
    background: var(--gold);
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.35s ease;
  }
  .service-card:hover { background: var(--smoke); }
  .service-card:hover .svc-num,
  .service-card:hover .svc-title,
  .service-card:hover .svc-desc { color: var(--paper); }
  .service-card:hover .svc-icon { filter: brightness(0) invert(1); opacity: 0.15; }
  .service-card:hover::after { transform: scaleX(1); }

  .svc-icon {
    font-size: 2.5rem; margin-bottom: 1.2rem;
    display: block; transition: all 0.3s;
  }
  .svc-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 0.85rem; letter-spacing: 0.2em;
    color: var(--gold-dark); margin-bottom: 0.5rem;
    transition: color 0.3s;
  }
  .svc-title {
    font-family: 'Syne', sans-serif;
    font-size: 1.2rem; font-weight: 700;
    margin-bottom: 0.8rem; transition: color 0.3s;
  }
  .svc-desc {
    font-size: 0.88rem; line-height: 1.7;
    color: var(--text-muted); transition: color 0.3s;
  }

  /* ─── WHY US ─── */
  #why {
    background: var(--smoke);
    padding: 7rem 5%;
    position: relative; overflow: hidden;
  }
  #why .section-label { color: var(--gold); }
  #why .section-title { color: var(--paper); }

  .why-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 5rem; align-items: center;
    margin-top: 4rem;
  }

  .why-left p {
    color: rgba(245,242,236,0.65);
    font-size: 1rem; line-height: 1.8; margin-bottom: 2rem;
  }

  .why-features { display: flex; flex-direction: column; gap: 1rem; }
  .why-feat {
    display: flex; gap: 1rem; align-items: flex-start;
    padding: 1.2rem 1.5rem;
    border: 1px solid rgba(245,242,236,0.08);
    transition: border-color 0.3s, background 0.3s;
  }
  .why-feat:hover {
    border-color: var(--gold);
    background: rgba(232,184,75,0.06);
  }
  .why-feat-icon {
    font-size: 1.5rem; flex-shrink: 0;
  }
  .why-feat-text h4 {
    font-family: 'Syne', sans-serif;
    font-size: 0.95rem; font-weight: 700;
    color: var(--paper); margin-bottom: 0.3rem;
  }
  .why-feat-text p {
    font-size: 0.83rem; color: rgba(245,242,236,0.5); margin: 0; line-height: 1.5;
  }

  .why-right { display: flex; flex-direction: column; gap: 1.5rem; }

  .stat-block {
    padding: 2rem;
    border: 1px solid rgba(245,242,236,0.1);
    position: relative; overflow: hidden;
  }
  .stat-block::before {
    content: ''; position: absolute;
    top: 0; left: 0; bottom: 0;
    width: 4px; background: var(--gold);
  }
  .stat-block .big-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 3.5rem; color: var(--gold);
    line-height: 1;
  }
  .stat-block .big-label {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem; font-weight: 600;
    color: var(--paper); letter-spacing: 0.05em;
  }
  .stat-block p {
    font-size: 0.82rem; color: rgba(245,242,236,0.45); margin-top: 0.4rem;
  }

  .stat-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }

  /* ─── BLOG ─── */
  #blog {
    padding: 7rem 5%;
  }

  .blog-grid {
    display: grid; grid-template-columns: 1.6fr 1fr 1fr;
    gap: 1.5rem; margin-top: 4rem;
  }

  .blog-card {
    background: var(--mist);
    overflow: hidden; cursor: pointer;
    transition: transform 0.3s;
  }
  .blog-card:hover { transform: translateY(-6px); }
  .blog-card:hover .blog-img { transform: scale(1.05); }

  .blog-img-wrap { overflow: hidden; height: 200px; }
  .blog-card.featured .blog-img-wrap { height: 260px; }
  .blog-img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease;
    background: linear-gradient(135deg, #1c1c26 0%, #2a2a3d 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 3rem;
  }

  .blog-body { padding: 1.5rem; }
  .blog-tag {
    font-family: 'Syne', sans-serif;
    font-size: 0.7rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.15em;
    color: var(--gold-dark); margin-bottom: 0.6rem;
    display: block;
  }
  .blog-title {
    font-family: 'Syne', sans-serif;
    font-size: 1rem; font-weight: 700;
    line-height: 1.4; margin-bottom: 0.5rem;
  }
  .blog-card.featured .blog-title { font-size: 1.3rem; }
  .blog-excerpt {
    font-size: 0.83rem; color: var(--text-muted); line-height: 1.6;
  }
  .blog-meta {
    font-size: 0.75rem; color: var(--text-muted);
    margin-top: 1rem; padding-top: 1rem;
    border-top: 1px solid rgba(10,10,15,0.08);
  }

  /* ─── CTA STRIP ─── */
  #cta {
    background: var(--gold);
    padding: 5rem 5%;
    display: grid; grid-template-columns: 1fr auto;
    align-items: center; gap: 3rem;
    position: relative; overflow: hidden;
  }
  #cta::before {
    content: 'DIGIFALCON';
    position: absolute; right: -2%;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 12rem; color: rgba(10,10,15,0.07);
    white-space: nowrap; user-select: none; pointer-events: none;
    line-height: 1;
  }

  .cta-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.2rem, 4vw, 3.5rem);
    color: var(--ink); line-height: 1.05;
  }
  .cta-sub {
    font-size: 1rem; color: rgba(10,10,15,0.65);
    margin-top: 0.5rem;
  }

  .btn-dark {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.1em;
    background: var(--ink); color: var(--paper);
    border: none; padding: 1rem 2.5rem;
    cursor: pointer; text-decoration: none;
    white-space: nowrap; flex-shrink: 0;
    transition: opacity 0.2s;
  }
  .btn-dark:hover { opacity: 0.85; }

  /* ─── CONTACT ─── */
  #contact {
    padding: 7rem 5%;
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 6rem; align-items: start;
  }

  .contact-info h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 4vw, 3.5rem);
    line-height: 1;
    margin: 1rem 0 1.5rem;
  }
  .contact-info p {
    font-size: 0.95rem; color: var(--text-muted);
    line-height: 1.7; margin-bottom: 2.5rem;
  }

  .contact-detail {
    display: flex; gap: 1rem; align-items: flex-start;
    margin-bottom: 1.2rem;
  }
  .cd-icon {
    width: 40px; height: 40px; flex-shrink: 0;
    background: var(--ink);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
  }
  .cd-text strong {
    font-family: 'Syne', sans-serif;
    font-size: 0.78rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--ink); display: block; margin-bottom: 0.2rem;
  }
  .cd-text span {
    font-size: 0.9rem; color: var(--text-muted);
  }

  .contact-form { display: flex; flex-direction: column; gap: 1rem; }

  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-group label {
    font-family: 'Syne', sans-serif;
    font-size: 0.72rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.15em;
    color: var(--ink);
  }
  .form-group input,
  .form-group select,
  .form-group textarea {
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    background: var(--mist);
    border: 1.5px solid transparent;
    padding: 0.9rem 1rem;
    outline: none; width: 100%;
    transition: border-color 0.25s;
    color: var(--ink);
  }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color: var(--gold); }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

  /* ─── FOOTER ─── */
  footer {
    background: var(--ink);
    padding: 4rem 5% 2rem;
  }

  .footer-top {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 3rem; padding-bottom: 3rem;
    border-bottom: 1px solid rgba(245,242,236,0.1);
  }

  .footer-brand .logo-text { color: var(--paper); }

  .footer-tagline {
    font-size: 0.88rem; color: rgba(245,242,236,0.45);
    line-height: 1.7; margin-top: 1rem;
  }

  .footer-col h5 {
    font-family: 'Syne', sans-serif;
    font-size: 0.75rem; font-weight: 700;
    text-transform: uppercase; letter-spacing: 0.18em;
    color: var(--gold); margin-bottom: 1.2rem;
  }
  .footer-col ul { list-style: none; }
  .footer-col ul li {
    font-size: 0.85rem; color: rgba(245,242,236,0.5);
    margin-bottom: 0.6rem; cursor: pointer;
    transition: color 0.2s;
  }
  .footer-col ul li:hover { color: var(--paper); }

  .footer-bottom {
    display: flex; justify-content: space-between; align-items: center;
    padding-top: 2rem;
  }
  .footer-bottom p {
    font-size: 0.8rem; color: rgba(245,242,236,0.3);
  }
  .footer-socials { display: flex; gap: 1rem; }
  .social-btn {
    width: 36px; height: 36px;
    border: 1px solid rgba(245,242,236,0.15);
    display: flex; align-items: center; justify-content: center;
    font-size: 1rem; cursor: pointer;
    transition: border-color 0.2s, background 0.2s;
    text-decoration: none;
  }
  .social-btn:hover { border-color: var(--gold); background: rgba(232,184,75,0.1); }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes spin {
    to { transform: rotate(360deg); }
  }
  @keyframes marquee {
    from { transform: translateX(0); }
    to   { transform: translateX(-50%); }
  }

  /* ─── SCROLL REVEAL ─── */
  .reveal {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible {
    opacity: 1; transform: translateY(0);
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 900px) {
    #hero { grid-template-columns: 1fr; padding-top: 7rem; }
    .hero-right { display: none; }
    .hero-bg-shape { display: none; }
    .services-grid { grid-template-columns: 1fr 1fr; }
    .why-grid, #contact { grid-template-columns: 1fr; gap: 3rem; }
    .blog-grid { grid-template-columns: 1fr; }
    .footer-top { grid-template-columns: 1fr 1fr; }
    #cta { grid-template-columns: 1fr; }
    nav .nav-links { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    <div class="logo-mark"></div>
    <span class="logo-text">Digi<span>falcon</span></span>
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#why">About</a></li>
    <li><a href="#blog">Blog</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Get Started</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg-grid"></div>
  <div class="hero-bg-shape"></div>

  <div class="hero-content">
    <div class="hero-eyebrow">Digital Marketing Agency</div>
    <h1 class="hero-h1">
      FLY<br>
      <span class="accent">HIGHER</span><br>
      <span class="outline">DIGITALLY</span>
    </h1>
    <p class="hero-sub">
      Digifalcon Agency crafts powerful digital strategies — from Meta & Google Ads to SEO, Web Development, and Personal Branding — that elevate your business above the competition.
    </p>
    <div class="hero-btns">
      <a href="#services" class="btn-primary">Explore Services</a>
      <a href="#contact" class="btn-secondary">Free Consultation</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="hero-visual">
      <div class="falcon-ring"></div>
      <div class="falcon-ring-2"></div>
      <div class="falcon-center">
        <span class="falcon-emoji">🦅</span>
        <span class="falcon-tagline">DIGIFALCON</span>
      </div>
      <div class="hero-stat stat-1">
        <div class="num">500+</div>
        <div class="lbl">Campaigns Launched</div>
      </div>
      <div class="hero-stat stat-2">
        <div class="num">98%</div>
        <div class="lbl">Client Satisfaction</div>
      </div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track">
    <span class="marquee-item"><span>✦</span> Meta Ads</span>
    <span class="marquee-item"><span>✦</span> Google Ads</span>
    <span class="marquee-item"><span>✦</span> SEO Optimization</span>
    <span class="marquee-item"><span>✦</span> Web Development</span>
    <span class="marquee-item"><span>✦</span> Personal Branding</span>
    <span class="marquee-item"><span>✦</span> PPC Campaigns</span>
    <span class="marquee-item"><span>✦</span> Digital Marketing</span>
    <span class="marquee-item"><span>✦</span> Meta Ads</span>
    <span class="marquee-item"><span>✦</span> Google Ads</span>
    <span class="marquee-item"><span>✦</span> SEO Optimization</span>
    <span class="marquee-item"><span>✦</span> Web Development</span>
    <span class="marquee-item"><span>✦</span> Personal Branding</span>
    <span class="marquee-item"><span>✦</span> PPC Campaigns</span>
    <span class="marquee-item"><span>✦</span> Digital Marketing</span>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="section-label">What We Do</div>
  <h2 class="section-title">Our Core<br>Services</h2>

  <div class="services-grid reveal">
    <div class="service-card">
      <span class="svc-icon">📱</span>
      <div class="svc-num">01</div>
      <h3 class="svc-title">Meta Ads</h3>
      <p class="svc-desc">Data-driven Facebook & Instagram ad campaigns that maximize reach, engagement, and conversions for your brand across Tamil Nadu and beyond.</p>
    </div>
    <div class="service-card">
      <span class="svc-icon">🔍</span>
      <div class="svc-num">02</div>
      <h3 class="svc-title">Google Ads</h3>
      <p class="svc-desc">Precision-targeted Google Search, Display, and Shopping campaigns that put your business in front of the right audience at exactly the right moment.</p>
    </div>
    <div class="service-card">
      <span class="svc-icon">💻</span>
      <div class="svc-num">03</div>
      <h3 class="svc-title">Website Development</h3>
      <p class="svc-desc">Custom, blazing-fast websites and landing pages engineered for conversions — from dynamic business sites to fully-featured e-commerce platforms.</p>
    </div>
    <div class="service-card">
      <span class="svc-icon">📈</span>
      <div class="svc-num">04</div>
      <h3 class="svc-title">SEO</h3>
      <p class="svc-desc">Organic search domination through technical SEO, keyword strategy, and authority building that puts your site on page one and keeps it there.</p>
    </div>
    <div class="service-card">
      <span class="svc-icon">🌟</span>
      <div class="svc-num">05</div>
      <h3 class="svc-title">Personal Branding</h3>
      <p class="svc-desc">Build a magnetic personal brand online. We craft your story, grow your audience, and position you as the go-to authority in your industry.</p>
    </div>
    <div class="service-card">
      <span class="svc-icon">💰</span>
      <div class="svc-num">06</div>
      <h3 class="svc-title">PPC Management</h3>
      <p class="svc-desc">Full-funnel pay-per-click strategy with continuous optimization, A/B testing, and transparent reporting to ensure every rupee drives real returns.</p>
    </div>
  </div>
</section>

<!-- WHY US -->
<section id="why">
  <div class="section-label">Why Choose Us</div>
  <h2 class="section-title">Built for Results.<br>Obsessed with Growth.</h2>

  <div class="why-grid">
    <div class="why-left">
      <p>At Digifalcon, we don't just run campaigns — we build ecosystems. Located in Perambalur, we combine deep local knowledge with world-class digital expertise to deliver strategies that actually work.</p>
      <div class="why-features reveal">
        <div class="why-feat">
          <span class="why-feat-icon">🎯</span>
          <div class="why-feat-text">
            <h4>Hyper-Targeted Campaigns</h4>
            <p>Precision audience targeting that minimizes waste and maximizes impact.</p>
          </div>
        </div>
        <div class="why-feat">
          <span class="why-feat-icon">📊</span>
          <div class="why-feat-text">
            <h4>Data-First Approach</h4>
            <p>Every decision backed by real analytics — no guesswork, only insights.</p>
          </div>
        </div>
        <div class="why-feat">
          <span class="why-feat-icon">🤝</span>
          <div class="why-feat-text">
            <h4>Transparent Reporting</h4>
            <p>Clear, honest performance reports you can actually understand.</p>
          </div>
        </div>
        <div class="why-feat">
          <span class="why-feat-icon">⚡</span>
          <div class="why-feat-text">
            <h4>Fast Execution</h4>
            <p>We move at the speed of the market — launch-ready within days.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="why-right reveal">
      <div class="stat-row">
        <div class="stat-block">
          <div class="big-num">150+</div>
          <div class="big-label">Happy Clients</div>
          <p>Across Perambalur, Ariyalur & Tamil Nadu</p>
        </div>
        <div class="stat-block">
          <div class="big-num">3×</div>
          <div class="big-label">Avg. ROI Growth</div>
          <p>Measurable returns on ad spend</p>
        </div>
      </div>
      <div class="stat-block">
        <div class="big-num">5+</div>
        <div class="big-label">Years of Excellence</div>
        <p>Deep experience in Tamil Nadu's digital landscape, delivering consistent growth for businesses of all sizes.</p>
      </div>
      <div class="stat-block">
        <div class="big-num">50M+</div>
        <div class="big-label">Ad Impressions Delivered</div>
        <p>Across Meta, Google, and display networks.</p>
      </div>
    </div>
  </div>
</section>

<!-- BLOG -->
<section id="blog">
  <div class="section-label">Insights & Resources</div>
  <h2 class="section-title">From The<br>Digifalcon Blog</h2>

  <div class="blog-grid reveal">
    <div class="blog-card featured">
      <div class="blog-img-wrap">
        <div class="blog-img">📣</div>
      </div>
      <div class="blog-body">
        <span class="blog-tag">Meta Ads</span>
        <h3 class="blog-title">How to Run Profitable Meta Ads for Local Businesses in Tamil Nadu</h3>
        <p class="blog-excerpt">Discover the exact targeting strategies, ad formats, and budgeting techniques that are working right now for small businesses in Tier 2 cities.</p>
        <div class="blog-meta">March 12, 2026 · 8 min read</div>
      </div>
    </div>
    <div class="blog-card">
      <div class="blog-img-wrap">
        <div class="blog-img">🔍</div>
      </div>
      <div class="blog-body">
        <span class="blog-tag">SEO</span>
        <h3 class="blog-title">Local SEO Checklist: Rank #1 in Your City</h3>
        <p class="blog-excerpt">A proven step-by-step checklist to dominate local search results and drive footfall to your physical business.</p>
        <div class="blog-meta">March 5, 2026 · 6 min read</div>
      </div>
    </div>
    <div class="blog-card">
      <div class="blog-img-wrap">
        <div class="blog-img">🌟</div>
      </div>
      <div class="blog-body">
        <span class="blog-tag">Personal Branding</span>
        <h3 class="blog-title">Build a Personal Brand That Attracts High-Value Clients</h3>
        <p class="blog-excerpt">The personal branding playbook: from defining your niche to growing a loyal following on LinkedIn and Instagram.</p>
        <div class="blog-meta">Feb 28, 2026 · 7 min read</div>
      </div>
    </div>
  </div>
</section>

<!-- CTA STRIP -->
<section id="cta">
  <div>
    <h2 class="cta-title">Ready to Launch Your<br>Digital Growth Journey?</h2>
    <p class="cta-sub">Get a free strategy session with our experts — no strings attached.</p>
  </div>
  <a href="#contact" class="btn-dark">Book Free Strategy Call →</a>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-info">
    <div class="section-label">Get In Touch</div>
    <h2>Let's Grow<br>Your Business</h2>
    <p>Have a project in mind? We'd love to hear about it. Fill in the form or reach out to us directly at our Perambalur office.</p>

    <div class="contact-detail">
      <div class="cd-icon">📍</div>
      <div class="cd-text">
        <strong>Our Office</strong>
        <span>Ariyalur Main Road, Kunnam,<br>Perambalur – 621 708, Tamil Nadu</span>
      </div>
    </div>
    <div class="contact-detail">
      <div class="cd-icon">📧</div>
      <div class="cd-text">
        <strong>Email Us</strong>
        <span>hello@digifalcon.in</span>
      </div>
    </div>
    <div class="contact-detail">
      <div class="cd-icon">📞</div>
      <div class="cd-text">
        <strong>Call / WhatsApp</strong>
        <span>+91 98765 43210</span>
      </div>
    </div>
  </div>

  <div class="contact-form reveal">
    <div class="form-row">
      <div class="form-group">
        <label>First Name</label>
        <input type="text" placeholder="Arjun">
      </div>
      <div class="form-group">
        <label>Last Name</label>
        <input type="text" placeholder="Kumar">
      </div>
    </div>
    <div class="form-group">
      <label>Email Address</label>
      <input type="email" placeholder="arjun@example.com">
    </div>
    <div class="form-group">
      <label>Phone Number</label>
      <input type="tel" placeholder="+91 XXXXX XXXXX">
    </div>
    <div class="form-group">
      <label>Service Interested In</label>
      <select>
        <option value="">Select a service…</option>
        <option>Meta Ads</option>
        <option>Google Ads</option>
        <option>Website Development</option>
        <option>SEO</option>
        <option>Personal Branding</option>
        <option>PPC Management</option>
        <option>Full Digital Package</option>
      </select>
    </div>
    <div class="form-group">
      <label>Message</label>
      <textarea rows="4" placeholder="Tell us about your business and goals…"></textarea>
    </div>
    <button class="btn-primary" style="width:100%;padding:1.1rem;" onclick="alert('Thank you! We will contact you within 24 hours. 🦅')">Send Message →</button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <div class="nav-logo">
        <div class="logo-mark"></div>
        <span class="logo-text">Digi<span>falcon</span></span>
      </div>
      <p class="footer-tagline">Your trusted digital partner in Perambalur, Tamil Nadu. We help businesses soar higher with data-driven digital marketing, powerful websites, and bold branding strategies.</p>
    </div>
    <div class="footer-col">
      <h5>Services</h5>
      <ul>
        <li>Meta Ads</li>
        <li>Google Ads</li>
        <li>Website Development</li>
        <li>SEO</li>
        <li>Personal Branding</li>
        <li>PPC Management</li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Company</h5>
      <ul>
        <li>About Us</li>
        <li>Our Work</li>
        <li>Blog</li>
        <li>Careers</li>
        <li>Contact</li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Contact</h5>
      <ul>
        <li>Ariyalur Main Road</li>
        <li>Kunnam, Perambalur</li>
        <li>Tamil Nadu – 621708</li>
        <li style="margin-top:0.8rem">hello@digifalcon.in</li>
        <li>+91 98765 43210</li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2026 Digifalcon Agency. All rights reserved. Crafted with ❤️ in Perambalur.</p>
    <div class="footer-socials">
      <a class="social-btn" href="#">f</a>
      <a class="social-btn" href="#">in</a>
      <a class="social-btn" href="#">ig</a>
      <a class="social-btn" href="#">yt</a>
    </div>
  </div>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        io.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => io.observe(el));
</script>

</body>
</html>
