<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ilias Dalbow — Social Media & Marketing</title>
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --purple: #7F77DD;
      --purple-light: #AFA9EC;
      --purple-xlight: #EEEDFE;
      --bg: #ffffff;
      --bg-secondary: #f5f5f3;
      --text: #1a1a1a;
      --text-secondary: #555;
      --text-tertiary: #999;
      --border: rgba(0,0,0,0.12);
      --border-secondary: rgba(0,0,0,0.22);
      --radius-md: 8px;
      --radius-lg: 12px;
    }

    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #1a1a1a;
        --bg-secondary: #242424;
        --text: #f0f0f0;
        --text-secondary: #aaa;
        --text-tertiary: #666;
        --border: rgba(255,255,255,0.12);
        --border-secondary: rgba(255,255,255,0.22);
        --purple-xlight: #2e2b55;
      }
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.7;
    }

    /* NAV */
    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.25rem 2rem;
      border-bottom: 0.5px solid var(--border);
      position: sticky;
      top: 0;
      background: var(--bg);
      z-index: 100;
    }
    .nav-name { font-size: 17px; font-weight: 500; letter-spacing: -0.3px; }
    .nav-links { display: flex; gap: 1.5rem; }
    .nav-links a {
      font-size: 13px;
      color: var(--text-secondary);
      text-decoration: none;
      cursor: pointer;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--text); }

    /* SECTIONS */
    section { padding: 4rem 2rem; max-width: 860px; margin: 0 auto; }

    /* HERO */
    .hero {
      padding-top: 5rem;
      padding-bottom: 5rem;
      border-bottom: 0.5px solid var(--border);
    }
    .hero-tag {
      font-size: 12px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      color: var(--text-tertiary);
      margin-bottom: 1rem;
    }
    .hero-name {
      font-size: 52px;
      font-weight: 500;
      line-height: 1.1;
      letter-spacing: -1.5px;
      margin-bottom: 1.25rem;
    }
    .hero-name span { color: var(--purple); }
    .hero-sub {
      font-size: 17px;
      color: var(--text-secondary);
      line-height: 1.7;
      max-width: 520px;
      margin-bottom: 2rem;
    }
    .hero-btns { display: flex; gap: 12px; flex-wrap: wrap; }

    /* BUTTONS */
    .btn-primary {
      background: var(--purple);
      color: #fff;
      border: none;
      padding: 10px 20px;
      border-radius: var(--radius-md);
      font-size: 13px;
      font-weight: 500;
      cursor: pointer;
      transition: opacity 0.2s;
      text-decoration: none;
      display: inline-block;
    }
    .btn-primary:hover { opacity: 0.85; }
    .btn-ghost {
      background: transparent;
      color: var(--text);
      border: 0.5px solid var(--border-secondary);
      padding: 10px 20px;
      border-radius: var(--radius-md);
      font-size: 13px;
      font-weight: 500;
      cursor: pointer;
      transition: background 0.2s;
      text-decoration: none;
      display: inline-block;
    }
    .btn-ghost:hover { background: var(--bg-secondary); }

    /* SECTION HEADERS */
    h2 {
      font-size: 14px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      color: var(--text-tertiary);
      margin-bottom: 2rem;
      font-weight: 400;
    }

    /* ABOUT */
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; align-items: start; }
    .about-text { font-size: 16px; line-height: 1.8; color: var(--text-secondary); }
    .about-text p + p { margin-top: 1rem; }
    .skills-list { display: flex; flex-direction: column; gap: 8px; }
    .skill-tag {
      background: var(--bg-secondary);
      border: 0.5px solid var(--border);
      border-radius: var(--radius-md);
      padding: 8px 12px;
      font-size: 13px;
      color: var(--text-secondary);
    }
    .skill-tag strong { color: var(--text); font-weight: 500; }

    /* WORK */
    .work-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .work-card {
      background: var(--bg);
      border: 0.5px solid var(--border);
      border-radius: var(--radius-lg);
      padding: 1.5rem;
      transition: border-color 0.2s;
    }
    .work-card:hover { border-color: var(--border-secondary); }
    .work-card.featured { grid-column: 1 / -1; border-color: var(--purple-light); }
    .work-label {
      font-size: 11px;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: var(--purple);
      margin-bottom: 0.5rem;
    }
    .work-title { font-size: 16px; font-weight: 500; margin-bottom: 0.5rem; }
    .work-desc { font-size: 13px; color: var(--text-secondary); line-height: 1.6; }
    .work-tags { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 1rem; }
    .tag {
      font-size: 11px;
      background: var(--bg-secondary);
      padding: 3px 8px;
      border-radius: 999px;
      color: var(--text-secondary);
    }

    /* SOCIAL LINKS */
    .social-links { display: flex; gap: 8px; flex-wrap: wrap; margin-top: 1rem; }
    .social-btn {
      display: inline-flex;
      align-items: center;
      gap: 5px;
      font-size: 12px;
      font-weight: 500;
      padding: 5px 11px;
      border-radius: 999px;
      border: 0.5px solid var(--border-secondary);
      background: transparent;
      color: var(--text-secondary);
      cursor: pointer;
      transition: background 0.2s, color 0.2s;
      text-decoration: none;
    }
    .social-btn:hover { background: var(--bg-secondary); color: var(--text); }
    .social-btn svg { width: 13px; height: 13px; flex-shrink: 0; }

    /* EXPERIENCE */
    .exp-list { display: flex; flex-direction: column; gap: 1.5rem; }
    .exp-item {
      display: grid;
      grid-template-columns: 110px 1fr;
      gap: 1.5rem;
      padding-bottom: 1.5rem;
      border-bottom: 0.5px solid var(--border);
    }
    .exp-item:last-child { border-bottom: none; }
    .exp-date { font-size: 12px; color: var(--text-tertiary); padding-top: 3px; }
    .exp-role { font-size: 15px; font-weight: 500; margin-bottom: 2px; }
    .exp-company { font-size: 13px; color: var(--purple); margin-bottom: 6px; }
    .exp-desc { font-size: 13px; color: var(--text-secondary); line-height: 1.7; }

    /* CONTACT */
    .contact-box {
      background: var(--bg-secondary);
      border-radius: var(--radius-lg);
      padding: 2.5rem;
      text-align: center;
    }
    .contact-box h3 {
      font-size: 28px;
      font-weight: 500;
      letter-spacing: -0.5px;
      margin-bottom: 0.75rem;
    }
    .contact-box p { font-size: 15px; color: var(--text-secondary); margin-bottom: 1.75rem; }
    .contact-links { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; }

    /* RESPONSIVE */
    @media (max-width: 600px) {
      .hero-name { font-size: 36px; }
      .about-grid { grid-template-columns: 1fr; }
      .work-grid { grid-template-columns: 1fr; }
      .work-card.featured { grid-column: 1; }
      .exp-item { grid-template-columns: 1fr; gap: 0.25rem; }
      nav { padding: 1rem; }
      .nav-links { gap: 1rem; }
    }
  </style>
