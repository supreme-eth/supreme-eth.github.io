# supreme-eth.github.io
[vibe-competition.html](https://github.com/user-attachments/files/26265529/vibe-competition.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Motion Labs x Crevia — Vibe Platform Builder Competition</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --teal: #5ecfaa;
    --teal-dim: #3a9e7e;
    --black: #050505;
    --dark: #0d0d0d;
    --card: #111111;
    --border: rgba(94,207,170,0.15);
    --text: #e8e8e8;
    --muted: #666;
    --accent: #5ecfaa;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    overflow-x: hidden;
    line-height: 1.6;
  }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    padding: 80px 60px 60px;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 80% 60% at 60% 40%, rgba(94,207,170,0.07) 0%, transparent 70%);
    pointer-events: none;
  }

  .grid-overlay {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(94,207,170,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(94,207,170,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
  }

  .logos-bar {
    display: flex;
    align-items: center;
    gap: 24px;
    margin-bottom: 80px;
    position: relative;
    z-index: 2;
  }

  .logo-img {
    height: 44px;
    width: auto;
    object-fit: contain;
  }

  .logo-crevia {
    filter: none;
  }

  .logo-motion {
    filter: none;
    height: 38px;
  }

  .x-divider {
    font-family: 'DM Mono', monospace;
    font-size: 18px;
    color: var(--teal);
    opacity: 0.6;
  }

  .hero-label {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.25em;
    color: var(--teal);
    text-transform: uppercase;
    margin-bottom: 28px;
    opacity: 0.8;
    position: relative;
    z-index: 2;
  }

  .hero-title {
    font-size: clamp(42px, 6vw, 88px);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.03em;
    position: relative;
    z-index: 2;
    max-width: 900px;
  }

  .hero-title .teal { color: var(--teal); }

  .hero-sub {
    margin-top: 32px;
    font-size: 17px;
    color: var(--muted);
    max-width: 600px;
    line-height: 1.7;
    position: relative;
    z-index: 2;
    font-weight: 400;
  }

  .hero-stats {
    display: flex;
    gap: 48px;
    margin-top: 60px;
    position: relative;
    z-index: 2;
    flex-wrap: wrap;
  }

  .stat {
    border-left: 2px solid var(--teal);
    padding-left: 20px;
  }

  .stat-val {
    font-size: 32px;
    font-weight: 800;
    color: var(--teal);
    letter-spacing: -0.02em;
    line-height: 1;
  }

  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-top: 6px;
  }

  /* SCROLL INDICATOR */
  .scroll-hint {
    position: absolute;
    bottom: 40px;
    left: 60px;
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    z-index: 2;
  }

  .scroll-line {
    width: 40px;
    height: 1px;
    background: var(--muted);
  }

  /* SECTIONS */
  .section {
    padding: 100px 60px;
    position: relative;
  }

  .section + .section {
    border-top: 1px solid var(--border);
  }

  .section-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.3em;
    color: var(--teal);
    text-transform: uppercase;
    margin-bottom: 16px;
    opacity: 0.7;
  }

  .section-title {
    font-size: clamp(28px, 3.5vw, 48px);
    font-weight: 700;
    letter-spacing: -0.025em;
    line-height: 1.1;
    margin-bottom: 48px;
    max-width: 700px;
  }

  /* OVERVIEW CARDS */
  .overview-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
  }

  .overview-card {
    background: var(--dark);
    padding: 36px 32px;
    position: relative;
    overflow: hidden;
  }

  .overview-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--teal), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .overview-card:hover::before { opacity: 1; }

  .card-icon {
    font-size: 28px;
    margin-bottom: 16px;
    display: block;
  }

  .card-title {
    font-size: 15px;
    font-weight: 700;
    margin-bottom: 8px;
    color: var(--text);
  }

  .card-body {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* GRANT MECHANISM */
  .grant-block {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: start;
  }

  @media (max-width: 768px) {
    .grant-block { grid-template-columns: 1fr; }
    .hero { padding: 60px 24px 60px; }
    .section { padding: 70px 24px; }
    .hero-stats { gap: 32px; }
    .scroll-hint { left: 24px; }
  }

  .grant-desc {
    font-size: 16px;
    color: #999;
    line-height: 1.75;
    margin-bottom: 32px;
  }

  .highlight-box {
    background: linear-gradient(135deg, rgba(94,207,170,0.08), rgba(94,207,170,0.02));
    border: 1px solid rgba(94,207,170,0.25);
    padding: 28px 32px;
    margin-bottom: 20px;
  }

  .highlight-box .big-num {
    font-size: 52px;
    font-weight: 800;
    color: var(--teal);
    letter-spacing: -0.03em;
    line-height: 1;
  }

  .highlight-box .big-label {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-top: 8px;
  }

  .flow-diagram {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .flow-step {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    padding: 24px 0;
    border-bottom: 1px solid var(--border);
  }

  .flow-step:last-child { border-bottom: none; }

  .flow-num {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--teal);
    width: 28px;
    flex-shrink: 0;
    padding-top: 2px;
  }

  .flow-content-title {
    font-size: 14px;
    font-weight: 600;
    margin-bottom: 4px;
  }

  .flow-content-body {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.5;
  }

  /* TIMELINE */
  .timeline {
    position: relative;
    padding-left: 32px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 8px; bottom: 8px;
    width: 1px;
    background: linear-gradient(to bottom, var(--teal), transparent);
  }

  .timeline-item {
    position: relative;
    padding-bottom: 40px;
    padding-left: 28px;
  }

  .timeline-item::before {
    content: '';
    position: absolute;
    left: -5px;
    top: 6px;
    width: 10px;
    height: 10px;
    background: var(--teal);
    border-radius: 50%;
    box-shadow: 0 0 12px rgba(94,207,170,0.5);
  }

  .timeline-day {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--teal);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .timeline-event {
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 6px;
  }

  .timeline-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.55;
    max-width: 480px;
  }

  /* KPI GRID */
  .kpi-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 24px;
  }

  .kpi-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 32px 28px;
    position: relative;
    transition: border-color 0.3s, transform 0.3s;
  }

  .kpi-card:hover {
    border-color: rgba(94,207,170,0.4);
    transform: translateY(-2px);
  }

  .kpi-category {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.25em;
    color: var(--teal);
    text-transform: uppercase;
    margin-bottom: 20px;
    opacity: 0.8;
  }

  .kpi-items {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .kpi-items li {
    font-size: 13px;
    color: #aaa;
    padding-left: 16px;
    position: relative;
    line-height: 1.4;
  }

  .kpi-items li::before {
    content: '→';
    position: absolute;
    left: 0;
    color: var(--teal);
    font-size: 12px;
  }

  /* ELIGIBILITY */
  .req-list {
    display: flex;
    flex-direction: column;
    gap: 0;
    max-width: 640px;
  }

  .req-item {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    padding: 22px 0;
    border-bottom: 1px solid var(--border);
  }

  .req-item:last-child { border-bottom: none; }

  .req-check {
    width: 22px;
    height: 22px;
    border: 1.5px solid var(--teal);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .req-check::after {
    content: '✓';
    color: var(--teal);
    font-size: 12px;
  }

  .req-text {
    font-size: 15px;
    color: #bbb;
    line-height: 1.5;
  }

  /* CTA FOOTER */
  .cta-section {
    padding: 120px 60px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .cta-section::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 70% 80% at 50% 50%, rgba(94,207,170,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .cta-tag {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.3em;
    color: var(--teal);
    text-transform: uppercase;
    margin-bottom: 24px;
    opacity: 0.7;
  }

  .cta-title {
    font-size: clamp(36px, 5vw, 64px);
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 1.05;
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  }

  .cta-sub {
    font-size: 16px;
    color: var(--muted);
    margin-bottom: 48px;
    position: relative;
    z-index: 1;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }

  .cta-buttons {
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
    position: relative;
    z-index: 1;
  }

  .btn-primary {
    background: var(--teal);
    color: var(--black);
    padding: 16px 36px;
    font-family: 'Syne', sans-serif;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    border: none;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: opacity 0.2s;
  }

  .btn-primary:hover { opacity: 0.85; }

  .btn-secondary {
    background: transparent;
    color: var(--teal);
    padding: 16px 36px;
    font-family: 'Syne', sans-serif;
    font-size: 14px;
    font-weight: 600;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    border: 1px solid rgba(94,207,170,0.4);
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: border-color 0.2s, background 0.2s;
  }

  .btn-secondary:hover {
    border-color: var(--teal);
    background: rgba(94,207,170,0.05);
  }

  /* FOOTER */
  .footer {
    padding: 32px 60px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 16px;
  }

  .footer-logos {
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .footer-logo-img {
    height: 24px;
    width: auto;
    object-fit: contain;
  }

  .footer-logo-motion {
    filter: none;
    height: 20px;
  }

  .footer-copy {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-label { animation: fadeUp 0.6s ease both 0.1s; }
  .hero-title { animation: fadeUp 0.7s ease both 0.25s; }
  .hero-sub { animation: fadeUp 0.7s ease both 0.4s; }
  .hero-stats { animation: fadeUp 0.7s ease both 0.55s; }
  .logos-bar { animation: fadeUp 0.6s ease both; }

  /* NAV DOT */
  .nav-dots {
    position: fixed;
    right: 28px;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    gap: 12px;
    z-index: 100;
  }

  .nav-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--muted);
    cursor: pointer;
    transition: background 0.3s, transform 0.3s;
  }

  .nav-dot.active {
    background: var(--teal);
    transform: scale(1.4);
  }

  @media (max-width: 768px) {
    .nav-dots { display: none; }
    .footer { padding: 24px; }
    .cta-section { padding: 80px 24px; }
  }
</style>
</head>
<body>

<nav class="nav-dots" id="navDots">
  <div class="nav-dot active" data-section="0" title="Hero"></div>
  <div class="nav-dot" data-section="1" title="Overview"></div>
  <div class="nav-dot" data-section="2" title="Grant"></div>
  <div class="nav-dot" data-section="3" title="Structure"></div>
  <div class="nav-dot" data-section="4" title="KPIs"></div>
  <div class="nav-dot" data-section="5" title="Eligibility"></div>
  <div class="nav-dot" data-section="6" title="CTA"></div>
</nav>

<!-- HERO -->
<section class="hero" id="sec0">
  <div class="grid-overlay"></div>
  <div class="logos-bar">
    <img src="data:image/png;base64,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" class="logo-img logo-crevia" alt="Crevia">
    <span class="x-divider">×</span>
    <img src="data:image/png;base64,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" class="logo-img logo-motion" alt="Motion Labs">
  </div>
  <div class="hero-label">Ecosystem Initiative · 2026</div>
  <h1 class="hero-title">Vibe Platform<br><span class="teal">Builder</span><br>Competition</h1>
  <p class="hero-sub">A 2-week competitive builder program designed to incentivize the creation, launch, and rapid growth of new vibe-coded platforms within the Motion ecosystem.</p>
  <div class="hero-stats">
    <div class="stat">
      <div class="stat-val">14</div>
      <div class="stat-label">Days</div>
    </div>
    <div class="stat">
      <div class="stat-val">20%</div>
      <div class="stat-label">Fee to Grant Pool</div>
    </div>
    <div class="stat">
      <div class="stat-val">1</div>
      <div class="stat-label">Winner Takes All</div>
    </div>
  </div>
  <div class="scroll-hint">
    <span class="scroll-line"></span>
    Scroll to explore
  </div>
</section>

<!-- OVERVIEW -->
<section class="section" id="sec1">
  <div class="section-tag">01 — Overview</div>
  <h2 class="section-title">Aligning builders, traders &amp; ecosystem participants</h2>
  <div class="overview-grid">
    <div class="overview-card">
      <span class="card-icon">⚡</span>
      <div class="card-title">Accelerate Ecosystem</div>
      <div class="card-body">Rapid deployment of new platforms built on Motion Labs infrastructure using Crevia's vibe-coding framework.</div>
    </div>
    <div class="overview-card">
      <span class="card-icon">🧪</span>
      <div class="card-title">Experiment &amp; Deploy</div>
      <div class="card-body">Encourage rapid experimentation and real-world deployment of platform concepts within a structured competitive window.</div>
    </div>
    <div class="overview-card">
      <span class="card-icon">🏆</span>
      <div class="card-title">Reward Performance</div>
      <div class="card-body">High-performance platform operators earn the entire accumulated grant wallet — merit-based, not pre-allocated.</div>
    </div>
    <div class="overview-card">
      <span class="card-icon">🔍</span>
      <div class="card-title">Identify Talent</div>
      <div class="card-body">Surface standout teams for longer-term collaboration and drive meaningful trading activity across the network.</div>
    </div>
  </div>
</section>

<!-- GRANT -->
<section class="section" id="sec2">
  <div class="section-tag">02 — Grant Mechanism</div>
  <h2 class="section-title">Performance-funded, not pre-allocated</h2>
  <div class="grant-block">
    <div>
      <p class="grant-desc">The grant pool grows organically with the ecosystem. The more trading activity generated by participating platforms, the larger the final reward becomes — directly tying builder success to ecosystem value creation.</p>
      <div class="highlight-box">
        <div class="big-num">20%</div>
        <div class="big-label">of the 5% sell fee across all platforms</div>
      </div>
      <div class="highlight-box" style="margin-top: 0;">
        <div class="big-num">100%</div>
        <div class="big-label">of accumulated pool to winner</div>
      </div>
    </div>
    <div class="flow-diagram">
      <div class="flow-step">
        <div class="flow-num">01</div>
        <div>
          <div class="flow-content-title">Platforms Launch &amp; Trade</div>
          <div class="flow-content-body">All participating platforms go live via Motion Labs infrastructure. Traders interact, generating on-chain volume.</div>
        </div>
      </div>
      <div class="flow-step">
        <div class="flow-num">02</div>
        <div>
          <div class="flow-content-title">Fees Auto-Route to Grant Wallet</div>
          <div class="flow-content-body">20% of the 5% sell transaction fee is automatically routed to a dedicated, transparent on-chain grant wallet.</div>
        </div>
      </div>
      <div class="flow-step">
        <div class="flow-num">03</div>
        <div>
          <div class="flow-content-title">Pool Grows With Activity</div>
          <div class="flow-content-body">The reward pool scales with real ecosystem usage — no cap, no pre-set prize. Volume determines value.</div>
        </div>
      </div>
      <div class="flow-step">
        <div class="flow-num">04</div>
        <div>
          <div class="flow-content-title">Winner Claims Entire Wallet</div>
          <div class="flow-content-body">At Day 14, the highest KPI performer receives the full accumulated grant for development, liquidity &amp; growth.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- STRUCTURE / TIMELINE -->
<section class="section" id="sec3">
  <div class="section-tag">03 — Competition Structure</div>
  <h2 class="section-title">14 days of open competition</h2>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-day">Day 0</div>
      <div class="timeline-event">Official Launch</div>
      <div class="timeline-desc">Competition opens. Builders begin creating vibe-coded platforms using Crevia and launching through Motion Labs infrastructure. Grant wallet activated on-chain.</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-day">Days 1–13</div>
      <div class="timeline-event">Active Competition Window</div>
      <div class="timeline-desc">Platforms compete across KPIs: trading volume, user traction, retention, and ecosystem contribution. Grant wallet accumulates in real-time. Active trading markets must be maintained throughout.</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-day">Day 14</div>
      <div class="timeline-event">Evaluation &amp; KPI Snapshot</div>
      <div class="timeline-desc">Final KPI snapshot taken. Motion Labs applies weighted evaluation framework across market activity, user traction, platform performance, and ecosystem contribution.</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-day">Post-Competition</div>
      <div class="timeline-event">Grant Distribution &amp; Recognition</div>
      <div class="timeline-desc">Winning project receives full accumulated grant wallet. Top teams identified for longer-term collaboration opportunities within the Motion Labs and Crevia ecosystem.</div>
    </div>
  </div>
</section>

<!-- KPIs -->
<section class="section" id="sec4">
  <div class="section-tag">04 — Evaluation Criteria</div>
  <h2 class="section-title">Weighted KPI framework</h2>
  <div class="kpi-grid">
    <div class="kpi-card">
      <div class="kpi-category">Market Activity</div>
      <ul class="kpi-items">
        <li>Trading volume generated</li>
        <li>Liquidity depth &amp; stability</li>
        <li>Number of transactions</li>
        <li>Buy vs sell flow dynamics</li>
      </ul>
    </div>
    <div class="kpi-card">
      <div class="kpi-category">User Traction</div>
      <ul class="kpi-items">
        <li>Unique active wallets</li>
        <li>Retention across competition period</li>
        <li>Growth velocity</li>
      </ul>
    </div>
    <div class="kpi-card">
      <div class="kpi-category">Platform Performance</div>
      <ul class="kpi-items">
        <li>Market cap sustainability</li>
        <li>Volatility management</li>
        <li>Execution reliability</li>
      </ul>
    </div>
    <div class="kpi-card">
      <div class="kpi-category">Ecosystem Contribution</div>
      <ul class="kpi-items">
        <li>Integration with Motion tools</li>
        <li>Network effects created</li>
        <li>Community engagement</li>
      </ul>
    </div>
  </div>
  <p style="margin-top: 28px; font-family: 'DM Mono', monospace; font-size: 12px; color: var(--muted); line-height: 1.6; max-width: 580px;">Motion Labs reserves the right to apply qualitative judgment in cases where raw metrics do not fully reflect platform quality or long-term potential.</p>
</section>

<!-- ELIGIBILITY -->
<section class="section" id="sec5">
  <div class="section-tag">05 — Eligibility Requirements</div>
  <h2 class="section-title">What qualifies to compete</h2>
  <div class="req-list">
    <div class="req-item">
      <div class="req-check"></div>
      <div class="req-text">Built using <strong>Crevia's vibe-coding framework</strong></div>
    </div>
    <div class="req-item">
      <div class="req-check"></div>
      <div class="req-text">Launched through <strong>Motion Labs launch infrastructure</strong></div>
    </div>
    <div class="req-item">
      <div class="req-check"></div>
      <div class="req-text">Active trading markets maintained <strong>throughout the full competition period</strong></div>
    </div>
    <div class="req-item">
      <div class="req-check"></div>
      <div class="req-text">Follows all <strong>technical and operational guidelines</strong> provided by Motion Labs</div>
    </div>
    <div class="req-item">
      <div class="req-check"></div>
      <div class="req-text">Project launched <strong>within the official 14-day competition window</strong></div>
    </div>
  </div>
  <p style="margin-top: 32px; font-family: 'DM Mono', monospace; font-size: 12px; color: #c0392b; opacity: 0.8;">Projects launched outside this stack or timeframe will not be eligible for the grant competition.</p>
</section>

<!-- CTA -->
<section class="cta-section" id="sec6">
  <div class="cta-tag">Build · Launch · Win</div>
  <h2 class="cta-title">The strongest platforms<br>naturally emerge.</h2>
  <p class="cta-sub">By tying builder rewards directly to market traction and user adoption, we create a high-signal environment where merit determines the winner.</p>
  <div class="cta-buttons">
    <a href="#" class="btn-primary">Start Building on Crevia</a>
    <a href="#" class="btn-secondary">Motion Labs Docs</a>
  </div>
</section>

<!-- FOOTER -->
<footer class="footer">
  <div class="footer-logos">
    <img src="data:image/png;base64,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" class="footer-logo-img" alt="Crevia">
    <span style="color: var(--muted); font-size: 12px;">×</span>
    <img src="data:image/png;base64,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" class="footer-logo-img footer-logo-motion" alt="Motion Labs">
  </div>
  <div class="footer-copy">Motion Labs x Crevia · Vibe Builder Competition · 2026</div>
</footer>

<script>
// Nav dot scrollspy
const sections = document.querySelectorAll('[id^="sec"]');
const dots = document.querySelectorAll('.nav-dot');

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const idx = entry.target.id.replace('sec', '');
      dots.forEach(d => d.classList.remove('active'));
      const dot = document.querySelector('[data-section="' + idx + '"]');
      if (dot) dot.classList.add('active');
    }
  });
}, { threshold: 0.4 });

sections.forEach(s => observer.observe(s));

dots.forEach(dot => {
  dot.addEventListener('click', () => {
    const idx = dot.getAttribute('data-section');
    document.getElementById('sec' + idx).scrollIntoView({ behavior: 'smooth' });
  });
});
</script>
</body>
</html>
