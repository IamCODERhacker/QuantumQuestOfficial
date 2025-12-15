# QuantumQuestOfficial
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>QuantumQuest 2026</title>
  <link rel="preconnect" href="https://fonts.gstatic.com" />
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Inter:wght@300;600&display=swap" rel="stylesheet" />
  <style>
    :root{
      --bg1:#0a0f1f;
      --bg2:#0d0221;
      --neon:#69f0ff;
      --accent:#ff2df2;
      --text:#e8f6ff;
      --muted:#98a4b3;
      --card:#0f1429;
      --glow:0 0 12px rgba(105,240,255,0.6), 0 0 32px rgba(255,45,242,0.35);
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      color:var(--text);
      background:
        radial-gradient(1200px 600px at 80% -20%, rgba(255,45,242,0.2), transparent 60%),
        radial-gradient(900px 500px at -10% 120%, rgba(105,240,255,0.12), transparent 60%),
        linear-gradient(135deg, var(--bg1), var(--bg2));
      font-family:'Inter', system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif;
      overflow-x:hidden;
    }

    /* Subtle animated scanline + noise overlay */
    .noise{
      position:fixed; inset:0; pointer-events:none; mix-blend-mode:overlay; opacity:0.06;
      background-image:
        repeating-linear-gradient(0deg, rgba(255,255,255,0.07) 0 2px, transparent 2px 4px);
      animation: flicker 5s infinite alternate ease-in-out;
    }
    @keyframes flicker {
      0%{opacity:0.03} 100%{opacity:0.09}
    }

    header{
      position:relative;
      padding:80px 24px 32px;
      text-align:center;
    }
    .brand{
      display:inline-block;
      padding:10px 18px;
      border:1px solid rgba(105,240,255,0.35);
      background:linear-gradient(to right, rgba(105,240,255,0.08), rgba(255,45,242,0.08));
      backdrop-filter: blur(6px);
      border-radius:14px;
      letter-spacing:2px;
      color:var(--neon);
      text-shadow: var(--glow);
      font-family:'Orbitron', sans-serif;
      font-weight:700;
      font-size:14px;
    }
    h1{
      margin:18px auto 10px;
      font-family:'Orbitron', sans-serif;
      font-size: clamp(34px, 6vw, 72px);
      line-height:1.05;
      position:relative;
      display:inline-block;
    }
    /* Glitch effect */
    h1::before, h1::after{
      content:attr(data-text);
      position:absolute; left:0; top:0;
      clip-path: inset(0 0 0 0);
      opacity:0.8;
    }
    h1::before{
      color:var(--accent);
      transform: translate(-2px, -1px);
      animation: glitch1 2.2s infinite steps(1, end);
      mix-blend-mode:screen;
    }
    h1::after{
      color:var(--neon);
      transform: translate(2px, 1px);
      animation: glitch2 2.2s infinite steps(1, end);
      mix-blend-mode:screen;
    }
    @keyframes glitch1 {
      0%{clip-path: inset(0 0 0 0)}
      10%{clip-path: inset(15% 0 60% 0)}
      20%{clip-path: inset(40% 0 30% 0)}
      30%{clip-path: inset(65% 0 10% 0)}
      35%{clip-path: inset(0 0 0 0)}
      100%{clip-path: inset(0 0 0 0)}
    }
    @keyframes glitch2 {
      0%{clip-path: inset(0 0 0 0)}
      15%{clip-path: inset(5% 0 70% 0)}
      25%{clip-path: inset(50% 0 25% 0)}
      45%{clip-path: inset(70% 0 5% 0)}
      50%{clip-path: inset(0 0 0 0)}
      100%{clip-path: inset(0 0 0 0)}
    }

    .subtitle{
      margin:8px auto 24px;
      max-width:800px;
      color:var(--muted);
      font-size:clamp(14px, 2.5vw, 18px);
    }

    .cta{
      display:flex;
      gap:12px;
      justify-content:center;
      flex-wrap:wrap;
      margin-top:10px;
    }
    .btn{
      position:relative;
      border:none; cursor:pointer;
      padding:16px 28px;
      border-radius:12px;
      color:#041017;
      background:linear-gradient(135deg, #69f0ff 0%, #a0ffe1 100%);
      font-weight:700;
      letter-spacing:.6px;
      font-size:16px;
      text-decoration:none;
      display:inline-block;
      transition: transform .2s ease, box-shadow .2s ease;
      box-shadow: 0 4px 15px rgba(105,240,255,0.3);
    }
    .btn.secondary{
      color:var(--text);
      background:linear-gradient(135deg, #1b2342 0%, #2b3463 100%);
      border:1px solid rgba(105,240,255,0.25);
    }
    .btn:hover{ 
      transform: translateY(-2px) scale(1.02); 
      box-shadow: var(--glow); 
    }

    /* Countdown card */
    .countdown{
      margin:40px auto 24px;
      max-width:980px;
      display:grid;
      grid-template-columns: repeat(4, 1fr);
      gap:14px;
      padding:20px;
      background:linear-gradient(180deg, rgba(13,2,33,0.6), rgba(10,15,31,0.7));
      border:1px solid rgba(105,240,255,0.25);
      border-radius:16px;
      box-shadow: 0 20px 60px rgba(0,0,0,0.35);
      backdrop-filter: blur(6px);
    }
    .timebox{
      text-align:center;
      padding:16px 10px;
      background:radial-gradient(120% 120% at 50% 30%, rgba(105,240,255,0.08), rgba(255,45,242,0.05));
      border:1px dashed rgba(105,240,255,0.28);
      border-radius:14px;
    }
    .label{
      font-size:12px;
      text-transform:uppercase;
      letter-spacing:1.8px;
      color:var(--muted);
      margin-bottom:8px;
    }
    .value{
      font-family:'Orbitron', sans-serif;
      font-weight:700;
      font-size: clamp(26px, 5vw, 44px);
      color:var(--neon);
      text-shadow: var(--glow);
    }

    /* Sections */
    section{
      max-width:1100px;
      margin:32px auto;
      padding:0 24px;
    }
    .card{
      margin:18px 0;
      padding:22px;
      background:linear-gradient(180deg, rgba(15,20,41,0.7), rgba(20,26,52,0.6));
      border:1px solid rgba(105,240,255,0.18);
      border-radius:16px;
    }
    .card h3{
      margin:0 0 10px;
      font-family:'Orbitron', sans-serif;
      font-size:22px;
      color:#bdf9ff;
      letter-spacing:.5px;
    }
    .card p{ color:var(--muted); }

    /* Footer */
    footer{
      margin:48px auto 24px;
      max-width:1100px;
      padding:0 24px 24px;
      color:var(--muted);
      text-align:center;
    }

    /* Responsive */
    @media (max-width:700px){
      .countdown{ grid-template-columns: repeat(2, 1fr); }
      header{ padding:64px 18px 24px; }
    }
  </style>
</head>
<body>
  <div class="noise" aria-hidden="true"></div>

  <header>
    <span class="brand">QUANTUMQUEST • 2026</span>
    <h1 data-text="QuantumQuest">QuantumQuest</h1>
    <p class="subtitle">
      Bengaluru's glitch-bright hackathon orbit—where ideas bend reality. Build, experiment, and ship with radical inclusion.
    </p>
    
    <!-- Updated CTA Buttons with Google Form Link -->
    <div class="cta">
      <a href="https://docs.google.com/forms/d/e/1FAIpQLSfyvHvmJRmu0ivQvWIrY166_UW3nthZmatUWByZjWQW0CFPfg/viewform?usp=dialog" 
         target="_blank" class="btn">Register Now</a>
      <a href="#about" class="btn secondary">Learn More</a>
    </div>

    <!-- Countdown - Updated to Feb 14, 2026 -->
    <div class="countdown" role="group" aria-label="Countdown to QuantumQuest">
      <div class="timebox">
        <div class="label">Days</div>
        <div class="value" id="dd">00</div>
      </div>
      <div class="timebox">
        <div class="label">Hours</div>
        <div class="value" id="hh">00</div>
      </div>
      <div class="timebox">
        <div class="label">Minutes</div>
        <div class="value" id="mm">00</div>
      </div>
      <div class="timebox">
        <div class="label">Seconds</div>
        <div class="value" id="ss">00</div>
      </div>
    </div>
  </header>

  <section id="about">
    <div class="card">
      <h3>Theme</h3>
      <p>
        Quantum frontiers, glitch aesthetics, and playful invention. Expect interactive challenges, browser-first builds, and hardware experiments.
      </p>
      <div style="margin-top: 20px;">
        <a href="https://docs.google.com/forms/d/e/1FAIpQLSfyvHvmJRmu0ivQvWIrY166_UW3nthZmatUWByZjWQW0CFPfg/viewform?usp=dialog" 
           target="_blank" class="btn" style="font-size: 14px; padding: 12px 24px;">Join the Quest</a>
      </div>
    </div>
    
    <div class="card">
      <h3>Who should join</h3>
      <p>
        Designers, builders, beginners, pros—everyone. Radical inclusion is the rule. Team up or solo, learn fast, ship bold.
      </p>
    </div>
    
    <div class="card">
      <h3>What to expect</h3>
      <p>
        Live progress moments, neon ambience, rapid prototyping, and spectacle. Bring curiosity; leave with momentum.
      </p>
    </div>
  </section>

  <footer>
    © 2026 QuantumQuest • Bengaluru, India • <a href="mailto:team@quantumquest.dev" style="color: var(--neon);">team@quantumquest.dev</a>
  </footer>

  <script>
    // Updated to February 14, 2026 9:00 AM IST (your hackathon date)
    const eventTimeIST = new Date('2026-02-14T09:00:00+05:30').getTime();

    const dd = document.getElementById('dd');
    const hh = document.getElementById('hh');
    const mm = document.getElementById('mm');
    const ss = document.getElementById('ss');

    function pad(n){ return n.toString().padStart(2,'0'); }

    function tick(){
      const now = Date.now();
      let diff = eventTimeIST - now;

      if (diff <= 0){
        dd.textContent = '00';
        hh.textContent = '00';
        mm.textContent = '00';
        ss.textContent = '00';
        document.title = 'QuantumQuest is live!';
        return;
      }

      const days = Math.floor(diff / (1000*60*60*24));
      diff -= days * (1000*60*60*24);
      const hours = Math.floor(diff / (1000*60*60));
      diff -= hours * (1000*60*60);
      const minutes = Math.floor(diff / (1000*60));
      diff -= minutes * (1000*60);
      const seconds = Math.floor(diff / 1000);

      dd.textContent = pad(days);
      hh.textContent = pad(hours);
      mm.textContent = pad(minutes);
      ss.textContent = pad(seconds);
    }

    tick();
    setInterval(tick, 1000);
  </script>
</body>
</html>