</head>
<body>

<nav>
  <div class="nav-name">Ilias Dalbow</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#work">Work</a>
    <a href="#experience">Experience</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="top">
  <div class="hero-tag">Marketing · Content · Brand</div>
  <div class="hero-name">Ilias<br><span>Dalbow</span></div>
  <div class="hero-sub">Marketing student &amp; social media specialist who turns brands into communities — one reel at a time.</div>
  <div class="hero-btns">
    <a class="btn-primary" href="#work">See my work</a>
    <a class="btn-ghost" href="#contact">Get in touch</a>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <h2>About</h2>
  <div class="about-grid">
    <div class="about-text">
      <p>I'm a Marketing student at the University of Delaware with a background in social media, content creation, and brand growth. I specialize in short-form video — Reels, Shorts, and the strategy behind them.</p>
      <p>Beyond the camera, I bring real-world experience in restaurant management, logistics, and customer service — which shapes how I communicate and connect with any audience.</p>
      <p>I'm bilingual, data-curious, and always chasing the next creative challenge.</p>
    </div>
    <div class="skills-list">
      <div class="skill-tag"><strong>Social media marketing</strong> — strategy &amp; growth</div>
      <div class="skill-tag"><strong>Short-form video</strong> — Reels, Shorts, Facebook</div>
      <div class="skill-tag"><strong>Copywriting</strong> — CTAs, captions, hooks</div>
      <div class="skill-tag"><strong>Community engagement</strong> — comments, DMs, audience</div>
      <div class="skill-tag"><strong>Analytics</strong> — R, Excel, platform insights</div>
      <div class="skill-tag"><strong>Bilingual</strong> — English &amp; Spanish</div>
    </div>
  </div>
</section>

