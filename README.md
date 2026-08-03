<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Aryan Patel — Mechanical Engineering</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #0D0F14;
      --surface:   #161A22;
      --surface2:  #1E2330;
      --border:    #2A3045;
      --accent:    #4ECDC4;
      --accent2:   #FF6B6B;
      --text:      #E8EAF0;
      --muted:     #7A8099;
      --display:   'Space Mono', monospace;
      --body:      'Space Grotesk', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--body);
      font-size: 16px;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; justify-content: space-between; align-items: center;
      padding: 18px 48px;
      background: rgba(13,15,20,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }
    .nav-logo {
      font-family: var(--display);
      font-size: 14px;
      color: var(--accent);
      letter-spacing: 0.05em;
    }
    .nav-links { display: flex; gap: 32px; list-style: none; }
    .nav-links a {
      font-size: 13px; font-weight: 500; color: var(--muted);
      text-decoration: none; letter-spacing: 0.04em; text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--accent); }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: flex; align-items: center;
      padding: 120px 48px 80px;
      position: relative;
      overflow: hidden;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px;
      max-width: 1100px;
      margin: 0 auto;
      width: 100%;
      align-items: center;
    }
    .hero-eyebrow {
      font-family: var(--display);
      font-size: 11px;
      letter-spacing: 0.15em;
      color: var(--accent);
      text-transform: uppercase;
      margin-bottom: 20px;
    }
    .hero-name {
      font-family: var(--display);
      font-size: clamp(42px, 6vw, 72px);
      font-weight: 700;
      line-height: 1.05;
      color: var(--text);
      margin-bottom: 16px;
    }
    .hero-name span { color: var(--accent); }
    .hero-title {
      font-size: 18px; font-weight: 400; color: var(--muted);
      margin-bottom: 32px;
      line-height: 1.5;
    }
    .hero-cta {
      display: flex; gap: 16px; flex-wrap: wrap;
    }
    .btn {
      display: inline-block;
      padding: 12px 28px;
      border-radius: 4px;
      font-size: 14px; font-weight: 600; letter-spacing: 0.03em;
      text-decoration: none; cursor: pointer;
      transition: all 0.2s;
    }
    .btn-primary {
      background: var(--accent); color: var(--bg);
    }
    .btn-primary:hover { background: #3bb8b0; transform: translateY(-1px); }
    .btn-outline {
      border: 1px solid var(--border); color: var(--text); background: transparent;
    }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); }

    /* Hero right — schematic art */
    .hero-art {
      display: flex; justify-content: center; align-items: center;
    }
    .schematic {
      width: 320px; height: 320px;
      position: relative;
    }
    .schematic svg { width: 100%; height: 100%; }

    /* ── SECTIONS ── */
    section { padding: 100px 48px; }
    .section-inner { max-width: 1100px; margin: 0 auto; }
    .section-label {
      font-family: var(--display);
      font-size: 11px; letter-spacing: 0.15em; text-transform: uppercase;
      color: var(--accent); margin-bottom: 12px;
    }
    .section-title {
      font-family: var(--display);
      font-size: clamp(26px, 4vw, 40px);
      font-weight: 700; color: var(--text);
      margin-bottom: 48px;
      line-height: 1.2;
    }

    /* ── SKILLS ── */
    #skills { background: var(--surface); }
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 24px;
    }
    .skill-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 28px;
      transition: border-color 0.2s, transform 0.2s;
    }
    .skill-card:hover { border-color: var(--accent); transform: translateY(-3px); }
    .skill-card h3 {
      font-family: var(--display); font-size: 13px;
      letter-spacing: 0.1em; text-transform: uppercase;
      color: var(--accent); margin-bottom: 16px;
    }
    .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
    .tag {
      background: var(--surface2); color: var(--text);
      padding: 5px 12px; border-radius: 3px;
      font-size: 13px; font-weight: 500;
    }

    /* ── PROJECTS ── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 28px;
    }
    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 36px;
      position: relative;
      overflow: hidden;
      transition: border-color 0.2s, transform 0.2s;
    }
    .project-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      opacity: 0; transition: opacity 0.2s;
    }
    .project-card:hover { border-color: var(--accent); transform: translateY(-4px); }
    .project-card:hover::before { opacity: 1; }
    .project-number {
      font-family: var(--display); font-size: 11px;
      color: var(--muted); letter-spacing: 0.1em; margin-bottom: 16px;
    }
    .project-card h3 {
      font-family: var(--display); font-size: 19px; font-weight: 700;
      color: var(--text); margin-bottom: 12px; line-height: 1.3;
    }
    .project-card p { color: var(--muted); font-size: 15px; line-height: 1.65; }
    .project-skills { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 20px; }
    .project-tag {
      font-size: 12px; padding: 4px 10px;
      background: var(--surface2); color: var(--accent);
      border-radius: 3px; font-weight: 600;
    }

    /* ── EXPERIENCE ── */
    #experience { background: var(--surface); }
    .timeline { display: flex; flex-direction: column; gap: 0; }
    .timeline-item {
      display: grid;
      grid-template-columns: 200px 1px 1fr;
      gap: 0 32px;
      padding-bottom: 48px;
    }
    .timeline-item:last-child { padding-bottom: 0; }
    .timeline-date {
      text-align: right;
      padding-top: 4px;
      font-family: var(--display); font-size: 12px;
      color: var(--muted); line-height: 1.5;
    }
    .timeline-line {
      display: flex; flex-direction: column; align-items: center;
    }
    .timeline-dot {
      width: 10px; height: 10px;
      background: var(--accent); border-radius: 50%;
      flex-shrink: 0; margin-top: 6px;
    }
    .timeline-connector {
      width: 1px; flex: 1;
      background: var(--border); margin-top: 8px;
    }
    .timeline-item:last-child .timeline-connector { display: none; }
    .timeline-content { padding-bottom: 4px; }
    .timeline-role {
      font-family: var(--display); font-size: 17px; font-weight: 700;
      color: var(--text); margin-bottom: 4px;
    }
    .timeline-org {
      font-size: 14px; color: var(--accent); font-weight: 600; margin-bottom: 12px;
    }
    .timeline-content p { color: var(--muted); font-size: 15px; line-height: 1.65; }

    /* ── CERTIFICATIONS ── */
    .certs-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 20px;
    }
    .cert-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 24px 28px;
      display: flex; align-items: center; gap: 16px;
      transition: border-color 0.2s;
    }
    .cert-card:hover { border-color: var(--accent); }
    .cert-icon {
      width: 40px; height: 40px;
      background: var(--surface2);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 20px; flex-shrink: 0;
    }
    .cert-card h4 { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 4px; }
    .cert-card span { font-size: 12px; color: var(--muted); font-family: var(--display); }

    /* ── AWARDS ── */
    #awards { background: var(--surface); }
    .awards-row {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }
    .award-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 24px 28px;
      border-left: 3px solid var(--accent);
    }
    .award-card h4 { font-weight: 700; font-size: 15px; color: var(--text); margin-bottom: 6px; }
    .award-card p { font-size: 14px; color: var(--muted); }
    .award-card .award-year { font-family: var(--display); font-size: 12px; color: var(--accent); margin-bottom: 8px; }

    /* ── CONTACT ── */
    #contact { text-align: center; }
    .contact-inner { max-width: 600px; margin: 0 auto; }
    .contact-inner p { font-size: 17px; color: var(--muted); margin-bottom: 36px; line-height: 1.7; }
    .contact-links { display: flex; justify-content: center; gap: 16px; flex-wrap: wrap; }
    .contact-link {
      display: flex; align-items: center; gap: 8px;
      padding: 12px 24px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 6px;
      color: var(--text); text-decoration: none; font-size: 14px; font-weight: 500;
      transition: all 0.2s;
    }
    .contact-link:hover { border-color: var(--accent); color: var(--accent); }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 28px 48px;
      display: flex; justify-content: space-between; align-items: center;
      color: var(--muted); font-size: 13px; font-family: var(--display);
    }
    footer span { color: var(--accent); }

    /* ── SCROLL ANIMATIONS ── */
    .reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.55s ease, transform 0.55s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      nav { padding: 16px 24px; }
      .nav-links { gap: 20px; }
      section { padding: 72px 24px; }
      #hero { padding: 100px 24px 60px; }
      .hero-grid { grid-template-columns: 1fr; gap: 40px; }
      .hero-art { display: none; }
      .timeline-item { grid-template-columns: 0 1px 1fr; }
      .timeline-date { display: none; }
      footer { flex-direction: column; gap: 8px; text-align: center; }
    }

    @media (prefers-reduced-motion: reduce) {
      .reveal { opacity: 1; transform: none; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">AP_</div>
  <ul class="nav-links">
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-grid">
    <div>
      <div class="hero-eyebrow">// Mechanical Engineering Student</div>
      <h1 class="hero-name">Aryan<br /><span>Patel.</span></h1>
      <p class="hero-title">
        Builder. Engineer. Lifeguard.<br />
        Toronto Metropolitan University · BEng Mechanical
      </p>
      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">View Projects</a>
        <a href="mailto:aryanpat2021@gmail.com" class="btn btn-outline">Get in Touch</a>
      </div>
    </div>
    <div class="hero-art">
      <!-- Schematic-style SVG art -->
      <svg viewBox="0 0 300 300" xmlns="http://www.w3.org/2000/svg" class="schematic">
        <defs>
          <radialGradient id="glow" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stop-color="#4ECDC4" stop-opacity="0.15"/>
            <stop offset="100%" stop-color="#4ECDC4" stop-opacity="0"/>
          </radialGradient>
        </defs>
        <circle cx="150" cy="150" r="140" fill="url(#glow)"/>
        <!-- Outer ring -->
        <circle cx="150" cy="150" r="120" fill="none" stroke="#2A3045" stroke-width="1"/>
        <circle cx="150" cy="150" r="90" fill="none" stroke="#2A3045" stroke-width="1" stroke-dasharray="4 6"/>
        <!-- Gear teeth outer -->
        <g stroke="#4ECDC4" stroke-width="1.5" fill="none">
          <circle cx="150" cy="150" r="65" stroke-width="2"/>
          <!-- Tick marks -->
          <line x1="150" y1="30" x2="150" y2="50" stroke-width="2"/>
          <line x1="150" y1="250" x2="150" y2="270" stroke-width="2"/>
          <line x1="30" y1="150" x2="50" y2="150" stroke-width="2"/>
          <line x1="250" y1="150" x2="270" y2="150" stroke-width="2"/>
          <line x1="61" y1="61" x2="75" y2="75" stroke-width="1.5"/>
          <line x1="225" y1="75" x2="239" y2="61" stroke-width="1.5"/>
          <line x1="61" y1="239" x2="75" y2="225" stroke-width="1.5"/>
          <line x1="225" y1="225" x2="239" y2="239" stroke-width="1.5"/>
        </g>
        <!-- Cross hairs -->
        <line x1="150" y1="85" x2="150" y2="215" stroke="#4ECDC4" stroke-width="1" opacity="0.4"/>
        <line x1="85" y1="150" x2="215" y2="150" stroke="#4ECDC4" stroke-width="1" opacity="0.4"/>
        <!-- Center hub -->
        <circle cx="150" cy="150" r="28" fill="#161A22" stroke="#4ECDC4" stroke-width="2"/>
        <circle cx="150" cy="150" r="10" fill="#4ECDC4"/>
        <!-- Circuit dots -->
        <circle cx="150" cy="85" r="4" fill="#FF6B6B"/>
        <circle cx="215" cy="150" r="4" fill="#FF6B6B"/>
        <circle cx="150" cy="215" r="4" fill="#4ECDC4"/>
        <circle cx="85" cy="150" r="4" fill="#4ECDC4"/>
        <!-- Label -->
        <text x="150" y="290" text-anchor="middle" fill="#7A8099" font-family="monospace" font-size="9" letter-spacing="2">ARYAN PATEL · v2025</text>
      </svg>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">What I work with</div>
      <h2 class="section-title">Skills</h2>
    </div>
    <div class="skills-grid">
      <div class="skill-card reveal">
        <h3>Engineering &amp; CAD</h3>
        <div class="skill-tags">
          <span class="tag">SolidWorks</span>
          <span class="tag">AutoCAD</span>
          <span class="tag">GD&amp;T</span>
        </div>
      </div>
      <div class="skill-card reveal">
        <h3>Programming</h3>
        <div class="skill-tags">
          <span class="tag">C</span>
          <span class="tag">Python</span>
          <span class="tag">MATLAB</span>
        </div>
      </div>
      <div class="skill-card reveal">
        <h3>Hardware &amp; Making</h3>
        <div class="skill-tags">
          <span class="tag">PCB Design</span>
          <span class="tag">Acid Etching</span>
          <span class="tag">Soldering</span>
          <span class="tag">Raspberry Pi</span>
        </div>
      </div>
      <div class="skill-card reveal">
        <h3>Safety &amp; Leadership</h3>
        <div class="skill-tags">
          <span class="tag">First Aid / CPR-C</span>
          <span class="tag">National Lifeguard</span>
          <span class="tag">Team Leadership</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">Things I've built</div>
      <h2 class="section-title">Projects</h2>
    </div>
    <div class="projects-grid">
      <div class="project-card reveal">
        <div class="project-number">PROJECT 01</div>
        <h3>Pi Pico Raspberry Xylophone</h3>
        <p>Designed and fabricated a custom controller board for a Raspberry Pi Pico using acid etching, precision drilling, and hand soldering. Programmed the Pico in Python to autonomously play three full songs on a physical xylophone.</p>
        <div class="project-skills">
          <span class="project-tag">Python</span>
          <span class="project-tag">Raspberry Pi Pico</span>
          <span class="project-tag">PCB Fabrication</span>
          <span class="project-tag">Soldering</span>
        </div>
      </div>
      <div class="project-card reveal">
        <div class="project-number">PROJECT 02</div>
        <h3>Handheld Microcontroller Game</h3>
        <p>Designed and chemically etched a custom PCB from scratch to build a fully functional handheld game console. Wrote the control logic firmware and manually soldered all components — transistors, buttons, and LEDs — into a working device.</p>
        <div class="project-skills">
          <span class="project-tag">PCB Design</span>
          <span class="project-tag">Chemical Etching</span>
          <span class="project-tag">Embedded C</span>
          <span class="project-tag">Electronics</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">Where I've worked</div>
      <h2 class="section-title">Experience</h2>
    </div>
    <div class="timeline reveal">

      <div class="timeline-item">
        <div class="timeline-date">Jun 2025 – Aug 2025</div>
        <div class="timeline-line">
          <div class="timeline-dot"></div>
          <div class="timeline-connector"></div>
        </div>
        <div class="timeline-content">
          <div class="timeline-role">Swimming Coach</div>
          <div class="timeline-org">Citi Swim</div>
          <p>Coached 25 competitive swimmers aged 10–16, organizing practices and preparing the team for city-level events outside of regular hours. Led the team to a third-place overall finish in the city.</p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-date">Mar 2024 – Present</div>
        <div class="timeline-line">
          <div class="timeline-dot"></div>
          <div class="timeline-connector"></div>
        </div>
        <div class="timeline-content">
          <div class="timeline-role">Lifeguard &amp; Swim Instructor</div>
          <div class="timeline-org">City of Mississauga</div>
          <p>Instructed over 2,000 individuals in swimming and water safety. Led a team of lifeguards in emergency response and provided ongoing customer support and guidance to participants and families.</p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="timeline-date">Sep 2023 – Jan 2024</div>
        <div class="timeline-line">
          <div class="timeline-dot"></div>
          <div class="timeline-connector"></div>
        </div>
        <div class="timeline-content">
          <div class="timeline-role">Car Service Technician Assistant</div>
          <div class="timeline-org">Volvo Mississauga — Co-op</div>
          <p>Diagnosed vehicle issues, repaired systems, and replaced worn components in a professional automotive environment. Collaborated with senior technicians on complex jobs and managed parts inventory.</p>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">Verified credentials</div>
      <h2 class="section-title">Certifications</h2>
    </div>
    <div class="certs-grid reveal">
      <div class="cert-card">
        <div class="cert-icon">🏊</div>
        <div>
          <h4>National Lifeguard</h4>
          <span>December 2023</span>
        </div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🚑</div>
        <div>
          <h4>Standard First Aid with CPR-C</h4>
          <span>August 2023</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- AWARDS -->
<section id="awards">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">Recognition</div>
      <h2 class="section-title">Awards</h2>
    </div>
    <div class="awards-row reveal">
      <div class="award-card">
        <div class="award-year">June 2023</div>
        <h4>Honor Roll — St. Francis Xavier S.S.</h4>
        <p>Achieved grades in the 90s or higher across all subjects in Grade 9 and 10.</p>
      </div>
      <div class="award-card">
        <div class="award-year">June 2018</div>
        <h4>Gold Medal — Top Child</h4>
        <p>Gold medals awarded in Math, Science, and English.</p>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-inner contact-inner">
    <div class="reveal">
      <div class="section-label" style="text-align:center;">Let's connect</div>
      <h2 class="section-title" style="text-align:center;">Get In Touch</h2>
      <p>I'm currently studying Mechanical Engineering at Toronto Metropolitan University and always open to co-op opportunities, projects, or just a conversation about engineering.</p>
      <div class="contact-links">
        <a href="mailto:aryanpat2021@gmail.com" class="contact-link">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
          aryanpat2021@gmail.com
        </a>
        <a href="tel:4372150533" class="contact-link">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.57 13a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.48 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 9.91a16 16 0 0 0 6.18 6.18l1.27-1.27a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
          437-215-0533
        </a>
        <a href="#" class="contact-link">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span>Aryan Patel</span>
  <span>Mississauga, ON · <span style="color:var(--accent)">aryanpat2021@gmail.com</span></span>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));
</script>
</body>
</html>
