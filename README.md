
<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=DM+Mono:wght@400;500&display=swap');
*{margin:0;padding:0;box-sizing:border-box}
body{background:#fafafa;font-family:'DM Sans',sans-serif;color:#111827;overflow-x:hidden}
canvas#bg{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none}
.page{position:relative;z-index:1;max-width:880px;margin:0 auto;padding:3rem 1.75rem 5rem}

.hdr{text-align:center;padding:3rem 0 2.5rem;animation:up .6s ease both}
.av-wrap{display:inline-block;position:relative;margin-bottom:1.4rem}
.av{width:90px;height:90px;border-radius:50%;background:#ede9fe;border:2px solid #c4b5fd;display:flex;align-items:center;justify-content:center;font-size:1.45rem;font-weight:700;color:#6d28d9;font-family:'DM Mono',monospace;position:relative;z-index:1}
.ring{position:absolute;inset:-5px;border-radius:50%;border:1.5px solid #ddd6fe;animation:rp 2.8s ease-in-out infinite}
.ring2{position:absolute;inset:-11px;border-radius:50%;border:1px solid #ede9fe;animation:rp 2.8s .9s ease-in-out infinite}
@keyframes rp{0%,100%{opacity:.7;transform:scale(1)}50%{opacity:.15;transform:scale(1.07)}}
h1{font-size:2.1rem;font-weight:700;color:#111827;letter-spacing:-.5px;line-height:1.15;margin-bottom:.4rem}
h1 em{font-style:normal;color:#7c3aed}
.role{font-family:'DM Mono',monospace;font-size:.78rem;color:#7c3aed;letter-spacing:2px;text-transform:uppercase;margin-bottom:.5rem;min-height:1.4em}
#cursor{display:inline-block;width:2px;height:.9em;background:#7c3aed;vertical-align:middle;animation:blink .9s step-end infinite;margin-left:1px}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.chips{display:flex;flex-wrap:wrap;gap:6px;justify-content:center;margin-top:.9rem}
.chip{background:#f5f3ff;border:1px solid #ddd6fe;border-radius:999px;padding:3px 12px;font-size:.73rem;color:#6d28d9;font-family:'DM Mono',monospace}

.stats{display:grid;grid-template-columns:repeat(4,1fr);gap:9px;margin:1.4rem 0;animation:up .6s .05s ease both}
.st{background:#fff;border:1px solid #ede9fe;border-radius:12px;padding:1rem;text-align:center;transition:border-color .2s,transform .2s}
.st:hover{border-color:#c4b5fd;transform:translateY(-2px)}
.stn{font-size:1.65rem;font-weight:700;color:#7c3aed;display:block;line-height:1;margin-bottom:2px;font-family:'DM Mono',monospace}
.stl{font-size:.64rem;color:#9ca3af;font-family:'DM Mono',monospace}

.card{background:#fff;border:1px solid #ede9fe;border-radius:16px;padding:1.6rem;margin-bottom:1.3rem;position:relative;overflow:hidden}
.card::before{content:'';position:absolute;top:0;left:0;right:0;height:2.5px;border-radius:16px 16px 0 0}
.c-v::before{background:#7c3aed}.c-i::before{background:#6366f1}.c-b::before{background:#3b82f6}.c-t::before{background:#0ea5e9}.c-g::before{background:#10b981}
.sec{font-family:'DM Mono',monospace;font-size:.62rem;letter-spacing:2.5px;text-transform:uppercase;color:#a78bfa;margin-bottom:1.1rem;display:flex;align-items:center;gap:8px}
.sec::after{content:'';flex:1;height:1px;background:#ede9fe}

.about p{color:#4b5563;line-height:1.8;font-size:.92rem}
.about p+p{margin-top:.55rem}
.hl{color:#7c3aed;font-weight:600}

.sk-row{display:flex;align-items:center;gap:11px;margin-bottom:12px}
.sk-row:last-child{margin-bottom:0}
.sk-nm{font-size:.77rem;font-family:'DM Mono',monospace;color:#6b7280;width:145px;flex-shrink:0;text-align:right}
.sk-tr{flex:1;height:5px;background:#f5f3ff;border-radius:999px;overflow:hidden}
.sk-br{height:100%;border-radius:999px;width:0;transition:width 1.3s cubic-bezier(.4,0,.2,1)}
.sk-pc{font-size:.71rem;font-family:'DM Mono',monospace;color:#a78bfa;width:32px;text-align:right}

.grp-lbl{font-size:.6rem;font-family:'DM Mono',monospace;letter-spacing:2px;text-transform:uppercase;color:#c4b5fd;margin-bottom:.5rem;margin-top:1rem}
.grp-lbl:first-child{margin-top:0}
.pills{display:flex;flex-wrap:wrap;gap:7px}
.pill{display:flex;align-items:center;gap:5px;background:#faf9ff;border:1px solid #ede9fe;border-radius:8px;padding:5px 10px;font-size:.77rem;color:#374151;transition:all .15s;cursor:default}
.pill:hover{background:#ede9fe;border-color:#c4b5fd;color:#5b21b6;transform:translateY(-1px)}
.pill svg{flex-shrink:0;width:14px;height:14px}

.arch-g{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:8px}
.arch{background:#faf9ff;border:1px solid #ede9fe;border-radius:10px;padding:.85rem .9rem;transition:all .2s}
.arch:hover{border-color:#c4b5fd;background:#f0edff}
.arch-ic{font-size:1.1rem;margin-bottom:4px}
.arch-n{font-size:.75rem;font-weight:600;color:#4c1d95;margin-bottom:2px}
.arch-d{font-size:.69rem;color:#9ca3af;line-height:1.45}

.proj-g{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px}
.proj{background:#faf9ff;border:1px solid #ede9fe;border-radius:12px;padding:1.1rem 1.2rem;transition:all .2s;text-decoration:none;display:block}
.proj:hover{border-color:#a78bfa;background:#f0edff;transform:translateY(-2px)}
.proj-top{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:.5rem}
.proj-ic{font-size:1.4rem}
.proj-badge{font-size:.62rem;font-family:'DM Mono',monospace;background:#f0edff;border:1px solid #ddd6fe;color:#6d28d9;border-radius:999px;padding:2px 9px}
.proj-name{font-size:.88rem;font-weight:600;color:#1a1a2e;margin-bottom:.3rem}
.proj-desc{font-size:.77rem;color:#6b7280;line-height:1.55;margin-bottom:.7rem}
.proj-tags{display:flex;flex-wrap:wrap;gap:5px}
.ptag{font-size:.66rem;font-family:'DM Mono',monospace;background:#fff;border:1px solid #e5e7eb;color:#7c3aed;border-radius:5px;padding:2px 7px}

.build-g{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:8px}
.build{background:#faf9ff;border:1px solid #ede9fe;border-radius:10px;padding:.8rem .5rem;text-align:center;transition:all .2s}
.build:hover{border-color:#a78bfa;background:#f0edff;transform:translateY(-2px)}
.build-e{font-size:1.2rem;display:block;margin-bottom:3px}
.build-n{font-size:.68rem;color:#7c3aed;font-weight:500}

.gh-strip{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:9px}
.gh-card{background:#faf9ff;border:1px solid #ede9fe;border-radius:12px;padding:1rem;text-align:center}
.gh-n{font-size:1.4rem;font-weight:700;color:#7c3aed;display:block;font-family:'DM Mono',monospace;margin-bottom:2px}
.gh-l{font-size:.68rem;color:#9ca3af;font-family:'DM Mono',monospace}

.lang-row{display:flex;height:8px;border-radius:999px;overflow:hidden;margin-bottom:10px}
.lang-seg{height:100%;transition:width 1s ease}
.lang-legend{display:flex;flex-wrap:wrap;gap:8px 16px}
.lang-dot{display:flex;align-items:center;gap:5px;font-size:.72rem;color:#6b7280;font-family:'DM Mono',monospace}
.dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}

.cta-row{display:flex;flex-wrap:wrap;gap:9px;justify-content:center;margin:1.8rem 0 1rem}
.cta{display:flex;align-items:center;gap:7px;background:#fff;border:1px solid #ede9fe;border-radius:10px;padding:9px 16px;color:#6d28d9;font-size:.8rem;font-family:'DM Mono',monospace;text-decoration:none;transition:all .2s;cursor:pointer}
.cta:hover{background:#f0edff;border-color:#a78bfa;transform:translateY(-1px)}

.copywrap{text-align:center;margin:1.2rem 0 .5rem}
.copybtn{background:#7c3aed;color:#fff;border:none;border-radius:999px;padding:10px 28px;font-family:'DM Mono',monospace;font-size:.77rem;cursor:pointer;letter-spacing:.5px;transition:background .15s,transform .15s}
.copybtn:hover{background:#6d28d9;transform:scale(1.03)}
.toast{text-align:center;font-family:'DM Mono',monospace;font-size:.73rem;color:#a78bfa;margin-top:.4rem;opacity:0;transition:opacity .3s;min-height:18px}

.footer{text-align:center;font-family:'DM Mono',monospace;font-size:.7rem;color:#d1d5db;letter-spacing:1px;margin-top:1.5rem}
.footer b{color:#a78bfa;font-weight:400}

@keyframes up{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}
.a1{animation:up .6s .04s ease both}.a2{animation:up .6s .09s ease both}.a3{animation:up .6s .14s ease both}.a4{animation:up .6s .19s ease both}.a5{animation:up .6s .24s ease both}.a6{animation:up .6s .29s ease both}.a7{animation:up .6s .34s ease both}.a8{animation:up .6s .39s ease both}
</style>

<canvas id="bg"></canvas>
<div class="page">

<div class="hdr">
  <div class="av-wrap">
    <div class="ring"></div><div class="ring2"></div>
    <div class="av">HM</div>
  </div>
  <h1>Hashem <em>Mdoukh</em></h1>
  <div class="role"><span id="typed"></span><span id="cursor"></span></div>
  <div class="chips">
    <span class="chip">React</span><span class="chip">Next.js</span><span class="chip">TypeScript</span>
    <span class="chip">Node.js</span><span class="chip">Palestine 🇵🇸</span><span class="chip">Open to Remote</span>
  </div>
</div>

<div class="stats">
  <div class="st"><span class="stn" data-t="3">0</span><span class="stl">Years Coding</span></div>
  <div class="st"><span class="stn" data-t="15">0</span><span class="stl">Technologies</span></div>
  <div class="st"><span class="stn" data-t="10">0</span><span class="stl">Projects Built</span></div>
  <div class="st"><span class="stn" data-t="2">0</span><span class="stl">Languages</span></div>
</div>

<div class="card c-v a1">
  <div class="sec">// about me</div>
  <div class="about">
    <p>I'm a <span class="hl">Front-End Engineer</span> who cares deeply about <span class="hl">scalable architecture</span>, clean code, and exceptional user experiences. I build production-grade apps with <span class="hl">React, Next.js &amp; TypeScript</span> — from feature-based modular systems to full monorepo setups with shared Design Systems.</p>
    <p>Beyond the frontend, I'm comfortable across the full stack — designing RESTful APIs with <span class="hl">Node.js &amp; Express</span>, modeling data with <span class="hl">MongoDB</span>, and wiring everything end-to-end.</p>
  </div>
</div>

<div class="card c-b a3">
  <div class="sec">// skill proficiency</div>
  <div id="skillsWrap"></div>
</div>

<div class="card c-t a4">
  <div class="sec">// github activity</div>
  <div class="gh-strip">
    <div class="gh-card"><span class="gh-n" data-t="40">0</span><span class="gh-l">Repositories</span></div>
    <div class="gh-card"><span class="gh-n" data-t="320">0</span><span class="gh-l">Contributions</span></div>
    <div class="gh-card"><span class="gh-n" data-t="18">0</span><span class="gh-l">Pull Requests</span></div>
  </div>
  <div style="margin-top:1.2rem">
    <div class="sec" style="margin-bottom:.7rem">// top languages</div>
    <div class="lang-row" id="langBar"></div>
    <div class="lang-legend" id="langLegend"></div>
  </div>
</div>

<div class="card c-i a5">
  <div class="sec">// tech stack</div>
  <div class="grp-lbl">Frontend</div>
  <div class="pills">
    <div class="pill"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="2" fill="#61DAFB"/><g fill="none" stroke="#61DAFB" stroke-width="1"><ellipse rx="7" ry="2.6" cx="12" cy="12"/><ellipse rx="7" ry="2.6" cx="12" cy="12" transform="rotate(60 12 12)"/><ellipse rx="7" ry="2.6" cx="12" cy="12" transform="rotate(120 12 12)"/></g></svg>React.js</div>
    <div class="pill"><svg viewBox="0 0 24 24"><path d="M12 2L2 21h4l6-10 6 10h4z" fill="#1a1a2e"/></svg>Next.js</div>
    <div class="pill"><svg viewBox="0 0 24 24"><path d="M3 3h8l6.5 11V3H21v18h-8L6.5 10V21H3z" fill="#3178C6"/></svg>TypeScript</div>
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="2" fill="none" stroke="#F7DF1E" stroke-width="1.2"/><path d="M7 8h10v1.2H7zm0 3.5h10v1.2H7zm0 3.5h7v1.2H7z" fill="#F7DF1E"/></svg>JavaScript</div>
    <div class="pill"><svg viewBox="0 0 24 24"><path d="M12 2L4 6v6c0 5 4 9.5 8 11 4-1.5 8-6 8-11V6z" fill="#DD0031"/><path d="M12 5l-5 2.5v5c0 3.5 2.5 6.5 5 7.8 2.5-1.3 5-4.3 5-7.8v-5z" fill="#C3002F"/><path d="M12 7.5l-2.5 7h1.2l.8-2h3l.8 2H16.5L12 7.5zm0 2l1 2.5h-2L12 9.5z" fill="white"/></svg>Angular</div>
  </div>
  <div class="grp-lbl">Styling & UI</div>
  <div class="pills">
    <div class="pill"><svg viewBox="0 0 24 24"><path d="M12 4c-2.6 0-4.3 1.3-5.1 4 1-1.3 2.1-1.8 3.4-1.5.7.2 1.2.7 1.8 1.3 1 1 2.1 2.2 4.5 2.2 2.6 0 4.3-1.3 5.1-4-1 1.3-2.1 1.8-3.4 1.5-.7-.2-1.2-.7-1.8-1.3C15.5 5.2 14.4 4 12 4zm-5.1 6c-2.6 0-4.3 1.3-5.1 4 1-1.3 2.1-1.8 3.4-1.5.7.2 1.2.7 1.8 1.3 1 1 2.1 2.2 4.5 2.2 2.6 0 4.3-1.3 5.1-4-1 1.3-2.1 1.8-3.4 1.5-.7-.2-1.2-.7-1.8-1.3-1-1-2.1-2.2-4.5-2.2z" fill="#38BDF8"/></svg>Tailwind CSS v4</div>
    <div class="pill"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="8" fill="none" stroke="#339AF0" stroke-width="1.4"/><circle cx="12" cy="12" r="3" fill="#339AF0"/></svg>Mantine UI</div>
    <div class="pill"><svg viewBox="0 0 24 24"><path d="M3 3l9-1 9 1-1.5 16L12 21l-7.5-2z" fill="#007FFF" opacity=".85"/></svg>MUI</div>
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2" fill="#264DE4" opacity=".8"/><path d="M7 7l1 10 4 1.2 4-1.2 1-10H7zm8.5 3H9.2l.2 2h5.8l-.4 4-2.8.8-2.8-.8-.2-2h1.5l.1 1 1.4.4 1.4-.4.2-2.5H9L8.5 10z" fill="white"/></svg>CSS Modules</div>
  </div>
  <div class="grp-lbl">State, Routing & Backend</div>
  <div class="pills">
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="3" fill="#FF4154"/><path d="M7 7h10v2H7zm0 3h10v2H7zm0 3h7v2H7z" fill="white"/></svg>TanStack Query</div>
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="3" fill="#F59E0B"/><path d="M12 6l3 5.5H9L12 6zm-3 7h6v4H9v-4z" fill="white"/></svg>TanStack Router</div>
    <div class="pill"><svg viewBox="0 0 24 24"><path d="M12 2c-1.5 0-2.8.8-3.7 2L5 12l3.8 7c.9 1.2 2.2 2 3.7 2s2.8-.8 3.7-2L20 12l-3.8-8C15.3 2.8 13.5 2 12 2z" fill="#83CD29"/><path d="M12 2c1.5 0 2.8.8 3.7 2L20 12l-3.8 7c-.9 1.2-2.2 2-3.7 2V2z" fill="#404137"/><circle cx="12" cy="12" r="3" fill="white"/></svg>Node.js</div>
    <div class="pill"><svg viewBox="0 0 24 24"><ellipse cx="12" cy="8" rx="8" ry="2.5" fill="#4DB33D"/><path d="M4 8v4c0 1.4 3.6 2.5 8 2.5s8-1.1 8-2.5V8c0 1.4-3.6 2.5-8 2.5S4 9.4 4 8z" fill="#3FA037"/><path d="M4 12v4c0 1.4 3.6 2.5 8 2.5s8-1.1 8-2.5v-4c0 1.4-3.6 2.5-8 2.5S4 13.4 4 12z" fill="#4DB33D" opacity=".8"/></svg>MongoDB</div>
  </div>
  <div class="grp-lbl">Architecture & Tooling</div>
  <div class="pills">
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="8" height="8" rx="1.5" fill="#6366f1"/><rect x="13" y="3" width="8" height="8" rx="1.5" fill="#8b5cf6"/><rect x="3" y="13" width="8" height="8" rx="1.5" fill="#8b5cf6"/><rect x="13" y="13" width="8" height="8" rx="1.5" fill="#6366f1"/></svg>Turborepo</div>
    <div class="pill"><svg viewBox="0 0 24 24"><ellipse cx="12" cy="7" rx="8" ry="2.5" fill="none" stroke="#F69220" stroke-width="1.4"/><path d="M4 7v5c0 1.4 3.6 2.5 8 2.5s8-1.1 8-2.5V7" stroke="#F69220" stroke-width="1.4" fill="none"/><path d="M4 12v5c0 1.4 3.6 2.5 8 2.5s8-1.1 8-2.5v-5" stroke="#F69220" stroke-width="1.4" fill="none"/></svg>pnpm Workspaces</div>
    <div class="pill"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="8.5" fill="none" stroke="#646CFF" stroke-width="1.4"/><path d="M8 14.5l8-8M8 8.5h6v6" stroke="#646CFF" stroke-width="1.4" fill="none" stroke-linecap="round"/></svg>Vite</div>
    <div class="pill"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="8.5" fill="none" stroke="#F05032" stroke-width="1.4"/><circle cx="8.5" cy="9.5" r="1.5" fill="#F05032"/><circle cx="15.5" cy="9.5" r="1.5" fill="#F05032"/><circle cx="12" cy="16" r="1.5" fill="#F05032"/><path d="M8.5 9.5l3.5 6.5 3.5-6.5" stroke="#F05032" stroke-width="1" fill="none"/></svg>Git &amp; GitHub</div>
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="3" fill="#007ACC"/><path d="M7 9.5h3v6H7zm3.5-2h3v8h-3zm3.5 3h3v5h-3z" fill="white"/></svg>VS Code</div>
    <div class="pill"><svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="3" fill="#FF6C37"/><path d="M8 9h8M8 12.5h6M8 16h7" stroke="white" stroke-width="1.5" stroke-linecap="round"/></svg>Postman</div>
  </div>
</div>

<div class="card c-v a6">
  <div class="sec">// engineering patterns</div>
  <div class="arch-g">
    <div class="arch"><div class="arch-ic">🧩</div><div class="arch-n">Feature-Based Arch</div><div class="arch-d">Domain-isolated modules with views, hooks, APIs & services</div></div>
    <div class="arch"><div class="arch-ic">🏗</div><div class="arch-n">Monorepo (Turborepo)</div><div class="arch-d">pnpm Workspaces with shared Design System packages</div></div>
    <div class="arch"><div class="arch-ic">🔄</div><div class="arch-n">Compound Components</div><div class="arch-d">Implicit state via Context for composable UI APIs</div></div>
    <div class="arch"><div class="arch-ic">🧠</div><div class="arch-n">Headless Components</div><div class="arch-d">Logic-only hooks, consumer-controlled rendering</div></div>
    <div class="arch"><div class="arch-ic">🔌</div><div class="arch-n">DIP + DTO Mapping</div><div class="arch-d">Interfaces decoupling UI from API details</div></div>
    <div class="arch"><div class="arch-ic">🚩</div><div class="arch-n">Feature Flags</div><div class="arch-d">Context-based A/B testing & remote rollouts</div></div>
  </div>
</div>

<div class="card c-g a7">
  <div class="sec">// what i build</div>
  <div class="build-g">
    <div class="build"><span class="build-e">📊</span><span class="build-n">Dashboards</span></div>
    <div class="build"><span class="build-e">⚡</span><span class="build-n">SaaS Platforms</span></div>
    <div class="build"><span class="build-e">🛒</span><span class="build-n">E-Commerce</span></div>
    <div class="build"><span class="build-e">🖥</span><span class="build-n">Admin Panels</span></div>
    <div class="build"><span class="build-e">🎨</span><span class="build-n">Design Systems</span></div>
    <div class="build"><span class="build-e">📦</span><span class="build-n">Component Libs</span></div>
    <div class="build"><span class="build-e">🔗</span><span class="build-n">Full-Stack Apps</span></div>
    <div class="build"><span class="build-e">📈</span><span class="build-n">Data Viz</span></div>
  </div>
</div>

<div class="cta-row a8">
  <a class="cta" href="mailto:mr.mdoukh@gmail.com">✉ mr.mdoukh@gmail.com</a>
  <a class="cta" href="https://github.com/hashem-mdoukh" target="_blank">⚡ github.com/hashem-mdoukh</a>
  <a class="cta" href="https://linkedin.com/in/hashem-mdoukh" target="_blank">◈ linkedin.com/in/hashem-mdoukh</a>
</div>

<div class="copywrap">
  <button class="copybtn" onclick="copyMe()">Copy README.md</button>
  <div class="toast" id="toast">README copied ✓</div>
</div>

<div class="footer">
  <b>Clean Code</b> · <b>Scalable Architecture</b> · <b>Exceptional UX</b><br><br>
  ✦ Open to remote &amp; international opportunities ✦
</div>
</div>

<script>
const cv = document.getElementById('bg');
const cx = cv.getContext('2d');
let pts=[];
function rs(){cv.width=window.innerWidth;cv.height=window.innerHeight;pts=[];for(let i=0;i<80;i++)pts.push({x:Math.random()*cv.width,y:Math.random()*cv.height,vx:(Math.random()-.5)*.15,vy:(Math.random()-.5)*.15,r:Math.random()*1.6+.4})}
rs();window.addEventListener('resize',rs);
function draw(){cx.clearRect(0,0,cv.width,cv.height);for(const p of pts){p.x+=p.vx;p.y+=p.vy;if(p.x<0||p.x>cv.width)p.vx*=-1;if(p.y<0||p.y>cv.height)p.vy*=-1;cx.beginPath();cx.arc(p.x,p.y,p.r,0,Math.PI*2);cx.fillStyle='rgba(124,58,237,.12)';cx.fill()}
for(let i=0;i<pts.length;i++)for(let j=i+1;j<pts.length;j++){const d=Math.hypot(pts[i].x-pts[j].x,pts[i].y-pts[j].y);if(d<100){cx.beginPath();cx.moveTo(pts[i].x,pts[i].y);cx.lineTo(pts[j].x,pts[j].y);cx.strokeStyle=`rgba(167,139,250,${.09*(1-d/100)})`;cx.lineWidth=.6;cx.stroke()}}
requestAnimationFrame(draw)}
draw();

const roles=['Front-End Engineer','React Developer','Next.js Specialist','TypeScript Expert','UI Architect'];
let ri=0,ci=0,del=false;
const tel=document.getElementById('typed');
function type(){
  if(!del){tel.textContent=roles[ri].slice(0,ci+1);ci++;if(ci===roles[ri].length){setTimeout(()=>{del=true;setTimeout(type,60)},1800);return}}
  else{tel.textContent=roles[ri].slice(0,ci-1);ci--;if(ci===0){del=false;ri=(ri+1)%roles.length}}
  setTimeout(type,del?45:70)}
setTimeout(type,600);

const skills=[
  {n:'React.js',p:92,c:'#7c3aed'},{n:'TypeScript',p:88,c:'#6366f1'},{n:'Next.js',p:85,c:'#8b5cf6'},
  {n:'Tailwind CSS',p:90,c:'#38BDF8'},{n:'TanStack Query',p:83,c:'#a78bfa'},{n:'Node.js / Express',p:75,c:'#83CD29'},
  {n:'MongoDB',p:70,c:'#4DB33D'},{n:'Angular',p:72,c:'#DD0031'}];
const sw=document.getElementById('skillsWrap');
skills.forEach(s=>{sw.innerHTML+=`<div class="sk-row"><div class="sk-nm">${s.n}</div><div class="sk-tr"><div class="sk-br" data-p="${s.p}" style="background:${s.c}"></div></div><div class="sk-pc">${s.p}%</div></div>`});
setTimeout(()=>{document.querySelectorAll('.sk-br').forEach(b=>{b.style.width=b.dataset.p+'%'})},400);

function cnt(el,t,suf=''){let n=0;const iv=setInterval(()=>{n=Math.min(n+Math.ceil(t/30),t);el.textContent=n+suf;if(n>=t)clearInterval(iv)},28)}
document.querySelectorAll('.stn').forEach(el=>cnt(el,parseInt(el.dataset.t),'+'));
document.querySelectorAll('.gh-n').forEach(el=>cnt(el,parseInt(el.dataset.t),'+'));

const langs=[{n:'TypeScript',pct:42,c:'#3178C6'},{n:'JavaScript',pct:28,c:'#F7DF1E'},{n:'CSS',pct:14,c:'#264DE4'},{n:'HTML',pct:10,c:'#E34F26'},{n:'Other',pct:6,c:'#c4b5fd'}];
const bar=document.getElementById('langBar'),leg=document.getElementById('langLegend');
langs.forEach(l=>{
  const s=document.createElement('div');s.className='lang-seg';s.style.cssText=`background:${l.c};width:0`;bar.appendChild(s);
  leg.innerHTML+=`<div class="lang-dot"><div class="dot" style="background:${l.c}"></div>${l.n} ${l.pct}%</div>`;
});
setTimeout(()=>{document.querySelectorAll('.lang-seg').forEach((s,i)=>{s.style.width=langs[i].pct+'%'})},500);

function copyMe(){
  const t=`# 👋 Hi, I'm Hashem Mdoukh

<div align="center">

### Front-End Engineer | React • Next.js • TypeScript

> Building scalable, maintainable, and high-performance web applications.

![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=7C3AED&center=true&vCenter=true&width=435&lines=Front-End+Engineer;React+Developer;Next.js+Specialist;TypeScript+Expert;UI+Architect)

</div>

---

## 🚀 About Me

I'm a **Front-End Engineer** passionate about creating modern digital products that combine exceptional user experiences with clean, scalable architecture.

- 🔭 Building production-grade apps with **React**, **Next.js** & **TypeScript**
- 🏗 Designing scalable **monorepo architectures** with Turborepo & pnpm Workspaces
- 🧩 Applying advanced patterns: **Compound Components**, **Headless Components**, **DIP + DTO mapping**
- 🌍 Based in **Palestine** | Open to **remote & international opportunities**
- 📫 Reach me at **mr.mdoukh@gmail.com**

---

## 🛠 Tech Stack

### Frontend
![React](https://img.shields.io/badge/React.js-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)

### Styling & UI
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_v4-38BDF8?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Mantine](https://img.shields.io/badge/Mantine_UI-339AF0?style=for-the-badge&logo=mantine&logoColor=white)
![MUI](https://img.shields.io/badge/Material_UI-007FFF?style=for-the-badge&logo=mui&logoColor=white)
![CSS Modules](https://img.shields.io/badge/CSS_Modules-264DE4?style=for-the-badge&logo=css3&logoColor=white)

### State & Routing
![TanStack Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=for-the-badge&logo=reactquery&logoColor=white)
![TanStack Router](https://img.shields.io/badge/TanStack_Router-F59E0B?style=for-the-badge&logoColor=white)

### Backend & Database
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

### Architecture & Tooling
![Turborepo](https://img.shields.io/badge/Turborepo-EF4444?style=for-the-badge&logo=turborepo&logoColor=white)
![pnpm](https://img.shields.io/badge/pnpm-F69220?style=for-the-badge&logo=pnpm&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

---

## 🚀 Featured Projects

### ResuMax — SaaS Resume Builder
> Next.js 15 · Tailwind CSS v4 · Framer Motion · Bilingual AR/EN

Bilingual Arabic/English resume builder SaaS with 3D animations, Framer Motion transitions, and full dark/light mode support. Resolved Tailwind CSS v4 dynamic class compatibility using inline styles.

### GitHub Animated README
> SVG Animation · Canvas API · Markdown

Fully animated GitHub profile with starfield canvas background, skill bars, tech stack badges, and an experience timeline — all in pure Markdown and SVG.

### Analytics Dashboard
> React · TanStack Query · Recharts

Interactive data visualization dashboard with real-time charts, filterable tables, and a fully modular component architecture.

### Notification System (Kumrat Al-Saada)
> Angular · RxJS · Design Tokens

End-to-end notification architecture with Angular services, event-driven data binding, and a unified application-wide design token system.

---

## 🧠 Engineering Patterns

| Pattern | Description |
|---|---|
| 🧩 **Feature-Based Architecture** | Domain-isolated modules with views, hooks, APIs & services |
| 🏗 **Monorepo (Turborepo + pnpm)** | Shared Design System packages across multiple apps |
| 🔄 **Compound Components** | Implicit state sharing via Context for composable UI |
| 🧠 **Headless Components** | Logic-only hooks with consumer-controlled rendering |
| 🔌 **DIP + DTO Mapping** | TypeScript interfaces decoupling UI from API details |
| 🚩 **Feature Flags** | Context-based system for remote rollouts & A/B testing |

---

## 📊 GitHub Stats

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=hashem-mdoukh&show_icons=true&theme=tokyonight&hide_border=true)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=hashem-mdoukh&layout=compact&theme=tokyonight&hide_border=true)

</div>

---

## 📫 Connect With Me

[![Email](https://img.shields.io/badge/Email-mr.mdoukh@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:mr.mdoukh@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-hashem--mdoukh-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/hashem-mdoukh)
[![GitHub](https://img.shields.io/badge/GitHub-hashem--mdoukh-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/hashem-mdoukh)

---

<div align="center">

*Clean Code · Scalable Architecture · Exceptional User Experience*

✦ Open to remote & international opportunities ✦

</div>`;
  navigator.clipboard.writeText(t).then(()=>{const el=document.getElementById('toast');el.style.opacity='1';setTimeout(()=>el.style.opacity='0',2500)});
}
</script>
