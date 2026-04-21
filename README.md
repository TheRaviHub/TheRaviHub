<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TheRaviHub — GitHub README Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --border: #30363d;
    --text: #c9d1d9;
    --muted: #8b949e;
    --accent: #58a6ff;
    --cyan: #39d353;
    --orange: #f78166;
    --yellow: #e3b341;
    --purple: #bc8cff;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: #010409;
    font-family: 'Inter', sans-serif;
    color: var(--text);
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0;
  }

  /* Top controls */
  .controls {
    width: 100%;
    max-width: 860px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
    flex-wrap: wrap;
    gap: 10px;
  }

  .ctrl-label {
    font-family: 'Fira Code', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
  }

  .tabs {
    display: flex;
    gap: 4px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 4px;
  }

  .tab {
    padding: 5px 14px;
    border-radius: 6px;
    font-size: 12px;
    font-family: 'Fira Code', monospace;
    cursor: pointer;
    color: var(--muted);
    border: none;
    background: transparent;
    transition: all 0.2s;
  }

  .tab.active {
    background: var(--accent);
    color: #000;
    font-weight: 600;
  }

  .copy-all {
    background: #238636;
    color: #fff;
    border: none;
    border-radius: 6px;
    padding: 6px 14px;
    font-size: 12px;
    font-family: 'Fira Code', monospace;
    cursor: pointer;
    transition: opacity 0.2s;
  }

  .copy-all:hover { opacity: 0.85; }

  /* GitHub wrapper */
  .gh-wrapper {
    width: 100%;
    max-width: 860px;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  /* Repo bar */
  .repo-bar {
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .repo-bar .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot.r { background: #ff5f57; }
  .dot.y { background: #febc2e; }
  .dot.g { background: #28c840; }

  .repo-path {
    margin-left: 8px;
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .repo-path span { color: var(--accent); }

  /* README content */
  .readme {
    padding: 40px 48px;
    display: none;
  }

  .readme.active { display: block; }

  /* Raw content */
  .raw-content {
    display: none;
    padding: 20px;
  }

  .raw-content.active { display: block; }

  .raw-content pre {
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    color: #adbac7;
    line-height: 1.7;
    white-space: pre-wrap;
    word-break: break-word;
  }

  /* README styles */
  .center { text-align: center; }

  .wave-header {
    width: 100%;
    border-radius: 8px 8px 0 0;
    display: block;
    margin-bottom: 16px;
  }

  .typing-line {
    font-family: 'Fira Code', monospace;
    font-size: 18px;
    color: var(--cyan);
    border-right: 2px solid var(--cyan);
    padding-right: 4px;
    animation: blink 1s step-end infinite;
    display: inline-block;
  }

  @keyframes blink {
    0%,100% { border-color: var(--cyan); }
    50% { border-color: transparent; }
  }

  /* Typing animation cycling */
  .typing-container { height: 32px; display: flex; justify-content: center; align-items: center; margin: 12px 0; }

  .badge-row {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 8px;
    margin: 16px 0 10px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border-radius: 6px;
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    font-weight: 600;
    text-decoration: none;
    transition: transform 0.15s, opacity 0.15s;
    cursor: pointer;
  }

  .badge:hover { transform: translateY(-2px); opacity: 0.9; }
  .badge.linkedin { background: #0A66C2; color: #fff; }
  .badge.instagram { background: #E4405F; color: #fff; }
  .badge.gmail { background: #D14836; color: #fff; }
  .badge.github-b { background: #181717; color: #fff; border: 1px solid #444; }
  .badge.views { background: #1a1a2e; color: #00e5ff; border: 1px solid #00e5ff44; }

  hr.divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 28px 0;
  }

  h2 {
    font-size: 20px;
    color: #fff;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  /* Code block */
  .code-block {
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }

  .code-header {
    background: #161b22;
    border-bottom: 1px solid var(--border);
    padding: 8px 16px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .code-header .lang {
    font-family: 'Fira Code', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .code-body {
    padding: 16px 20px;
    font-family: 'Fira Code', monospace;
    font-size: 13px;
    line-height: 1.8;
    color: #c9d1d9;
  }

  .code-key { color: #ff7b72; }
  .code-str { color: #a5d6ff; }
  .code-val { color: #79c0ff; }
  .code-bracket { color: #e6edf3; }
  .code-comment { color: #8b949e; }

  /* Project cards */
  .project-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 8px;
  }

  .project-card {
    background: #161b22;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .project-card:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .project-card h3 {
    font-size: 14px;
    color: #fff;
    margin-bottom: 8px;
  }

  .project-card p {
    font-size: 12.5px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 10px;
  }

  .project-card ul {
    list-style: none;
    margin-bottom: 12px;
  }

  .project-card ul li {
    font-size: 12px;
    color: var(--text);
    padding: 2px 0;
    padding-left: 14px;
    position: relative;
  }

  .project-card ul li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--cyan);
  }

  .stack-line {
    font-family: 'Fira Code', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .stack-line code {
    background: #21262d;
    color: #e6edf3;
    padding: 2px 6px;
    border-radius: 4px;
    margin-right: 4px;
  }

  /* Skill icons section */
  .skill-section { margin-bottom: 20px; }

  .skill-section-label {
    font-family: 'Fira Code', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 10px;
    padding-bottom: 6px;
    border-bottom: 1px solid var(--border);
  }

  .skill-icons {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    align-items: center;
  }

  .skill-icon {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: #21262d;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 6px 10px;
    font-size: 12px;
    color: var(--text);
    font-family: 'Fira Code', monospace;
    transition: all 0.2s;
    cursor: default;
  }

  .skill-icon:hover {
    border-color: var(--accent);
    color: #fff;
    transform: translateY(-2px);
  }

  .skill-icon .dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* Stats row */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 12px;
  }

  .stat-card {
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    text-align: center;
  }

  .stat-card img {
    width: 100%;
    border-radius: 4px;
    filter: brightness(0.95);
  }

  .streak-card {
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    text-align: center;
    margin-bottom: 12px;
  }

  .streak-card img { width: 100%; }

  /* Activity graph */
  .activity-card {
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    margin-bottom: 12px;
    text-align: center;
  }

  .activity-card img { width: 100%; border-radius: 4px; }

  /* Trophy */
  .trophy-card {
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    text-align: center;
    margin-bottom: 12px;
  }

  .trophy-card img { width: 100%; }

  /* Progress bars */
  .progress-section { display: flex; flex-direction: column; gap: 10px; }

  .progress-item { display: flex; flex-direction: column; gap: 4px; }

  .progress-meta {
    display: flex;
    justify-content: space-between;
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .progress-meta .skill-name { color: var(--text); }

  .progress-bar {
    height: 6px;
    background: #21262d;
    border-radius: 4px;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    border-radius: 4px;
    transition: width 1.5s ease;
    width: 0;
  }

  .fill-cyan { background: linear-gradient(90deg, #00e5ff, #00b4cc); }
  .fill-blue { background: linear-gradient(90deg, #58a6ff, #1f6feb); }
  .fill-green { background: linear-gradient(90deg, #39d353, #26a641); }
  .fill-orange { background: linear-gradient(90deg, #f78166, #da3633); }
  .fill-purple { background: linear-gradient(90deg, #bc8cff, #8957e5); }
  .fill-yellow { background: linear-gradient(90deg, #e3b341, #bb8009); }

  /* Creative section */
  .creative-box {
    background: #161b22;
    border: 1px solid var(--border);
    border-left: 3px solid var(--yellow);
    border-radius: 8px;
    padding: 18px 20px;
  }

  .creative-box p {
    font-size: 13.5px;
    color: var(--text);
    line-height: 1.7;
  }

  /* Connect section */
  .connect-box {
    background: linear-gradient(135deg, #161b22 0%, #1a1f2e 100%);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    text-align: center;
  }

  .connect-box p {
    color: var(--muted);
    font-size: 13.5px;
    line-height: 1.7;
    margin-bottom: 16px;
  }

  .connect-box p strong { color: var(--text); }

  .wave-footer {
    width: 100%;
    display: block;
    margin-top: 24px;
  }

  .footer-quote {
    text-align: center;
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-top: 12px;
    font-style: italic;
  }

  /* Toast */
  .toast {
    position: fixed;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%) translateY(10px);
    background: #238636;
    color: #fff;
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    padding: 8px 18px;
    border-radius: 8px;
    opacity: 0;
    transition: all 0.25s;
    pointer-events: none;
    z-index: 999;
  }

  .toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }

  @media (max-width: 600px) {
    .readme { padding: 24px 20px; }
    .project-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- Controls -->
<div class="controls">
  <span class="ctrl-label">👁 GitHub README Preview — TheRaviHub</span>
  <div class="tabs">
    <button class="tab active" onclick="switchTab('preview', this)">Preview</button>
    <button class="tab" onclick="switchTab('raw', this)">Raw Markdown</button>
  </div>
  <button class="copy-all" onclick="copyRaw()">📋 Copy README</button>
</div>

<!-- GitHub wrapper -->
<div class="gh-wrapper">
  <!-- Repo bar -->
  <div class="repo-bar">
    <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
    <span class="repo-path"><span>TheRaviHub</span> / README.md</span>
  </div>

  <!-- PREVIEW TAB -->
  <div class="readme active" id="tab-preview">

    <!-- Wave header -->
    <div class="center">
      <img class="wave-header" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=160&section=header&text=Ravi%20Kumar%20Singh&fontSize=38&fontColor=fff&animation=twinkling&fontAlignY=35&desc=AI%20%26%20ML%20Student%20%7C%20Builder%20%7C%20Creative&descAlignY=58&descSize=14" alt="header" onerror="this.style.background='linear-gradient(135deg,#0d2233,#1a0533)';this.style.height='120px';this.alt='Ravi Kumar Singh'"/>

      <!-- Typing animation -->
      <div class="typing-container">
        <span class="typing-line" id="typing-el">Aspiring AI Engineer 🚀</span>
      </div>

      <!-- Badges -->
      <div class="badge-row">
        <span class="badge linkedin">💼 LinkedIn</span>
        <span class="badge instagram">📸 Instagram</span>
        <span class="badge gmail">✉️ Gmail</span>
        <span class="badge github-b">🐙 GitHub</span>
      </div>
      <div class="badge-row">
        <span class="badge views">👁 Profile Views Loading...</span>
      </div>
    </div>

    <hr class="divider"/>

    <!-- About -->
    <h2>🧠 About Me</h2>
    <div class="code-block">
      <div class="code-header">
        <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
        <span class="lang">python</span>
      </div>
      <div class="code-body">
        <span class="code-key">ravi</span> <span style="color:#ff7b72">=</span> <span class="code-bracket">{</span><br>
        &nbsp;&nbsp;<span class="code-str">"name"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"Ravi Kumar Singh"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"location"</span>&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"Ranchi, Jharkhand 🇮🇳"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"university"</span>&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"SRM University, AP — 2nd Year CSE"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"role"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"@ Hush Networks"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"goal"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"Become an AI Engineer 🤖"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"building"</span>&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"Property Price Prediction Model"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"ai_in_life"</span>&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"Using AI tools in daily workflow"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"creative"</span>&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"Video Editor — DaVinci Resolve 🎬"</span><span class="code-bracket">,</span><br>
        &nbsp;&nbsp;<span class="code-str">"learning"</span>&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-bracket">[</span><span class="code-val">"ML"</span><span class="code-bracket">,</span> <span class="code-val">"DSA"</span><span class="code-bracket">,</span> <span class="code-val">"System Design"</span><span class="code-bracket">,</span> <span class="code-val">"AI Workflows"</span><span class="code-bracket">],</span><br>
        &nbsp;&nbsp;<span class="code-str">"fun_fact"</span>&nbsp;&nbsp;&nbsp;&nbsp; <span class="code-bracket">:</span> <span class="code-val">"I debug code and cut frames — same energy"</span><span class="code-bracket">,</span><br>
        <span class="code-bracket">}</span>
      </div>
    </div>

    <hr class="divider"/>

    <!-- Projects -->
    <h2>🚀 What I'm Currently Building</h2>
    <div class="project-grid">
      <div class="project-card">
        <h3>🏠 Property Price Prediction</h3>
        <p>My first real end-to-end ML project — from raw messy data to a working model.</p>
        <ul>
          <li>Feature engineering & data cleaning</li>
          <li>Regression models & hyperparameter tuning</li>
          <li>Learning ML beyond tutorials</li>
        </ul>
        <div class="stack-line"><code>Python</code><code>Pandas</code><code>Scikit-learn</code><code>Matplotlib</code></div>
      </div>
      <div class="project-card">
        <h3>🤖 AI in Daily Workflow</h3>
        <p>Integrating AI tools into how I actually work — not just studying it.</p>
        <ul>
          <li>Prompt engineering for real tasks</li>
          <li>Automating repetitive workflows</li>
          <li>Exploring LLM APIs & agents</li>
        </ul>
        <div class="stack-line"><code>Python</code><code>LLM APIs</code><code>Automation</code></div>
      </div>
    </div>

    <hr class="divider"/>

    <!-- Tech Stack -->
    <h2>🛠️ Tech Stack</h2>

    <div class="skill-section">
      <div class="skill-section-label">Languages</div>
      <div class="skill-icons">
        <span class="skill-icon"><span class="dot" style="background:#555"></span>C</span>
        <span class="skill-icon"><span class="dot" style="background:#00599C"></span>C++</span>
        <span class="skill-icon"><span class="dot" style="background:#ED8B00"></span>Java</span>
        <span class="skill-icon"><span class="dot" style="background:#3776AB"></span>Python</span>
        <span class="skill-icon"><span class="dot" style="background:#F7DF1E"></span>JavaScript</span>
      </div>
    </div>

    <div class="skill-section">
      <div class="skill-section-label">ML & AI</div>
      <div class="skill-icons">
        <span class="skill-icon"><span class="dot" style="background:#013243"></span>NumPy</span>
        <span class="skill-icon"><span class="dot" style="background:#150458"></span>Pandas</span>
        <span class="skill-icon"><span class="dot" style="background:#F7931E"></span>Scikit-learn</span>
        <span class="skill-icon"><span class="dot" style="background:#11557c"></span>Matplotlib</span>
        <span class="skill-icon"><span class="dot" style="background:#ff6f00"></span>Jupyter</span>
      </div>
    </div>

    <div class="skill-section">
      <div class="skill-section-label">Web & Cloud</div>
      <div class="skill-icons">
        <span class="skill-icon"><span class="dot" style="background:#E34F26"></span>HTML5</span>
        <span class="skill-icon"><span class="dot" style="background:#FFCA28"></span>Firebase</span>
        <span class="skill-icon"><span class="dot" style="background:#000"></span>Vercel</span>
        <span class="skill-icon"><span class="dot" style="background:#00C7B7"></span>Netlify</span>
        <span class="skill-icon"><span class="dot" style="background:#F38020"></span>Cloudflare</span>
      </div>
    </div>

    <div class="skill-section">
      <div class="skill-section-label">Tools & Creative</div>
      <div class="skill-icons">
        <span class="skill-icon"><span class="dot" style="background:#F05032"></span>Git</span>
        <span class="skill-icon"><span class="dot" style="background:#007ACC"></span>VS Code</span>
        <span class="skill-icon"><span class="dot" style="background:#233A51"></span>DaVinci Resolve</span>
        <span class="skill-icon"><span class="dot" style="background:#000"></span>Notion</span>
      </div>
    </div>

    <hr class="divider"/>

    <!-- GitHub Stats -->
    <h2>📊 GitHub Stats</h2>

    <div class="stats-row">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=TheRaviHub&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=00e5ff&icon_color=00e5ff&text_color=c9d1d9" alt="GitHub Stats" onerror="this.parentElement.innerHTML='<p style=\'color:#8b949e;font-family:Fira Code,monospace;font-size:12px\'>📊 Stats loading on GitHub...</p>'"/>
      </div>
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=TheRaviHub&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00e5ff&text_color=c9d1d9" alt="Top Languages" onerror="this.parentElement.innerHTML='<p style=\'color:#8b949e;font-family:Fira Code,monospace;font-size:12px\'>📊 Languages loading on GitHub...</p>'"/>
      </div>
    </div>

    <div class="streak-card">
      <img src="https://streak-stats.demolab.com?user=TheRaviHub&theme=tokyonight&hide_border=true&background=0D1117&stroke=00e5ff&ring=00e5ff&fire=ff6b35&currStreakLabel=00e5ff" alt="Streak Stats" onerror="this.parentElement.innerHTML='<p style=\'color:#8b949e;font-family:Fira Code,monospace;font-size:12px\'>🔥 Streak loading on GitHub...</p>'"/>
    </div>

    <div class="activity-card">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=TheRaviHub&theme=tokyo-night&hide_border=true&bg_color=0d1117&color=00e5ff&line=00e5ff&point=ffffff" alt="Activity Graph" onerror="this.parentElement.innerHTML='<p style=\'color:#8b949e;font-family:Fira Code,monospace;font-size:12px\'>📈 Activity graph loads on GitHub...</p>'"/>
    </div>

    <div class="trophy-card">
      <img src="https://github-profile-trophy.vercel.app/?username=TheRaviHub&theme=tokyonight&no-frame=true&row=1&column=6&margin-w=4&margin-h=4" alt="Trophies" onerror="this.parentElement.innerHTML='<p style=\'color:#8b949e;font-family:Fira Code,monospace;font-size:12px\'>🏆 Trophies load on GitHub...</p>'"/>
    </div>

    <hr class="divider"/>

    <!-- Level up -->
    <h2>📈 Leveling Up</h2>
    <div class="progress-section" id="progress-bars">
      <div class="progress-item">
        <div class="progress-meta"><span class="skill-name">Python</span><span>70%</span></div>
        <div class="progress-bar"><div class="progress-fill fill-blue" data-width="70"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-meta"><span class="skill-name">Machine Learning</span><span>55%</span></div>
        <div class="progress-bar"><div class="progress-fill fill-cyan" data-width="55"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-meta"><span class="skill-name">AI Engineering</span><span>40%</span></div>
        <div class="progress-bar"><div class="progress-fill fill-purple" data-width="40"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-meta"><span class="skill-name">DSA</span><span>35%</span></div>
        <div class="progress-bar"><div class="progress-fill fill-orange" data-width="35"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-meta"><span class="skill-name">System Design</span><span>25%</span></div>
        <div class="progress-bar"><div class="progress-fill fill-yellow" data-width="25"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-meta"><span class="skill-name">Video Editing (DaVinci)</span><span>80%</span></div>
        <div class="progress-bar"><div class="progress-fill fill-green" data-width="80"></div></div>
      </div>
    </div>

    <hr class="divider"/>

    <!-- Creative -->
    <h2>🎬 Beyond the Code</h2>
    <div class="creative-box">
      <p>
        I edit videos in <strong>DaVinci Resolve</strong> — color grading, cuts, storytelling.<br>
        Turns out building an ML model and editing a timeline aren't that different.<br>
        Both are about making something <em>messy</em> into something <em>clean.</em>
      </p>
    </div>

    <hr class="divider"/>

    <!-- Connect -->
    <div class="connect-box">
      <h2 style="justify-content:center;margin-bottom:12px;">🤝 Let's Connect</h2>
      <p>
        I'm a <strong>2nd year student</strong> actively building, learning, and connecting.<br>
        If you're in ML/AI, building something open-source, or just want to talk tech —<br>
        <strong>reach out. always open.</strong>
      </p>
      <div class="badge-row" style="justify-content:center">
        <span class="badge linkedin">💼 LinkedIn</span>
        <span class="badge gmail">✉️ onlyravi4321@gmail.com</span>
      </div>
    </div>

    <!-- Footer -->
    <img class="wave-footer" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=80&section=footer" alt="" onerror="this.style.display='none'"/>
    <p class="footer-quote">Building one commit at a time — from Ranchi to the world 🌍</p>

  </div>

  <!-- RAW TAB -->
  <div class="raw-content" id="tab-raw">
    <pre id="raw-md"></pre>
  </div>
</div>

<div class="toast" id="toast">✓ Copied to clipboard!</div>

<script>
// ── Typing animation ──────────────────────────────────────────
const lines = [
  "Aspiring AI Engineer 🚀",
  "ML Student @ SRM University AP",
  "Building Property Price Prediction",
  "Integrating AI in Daily Workflow",
  "Video Editor — DaVinci Resolve 🎬",
  "Learning by Building, Always 💡"
];

let lineIdx = 0, charIdx = 0, deleting = false;
const el = document.getElementById('typing-el');

function type() {
  const current = lines[lineIdx];
  if (!deleting) {
    el.textContent = current.slice(0, ++charIdx);
    if (charIdx === current.length) {
      deleting = true;
      setTimeout(type, 1800);
      return;
    }
  } else {
    el.textContent = current.slice(0, --charIdx);
    if (charIdx === 0) {
      deleting = false;
      lineIdx = (lineIdx + 1) % lines.length;
    }
  }
  setTimeout(type, deleting ? 40 : 80);
}
type();

// ── Progress bars animate on load ─────────────────────────────
setTimeout(() => {
  document.querySelectorAll('.progress-fill').forEach(bar => {
    bar.style.width = bar.dataset.width + '%';
  });
}, 400);

// ── Tab switching ──────────────────────────────────────────────
const rawMarkdown = `<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=160&section=header&text=Ravi%20Kumar%20Singh&fontSize=38&fontColor=fff&animation=twinkling&fontAlignY=35&desc=AI%20%26%20ML%20Student%20%7C%20Builder%20%7C%20Creative&descAlignY=58&descSize=14" width="100%"/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&duration=3000&pause=1000&color=39D353&center=true&vCenter=true&width=600&lines=Aspiring+AI+Engineer+🚀;ML+Student+%40+SRM+University+AP;Building+Property+Price+Prediction;Integrating+AI+in+Daily+Workflow;Video+Editor+—+DaVinci+Resolve+🎬;Learning+by+Building%2C+Always+💡)](https://git.io/typing-svg)

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](#)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/ravihere_)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:onlyravi4321@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/TheRaviHub)

![Profile Views](https://komarev.com/ghpvc/?username=TheRaviHub&style=for-the-badge&color=00e5ff&label=PROFILE+VIEWS)

</div>

---

## 🧠 About Me

\`\`\`python
ravi = {
    "name"         : "Ravi Kumar Singh",
    "location"     : "Ranchi, Jharkhand 🇮🇳",
    "university"   : "SRM University, AP — 2nd Year CSE",
    "role"         : "@ Hush Networks",
    "goal"         : "Become an AI Engineer 🤖",
    "building"     : "Property Price Prediction Model",
    "ai_in_life"   : "Using AI tools in daily workflow",
    "creative"     : "Video Editor — DaVinci Resolve 🎬",
    "learning"     : ["ML", "DSA", "System Design", "AI Workflows"],
    "fun_fact"     : "I debug code and cut frames — same energy",
}
\`\`\`

---

## 🚀 What I'm Currently Building

<table>
<tr>
<td width="50%">

### 🏠 Property Price Prediction
My first real end-to-end ML project — from raw messy data to a working model.
- Feature engineering & data cleaning
- Regression models & hyperparameter tuning
- Learning ML beyond tutorials

**Stack:** \`Python\` \`Pandas\` \`Scikit-learn\` \`Matplotlib\`

</td>
<td width="50%">

### 🤖 AI in Daily Workflow
Integrating AI tools into how I actually work — not just studying it.
- Prompt engineering for real tasks
- Automating repetitive workflows
- Exploring LLM APIs & agents

**Stack:** \`Python\` \`LLM APIs\` \`Automation\`

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

<div align="center">

**Languages**

[![My Skills](https://skillicons.dev/icons?i=c,cpp,java,python,js&theme=dark)](https://skillicons.dev)

**ML & AI**

![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**Web & Cloud**

[![My Skills](https://skillicons.dev/icons?i=html,firebase,vercel,netlify,cloudflare&theme=dark)](https://skillicons.dev)

**Tools & Creative**

[![My Skills](https://skillicons.dev/icons?i=git,vscode,notion&theme=dark)](https://skillicons.dev)
![DaVinci Resolve](https://img.shields.io/badge/DaVinci%20Resolve-233A51?style=for-the-badge&logo=davinci-resolve&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=TheRaviHub&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=00e5ff&icon_color=00e5ff&text_color=c9d1d9"/>
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=TheRaviHub&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00e5ff&text_color=c9d1d9"/>

[![GitHub Streak](https://streak-stats.demolab.com?user=TheRaviHub&theme=tokyonight&hide_border=true&background=0D1117&stroke=00e5ff&ring=00e5ff&fire=ff6b35&currStreakLabel=00e5ff)](https://git.io/streak-stats)

[![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=TheRaviHub&theme=tokyo-night&hide_border=true&bg_color=0d1117&color=00e5ff&line=00e5ff&point=ffffff)](https://github.com/ashutosh00710/github-readme-activity-graph)

[![Trophies](https://github-profile-trophy.vercel.app/?username=TheRaviHub&theme=tokyonight&no-frame=true&row=1&column=6&margin-w=4)](https://github.com/ryo-ma/github-profile-trophy)

</div>

---

## 📈 Leveling Up

\`\`\`
Python              ████████████████░░░░   70%
Machine Learning    ██████████████░░░░░░   55%
AI Engineering      ██████████░░░░░░░░░░   40%
DSA                 █████████░░░░░░░░░░░   35%
System Design       ██████░░░░░░░░░░░░░░   25%
Video Editing 🎬    ████████████████████   80%
\`\`\`

---

## 🎬 Beyond the Code

> I edit videos in **DaVinci Resolve** — color grading, cuts, storytelling.
> Turns out building an ML model and editing a timeline aren't that different.
> Both are about making something *messy* into something *clean.*

---

## 🤝 Let's Connect

<div align="center">

I'm a **2nd year student** actively building, learning, and connecting.
If you're in ML/AI, building something open-source, or just want to talk tech — **reach out. always open.**

[![LinkedIn](https://img.shields.io/badge/Let's_Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](#)
[![Email](https://img.shields.io/badge/onlyravi4321@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:onlyravi4321@gmail.com)

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=80&section=footer" width="100%"/>

*Building one commit at a time — from Ranchi to the world 🌍*

</div>`;

document.getElementById('raw-md').textContent = rawMarkdown;

function switchTab(tab, btn) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  btn.classList.add('active');
  document.getElementById('tab-preview').classList.remove('active');
  document.getElementById('tab-raw').classList.remove('active');
  document.getElementById('tab-' + tab).classList.add('active');
}

function copyRaw() {
  navigator.clipboard.writeText(rawMarkdown).then(() => {
    const t = document.getElementById('toast');
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 2500);
  });
}
</script>
</body>
</html>