<!-- WORK -->
<section id="work">
  <h2>Work</h2>
  <div class="work-grid">

    <div class="work-card featured">
      <div class="work-label">Freelance · 2026–Present</div>
      <div class="work-title">Sarafina Fiber Art — Social Media</div>
      <div class="work-desc">Built and manage the brand's entire social presence. Focus on short-form video content designed to grow organic reach, with strategic CTAs and active community engagement to turn viewers into followers and followers into customers.</div>
      <div class="work-tags">
        <span class="tag">Reels</span>
        <span class="tag">YouTube Shorts</span>
        <span class="tag">Facebook</span>
        <span class="tag">CTAs</span>
        <span class="tag">Brand building</span>
      </div>
      <div class="social-links">
        <a class="social-btn" href="https://www.instagram.com/sarafinafiberart/" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
          Instagram
        </a>
        <a class="social-btn" href="https://www.youtube.com/@sarafinafiberart" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 8s-.3-2-1.2-2.8c-1.1-1.2-2.4-1.2-3-1.3C15.6 3.8 12 3.8 12 3.8s-3.6 0-5.8.2c-.6.1-1.9.1-3 1.3C2.3 6 2 8 2 8S1.8 10.2 1.8 12.5v2.1c0 2.2.2 4.4.2 4.4s.3 2 1.2 2.8c1.1 1.2 2.6 1.1 3.3 1.2C8.8 23 12 23 12 23s3.6 0 5.8-.2c.6-.1 1.9-.1 3-1.3.9-.8 1.2-2.8 1.2-2.8s.2-2.2.2-4.4v-2.1C22.2 10.2 22 8 22 8z"/><polygon points="10,8.5 10,15.5 16,12" fill="currentColor" stroke="none"/></svg>
          YouTube
        </a>
        <a class="social-btn" href="https://www.facebook.com/sarafinafiberart" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg>
          Facebook
        </a>
      </div>
    </div>

    <div class="work-card">
      <div class="work-label">The Picklr · 2026–Present</div>
      <div class="work-title">Social Media Marketing</div>
      <div class="work-desc">Developing and executing content strategy for a growing recreational sports brand in Newark, DE.</div>
      <div class="work-tags">
        <span class="tag">Content strategy</span>
        <span class="tag">Video</span>
        <span class="tag">Engagement</span>
      </div>
      <div class="social-links">
        <a class="social-btn" href="https://www.instagram.com/thepicklr.newark/" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
          @ThePicklr.Newark
        </a>
      </div>
    </div>

    <div class="work-card">
      <div class="work-label">University of Delaware · 2025</div>
      <div class="work-title">BS Marketing — In Progress</div>
      <div class="work-desc">Studying consumer behavior, brand management, and digital marketing at UD's Lerner College of Business.</div>
      <div class="work-tags">
        <span class="tag">Marketing</span>
        <span class="tag">Lerner College</span>
      </div>
    </div>

  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <h2>Experience</h2>
  <div class="exp-list">
    <div class="exp-item">
      <div class="exp-date">Jan 2026–Now</div>
      <div>
        <div class="exp-role">Social Media Marketing Coordinator</div>
        <div class="exp-company">The Picklr, Newark DE</div>
        <div class="exp-desc">Short-form video, community engagement, and content strategy for a growing brand.</div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">Jan 2026–Now</div>
      <div>
        <div class="exp-role">Freelance Social Media Manager</div>
        <div class="exp-company">Sarafina Fiber Art</div>
        <div class="exp-desc">End-to-end social media management focused on Reels, Shorts, and organic audience growth.</div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">Aug 2025–Now</div>
      <div>
        <div class="exp-role">Team Member</div>
        <div class="exp-company">The Picklr, Newark DE</div>
        <div class="exp-desc">Customer experience and daily operations at a recreational sports facility.</div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">Sep 2023–Now</div>
      <div>
        <div class="exp-role">Server &amp; Manager</div>
        <div class="exp-company">The Naked Olive, Kennett Square PA</div>
        <div class="exp-desc">High-volume service and floor management in a fast-paced restaurant environment.</div>
      </div>
    </div>
    <div class="exp-item">
      <div class="exp-date">Summer 2025</div>
      <div>
        <div class="exp-role">Warehouse &amp; Logistics Associate</div>
        <div class="exp-company">The Tondo Group</div>
        <div class="exp-desc">Order fulfillment and shipment coordination at a small 3PL shipping company.</div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <h2>Contact</h2>
  <div class="contact-box">
    <h3>Let's work together</h3>
    <p>Whether it's social strategy, content, or just a conversation — my inbox is open.</p>
    <div class="contact-links">
      <a class="btn-primary" href="mailto:ilias.a.dalbow@gmail.com">ilias.a.dalbow@gmail.com</a>
      <a class="btn-ghost" href="https://linkedin.com/in/ilias-dalbow-12282003ad" target="_blank" rel="noopener">LinkedIn</a>
      <a class="btn-ghost" href="tel:3025458163">(302) 545-8163</a>
    </div>
  </div>
</section>

</body>
</html>
