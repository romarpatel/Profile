[index.html.html](https://github.com/user-attachments/files/31236700/index.html.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Roma Patel — Revenue Operations &amp; Deal Architecture</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Serif:ital,wght@0,400;0,600;1,400&family=IBM+Plex+Sans:wght@300;400;500;600&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --navy-bg: #0A2A43;
    --navy-panel: #0E3A5C;
    --grid-line: rgba(234,242,248,0.06);
    --grid-line-strong: rgba(234,242,248,0.12);
    --ink: #EAF2F8;
    --ink-dim: #9FB8CC;
    --ink-faint: #6E8AA3;
    --brass: #D3AE45;
    --brass-dim: rgba(211,174,69,0.35);
    --line: rgba(234,242,248,0.5);
    --radius: 2px;
  }

  *{ box-sizing: border-box; }

  html{ scroll-behavior: smooth; }

  body{
    margin:0;
    background:
      repeating-linear-gradient(0deg, var(--grid-line) 0, var(--grid-line) 1px, transparent 1px, transparent 40px),
      repeating-linear-gradient(90deg, var(--grid-line) 0, var(--grid-line) 1px, transparent 1px, transparent 40px),
      var(--navy-bg);
    color: var(--ink);
    font-family: 'IBM Plex Sans', sans-serif;
    font-weight: 400;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  .crop{
    position: fixed;
    width: 22px;
    height: 22px;
    z-index: 50;
    pointer-events: none;
  }
  .crop::before, .crop::after{
    content:"";
    position: absolute;
    background: var(--brass-dim);
  }
  .crop::before{ width:100%; height:1px; top:50%; left:0; }
  .crop::after{ width:1px; height:100%; left:50%; top:0; }
  .crop.tl{ top:18px; left:18px; }
  .crop.tr{ top:18px; right:18px; }
  .crop.bl{ bottom:18px; left:18px; }
  .crop.br{ bottom:18px; right:18px; }

  .wrap{
    max-width: 900px;
    margin: 0 auto;
    padding: 64px 28px 40px;
  }

  /* ---------- Title block (top) ---------- */
  .titlebar{
    display:flex;
    justify-content: space-between;
    align-items: baseline;
    font-family:'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--ink-faint);
    border-bottom: 1px solid var(--grid-line-strong);
    padding-bottom: 14px;
    margin-bottom: 56px;
    flex-wrap: wrap;
    gap: 8px;
  }
  .titlebar span b{ color: var(--brass); font-weight: 500; }

  /* ---------- Hero ---------- */
  .hero{ margin-bottom: 64px; }
  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--brass);
    margin-bottom: 18px;
  }
  h1{
    font-family:'IBM Plex Serif', serif;
    font-weight: 600;
    font-size: clamp(40px, 7vw, 64px);
    letter-spacing: -0.01em;
    margin: 0 0 14px;
    color: var(--ink);
  }
  .role-line{
    font-family:'IBM Plex Mono', monospace;
    font-size: 14px;
    letter-spacing: 0.02em;
    color: var(--ink-dim);
    margin: 0 0 28px;
  }
  .value-prop{
    font-size: 19px;
    max-width: 620px;
    color: var(--ink);
    font-weight: 300;
    margin: 0 0 30px;
  }
  .value-prop em{ font-style: normal; color: var(--brass); }

  .status-pill{
    display:inline-flex;
    align-items:center;
    gap: 10px;
    font-family:'IBM Plex Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink);
    border: 1px solid var(--brass-dim);
    padding: 9px 16px;
    border-radius: var(--radius);
  }
  .status-dot{
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--brass);
    box-shadow: 0 0 0 3px rgba(211,174,69,0.18);
  }

  /* ---------- Section heading ---------- */
  .section{ margin-bottom: 64px; }
  .sec-head{
    display:flex;
    align-items:baseline;
    gap: 14px;
    margin-bottom: 26px;
  }
  .sec-num{
    font-family:'IBM Plex Mono', monospace;
    font-size: 12px;
    color: var(--brass);
  }
  .sec-title{
    font-family:'IBM Plex Serif', serif;
    font-size: 22px;
    font-weight: 600;
    color: var(--ink);
    margin: 0;
  }
  .sec-rule{
    flex:1;
    height:1px;
    background: var(--grid-line-strong);
  }

  /* ---------- Schematic (signature element) ---------- */
  .schematic{
    width: 100%;
    height: auto;
    display:block;
    margin-bottom: 8px;
  }
  .schem-line{
    fill:none;
    stroke: var(--line);
    stroke-width: 1.5;
    stroke-dasharray: 8 6;
  }
  .schem-node-ring{
    fill: var(--navy-panel);
    stroke: var(--brass);
    stroke-width: 1.5;
  }
  .schem-node-dot{ fill: var(--brass); }
  .schem-label{
    font-family:'IBM Plex Mono', monospace;
    font-size: 11.5px;
    letter-spacing: 0.06em;
    fill: var(--ink);
    text-transform: uppercase;
  }
  .schem-sub{
    font-family:'IBM Plex Mono', monospace;
    font-size: 10.5px;
    fill: var(--ink-faint);
  }

  .draw{
    stroke-dashoffset: 1;
    animation: draw 2.4s ease-out forwards;
  }
  @keyframes draw{
    from{ stroke-dashoffset: 900; opacity: 0; }
    to{ stroke-dashoffset: 0; opacity: 1; }
  }
  @media (prefers-reduced-motion: reduce){
    .draw{ animation: none; stroke-dashoffset: 0; opacity: 1; }
  }

  /* ---------- Spec list ---------- */
  .spec-grid{
    display:grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    border-top: 1px solid var(--grid-line-strong);
  }
  .spec-item{
    padding: 18px 18px 18px 0;
    border-bottom: 1px solid var(--grid-line-strong);
  }
  .spec-item:nth-child(odd){ border-right: 1px solid var(--grid-line-strong); padding-right: 24px; }
  .spec-item:nth-child(even){ padding-left: 24px; }
  .spec-label{
    font-family:'IBM Plex Mono', monospace;
    font-size: 10.5px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--brass);
    margin-bottom: 8px;
  }
  .spec-value{
    font-size: 15px;
    color: var(--ink);
    font-weight: 300;
  }
  .spec-value b{ color: var(--ink); font-weight: 500; }

  /* ---------- Capability list ---------- */
  .cap-list{ list-style:none; margin:0; padding:0; }
  .cap-list li{
    display:grid;
    grid-template-columns: 130px 1fr;
    gap: 20px;
    padding: 16px 0;
    border-bottom: 1px solid var(--grid-line-strong);
    align-items: baseline;
  }
  .cap-tag{
    font-family:'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--brass);
  }
  .cap-text b{ color: var(--ink); font-weight: 500; }
  .cap-text{ color: var(--ink-dim); font-weight: 300; font-size: 15px; }

  /* ---------- Timeline / background ---------- */
  .timeline{ position: relative; padding-left: 26px; }
  .timeline::before{
    content:"";
    position:absolute; left: 4px; top: 6px; bottom: 6px; width: 1px;
    background: var(--grid-line-strong);
  }
  .tl-item{ position: relative; padding-bottom: 26px; }
  .tl-item:last-child{ padding-bottom: 0; }
  .tl-item::before{
    content:"";
    position:absolute; left: -26px; top: 5px;
    width: 9px; height: 9px; border-radius: 50%;
    background: var(--navy-bg);
    border: 1.5px solid var(--brass);
  }
  .tl-role{ font-weight: 500; color: var(--ink); font-size: 15.5px; }
  .tl-meta{
    font-family:'IBM Plex Mono', monospace;
    font-size: 11px;
    color: var(--ink-faint);
    margin-top: 4px;
    letter-spacing: 0.04em;
  }

  /* ---------- Footer title block ---------- */
  footer{
    border-top: 1px solid var(--grid-line-strong);
    padding-top: 26px;
    margin-top: 20px;
  }
  .footgrid{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
  }
  .foot-label{
    font-family:'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-faint);
    margin-bottom: 6px;
  }
  .foot-value{
    font-size: 14px;
    color: var(--ink);
  }
  .foot-value a{ color: var(--brass); text-decoration: none; border-bottom: 1px solid var(--brass-dim); }
  .foot-value a:hover{ border-bottom-color: var(--brass); }

  a:focus-visible, .status-pill:focus-visible{
    outline: 2px solid var(--brass);
    outline-offset: 3px;
  }

  .schematic-mobile{ display:none; max-width: 320px; }

  @media (max-width: 640px){
    .crop{ display:none; }
    .wrap{ padding: 40px 20px 32px; }
    .titlebar{ font-size: 10px; }
    .spec-grid{ grid-template-columns: 1fr; }
    .spec-item:nth-child(odd){ border-right:none; padding-right:0; }
    .spec-item:nth-child(even){ padding-left:0; }
    .cap-list li{ grid-template-columns: 1fr; gap: 6px; }
    .footgrid{ grid-template-columns: 1fr 1fr; }
    .schematic-desktop{ display:none; }
    .schematic-mobile{ display:block; }
  }
