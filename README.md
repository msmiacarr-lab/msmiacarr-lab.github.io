
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Soft Power Works — Nonprofit Operations Consulting</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400;1,600&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #f4ede0;
      --cream-light: #faf6ef;
      --green-deep: #1c3a28;
      --green-mid: #2d5c3e;
      --green-soft: #4a7c5f;
      --terracotta: #b85c38;
      --terracotta-light: #d4795a;
      --ink: #1a1a18;
      --ink-soft: #3d3d38;
      --border: rgba(28,58,40,0.15);
      --serif: 'Playfair Display', Georgia, serif;
      --sans: 'DM Sans', sans-serif;
      --mono: 'DM Mono', monospace;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: var(--sans);
      background: var(--cream-light);
      color: var(--ink);
      font-size: 16px;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 1.2rem 2.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(244,237,224,0.92);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: var(--serif);
      font-size: 1.15rem;
      font-weight: 700;
      color: var(--green-deep);
      letter-spacing: 0.01em;
      text-decoration: none;
    }

    .nav-logo span { color: var(--terracotta); }

    nav ul {
      list-style: none;
      display: flex;
      gap: 2.5rem;
    }

    nav ul a {
      font-size: 0.82rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--ink-soft);
      text-decoration: none;
      transition: color 0.2s;
    }

    nav ul a:hover { color: var(--terracotta); }

    .nav-cta {
      background: var(--green-deep) !important;
      color: var(--cream) !important;
      padding: 0.5rem 1.2rem;
      border-radius: 2px;
      letter-spacing: 0.06em !important;
      transition: background 0.2s !important;
    }

    .nav-cta:hover { background: var(--green-mid) !important; color: var(--cream) !important; }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      padding-top: 5rem;
      background: var(--cream);
      position: relative;
      overflow: hidden;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -80px; right: -80px;
      width: 520px; height: 520px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(184,92,56,0.08) 0%, transparent 70%);
      pointer-events: none;
    }

    .hero-left {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 5rem 4rem 5rem 6rem;
    }

    .hero-eyebrow {
      font-family: var(--mono);
      font-size: 0.72rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--terracotta);
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.8s 0.2s forwards;
    }

    .hero h1 {
      font-family: var(--serif);
      font-size: clamp(2.8rem, 4.5vw, 4.2rem);
      font-weight: 700;
      line-height: 1.1;
      color: var(--green-deep);
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.8s 0.4s forwards;
    }

    .hero h1 em {
      font-style: italic;
      color: var(--terracotta);
    }

    .hero-sub {
      font-size: 1.05rem;
      font-weight: 300;
      color: var(--ink-soft);
      max-width: 420px;
      line-height: 1.7;
      margin-bottom: 2.5rem;
      opacity: 0;
      animation: fadeUp 0.8s 0.6s forwards;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      opacity: 0;
      animation: fadeUp 0.8s 0.8s forwards;
    }

    .btn-primary {
      background: var(--green-deep);
      color: var(--cream);
      padding: 0.85rem 2rem;
      border: none;
      font-family: var(--sans);
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      text-decoration: none;
      cursor: pointer;
      transition: background 0.2s, transform 0.15s;
      border-radius: 2px;
    }

    .btn-primary:hover { background: var(--green-mid); transform: translateY(-1px); }

    .btn-secondary {
      background: transparent;
      color: var(--green-deep);
      padding: 0.85rem 2rem;
      border: 1.5px solid var(--green-deep);
      font-family: var(--sans);
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      text-decoration: none;
      cursor: pointer;
      transition: all 0.2s;
      border-radius: 2px;
    }

    .btn-secondary:hover { background: var(--green-deep); color: var(--cream); }

    .hero-right {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 4rem 4rem 4rem 2rem;
      position: relative;
    }

    .hero-card {
      background: var(--green-deep);
      color: var(--cream);
      padding: 3rem 2.5rem;
      max-width: 360px;
      width: 100%;
      border-radius: 4px;
      position: relative;
      opacity: 0;
      animation: fadeUp 0.9s 1s forwards;
    }

    .hero-card::before {
      content: '"';
      font-family: var(--serif);
      font-size: 7rem;
      color: var(--terracotta);
      opacity: 0.35;
      position: absolute;
      top: -1.5rem;
      left: 1.5rem;
      line-height: 1;
    }

    .hero-card p {
      font-family: var(--serif);
      font-style: italic;
      font-size: 1.1rem;
      line-height: 1.65;
      margin-bottom: 1.5rem;
      opacity: 0.9;
    }

    .hero-card-attr {
      font-size: 0.75rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      opacity: 0.55;
    }

    .hero-stats {
      display: flex;
      gap: 2rem;
      margin-top: 2rem;
      padding-top: 2rem;
      border-top: 1px solid rgba(244,237,224,0.15);
    }

    .stat-num {
      font-family: var(--serif);
      font-size: 2rem;
      font-weight: 600;
      color: var(--terracotta-light);
      display: block;
    }

    .stat-label {
      font-size: 0.72rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      opacity: 0.6;
    }

    /* MARQUEE */
    .marquee-strip {
      background: var(--green-deep);
      padding: 0.9rem 0;
      overflow: hidden;
      white-space: nowrap;
    }

    .marquee-inner {
      display: inline-block;
      animation: marquee 28s linear infinite;
    }

    .marquee-inner span {
      font-family: var(--mono);
      font-size: 0.75rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--cream);
      opacity: 0.7;
      padding: 0 2.5rem;
    }

    .marquee-inner span.dot {
      color: var(--terracotta-light);
      opacity: 1;
      padding: 0 0.5rem;
    }

    @keyframes marquee {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    /* SECTIONS */
    section { padding: 7rem 0; }

    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 2.5rem;
    }

    .section-label {
      font-family: var(--mono);
      font-size: 0.72rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--terracotta);
      display: block;
      margin-bottom: 1rem;
    }

    .section-title {
      font-family: var(--serif);
      font-size: clamp(2rem, 3vw, 2.8rem);
      font-weight: 700;
      color: var(--green-deep);
      line-height: 1.2;
      margin-bottom: 1.5rem;
    }

    .section-title em { font-style: italic; color: var(--terracotta); }

    /* ABOUT */
    .about { background: var(--cream-light); }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 6rem;
      align-items: center;
    }

    .about-text p {
      font-size: 1.05rem;
      font-weight: 300;
      color: var(--ink-soft);
      line-height: 1.8;
      margin-bottom: 1.2rem;
    }

    .about-text p strong {
      font-weight: 500;
      color: var(--green-deep);
    }

    .about-values {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }

    .value-card {
      background: var(--cream);
      border: 1px solid var(--border);
      padding: 1.5rem;
      border-radius: 4px;
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .value-card:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(28,58,40,0.08); }

    .value-icon {
      font-size: 1.5rem;
      margin-bottom: 0.75rem;
      display: block;
    }

    .value-card h4 {
      font-family: var(--serif);
      font-size: 1rem;
      font-weight: 600;
      color: var(--green-deep);
      margin-bottom: 0.4rem;
    }

    .value-card p {
      font-size: 0.85rem;
      color: var(--ink-soft);
      line-height: 1.6;
    }

    /* SERVICES */
    .services { background: var(--green-deep); }

    .services .section-label { color: var(--terracotta-light); }
    .services .section-title { color: var(--cream); }

    .services-intro {
      font-size: 1.05rem;
      font-weight: 300;
      color: rgba(244,237,224,0.75);
      max-width: 560px;
      line-height: 1.7;
      margin-bottom: 4rem;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }

    .service-card {
      background: rgba(244,237,224,0.06);
      border: 1px solid rgba(244,237,224,0.12);
      border-radius: 4px;
      padding: 2.5rem 2rem;
      transition: background 0.25s, border-color 0.25s, transform 0.2s;
      position: relative;
      overflow: hidden;
    }

    .service-card::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      height: 3px;
      width: 0;
      background: var(--terracotta);
      transition: width 0.3s;
    }

    .service-card:hover {
      background: rgba(244,237,224,0.1);
      border-color: rgba(244,237,224,0.2);
      transform: translateY(-4px);
    }

    .service-card:hover::after { width: 100%; }

    .service-tier {
      font-family: var(--mono);
      font-size: 0.68rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--terracotta-light);
      margin-bottom: 1rem;
      display: block;
    }

    .service-card h3 {
      font-family: var(--serif);
      font-size: 1.4rem;
      font-weight: 600;
      color: var(--cream);
      margin-bottom: 1rem;
      line-height: 1.25;
    }

    .service-card p {
      font-size: 0.92rem;
      color: rgba(244,237,224,0.65);
      line-height: 1.7;
      margin-bottom: 1.5rem;
    }

    .service-price {
      font-family: var(--serif);
      font-size: 1.25rem;
      color: var(--cream);
      font-weight: 600;
      margin-bottom: 1.5rem;
    }

    .service-price span {
      font-family: var(--sans);
      font-size: 0.78rem;
      font-weight: 300;
      color: rgba(244,237,224,0.5);
      margin-left: 0.25rem;
    }

    .service-list { list-style: none; padding: 0; }

    .service-list li {
      font-size: 0.85rem;
      color: rgba(244,237,224,0.6);
      padding: 0.35rem 0;
      padding-left: 1.25rem;
      position: relative;
    }

    .service-list li::before {
      content: '→';
      position: absolute;
      left: 0;
      color: var(--terracotta-light);
      font-size: 0.75rem;
    }

    /* WORK */
    .work { background: var(--cream); }

    .work-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 2rem;
      margin-top: 3.5rem;
    }

    .work-card {
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 2.5rem;
      background: var(--cream-light);
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .work-card:hover { transform: translateY(-3px); box-shadow: 0 10px 30px rgba(28,58,40,0.09); }

    .work-org {
      font-family: var(--mono);
      font-size: 0.7rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--terracotta);
      margin-bottom: 0.75rem;
    }

    .work-card h3 {
      font-family: var(--serif);
      font-size: 1.2rem;
      font-weight: 600;
      color: var(--green-deep);
      margin-bottom: 0.75rem;
    }

    .work-card p {
      font-size: 0.92rem;
      color: var(--ink-soft);
      line-height: 1.7;
      margin-bottom: 1.25rem;
    }

    .work-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; }

    .tag {
      font-size: 0.72rem;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      background: rgba(28,58,40,0.07);
      color: var(--green-mid);
      padding: 0.3rem 0.75rem;
      border-radius: 100px;
      font-weight: 500;
    }

    /* TESTIMONIALS */
    .testimonials { background: var(--cream-light); }

    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
      margin-top: 3.5rem;
    }

    .testimonial-card {
      background: var(--cream);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 2rem;
    }

    .quote-mark {
      font-family: var(--serif);
      font-size: 3.5rem;
      line-height: 0.8;
      color: var(--terracotta);
      opacity: 0.35;
      display: block;
      margin-bottom: 0.5rem;
    }

    .testimonial-card p {
      font-family: var(--serif);
      font-style: italic;
      font-size: 0.98rem;
      color: var(--ink-soft);
      line-height: 1.7;
      margin-bottom: 1.25rem;
    }

    .testimonial-attr {
      font-size: 0.78rem;
      font-weight: 500;
      color: var(--green-deep);
    }

    .testimonial-attr span {
      display: block;
      font-weight: 300;
      color: var(--ink-soft);
      opacity: 0.7;
    }

    /* CONTACT */
    .contact { background: var(--cream); }

    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 6rem;
      align-items: start;
    }

    .contact-left h2 {
      font-family: var(--serif);
      font-size: clamp(1.9rem, 2.8vw, 2.6rem);
      font-weight: 700;
      color: var(--green-deep);
      line-height: 1.2;
      margin-bottom: 1.25rem;
    }

    .contact-left h2 em { font-style: italic; color: var(--terracotta); }

    .contact-left p {
      font-size: 1rem;
      font-weight: 300;
      color: var(--ink-soft);
      line-height: 1.75;
      margin-bottom: 2rem;
    }

    .contact-details { display: flex; flex-direction: column; gap: 0.75rem; }

    .contact-detail {
      display: flex;
      align-items: center;
      gap: 0.75rem;
      font-size: 0.9rem;
      color: var(--ink-soft);
    }

    .contact-detail-icon {
      width: 32px;
      height: 32px;
      background: var(--green-deep);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.75rem;
      flex-shrink: 0;
      color: var(--cream);
    }

    .contact-form { display: flex; flex-direction: column; gap: 1.25rem; }

    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

    .form-group { display: flex; flex-direction: column; gap: 0.4rem; }

    .form-group label {
      font-size: 0.78rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--green-deep);
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      font-family: var(--sans);
      font-size: 0.95rem;
      background: var(--cream-light);
      border: 1.5px solid var(--border);
      border-radius: 3px;
      padding: 0.75rem 1rem;
      color: var(--ink);
      transition: border-color 0.2s;
      outline: none;
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus { border-color: var(--green-mid); }

    .form-group textarea { resize: vertical; min-height: 130px; }

    .form-submit {
      background: var(--terracotta);
      color: white;
      border: none;
      padding: 1rem 2.5rem;
      font-family: var(--sans);
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      cursor: pointer;
      border-radius: 2px;
      transition: background 0.2s, transform 0.15s;
      align-self: flex-start;
    }

    .form-submit:hover { background: var(--terracotta-light); transform: translateY(-1px); }

    /* FOOTER */
    footer {
      background: var(--green-deep);
      color: var(--cream);
      padding: 3rem 0;
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .footer-logo {
      font-family: var(--serif);
      font-size: 1.1rem;
      font-weight: 700;
    }

    .footer-logo span { color: var(--terracotta-light); }

    .footer-copy { font-size: 0.8rem; opacity: 0.5; }

    .footer-links { display: flex; gap: 2rem; }

    .footer-links a {
      font-size: 0.8rem;
      color: rgba(244,237,224,0.55);
      text-decoration: none;
      transition: color 0.2s;
    }

    .footer-links a:hover { color: var(--terracotta-light); }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 900px) {
      nav ul { display: none; }
      .hero { grid-template-columns: 1fr; min-height: auto; }
      .hero-left { padding: 6rem 2rem 3rem; }
      .hero-right { padding: 0 2rem 4rem; }
      .hero-card { max-width: 100%; }
      .about-grid, .contact-grid { grid-template-columns: 1fr; gap: 3rem; }
      .services-grid { grid-template-columns: 1fr; }
      .work-grid, .testimonials-grid { grid-template-columns: 1fr; }
      .form-row { grid-template-columns: 1fr; }
      section { padding: 4rem 0; }
    }
  </style>
