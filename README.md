<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Satyanarayana - PEGA LSA Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link href="https://fonts.googleapis.com/css2?family=Calibre:wght@400;500;600&family=SF+Mono&family=Fira+Code:wght@300;400&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --navy:        #0a192f;
      --navy-light:  #112240;
      --navy-shadow: #020c1b;
      --slate-dark:  #495670;
      --slate:       #8892b0;
      --slate-light: #a8b2d8;
      --white:       #ccd6f6;
      --white-bright:#e6f1ff;
      --green:       #64ffda;
      --green-tint:  rgba(100,255,218,0.1);
      --font-sans:   'Inter', 'Calibre', 'Helvetica Neue', Arial, sans-serif;
      --font-mono:   'Fira Code', 'SF Mono', monospace;
      --transition:  all 0.25s cubic-bezier(0.645,0.045,0.355,1);
      --nav-height:  70px;
      --tab-height:  42px;
    }
    html { scroll-behavior: smooth; box-sizing: border-box; }
    *, *::before, *::after { box-sizing: inherit; margin: 0; padding: 0; }
    body {
      background: var(--navy);
      color: var(--slate);
      font-family: var(--font-sans);
      font-size: 16px;
      line-height: 1.3;
      counter-reset: section;
      overflow-x: hidden;
    }
    a { color: var(--green); text-decoration: none; transition: var(--transition); }
    a:hover { color: var(--green); }
    ::selection { background: var(--slate-dark); }
    ::-webkit-scrollbar { width: 8px; }
    ::-webkit-scrollbar-track { background: var(--navy); }
    ::-webkit-scrollbar-thumb { background: var(--slate-dark); border-radius: 4px; }

    /* ─── NAV ─── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
      height: var(--nav-height);
      display: flex; justify-content: space-between; align-items: center;
      padding: 0 50px;
      background: rgba(10,25,47,0.85);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(100,255,218,0.05);
      transition: var(--transition);
    }
    .nav-logo {
      color: var(--green);
      font-family: var(--font-mono);
      font-size: 1.2rem;
      font-weight: 400;
      letter-spacing: 2px;
      text-decoration: none;
    }
    .nav-links { display: flex; align-items: center; gap: 8px; list-style: none; }
    .nav-links li a {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      letter-spacing: 0.1em;
      padding: 10px 16px;
      color: var(--white);
      transition: var(--transition);
    }
    .nav-links li a:hover { color: var(--green); }
    .nav-links li a span { color: var(--green); margin-right: 4px; }
    .nav-resume {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      padding: 10px 18px;
      border: 1px solid var(--green);
      border-radius: 4px;
      color: var(--green);
      margin-left: 12px;
      transition: var(--transition);
    }
    .nav-resume:hover { background: var(--green-tint); }

    /* ─── SIDEBAR ─── */
    .side-left, .side-right {
      position: fixed;
      bottom: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 20px;
      z-index: 10;
    }
    .side-left { left: 40px; }
    .side-right { right: 40px; }
    .side-left::after, .side-right::after {
      content: '';
      display: block;
      width: 1px;
      height: 90px;
      background: var(--slate);
    }
    .side-left a {
      color: var(--slate);
      font-size: 1.1rem;
      width: 22px;
      height: 22px;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: var(--transition);
    }
    .side-left a:hover { color: var(--green); transform: translateY(-3px); }
    .side-right a {
      font-family: var(--font-mono);
      font-size: 0.72rem;
      letter-spacing: 0.12em;
      color: var(--slate);
      writing-mode: vertical-rl;
      transition: var(--transition);
    }
    .side-right a:hover { color: var(--green); transform: translateY(-3px); }

    /* ─── MAIN ─── */
    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 0 150px;
    }
    section {
      padding: 100px 0;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    #hero { padding: 0; }

    /* ─── SECTION HEADINGS ─── */
    .section-heading {
      display: flex;
      align-items: center;
      gap: 20px;
      font-family: var(--font-sans);
      font-size: clamp(1.4rem, 3vw, 1.75rem);
      font-weight: 600;
      color: var(--white);
      white-space: nowrap;
      margin-bottom: 40px;
    }
    .section-heading::before {
      content: counter(section, decimal-leading-zero) ".";
      counter-increment: section;
      font-family: var(--font-mono);
      font-size: 1rem;
      font-weight: 400;
      color: var(--green);
    }
    .section-heading::after {
      content: '';
      display: block;
      width: 300px;
      height: 1px;
      background: var(--slate-dark);
    }

    /* ─── HERO ─── */
    #hero {
      max-width: 900px;
      padding-top: var(--nav-height);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .hero-intro {
      font-family: var(--font-mono);
      font-size: 0.95rem;
      color: var(--green);
      margin-bottom: 20px;
      letter-spacing: 0.05em;
    }
    .hero-name {
      font-size: clamp(2.5rem, 7vw, 5rem);
      font-weight: 600;
      color: var(--white-bright);
      line-height: 1.1;
      margin-bottom: 8px;
    }
    .hero-tagline {
      font-size: clamp(1.8rem, 5vw, 3.5rem);
      font-weight: 600;
      color: var(--slate);
      line-height: 1.1;
      margin-bottom: 30px;
    }
    .hero-desc {
      max-width: 520px;
      font-size: 1rem;
      line-height: 1.75;
      color: var(--slate);
      margin-bottom: 50px;
    }
    .hero-desc a { color: var(--green); }
    .hero-cta {
      display: inline-block;
      padding: 18px 28px;
      border: 1px solid var(--green);
      border-radius: 4px;
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--green);
      letter-spacing: 0.08em;
      transition: var(--transition);
    }
    .hero-cta:hover { background: var(--green-tint); transform: translateY(-2px); }
    .cert-badge-hero {
      margin-top: 40px;
      display: flex;
      gap: 20px;
      align-items: center;
      flex-wrap: wrap;
    }
    .cert-badge-hero img { height: 70px; opacity: 0.85; transition: var(--transition); }
    .cert-badge-hero img:hover { opacity: 1; transform: translateY(-3px); }

    /* ─── ABOUT ─── */
    #about { min-height: auto; }
    .about-grid {
      display: grid;
      grid-template-columns: 3fr 2fr;
      gap: 50px;
      align-items: start;
    }
    .about-text p {
      font-size: 1rem;
      line-height: 1.8;
      color: var(--slate);
      margin-bottom: 16px;
    }
    .about-text p a { color: var(--green); }
    .about-text ul {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 6px 20px;
      list-style: none;
      margin-top: 16px;
    }
    .about-text ul li {
      font-family: var(--font-mono);
      font-size: 0.82rem;
      color: var(--slate);
    }
    .about-text ul li::before { content: '▹ '; color: var(--green); }
    .about-img-wrap {
      position: relative;
      max-width: 280px;
      margin: 0 auto;
    }
    .about-img-placeholder {
      width: 100%;
      padding-bottom: 100%;
      background: var(--navy-light);
      border-radius: 4px;
      border: 2px solid var(--green);
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .about-img-placeholder::after {
      content: '';
      position: absolute;
      inset: 0;
      background: var(--green-tint);
      transition: var(--transition);
    }
    .about-img-placeholder:hover::after { opacity: 0; }
    .about-img-wrap::after {
      content: '';
      position: absolute;
      top: 14px;
      left: 14px;
      width: 100%;
      height: 100%;
      border: 2px solid var(--green);
      border-radius: 4px;
      z-index: -1;
      transition: var(--transition);
    }
    .about-img-wrap:hover::after { top: 8px; left: 8px; }
    .about-initials {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-family: var(--font-mono);
      font-size: 3rem;
      color: var(--green);
      z-index: 1;
      font-weight: 400;
    }

    /* ─── CERTIFICATIONS ─── */
    #certifications { min-height: auto; }
    .certs-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
      gap: 24px;
    }
    .cert-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 14px;
      padding: 28px 20px;
      background: var(--navy-light);
      border-radius: 4px;
      border: 1px solid var(--navy-light);
      text-align: center;
      transition: var(--transition);
      cursor: default;
    }
    .cert-item:hover {
      border-color: var(--green);
      transform: translateY(-5px);
      box-shadow: 0 8px 30px -10px rgba(100,255,218,0.2);
    }
    .cert-item img { height: 90px; object-fit: contain; }
    .cert-item p {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--slate-light);
      line-height: 1.4;
    }
    .cert-verify {
      margin-top: 30px;
      font-family: var(--font-mono);
      font-size: 0.82rem;
      color: var(--slate);
      text-align: center;
    }
    .cert-verify a { color: var(--green); }

    /* ─── EXPERIENCE ─── */
    #experience { min-height: auto; }
    .tabs-wrap { display: flex; gap: 0; }
    .tabs-list {
      display: flex;
      flex-direction: column;
      min-width: 160px;
      border-left: 2px solid var(--navy-light);
    }
    .tab-btn {
      background: none;
      border: none;
      border-left: 2px solid transparent;
      margin-left: -2px;
      padding: 0 20px;
      height: var(--tab-height);
      font-family: var(--font-mono);
      font-size: 0.82rem;
      color: var(--slate);
      text-align: left;
      cursor: pointer;
      white-space: nowrap;
      transition: var(--transition);
      letter-spacing: 0.04em;
    }
    .tab-btn:hover { background: var(--green-tint); color: var(--green); }
    .tab-btn.active { border-left-color: var(--green); color: var(--green); background: var(--green-tint); }
    .tab-panel { display: none; padding: 0 30px; }
    .tab-panel.active { display: block; }
    .tab-title {
      font-size: 1.1rem;
      font-weight: 500;
      color: var(--white);
      margin-bottom: 4px;
    }
    .tab-title span { color: var(--green); }
    .tab-company {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      color: var(--slate);
      margin-bottom: 20px;
      letter-spacing: 0.04em;
    }
    .tab-company span { color: var(--green); font-style: italic; }
    .tab-duties { list-style: none; display: flex; flex-direction: column; gap: 10px; }
    .tab-duties li {
      position: relative;
      padding-left: 22px;
      font-size: 0.95rem;
      line-height: 1.7;
      color: var(--slate);
    }
    .tab-duties li::before {
      content: '▹';
      position: absolute;
      left: 0;
      color: var(--green);
      font-size: 0.85rem;
      top: 2px;
    }

    /* ─── WORK/PROJECTS ─── */
    #portfolio { min-height: auto; }
    .projects-list { display: flex; flex-direction: column; gap: 0; }
    .project-item {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      padding: 40px 0;
      border-bottom: 1px solid var(--navy-light);
      align-items: center;
    }
    .project-item:last-child { border-bottom: none; }
    .project-item:nth-child(even) .project-content { order: 2; }
    .project-item:nth-child(even) .project-img { order: 1; }
    .project-overline {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      color: var(--green);
      margin-bottom: 8px;
      letter-spacing: 0.05em;
    }
    .project-title {
      font-size: 1.3rem;
      font-weight: 600;
      color: var(--white);
      margin-bottom: 16px;
    }
    .project-desc {
      background: var(--navy-light);
      padding: 22px;
      border-radius: 4px;
      font-size: 0.9rem;
      line-height: 1.75;
      color: var(--slate);
      margin-bottom: 16px;
    }
    .project-tech {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      list-style: none;
    }
    .project-tech li {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--slate);
    }
    .project-img {
      background: var(--navy-light);
      border-radius: 4px;
      height: 200px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 4rem;
      border: 1px solid rgba(100,255,218,0.1);
      transition: var(--transition);
    }
    .project-item:hover .project-img { border-color: var(--green); }

    /* ─── CONTACT ─── */
    #contact {
      max-width: 600px;
      margin: 0 auto;
      text-align: center;
      padding: 100px 0;
      min-height: auto;
    }
    .contact-num {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--green);
      margin-bottom: 16px;
      letter-spacing: 0.1em;
    }
    .contact-num::before { content: counter(section, decimal-leading-zero) "."; counter-increment: section; margin-right: 8px; }
    .contact-title {
      font-size: clamp(2rem, 5vw, 3rem);
      font-weight: 600;
      color: var(--white);
      margin-bottom: 20px;
    }
    .contact-desc {
      font-size: 1rem;
      line-height: 1.8;
      color: var(--slate);
      margin-bottom: 50px;
    }
    .contact-btn {
      display: inline-block;
      padding: 18px 28px;
      border: 1px solid var(--green);
      border-radius: 4px;
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--green);
      letter-spacing: 0.1em;
      transition: var(--transition);
    }
    .contact-btn:hover { background: var(--green-tint); transform: translateY(-2px); }

    /* ─── FOOTER ─── */
    footer {
      padding: 20px;
      text-align: center;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--slate-dark);
      line-height: 1.8;
    }
    footer a { color: var(--slate-dark); }
    footer a:hover { color: var(--green); }

    /* ─── MOBILE NAV ─── */
    .mobile-nav-toggle { display: none; }
    .mobile-overlay { display: none; }

    @media (max-width: 1080px) {
      main { padding: 0 100px; }
      .side-left, .side-right { display: none; }
    }
    @media (max-width: 768px) {
      nav { padding: 0 25px; }
      main { padding: 0 25px; }
      .nav-links { display: none; }
      .about-grid { grid-template-columns: 1fr; }
      .about-img-wrap { display: none; }
      .project-item { grid-template-columns: 1fr; }
      .project-item:nth-child(even) .project-content { order: 1; }
      .project-item:nth-child(even) .project-img { order: 2; }
      .project-img { height: 150px; }
      .tabs-wrap { flex-direction: column; }
      .tabs-list { flex-direction: row; overflow-x: auto; border-left: none; border-bottom: 2px solid var(--navy-light); min-width: unset; }
      .tab-btn { border-left: none; border-bottom: 2px solid transparent; margin-left: 0; margin-bottom: -2px; height: 36px; }
      .tab-btn.active { border-left-color: transparent; border-bottom-color: var(--green); }
      .tab-panel { padding: 20px 0 0; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#home">SC</a>
  <ul class="nav-links">
    <li><a href="#about"><span>01.</span>About</a></li>
    <li><a href="#certifications"><span>02.</span>Certifications</a></li>
    <li><a href="#experience"><span>03.</span>Experience</a></li>
    <li><a href="#portfolio"><span>04.</span>Work</a></li>
    <li><a href="#contact"><span>05.</span>Contact</a></li>
  </ul>
  <a class="nav-resume" href="https://academy.pega.com/verify-certification?email=satyanarayanachav%40gmail.com" target="_blank">Verify Certs</a>
</nav>

<!-- SIDE LEFT -->
<div class="side-left">
  <a href="mailto:satyanarayanachav@gmail.com" title="Email" aria-label="Email">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
  </a>
  <a href="tel:5515542451" title="Phone" aria-label="Phone">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 8.8 19.79 19.79 0 01.01 2.22a2 2 0 012-2.18h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.91 7.91a16 16 0 006.06 6.06l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
  </a>
  <a href="https://linkedin.com" target="_blank" title="LinkedIn" aria-label="LinkedIn">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
  </a>
</div>

<!-- SIDE RIGHT -->
<div class="side-right">
  <a href="mailto:satyanarayanachav@gmail.com">satyanarayanachav@gmail.com</a>
</div>

<main>

  <!-- HERO -->
  <section id="home">
    <p class="hero-intro">Hi, my name is</p>
    <h1 class="hero-name">Satyanarayana Chitikala.</h1>
    <h2 class="hero-tagline">I Design PEGA Solutions.</h2>
    <p class="hero-desc">
      I'm a PEGA Certified Lead System Architect (CLSA) based in New York, NY,
      with over 10 years of experience designing and delivering robust, scalable,
      and enterprise-grade PEGA applications across telecom, banking, insurance, and finance.
    </p>
    <a class="hero-cta" href="#portfolio">Check out my work!</a>

    <div class="cert-badge-hero">
      <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACLSA74V1P_Current.png" alt="PEGA Lead System Architect Certified"/>
      <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACSSA71V1_Current.png" alt="PEGA Certified Senior System Architect"/>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <h2 class="section-heading">About Me</h2>
    <div class="about-grid">
      <div class="about-text">
        <p>
          Hello! I'm Satya, a PEGA Certified Lead System Architect with over 10 years of experience. My journey
          in enterprise software started with a fascination for how complex business problems can be elegantly
          solved with the right platform. Today, I specialize in transforming intricate requirements into
          scalable PEGA solutions that drive real operational value.
        </p>
        <p>
          I tend to start with <strong style="color:var(--white)">class hierarchy and data model first</strong> — everything else in PEGA
          goes smoother when reuse and specialization are thought through early. Usually the one sitting with
          customer SMEs and architects, asking blunt questions about pain points, then sketching PEGA case
          life cycles that match how work really flows.
        </p>
        <p>
          I bring a <strong style="color:var(--white)">consulting mindset</strong> to every project: balancing what the platform can do with
          what the client can support, and laying out practical roadmaps instead of theoretical target states.
          I'm still very hands-on — I build and review rules daily, and stay current with
          <a href="https://academy.pega.com" target="_blank">Pega Infinity 24.x</a> and Pega Constellation.
        </p>
        <p>Here are a few technologies I've been working with recently:</p>
        <ul>
          <li>Pega Infinity 23/24.x</li>
          <li>Pega Constellation</li>
          <li>REST / SOAP / MQ</li>
          <li>Pega Decision Hub</li>
          <li>Java, JavaScript</li>
          <li>AWS / Azure Cloud</li>
          <li>Jenkins / CI/CD</li>
          <li>Oracle / SQL Server</li>
        </ul>
      </div>
      <div class="about-img-wrap">
        <div class="about-img-placeholder">
          <span class="about-initials">SC</span>
        </div>
      </div>
    </div>
  </section>

  <!-- CERTIFICATIONS -->
  <section id="certifications">
    <h2 class="section-heading">My Certifications &amp; Badges</h2>
    <div class="certs-grid">
      <div class="cert-item">
        <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACLSA74V1P_Current.png" alt="PEGA Certified Lead System Architect"/>
        <p>PEGA Certified Lead System Architect</p>
      </div>
      <div class="cert-item">
        <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACSSA71V1_Current.png" alt="PEGA Certified Senior System Architect"/>
        <p>PEGA Certified Senior System Architect</p>
      </div>
      <div class="cert-item">
        <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACPBA74V1_Current.png" alt="PEGA Certified Business Architect"/>
        <p>PEGA Certified Business Architect</p>
      </div>
      <div class="cert-item">
        <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACPDC86V1_Current.png" alt="PEGA Certified Decisioning Consultant"/>
        <p>PEGA Certified Decisioning Architect</p>
      </div>
      <div class="cert-item">
        <img src="https://academyartifacts.s3.amazonaws.com/Images/Prod/PEGACSA74V1_Current.png" alt="PEGA Certified System Architect"/>
        <p>PEGA Certified System Architect</p>
      </div>
    </div>
    <p class="cert-verify">
      Verify all certifications at
      <a href="https://academy.pega.com/verify-certification?email=satyanarayanachav%40gmail.com" target="_blank">
        academy.pega.com →
      </a>
    </p>
  </section>

  <!-- EXPERIENCE -->
  <section id="experience">
    <h2 class="section-heading">Where I've Worked</h2>
    <div class="tabs-wrap">
      <div class="tabs-list">
        <button class="tab-btn active" data-tab="amdocs">AMDOCS</button>
        <button class="tab-btn" data-tab="perseusx">PerseusX</button>
        <button class="tab-btn" data-tab="lti">LTI MindTree</button>
        <button class="tab-btn" data-tab="cts2">Cognizant</button>
        <button class="tab-btn" data-tab="cts1">Cognizant (2)</button>
        <button class="tab-btn" data-tab="hcl">HCL</button>
      </div>

      <div class="tab-panel active" id="tab-amdocs">
        <h3 class="tab-title">Sr. Pega Developer <span>@ AMDOCS Inc.</span></h3>
        <p class="tab-company">May 2024 – Present &nbsp;|&nbsp; <span>New York City, NY</span></p>
        <ul class="tab-duties">
          <li>Lead end-to-end design and development of Pega applications ensuring alignment with business goals, compliance needs, and enterprise architecture standards.</li>
          <li>Translate complex business requirements into scalable Pega functional designs using Pega Express and industry best practices.</li>
          <li>Architect and oversee integrations with REST, SOAP, MQ, and SQL-based systems to enhance data flow and interoperability.</li>
          <li>Implement advanced Pega Case Management solutions to streamline case routing, SLA handling, and resolution efficiency.</li>
          <li>Support deployment and configuration of Pega Decision Hub to enable real-time decisioning and personalization.</li>
          <li>Monitor application performance using PDC/PAL and implement tuning strategies to ensure scalability and reliability.</li>
          <li>Mentor junior developers and guide cross-functional teams on Pega architecture, guardrails, and solution design.</li>
        </ul>
      </div>

      <div class="tab-panel" id="tab-perseusx">
        <h3 class="tab-title">Sr. Pega Developer <span>@ PerseusX Incorporated</span></h3>
        <p class="tab-company">Feb 2022 – Sep 2023 &nbsp;|&nbsp; <span>Guadalajara, Mexico</span></p>
        <ul class="tab-duties">
          <li>Designed scalable Pega case types, workflows, and lifecycle models tailored to Payer domain requirements.</li>
          <li>Built robust integration layers using REST, SOAP, and Connect SQL with standardized error handling and retry logic.</li>
          <li>Conducted detailed process analysis to identify automation opportunities and optimize business workflows.</li>
          <li>Developed Pega Reporting dashboards to support operational insights and compliance monitoring.</li>
          <li>Ensured guardrail compliance through code reviews, design validations, and adherence to Pega best practices.</li>
          <li>Collaborated with Payer domain SMEs to align Pega solutions with claims, enrollment, and authorization processes.</li>
          <li>Supported UAT cycles by resolving defects, clarifying requirements, and validating end-to-end functionality.</li>
        </ul>
      </div>

      <div class="tab-panel" id="tab-lti">
        <h3 class="tab-title">Sr. Pega Developer <span>@ LTI MindTree</span></h3>
        <p class="tab-company">Feb 2021 – Jan 2022 &nbsp;|&nbsp; <span>Hyderabad, India</span></p>
        <ul class="tab-duties">
          <li>Led DCO workshops to gather requirements and convert them into Pega process models and functional designs.</li>
          <li>Designed and implemented Pega case structures, flows, and decision logic for regulatory and operational workflows.</li>
          <li>Provided architectural guidance on data modeling, class structure, and integration patterns.</li>
          <li>Integrated external systems using REST/SOAP connectors with secure authentication and error handling.</li>
          <li>Conducted performance tuning using PDC, PAL, and tracer tools to optimize application performance.</li>
          <li>Coordinated with DevOps teams to support CI/CD pipelines and release management.</li>
        </ul>
      </div>

      <div class="tab-panel" id="tab-cts2">
        <h3 class="tab-title">Pega System Analyst <span>@ Cognizant Technology Solutions</span></h3>
        <p class="tab-company">Jul 2020 – Jan 2021 &nbsp;|&nbsp; <span>Hyderabad, India &nbsp;·&nbsp; Toronto Dominion Bank, Canada</span></p>
        <ul class="tab-duties">
          <li>Designed Smart Dispute and claims workflows using Pega Case Management and SLA-driven routing for Visa, Mastercard, and Amex compliance.</li>
          <li>Developed integrations with core banking systems using REST/SOAP and reusable data pages.</li>
          <li>Built decision rules, validation logic, and UI components to support regulatory and operational processes.</li>
          <li>Created Pega Reporting dashboards for compliance, audit, and operational insights.</li>
          <li>Mentored junior developers on Pega rule design, debugging, and best practices.</li>
          <li>Collaborated with QA, BA, and DevOps teams to ensure smooth project delivery.</li>
        </ul>
      </div>

      <div class="tab-panel" id="tab-cts1">
        <h3 class="tab-title">Pega System Analyst <span>@ Cognizant Technology Solutions</span></h3>
        <p class="tab-company">Jun 2019 – Jun 2020 &nbsp;|&nbsp; <span>Hyderabad, India &nbsp;·&nbsp; CSAA Insurance, USA</span></p>
        <ul class="tab-duties">
          <li>Involved in DCO sessions to gather and document business requirements for life insurance claims automation.</li>
          <li>Configured and customized PEGA platform components to meet business requirements and ensure optimal performance.</li>
          <li>Collaborated with cross-functional teams to ensure timely project delivery meeting client expectations.</li>
          <li>Led a team in the design and implementation of Pega solutions, providing guidance on best practices.</li>
          <li>Provided technical guidance and mentorship to junior developers, ensuring high-quality deliverables.</li>
          <li>Developed and documented use cases, providing comprehensive analysis and solutions.</li>
        </ul>
      </div>

      <div class="tab-panel" id="tab-hcl">
        <h3 class="tab-title">PEGA Developer <span>@ Hindustan Computer Limited (HCL)</span></h3>
        <p class="tab-company">Jul 2016 – May 2019 &nbsp;|&nbsp; <span>Chennai, India &nbsp;·&nbsp; Commonwealth Bank of Australia</span></p>
        <ul class="tab-duties">
          <li>Developed foundational Pega components including UI screens, flows, activities, and decision rules for mortgage loan origination.</li>
          <li>Built integrations with external systems using SOAP, MQ, and SQL connectors.</li>
          <li>Designed and implemented case types and workflows for the full loan origination and servicing lifecycle.</li>
          <li>Performed PRPC debugging, performance tuning, and guardrail compliance enforcement.</li>
          <li>Created reports, portals, and analytics dashboards to support business operations.</li>
          <li>Conducted unit testing, integration testing, and supported QA teams during validation cycles.</li>
        </ul>
      </div>

    </div>
  </section>

  <!-- WORK / PORTFOLIO -->
  <section id="portfolio">
    <h2 class="section-heading">Some Things I've Built</h2>
    <div class="projects-list">

      <div class="project-item">
        <div class="project-content">
          <p class="project-overline">Featured Project</p>
          <h3 class="project-title">MetroNet OSP &amp; Enterprise Ticketing</h3>
          <div class="project-desc">
            MetroNet, a leading telecom provider, implemented an Outside Plant (OSP) management and
            Enterprise Ticketing Tool on Pega Infinity 24.x. The solution streamlined management of
            physical network infrastructure and automated customer inquiry handling with Pega Constellation UI,
            real-time SLA dashboards, and Decision Hub-powered case routing.
          </div>
          <ul class="project-tech">
            <li>Pega Infinity 24.x</li>
            <li>Pega Constellation</li>
            <li>REST API</li>
            <li>SOAP / MQ</li>
            <li>Pega Cloud</li>
            <li>Decision Hub</li>
          </ul>
        </div>
        <div class="project-img">📡</div>
      </div>

      <div class="project-item">
        <div class="project-content">
          <p class="project-overline">Featured Project</p>
          <h3 class="project-title">TD Bank Smart Dispute</h3>
          <div class="project-desc">
            End-to-end dispute management solution for Toronto Dominion Bank handling credit and debit
            card chargebacks in compliance with Visa, Mastercard, and Amex card network regulations.
            The system automated dispute intake, investigation, evidence management, and chargeback
            processes — achieving 100% regulatory audit compliance pass rate.
          </div>
          <ul class="project-tech">
            <li>Pega Smart Dispute</li>
            <li>Pega Case Management</li>
            <li>REST / SOAP</li>
            <li>Reusable Data Pages</li>
            <li>SLA Routing</li>
          </ul>
        </div>
        <div class="project-img">🏦</div>
      </div>

      <div class="project-item">
        <div class="project-content">
          <p class="project-overline">Featured Project</p>
          <h3 class="project-title">P&amp;G Transfer Pricing Automation</h3>
          <div class="project-desc">
            Automated Procter &amp; Gamble's global transfer pricing workflows for goods, services,
            and intellectual property across international subsidiaries. Built a regulatory-grade
            Pega solution with full audit trails, REST/SOAP integrations to legacy ERP systems,
            and CI/CD pipelines that cut release times by 60%.
          </div>
          <ul class="project-tech">
            <li>Pega PRPC</li>
            <li>REST / SOAP</li>
            <li>Jenkins CI/CD</li>
            <li>PDC / PAL</li>
            <li>AWS</li>
          </ul>
        </div>
        <div class="project-img">💰</div>
      </div>

      <div class="project-item">
        <div class="project-content">
          <p class="project-overline">Featured Project</p>
          <h3 class="project-title">CBA Mortgage Loan Origination</h3>
          <div class="project-desc">
            Full loan origination lifecycle platform for Commonwealth Bank of Australia covering
            both proprietary and broker-originated mortgages. Included pre-approval tools, application
            submission, document ingestion, credit assessment, and settlement preparation — integrating
            with core banking systems via SOAP, MQ, and SQL.
          </div>
          <ul class="project-tech">
            <li>Pega PRPC</li>
            <li>SOAP / MQ / SQL</li>
            <li>Case Management</li>
            <li>REST API</li>
            <li>Pega Cloud</li>
          </ul>
        </div>
        <div class="project-img">🏠</div>
      </div>

    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <p class="contact-num">What's Next?</p>
    <h2 class="contact-title">Get In Touch</h2>
    <p class="contact-desc">
      I'm currently open to new opportunities and collaborations. Whether you need a
      Lead System Architect to drive your next PEGA implementation, or just want to
      connect and talk PEGA — my inbox is always open!
    </p>
    <a class="contact-btn" href="mailto:satyanarayanachav@gmail.com">Say Hello</a>
  </section>

</main>

<footer>
  <p>Designed &amp; Built by Satyanarayana Chitikala</p>
  <p>
    <a href="https://academy.pega.com/verify-certification?email=satyanarayanachav%40gmail.com" target="_blank">Verify PEGA Certifications</a>
  </p>
</footer>

<script>
  // Tab switching
  document.querySelectorAll('.tab-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
      document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
      btn.classList.add('active');
      document.getElementById('tab-' + btn.dataset.tab).classList.add('active');
    });
  });

  // Nav shadow on scroll
  window.addEventListener('scroll', () => {
    const nav = document.querySelector('nav');
    if (window.scrollY > 50) {
      nav.style.boxShadow = '0 10px 30px -10px rgba(2,12,27,0.7)';
    } else {
      nav.style.boxShadow = 'none';
    }
  });
</script>
</body>
</html>