</style>
</head>
<body>

<div class="crop tl"></div>
<div class="crop tr"></div>
<div class="crop bl"></div>
<div class="crop br"></div>

<div class="wrap">

  <div class="titlebar">
    <span>Operator Profile <b>·</b> Rev. 2026.08</span>
    <span>Remote — Chino, CA</span>
    <span><b>Status:</b> Actively Engaging</span>
  </div>

  <!-- HERO -->
  <section class="hero">
    <div class="eyebrow">Revenue Operations — Deal Architecture</div>
    <h1>Roma Patel</h1>
    <p class="role-line">FRACTIONAL &nbsp;/&nbsp; INTERIM &nbsp;/&nbsp; FULL-TIME &nbsp;—&nbsp; HEALTHCARE &amp; HEALTH TECH</p>
    <p class="value-prop">I design and build the revenue operating systems — Deal Desk governance, pricing architecture, and forecasting infrastructure — that healthcare organizations need but haven't had the bandwidth to build. Then I <em>hand it off, working.</em></p>
    <span class="status-pill"><span class="status-dot"></span>Open to fractional, interim &amp; full-time engagements</span>
  </section>

  <!-- SIGNATURE SCHEMATIC -->
  <section class="section">
    <svg class="schematic schematic-desktop" viewBox="0 0 840 190" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Four stage operating model: Diagnose, Design, Build, Handoff">
      <path class="schem-line draw" d="M120,60 L280,60" />
      <path class="schem-line draw" d="M340,60 L500,60" style="animation-delay:0.3s" />
      <path class="schem-line draw" d="M560,60 L720,60" style="animation-delay:0.6s" />

      <!-- Node 1 -->
      <circle class="schem-node-ring" cx="90" cy="60" r="30"/>
      <circle class="schem-node-dot" cx="90" cy="60" r="4"/>
      <text class="schem-label" x="90" y="112" text-anchor="middle">Diagnose</text>
      <text class="schem-sub" x="90" y="130" text-anchor="middle">stakeholder &amp; gap review</text>

      <!-- Node 2 -->
      <circle class="schem-node-ring" cx="310" cy="60" r="30"/>
      <circle class="schem-node-dot" cx="310" cy="60" r="4"/>
      <text class="schem-label" x="310" y="112" text-anchor="middle">Design</text>
      <text class="schem-sub" x="310" y="130" text-anchor="middle">governance &amp; KPI architecture</text>

      <!-- Node 3 -->
      <circle class="schem-node-ring" cx="530" cy="60" r="30"/>
      <circle class="schem-node-dot" cx="530" cy="60" r="4"/>
      <text class="schem-label" x="530" y="112" text-anchor="middle">Build</text>
      <text class="schem-sub" x="530" y="130" text-anchor="middle">deploy &amp; automate</text>

      <!-- Node 4 -->
      <circle class="schem-node-ring" cx="750" cy="60" r="30"/>
      <circle class="schem-node-dot" cx="750" cy="60" r="4"/>
      <text class="schem-label" x="750" y="112" text-anchor="middle">Handoff</text>
      <text class="schem-sub" x="750" y="130" text-anchor="middle">train &amp; transition owner</text>
    </svg>

    <svg class="schematic schematic-mobile" viewBox="0 0 340 420" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Four stage operating model: Diagnose, Design, Build, Handoff">
      <path class="schem-line draw" d="M30,55 L30,140" />
      <path class="schem-line draw" d="M30,180 L30,265" style="animation-delay:0.3s" />
      <path class="schem-line draw" d="M30,305 L30,390" style="animation-delay:0.6s" />

      <circle class="schem-node-ring" cx="30" cy="30" r="24"/>
      <circle class="schem-node-dot" cx="30" cy="30" r="4"/>
      <text class="schem-label" x="70" y="26" text-anchor="start">Diagnose</text>
      <text class="schem-sub" x="70" y="44" text-anchor="start">stakeholder &amp; gap review</text>

      <circle class="schem-node-ring" cx="30" cy="155" r="24"/>
      <circle class="schem-node-dot" cx="30" cy="155" r="4"/>
      <text class="schem-label" x="70" y="151" text-anchor="start">Design</text>
      <text class="schem-sub" x="70" y="169" text-anchor="start">governance &amp; KPI architecture</text>

      <circle class="schem-node-ring" cx="30" cy="280" r="24"/>
      <circle class="schem-node-dot" cx="30" cy="280" r="4"/>
      <text class="schem-label" x="70" y="276" text-anchor="start">Build</text>
      <text class="schem-sub" x="70" y="294" text-anchor="start">deploy &amp; automate</text>

      <circle class="schem-node-ring" cx="30" cy="405" r="24"/>
      <circle class="schem-node-dot" cx="30" cy="405" r="4"/>
      <text class="schem-label" x="70" y="401" text-anchor="start">Handoff</text>
      <text class="schem-sub" x="70" y="419" text-anchor="start">train &amp; transition owner</text>
    </svg>
  </section>

  <!-- WHERE I ADD VALUE -->
  <section class="section">
    <div class="sec-head">
      <span class="sec-num">01</span>
      <h2 class="sec-title">Where I Add Value</h2>
      <div class="sec-rule"></div>
    </div>
    <ul class="cap-list">
      <li>
        <span class="cap-tag">Deal Desk</span>
        <span class="cap-text"><b>Contract governance build-outs</b> — approval workflows, shared service models, and contracting standards, especially through M&amp;A / post-merger integration.</span>
      </li>
      <li>
        <span class="cap-tag">Pricing</span>
        <span class="cap-text"><b>Pricing &amp; deal architecture</b> — pricing models, quota/commission frameworks, and deal-structuring guardrails that scale with growth.</span>
      </li>
      <li>
        <span class="cap-tag">Forecasting</span>
        <span class="cap-text"><b>Pipeline governance</b> — KPI architecture, scorecards, and operating cadence that give leadership real-time, trustworthy visibility.</span>
      </li>
      <li>
        <span class="cap-tag">Integration</span>
        <span class="cap-text"><b>Post-merger / post-investment integration</b> — standardizing fragmented processes without disrupting revenue continuity.</span>
      </li>
      <li>
        <span class="cap-tag">PE-Backed</span>
        <span class="cap-text"><b>RevOps stand-up for portfolio companies</b> — the zero-to-one build needed after a platform investment, before a full-time VP hire is justified.</span>
      </li>
    </ul>
  </section>

  <!-- PROOF POINTS -->
  <section class="section">
    <div class="sec-head">
      <span class="sec-num">02</span>
      <h2 class="sec-title">Proof Points</h2>
      <div class="sec-rule"></div>
    </div>
    <div class="spec-grid">
      <div class="spec-item">
        <div class="spec-label">Forecast Accuracy</div>
        <div class="spec-value"><b>±40% → ±5%</b> via an enterprise-wide forecasting model built from the ground up.</div>
      </div>
      <div class="spec-item">
        <div class="spec-label">Pipeline Visibility</div>
        <div class="spec-value">Scaled from <b>$7.5B to $13B+</b> through rebuilt CRM &amp; pipeline governance.</div>
      </div>
      <div class="spec-item">
        <div class="spec-label">Shared Services</div>
        <div class="spec-value"><b>97%</b> of transactional deal activity transitioned during post-merger integration.</div>
      </div>
      <div class="spec-item">
        <div class="spec-label">Cycle Time</div>
        <div class="spec-value">Contract turnaround reduced by <b>30%</b> through workflow redesign.</div>
      </div>
      <div class="spec-item">
        <div class="spec-label">Capacity Recovered</div>
        <div class="spec-value"><b>4,000+ hours</b> annually via forecasting automation.</div>
      </div>
      <div class="spec-item">
        <div class="spec-label">Scale of Ownership</div>
        <div class="spec-value">Quota &amp; pricing frameworks for a <b>3,000+ seller</b>, $6B portfolio.</div>
      </div>
    </div>
  </section>

  <!-- BACKGROUND -->
  <section class="section">
    <div class="sec-head">
      <span class="sec-num">03</span>
      <h2 class="sec-title">Background</h2>
      <div class="sec-rule"></div>
    </div>
    <div class="timeline">
      <div class="tl-item">
        <div class="tl-role">VP, Customer Deal Desk — Oracle Health</div>
        <div class="tl-meta">2023–2025 · Promoted by the Global SVP of Finance Operations</div>
      </div>
      <div class="tl-item">
        <div class="tl-role">Sr. Director, Sales Effectiveness &amp; Forecasting — Oracle Health</div>
        <div class="tl-meta">2021–2023</div>
      </div>
      <div class="tl-item">
        <div class="tl-role">Director, Sales Operations &amp; Business Analytics — Philips Healthcare</div>
        <div class="tl-meta">2018–2021</div>
      </div>
      <div class="tl-item">
        <div class="tl-role">Lean Six Sigma Certified · B.S. Chemical Engineering &amp; Materials Science, UC Irvine</div>
        <div class="tl-meta">Credentials</div>
      </div>
    </div>
  </section>

  <!-- FOOTER / TITLE BLOCK -->
  <footer>
    <div class="footgrid">
      <div>
        <div class="foot-label">Contact</div>
        <div class="foot-value"><a href="mailto:roma114@gmail.com">roma114@gmail.com</a></div>
      </div>
      <div>
        <div class="foot-label">Phone</div>
        <div class="foot-value">(818) 823-6382</div>
      </div>
      <div>
        <div class="foot-label">Based In</div>
        <div class="foot-value">Chino, CA · Remote</div>
      </div>
      <div>
        <div class="foot-label">Engagement</div>
        <div class="foot-value">10–20 hrs/wk · Interim · Project</div>
      </div>
    </div>
  </footer>

</div>
</body>
</html>