</head>
<body>

<nav>
  <a href="#" class="nav-logo">Soft Power<span>.</span>Works</a>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#work">Work</a></li>
    <li><a href="#contact" class="nav-cta">Let's Talk</a></li>
  </ul>
</nav>

<section class="hero">
  <div class="hero-left">
    <span class="hero-eyebrow">Nonprofit Operations Consulting</span>
    <h1>Operations that hold<br/><em>the mission</em><br/>steady.</h1>
    <p class="hero-sub">
      I help mission-driven organizations build the operational infrastructure they need to do the work they actually came to do — without burning out their people or losing their way.
    </p>
    <div class="hero-actions">
      <a href="#services" class="btn-primary">See How I Work</a>
      <a href="#contact" class="btn-secondary">Start a Conversation</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-card">
      <p>"She built us a real foundation — financial systems, governance, donor infrastructure. What we had before was duct tape. What she left us was an organization."</p>
      <div class="hero-card-attr">— One Happy Exec</div>
      <div class="hero-stats">
        <div>
          <span class="stat-num">10+</span>
          <span class="stat-label">Years in ops leadership</span>
        </div>
        <div>
          <span class="stat-num">$1.9M+</span>
          <span class="stat-label">Federal grants managed</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="marquee-strip">
  <div class="marquee-inner">
    <span>Governance Design</span><span class="dot">✦</span>
    <span>Financial Systems</span><span class="dot">✦</span>
    <span>CRM &amp; Data Infrastructure</span><span class="dot">✦</span>
    <span>Grants Management</span><span class="dot">✦</span>
    <span>Team Operations</span><span class="dot">✦</span>
    <span>Strategic Advisory</span><span class="dot">✦</span>
    <span>Workflow Design</span><span class="dot">✦</span>
    <span>Change Management</span><span class="dot">✦</span>
    <span>Governance Design</span><span class="dot">✦</span>
    <span>Financial Systems</span><span class="dot">✦</span>
    <span>CRM &amp; Data Infrastructure</span><span class="dot">✦</span>
    <span>Grants Management</span><span class="dot">✦</span>
    <span>Team Operations</span><span class="dot">✦</span>
    <span>Strategic Advisory</span><span class="dot">✦</span>
    <span>Workflow Design</span><span class="dot">✦</span>
    <span>Change Management</span><span class="dot">✦</span>
  </div>
