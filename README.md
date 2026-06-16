# This-Is-For-The-Soul-booking(https://github.com/user-attachments/files/29007718/TIFTS.html)
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>This Is for the Soul — Tarot Readings</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400&display=swap" rel="stylesheet" />
  <style>
    /* ── TOKENS ────────────────────────────────────────────── */
    :root {
      --parchment:  #F2EBE1;
      --blush:      #E8D8CC;
      --gold:       #C4956A;
      --mauve:      #8C6F6B;
      --espresso:   #3B2D2A;
      --white:      #FDFAF7;

      --font-display: 'Playfair Display', Georgia, serif;
      --font-body:    'DM Sans', system-ui, sans-serif;
      --font-mono:    'DM Mono', monospace;

      --radius: 12px;
      --max-w: 1100px;
    }

    /* ── RESET ─────────────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: var(--font-body);
      background: var(--parchment);
      color: var(--espresso);
      -webkit-font-smoothing: antialiased;
    }
    img { display: block; max-width: 100%; }
    a { color: inherit; text-decoration: none; }

    /* ── NAV ───────────────────────────────────────────────── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20px 40px;
      background: rgba(242, 235, 225, 0.85);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(140, 111, 107, 0.15);
    }
    .nav-logo {
      font-family: var(--font-display);
      font-size: 1rem;
      letter-spacing: 0.04em;
      color: var(--espresso);
    }
    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
    }
    .nav-links a {
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      color: var(--mauve);
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--espresso); }
    .nav-cta {
      background: var(--espresso);
      color: var(--parchment) !important;
      padding: 8px 20px;
      border-radius: 100px;
      transition: background 0.2s !important;
    }
    .nav-cta:hover { background: var(--gold) !important; color: var(--white) !important; }

    /* ── HERO ──────────────────────────────────────────────── */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 120px 24px 80px;
      position: relative;
      overflow: hidden;
    }

    /* celestial background */
    .hero-canvas {
      position: absolute;
      inset: 0;
      pointer-events: none;
      z-index: 0;
    }

    .hero-content { position: relative; z-index: 1; max-width: 720px; }

    .hero-eyebrow {
      font-family: var(--font-mono);
      font-size: 0.72rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 24px;
    }

    .hero-title {
      font-family: var(--font-display);
      font-size: clamp(2.8rem, 6vw, 5rem);
      line-height: 1.1;
      color: var(--espresso);
      margin-bottom: 12px;
    }
    .hero-title em {
      font-style: italic;
      color: var(--gold);
    }

    .hero-sub {
      font-size: clamp(1rem, 2vw, 1.2rem);
      font-weight: 300;
      color: var(--mauve);
      line-height: 1.7;
      margin-top: 20px;
      margin-bottom: 40px;
      max-width: 520px;
      margin-left: auto;
      margin-right: auto;
    }

    .hero-actions {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 14px 32px;
      border-radius: 100px;
      font-size: 0.9rem;
      font-weight: 500;
      letter-spacing: 0.02em;
      cursor: pointer;
      border: none;
      transition: all 0.22s ease;
    }
    .btn-primary {
      background: var(--espresso);
      color: var(--parchment);
    }
    .btn-primary:hover { background: var(--gold); }
    .btn-ghost {
      background: transparent;
      color: var(--espresso);
      border: 1.5px solid rgba(59,45,42,0.3);
    }
    .btn-ghost:hover {
      border-color: var(--gold);
      color: var(--gold);
    }

    /* scroll cue */
    .scroll-cue {
      position: absolute;
      bottom: 36px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      font-size: 0.72rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--mauve);
      opacity: 0.7;
      animation: bobDown 2.2s ease-in-out infinite;
      z-index: 1;
    }
    .scroll-cue svg { width: 18px; height: 18px; }
    @keyframes bobDown {
      0%, 100% { transform: translateX(-50%) translateY(0); }
      50%       { transform: translateX(-50%) translateY(6px); }
    }

    /* ── ABOUT STRIP ───────────────────────────────────────── */
    .about-strip {
      background: var(--blush);
      padding: 64px 24px;
      text-align: center;
    }
    .about-strip p {
      max-width: 600px;
      margin: 0 auto;
      font-size: 1.05rem;
      line-height: 1.85;
      color: var(--espresso);
      font-weight: 300;
    }
    .about-strip strong {
      font-weight: 500;
      color: var(--espresso);
    }

    /* ── READINGS SECTION ──────────────────────────────────── */
    .readings {
      padding: 96px 24px;
      max-width: var(--max-w);
      margin: 0 auto;
    }
    .section-header {
      text-align: center;
      margin-bottom: 64px;
    }
    .section-eyebrow {
      font-family: var(--font-mono);
      font-size: 0.72rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 16px;
    }
    .section-title {
      font-family: var(--font-display);
      font-size: clamp(1.8rem, 3.5vw, 2.8rem);
      line-height: 1.2;
      color: var(--espresso);
    }
    .section-title em { font-style: italic; color: var(--gold); }
    .section-sub {
      margin-top: 16px;
      color: var(--mauve);
      font-size: 1rem;
      font-weight: 300;
      max-width: 480px;
      margin-left: auto;
      margin-right: auto;
      line-height: 1.7;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 24px;
    }

    .reading-card {
      background: var(--white);
      border-radius: var(--radius);
      padding: 36px 32px;
      border: 1px solid rgba(140, 111, 107, 0.15);
      display: flex;
      flex-direction: column;
      gap: 16px;
      transition: transform 0.22s ease, box-shadow 0.22s ease;
      position: relative;
      overflow: hidden;
    }
    .reading-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--gold), var(--mauve));
      opacity: 0;
      transition: opacity 0.22s;
    }
    .reading-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 16px 40px rgba(59,45,42,0.1);
    }
    .reading-card:hover::before { opacity: 1; }

    .card-icon {
      font-size: 1.6rem;
      line-height: 1;
    }
    .card-tag {
      font-family: var(--font-mono);
      font-size: 0.68rem;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: -8px;
    }
    .card-title {
      font-family: var(--font-display);
      font-size: 1.35rem;
      color: var(--espresso);
      line-height: 1.3;
    }
    .card-desc {
      font-size: 0.9rem;
      line-height: 1.75;
      color: var(--mauve);
      font-weight: 300;
      flex: 1;
    }
    .card-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding-top: 16px;
      border-top: 1px solid rgba(140,111,107,0.12);
      margin-top: auto;
    }
    .card-price {
      font-family: var(--font-mono);
      font-size: 1.1rem;
      color: var(--espresso);
      font-weight: 400;
    }
    .card-delivery {
      font-size: 0.78rem;
      color: var(--mauve);
    }
    .card-btn {
      background: var(--espresso);
      color: var(--parchment);
      padding: 10px 22px;
      border-radius: 100px;
      font-size: 0.83rem;
      font-weight: 500;
      cursor: pointer;
      border: none;
      transition: background 0.2s;
      font-family: var(--font-body);
    }
    .card-btn:hover { background: var(--gold); }

    /* ── HOW IT WORKS ──────────────────────────────────────── */
    .how {
      background: var(--blush);
      padding: 96px 24px;
    }
    .how-inner {
      max-width: var(--max-w);
      margin: 0 auto;
    }
    .steps {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 40px;
      margin-top: 64px;
    }
    .step {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }
    .step-num {
      font-family: var(--font-display);
      font-size: 2.4rem;
      color: var(--gold);
      line-height: 1;
      font-style: italic;
    }
    .step-title {
      font-family: var(--font-display);
      font-size: 1.1rem;
      color: var(--espresso);
    }
    .step-body {
      font-size: 0.88rem;
      line-height: 1.8;
      color: var(--mauve);
      font-weight: 300;
    }

    /* ── FAQ ───────────────────────────────────────────────── */
    .faq {
      padding: 96px 24px;
      max-width: 720px;
      margin: 0 auto;
    }
    .faq-list {
      margin-top: 56px;
      display: flex;
      flex-direction: column;
      gap: 0;
    }
    .faq-item {
      border-top: 1px solid rgba(140,111,107,0.2);
    }
    .faq-item:last-child { border-bottom: 1px solid rgba(140,111,107,0.2); }
    .faq-q {
      width: 100%;
      background: none;
      border: none;
      text-align: left;
      padding: 24px 0;
      font-family: var(--font-display);
      font-size: 1.05rem;
      color: var(--espresso);
      cursor: pointer;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
    }
    .faq-q:hover { color: var(--gold); }
    .faq-icon {
      flex-shrink: 0;
      width: 22px;
      height: 22px;
      border-radius: 50%;
      border: 1.5px solid var(--mauve);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1rem;
      color: var(--mauve);
      transition: all 0.2s;
    }
    .faq-item.open .faq-icon {
      background: var(--gold);
      border-color: var(--gold);
      color: white;
      transform: rotate(45deg);
    }
    .faq-a {
      font-size: 0.9rem;
      line-height: 1.85;
      color: var(--mauve);
      font-weight: 300;
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.35s ease, padding 0.2s;
      padding-bottom: 0;
    }
    .faq-item.open .faq-a {
      max-height: 300px;
      padding-bottom: 24px;
    }

    /* ── FOOTER ────────────────────────────────────────────── */
    footer {
      background: var(--espresso);
      color: var(--parchment);
      text-align: center;
      padding: 56px 24px;
    }
    .footer-logo {
      font-family: var(--font-display);
      font-size: 1.5rem;
      font-style: italic;
      margin-bottom: 12px;
      color: var(--gold);
    }
    .footer-tagline {
      font-size: 0.85rem;
      color: rgba(232,216,204,0.6);
      margin-bottom: 32px;
      font-weight: 300;
    }
    .footer-links {
      display: flex;
      gap: 28px;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 40px;
    }
    .footer-links a {
      font-size: 0.8rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: rgba(232,216,204,0.5);
      transition: color 0.2s;
    }
    .footer-links a:hover { color: var(--gold); }
    .footer-copy {
      font-size: 0.75rem;
      color: rgba(232,216,204,0.3);
      font-family: var(--font-mono);
    }

    /* ── BOOKING MODAL ─────────────────────────────────────── */
    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(59,45,42,0.5);
      backdrop-filter: blur(4px);
      z-index: 200;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.25s;
    }
    .modal-overlay.open {
      opacity: 1;
      pointer-events: all;
    }
    .modal {
      background: var(--white);
      border-radius: 16px;
      padding: 48px 40px;
      max-width: 520px;
      width: 100%;
      position: relative;
      transform: translateY(16px);
      transition: transform 0.25s;
    }
    .modal-overlay.open .modal { transform: translateY(0); }
    .modal-close {
      position: absolute;
      top: 20px; right: 20px;
      background: none;
      border: none;
      font-size: 1.4rem;
      cursor: pointer;
      color: var(--mauve);
      line-height: 1;
      padding: 4px;
    }
    .modal-close:hover { color: var(--espresso); }
    .modal-eyebrow {
      font-family: var(--font-mono);
      font-size: 0.68rem;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 12px;
    }
    .modal-title {
      font-family: var(--font-display);
      font-size: 1.6rem;
      color: var(--espresso);
      margin-bottom: 8px;
    }
    .modal-price {
      font-family: var(--font-mono);
      font-size: 1rem;
      color: var(--mauve);
      margin-bottom: 28px;
    }
    .modal form { display: flex; flex-direction: column; gap: 16px; }
    .form-group { display: flex; flex-direction: column; gap: 6px; }
    .form-group label {
      font-size: 0.8rem;
      font-weight: 500;
      letter-spacing: 0.04em;
      color: var(--espresso);
    }
    .form-group input,
    .form-group textarea {
      padding: 12px 16px;
      border: 1.5px solid rgba(140,111,107,0.25);
      border-radius: 8px;
      font-family: var(--font-body);
      font-size: 0.9rem;
      color: var(--espresso);
      background: var(--parchment);
      outline: none;
      transition: border-color 0.2s;
      resize: vertical;
    }
    .form-group input:focus,
    .form-group textarea:focus {
      border-color: var(--gold);
    }
    .form-group textarea { min-height: 100px; }
    .modal-submit {
      margin-top: 8px;
      width: 100%;
      padding: 15px;
      background: var(--espresso);
      color: var(--parchment);
      border: none;
      border-radius: 100px;
      font-family: var(--font-body);
      font-size: 0.95rem;
      font-weight: 500;
      cursor: pointer;
      transition: background 0.2s;
    }
    .modal-submit:hover { background: var(--gold); }
    .modal-note {
      font-size: 0.75rem;
      color: var(--mauve);
      text-align: center;
      margin-top: 4px;
      font-weight: 300;
    }

    /* ── RESPONSIVE ────────────────────────────────────────── */
    @media (max-width: 680px) {
      nav { padding: 16px 20px; }
      .nav-links { display: none; }
      .modal { padding: 36px 24px; }
      .readings, .how-inner, .faq { padding-left: 20px; padding-right: 20px; }
    }

    /* ── REDUCED MOTION ────────────────────────────────────── */
    @media (prefers-reduced-motion: reduce) {
      .scroll-cue { animation: none; }
      * { transition-duration: 0.01ms !important; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <span class="nav-logo">This Is for the Soul</span>
    <ul class="nav-links">
      <li><a href="#readings">Readings</a></li>
      <li><a href="#how">How It Works</a></li>
      <li><a href="#faq">FAQ</a></li>
      <li><a href="#readings" class="nav-cta">Book Now</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <canvas class="hero-canvas" id="heroCanvas"></canvas>
    <div class="hero-content">
      <p class="hero-eyebrow">Channeled tarot readings · delivered to you</p>
      <h1 class="hero-title">The cards know<br><em>what you came here for.</em></h1>
      <p class="hero-sub">Pre-recorded readings channeled just for you — honest, grounded, and straight from the soul. No sugarcoating. Just clarity.</p>
      <div class="hero-actions">
        <a href="#readings" class="btn btn-primary">Browse Readings</a>
        <a href="#how" class="btn btn-ghost">See How It Works</a>
      </div>
    </div>
    <div class="scroll-cue" aria-hidden="true">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M12 5v14M5 12l7 7 7-7"/>
      </svg>
    </div>
  </section>

  <!-- ABOUT STRIP -->
  <section class="about-strip">
    <p>I'm Bri — tarot reader, content creator, and the voice behind <strong>This Is for the Soul</strong>. I pull cards the way a best friend tells you the truth: with love, but without the fluff. These readings aren't about prediction — they're about reflection, clarity, and showing you what you already know.</p>
  </section>

  <!-- READINGS -->
  <section class="readings" id="readings">
    <div class="section-header">
      <p class="section-eyebrow">Choose your reading</p>
      <h2 class="section-title">What do you need<br><em>right now?</em></h2>
      <p class="section-sub">Each reading is pre-recorded, channeled specifically for your question, and delivered within the timeframe listed.</p>
    </div>

    <div class="cards-grid">

      <div class="reading-card">
        <p class="card-tag">Most Popular</p>
        <p class="card-icon">✦</p>
        <h3 class="card-title">The Soul Check-In</h3>
        <p class="card-desc">A general energy reading for where you are right now. What's moving, what's stuck, what the cards want you to know. Perfect if you're not sure what question to ask — the cards will find it.</p>
        <div class="card-footer">
          <div>
            <p class="card-price">$33</p>
            <p class="card-delivery">Delivered in 3–5 days</p>
          </div>
          <button class="card-btn" onclick="window.open('https://buy.stripe.com/4gMaEX9Xj4ipbwufzh8N209', '_blank')">Book This</button>
        </div>
      </div>

      <div class="reading-card">
        <p class="card-icon">◇</p>
        <h3 class="card-title">Ask the Cards</h3>
        <p class="card-desc">You have one specific question — love, career, a decision you're sitting with. Bring it, and I'll pull the cards that speak directly to it. No filler, just the honest answer you need.</p>
        <div class="card-footer">
          <div>
            <p class="card-price">$55</p>
            <p class="card-delivery">Delivered in 3–5 days</p>
          </div>
          <button class="card-btn" onclick="window.open('https://buy.stripe.com/dRmeVdc5r3elbwu4UD8N20a', '_blank')">Book This</button>
        </div>
      </div>

      <div class="reading-card">
        <p class="card-icon">◯</p>
        <h3 class="card-title">The Deep Dive</h3>
        <p class="card-desc">A full spread for the bigger questions — your purpose, a major life crossroads, something you've been circling for a while. This one goes deep. Expect a longer recording and a lot of honesty.</p>
        <div class="card-footer">
          <div>
            <p class="card-price">$77</p>
            <p class="card-delivery">Delivered in 3–5 days</p>
          </div>
          <button class="card-btn" onclick="window.open('https://buy.stripe.com/6oU6oH2uR3elasq3Qz8N20b', '_blank')">Book This</button>
        </div>
      </div>

    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section class="how" id="how">
    <div class="how-inner">
      <div class="section-header">
        <p class="section-eyebrow">The process</p>
        <h2 class="section-title">Simple, <em>intentional,</em><br>made for you.</h2>
      </div>
      <div class="steps">
        <div class="step">
          <p class="step-num">I.</p>
          <h3 class="step-title">You book &amp; share</h3>
          <p class="step-body">Choose your reading, complete your booking, and share a little about what you're bringing to the cards — a question, a situation, or just where you are.</p>
        </div>
        <div class="step">
          <p class="step-num">II.</p>
          <h3 class="step-title">I channel &amp; record</h3>
          <p class="step-body">I sit with your energy, pull your cards, and record a reading that's meant only for you. No scripts, no templates — just what comes through.</p>
        </div>
        <div class="step">
          <p class="step-num">III.</p>
          <h3 class="step-title">You receive &amp; reflect</h3>
          <p class="step-body">Your reading lands in your inbox — a private video link, yours to return to as many times as you need. The real work starts with you.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="faq" id="faq">
    <div class="section-header">
      <p class="section-eyebrow">Questions</p>
      <h2 class="section-title">What you're<br><em>probably wondering</em></h2>
    </div>
    <div class="faq-list">
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">
          What exactly is a pre-recorded reading?
          <span class="faq-icon">+</span>
        </button>
        <p class="faq-a">It's a video I record just for you — not a live call, not a template. I sit with your intention, pull your cards, and deliver an honest, channeled reading as a private video link sent to your email.</p>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">
          Do I need to believe in tarot for it to work?
          <span class="faq-icon">+</span>
        </button>
        <p class="faq-a">Not at all. I use tarot as a mirror — a tool for reflection, not prediction. Whether you're a believer or just curious, you'll walk away with something to think about. The cards meet you where you are.</p>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">
          How do I share my question or intention?
          <span class="faq-icon">+</span>
        </button>
        <p class="faq-a">During booking, there's a field where you can share whatever feels relevant — a specific question, a situation, a feeling, or even just "I don't know what I need right now." That's enough.</p>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">
          When will I receive my reading?
          <span class="faq-icon">+</span>
        </button>
        <p class="faq-a">Each listing shows a delivery window — for all readings right now, that's 3–5 days. I'll send it directly to the email you provide at booking.</p>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">
          What's your refund policy?
          <span class="faq-icon">+</span>
        </button>
        <p class="faq-a">Because readings are energetically personalized and can't be "returned," all sales are final once your reading has been recorded. If you have concerns before I've started, please reach out.</p>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p class="footer-logo">This Is for the Soul</p>
    <p class="footer-tagline">Honest readings, real and raw reflection personalized for you.</p>
    <nav class="footer-links" aria-label="Footer navigation">
      <a href="#readings">Book a Reading</a>
      <a href="https://substack.com" target="_blank" rel="noopener">Substack</a>
      <a href="#" target="_blank" rel="noopener">Podcast</a>
      <a href="#" target="_blank" rel="noopener">YouTube</a>
    </nav>
    <p class="footer-copy">© 2025 This Is for the Soul · All rights reserved</p>
  </footer>

  <!-- BOOKING MODAL -->
  <div class="modal-overlay" id="modal" onclick="handleOverlayClick(event)">
    <div class="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
      <button class="modal-close" onclick="closeModal()" aria-label="Close">×</button>
      <p class="modal-eyebrow">Book your reading</p>
      <h2 class="modal-title" id="modal-title">The Soul Check-In</h2>
      <p class="modal-price" id="modal-price">$22</p>
      <form onsubmit="handleSubmit(event)">
        <div class="form-group">
          <label for="name">Your name</label>
          <input type="text" id="name" placeholder="First name is fine" required />
        </div>
        <div class="form-group">
          <label for="email">Email address</label>
          <input type="email" id="email" placeholder="Where I'll send your reading" required />
        </div>
        <div class="form-group">
          <label for="intention">Your question or intention <span style="color:var(--mauve);font-weight:300">(optional)</span></label>
          <textarea id="intention" placeholder="Share whatever feels relevant — a question, a situation, or even just where you're at right now."></textarea>
        </div>
        <button type="submit" class="modal-submit">Continue to Payment →</button>
        <p class="modal-note">You'll be taken to a secure checkout page to complete your booking.</p>
      </form>
    </div>
  </div>

  <script>
    /* ── CELESTIAL CANVAS ─────────────────────────────────── */
    const canvas = document.getElementById('heroCanvas');
    const ctx = canvas.getContext('2d');
    let W, H, stars = [];

    function resize() {
      W = canvas.width  = canvas.offsetWidth;
      H = canvas.height = canvas.offsetHeight;
    }

    function initStars() {
      stars = [];
      const count = Math.floor((W * H) / 9000);
      for (let i = 0; i < count; i++) {
        stars.push({
          x: Math.random() * W,
          y: Math.random() * H,
          r: Math.random() * 1.4 + 0.3,
          a: Math.random() * Math.PI * 2,
          speed: (Math.random() * 0.003 + 0.001) * (Math.random() < 0.5 ? 1 : -1),
          baseOpacity: Math.random() * 0.35 + 0.1,
        });
      }
    }

    let rot = 0;
    function draw() {
      ctx.clearRect(0, 0, W, H);
      rot += 0.0004;

      /* rotating star cluster */
      const cx = W * 0.72, cy = H * 0.28, clusterR = Math.min(W, H) * 0.32;
      stars.forEach(s => {
        s.a += s.speed;
        const x = cx + Math.cos(s.a + rot) * clusterR * (s.r / 1.8);
        const y = cy + Math.sin(s.a + rot) * clusterR * (s.r / 1.8) * 0.6;
        const t = (Date.now() / 2800) + s.a;
        const opacity = s.baseOpacity * (0.7 + 0.3 * Math.sin(t));
        ctx.beginPath();
        ctx.arc(x, y, s.r, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(196,149,106,${opacity})`;
        ctx.fill();
      });

      /* large crescent-like glyph */
      ctx.save();
      ctx.translate(cx, cy);
      ctx.rotate(rot * 0.4);
      ctx.beginPath();
      ctx.arc(0, 0, clusterR * 0.55, 0, Math.PI * 2);
      ctx.strokeStyle = `rgba(196,149,106,0.07)`;
      ctx.lineWidth = 1;
      ctx.stroke();
      ctx.beginPath();
      ctx.arc(clusterR * 0.18, 0, clusterR * 0.44, 0, Math.PI * 2);
      ctx.strokeStyle = `rgba(196,149,106,0.05)`;
      ctx.stroke();
      ctx.restore();

      requestAnimationFrame(draw);
    }

    window.addEventListener('resize', () => { resize(); initStars(); });
    resize(); initStars(); draw();

    /* ── FAQ ──────────────────────────────────────────────── */
    function toggleFaq(btn) {
      const item = btn.closest('.faq-item');
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item.open').forEach(el => el.classList.remove('open'));
      if (!isOpen) item.classList.add('open');
    }

    /* ── MODAL ────────────────────────────────────────────── */
    function openModal(name, price) {
      document.getElementById('modal-title').textContent = name;
      document.getElementById('modal-price').textContent = price;
      document.getElementById('modal').classList.add('open');
      document.body.style.overflow = 'hidden';
    }

    function closeModal() {
      document.getElementById('modal').classList.remove('open');
      document.body.style.overflow = '';
    }

    function handleOverlayClick(e) {
      if (e.target === document.getElementById('modal')) closeModal();
    }

    document.addEventListener('keydown', e => {
      if (e.key === 'Escape') closeModal();
    });

    function handleSubmit(e) {
      e.preventDefault();
      // TODO: wire to Stripe payment link or backend
      alert('Stripe integration coming soon — your booking details have been captured.');
    }
  </script>
</body>
</html>