</div>

<section class="about" id="about">
  <div class="container">
    <div class="about-grid">
      <div class="about-text">
        <span class="section-label">About</span>
        <h2 class="section-title">Good operations are<br/><em>a form of care.</em></h2>
        <p>I'm Mia Carr — a nonprofit operations consultant with over a decade of experience building the systems that let organizations focus on the people they serve, not the chaos behind the scenes.</p>
        <p>My background spans <strong>political organizing, membership management, federal grants compliance, and full organizational buildouts from scratch</strong>. I've run operations for political consulting firms, built CRM and fundraising infrastructure for growing nonprofits, and led multi-program flagship initiatives at a national LGBTQ+ advocacy organization.</p>
        <p>I've worked in rooms that were underfunded, overstretched, and unclear on how they'd survive the next quarter — and I've helped turn those rooms into places people are proud to work.</p>
        <a href="#contact" class="btn-primary" style="margin-top:1.25rem;display:inline-block;">Work with me</a>
      </div>
      <div>
<div style="text-align:center; margin-bottom:2rem;">
        <img src="data:image/png;base64,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" alt="Mia Carr" style="width:180px;height:180px;border-radius:50%;object-fit:cover;object-position:center top;border:4px solid var(--terracotta);box-shadow:0 8px 32px rgba(0,0,0,0.12);" />
        <p style="margin-top:0.75rem;font-family:var(--font-serif);font-size:1.1rem;color:var(--forest);font-weight:600;">Mia Carr</p>
        <p style="margin-top:0.2rem;font-size:0.875rem;color:var(--text-muted);letter-spacing:0.05em;text-transform:uppercase;">Director, Soft Power Works</p>
      </div>
      <div class="about-values">
          <div class="value-card">
            <span class="value-icon">⚙️</span>
            <h4>Systems thinking</h4>
            <p>I see the whole picture — and design fixes that don't break three other things.</p>
          </div>
          <div class="value-card">
            <span class="value-icon">🤝</span>
            <h4>Mission alignment</h4>
            <p>Operations should serve your values, not just your budget spreadsheet.</p>
          </div>
          <div class="value-card">
            <span class="value-icon">📊</span>
            <h4>Real infrastructure</h4>
            <p>Not workarounds. Sustainable, documented systems your team can actually use.</p>
          </div>
          <div class="value-card">
            <span class="value-icon">🔊</span>
            <h4>Direct communication</h4>
            <p>You'll always know where we stand and what comes next. No vague deliverables.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="services" id="services">
  <div class="container">
    <span class="section-label">Services</span>
    <h2 class="section-title">Three ways to<br/><em>work together.</em></h2>
    <p class="services-intro">Every engagement is scoped around your actual situation — not a one-size template. Here's where we typically start.</p>
    <div class="services-grid">
      <div class="service-card">
        <span class="service-tier">Tier 01</span>
        <h3>Operational Reset</h3>
        <p>A deep-dive audit and rebuild of your core operational infrastructure. Right for orgs that have grown past their current systems — or never built real ones to begin with.</p>
        <div class="service-price">From $7,500 <span>project-based</span></div>
        <ul class="service-list">
          <li>Operational &amp; financial systems audit</li>
          <li>Governance and compliance review</li>
          <li>CRM and data infrastructure build</li>
          <li>Staff workflow redesign</li>
          <li>Full documentation package</li>
        </ul>
      </div>
      <div class="service-card">
        <span class="service-tier">Tier 02</span>
        <h3>Workflow &amp; Process Design</h3>
        <p>Targeted process work for specific pain points — onboarding, grants management, financial reporting, donor tracking, or team coordination systems.</p>
        <div class="service-price">From $5,000 <span>project-based</span></div>
        <ul class="service-list">
          <li>Process mapping and redesign</li>
          <li>Tool selection and setup</li>
          <li>SOP documentation</li>
          <li>Staff training</li>
          <li>30-day check-in</li>
        </ul>
      </div>
      <div class="service-card">
        <span class="service-tier">Tier 03</span>
        <h3>Strategic Advisory</h3>
        <p>Ongoing fractional operations support for leaders who need a trusted thinking partner without adding a full-time hire. Flexible retainer structure.</p>
        <div class="service-price">From $3,000 <span>/ month</span></div>
        <ul class="service-list">
          <li>Weekly or biweekly strategy sessions</li>
          <li>On-call ops consultation</li>
          <li>Vendor and tool management</li>
          <li>Project and team oversight</li>
          <li>Board meeting prep support</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section class="work" id="work">
  <div class="container">
    <span class="section-label">Selected Work</span>
    <h2 class="section-title">What this<br/><em>looks like in practice.</em></h2>
    <div class="work-grid">
      <div class="work-card">
        <div class="work-org">Founding Engagement · Nonprofit Foundation</div>
        <h3>Building an organization from a blank page</h3>
        <p>Joined as Founding Executive Director at a newly-formed foundation focused on mentorship and financial empowerment for young adults. Built the full operational infrastructure from scratch: budget systems, governance frameworks, donor management, CRM integration, a digital fundraising campaign, and an alumni outreach model.</p>
        <div class="work-tags">
          <span class="tag">Governance</span>
          <span class="tag">Fundraising Infrastructure</span>
          <span class="tag">CRM Build</span>
          <span class="tag">Financial Systems</span>
        </div>
      </div>
      <div class="work-card">
        <div class="work-org">Federal Grants Compliance · Conservation Sector</div>
        <h3>$1.9M federal grant management and compliance</h3>
        <p>Led compliance and program operations for a $1.9M federal grant through the Forest Service, including reporting, budget tracking, subcontractor coordination, and regulatory documentation. Zero compliance findings across the contract period.</p>
        <div class="work-tags">
          <span class="tag">Federal Compliance</span>
          <span class="tag">Budget Oversight</span>
          <span class="tag">Grant Reporting</span>
        </div>
      </div>
      <div class="work-card">
        <div class="work-org">National LGBTQ+ Advocacy Organization</div>
        <h3>Cross-functional operations across 175+ stakeholders</h3>
        <p>As Engagement Director, managed three flagship leadership programs and served as operational hub across Development, Political, and Communications teams. Coordinated a 175+ member campaign board and built reporting infrastructure that spanned multiple departments.</p>
        <div class="work-tags">
          <span class="tag">Stakeholder Management</span>
          <span class="tag">Program Operations</span>
          <span class="tag">Cross-functional Coordination</span>
        </div>
      </div>
      <div class="work-card">
        <div class="work-org">Political Consulting Firm</div>
        <h3>30% increase in client service capacity</h3>
        <p>As Director of Operations at a political consulting firm, restructured internal operations and client delivery workflows that drove a 30% increase in service capacity without adding headcount. Managed campaign analytics, voter targeting systems, and data infrastructure.</p>
        <div class="work-tags">
          <span class="tag">Operations Redesign</span>
          <span class="tag">Data Systems</span>
          <span class="tag">Capacity Building</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="testimonials">
  <div class="container">
    <span class="section-label">Testimonials</span>
    <h2 class="section-title">In their<br/><em>own words.</em></h2>
    <div class="testimonials-grid">
      <div class="testimonial-card">
        <span class="quote-mark">"</span>
        <p>Mia is great at taking random thoughts and ideas and turning them into processes.</p>
        <div class="testimonial-attr">
          Paul
          <span>The Penniman Foundation</span>
        </div>
      </div>
      <div class="testimonial-card">
        <span class="quote-mark">"</span>
        <p>Mia doesn't just fix problems — she builds the systems that prevent them. She came in when we were completely overwhelmed and left us with real infrastructure and a team that knew how to use it.</p>
        <div class="testimonial-attr">
          Erick
          <span>Burke Properties DMV</span>
        </div>
      </div>
      <div class="testimonial-card">
        <span class="quote-mark">"</span>
        <p>What stood out was how clearly she understood our mission alongside our operational gaps. She never lost sight of the people we serve while building the systems we needed to serve them better.</p>
        <div class="testimonial-attr">
          Stephen
          <span>Ellsworth, LLC</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="contact" id="contact">
  <div class="container">
    <div class="contact-grid">
      <div class="contact-left">
        <span class="section-label">Get in Touch</span>
        <h2>Ready to build something that <em>actually works?</em></h2>
        <p>Whether you're navigating a messy transition, building from scratch, or just need a thinking partner who understands operations and mission — let's talk about what you're working with.</p>
        <div class="contact-details">
          <div class="contact-detail">
            <div class="contact-detail-icon">✉</div>
            <span>admin@softpowerworks.org</span>
          </div>
          <div class="contact-detail">
            <div class="contact-detail-icon">📍</div>
            <span>Bowie, MD · Remote &amp; Mid-Atlantic</span>
          </div>
        </div>
      </div>
      <div>
        <form class="contact-form" onsubmit="handleSubmit(event)">
          <div class="form-row">
            <div class="form-group">
              <label for="name">Your Name</label>
              <input type="text" id="name" placeholder="Full name" required />
            </div>
            <div class="form-group">
              <label for="org">Organization</label>
              <input type="text" id="org" placeholder="Org name" />
            </div>
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" placeholder="you@organization.org" required />
          </div>
          <div class="form-group">
            <label for="service">What are you looking for?</label>
            <select id="service">
              <option value="">Select a service...</option>
              <option>Operational Reset</option>
              <option>Workflow &amp; Process Design</option>
              <option>Strategic Advisory Retainer</option>
              <option>Not sure yet — let's talk</option>
            </select>
          </div>
          <div class="form-group">
            <label for="message">Tell me about your situation</label>
            <textarea id="message" placeholder="What's going on? What's not working? What does success look like?"></textarea>
          </div>
          <button type="submit" class="form-submit">Send Message</button>
          <div id="form-confirm" style="display:none; font-size:0.9rem; color:var(--green-mid); font-weight:500; margin-top:0.5rem;">
            Message sent! I'll be in touch within 2 business days.
          </div>
        </form>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="container">
    <div class="footer-inner">
      <div class="footer-logo">Soft Power<span>.</span>Works</div>
      <div class="footer-links">
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#work">Work</a>
        <a href="#contact">Contact</a>
      </div>
      <div class="footer-copy">© 2026 Soft Power Works. All rights reserved.</div>
    </div>
  </div>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
  function handleSubmit(e) {
    e.preventDefault();
    document.getElementById('form-confirm').style.display = 'block';
    e.target.reset();
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(el => {
      if (el.isIntersecting) {
        el.target.style.opacity = '1';
        el.target.style.transform = 'translateY(0)';
        observer.unobserve(el.target);
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.work-card, .service-card, .testimonial-ca
