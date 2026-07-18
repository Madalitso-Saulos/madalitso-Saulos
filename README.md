<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Madalitso Saulos · cyber portfolio</title>
  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz@14..32&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #0D1117;
      color: #e6edf3;
      font-family: 'Inter', sans-serif;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* scrollbar */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #0D1117; }
    ::-webkit-scrollbar-thumb { background: #00BFFF; border-radius: 10px; }

    /* glassmorphism cards */
    .glass {
      background: rgba(13, 17, 23, 0.55);
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
      border: 1px solid rgba(0, 191, 255, 0.15);
      border-radius: 24px;
      box-shadow: 0 12px 40px rgba(0, 0, 0, 0.6);
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 1rem 3rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 999;
      transition: background 0.3s, backdrop-filter 0.3s;
      background: transparent;
      font-family: 'JetBrains Mono', monospace;
    }
    nav.scrolled {
      background: rgba(13, 17, 23, 0.75);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border-bottom: 1px solid rgba(0, 191, 255, 0.2);
    }
    .nav-logo {
      font-weight: 600;
      color: #00BFFF;
      letter-spacing: 1px;
      font-size: 1.2rem;
    }
    .nav-logo i {
      margin-right: 8px;
      color: #3B82F6;
    }
    .nav-links a {
      color: #b0c7d9;
      margin-left: 2rem;
      text-decoration: none;
      font-size: 0.9rem;
      transition: 0.2s;
      border-bottom: 2px solid transparent;
      padding-bottom: 4px;
    }
    .nav-links a:hover {
      color: #00BFFF;
      border-bottom-color: #00BFFF;
    }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 6rem 4rem 4rem 4rem;
      position: relative;
      overflow: hidden;
    }
    .hero-content {
      max-width: 700px;
      z-index: 10;
      position: relative;
    }
    .hero h1 {
      font-size: 3.8rem;
      font-weight: 700;
      letter-spacing: -1px;
      background: linear-gradient(135deg, #f0f6fc 0%, #8ab4f8 80%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 0.25rem;
    }
    .hero-typing {
      font-family: 'JetBrains Mono', monospace;
      font-size: 1.3rem;
      color: #8ab4f8;
      min-height: 2.8rem;
      border-right: 2px solid #00BFFF;
      display: inline-block;
      padding-right: 6px;
      white-space: nowrap;
      overflow: hidden;
      animation: blink 0.8s step-end infinite alternate;
      margin: 0.5rem 0 0.8rem 0;
    }
    @keyframes blink {
      0% { border-color: #00BFFF; }
      50% { border-color: transparent; }
      100% { border-color: #00BFFF; }
    }
    .hero-desc {
      font-size: 1.2rem;
      color: #b0c7d9;
      max-width: 600px;
      margin: 0.8rem 0 2rem 0;
      line-height: 1.8;
      border-left: 3px solid #00BFFF;
      padding-left: 1.2rem;
    }
    .btn-group {
      display: flex;
      gap: 1.2rem;
      flex-wrap: wrap;
    }
    .btn {
      padding: 0.85rem 2.2rem;
      border-radius: 60px;
      font-weight: 600;
      font-size: 0.95rem;
      text-decoration: none;
      transition: 0.25s;
      border: 1px solid transparent;
      background: #161f2b;
      color: #e6edf3;
      box-shadow: 0 0 12px rgba(0, 191, 255, 0.1);
      display: inline-flex;
      align-items: center;
      gap: 10px;
      backdrop-filter: blur(4px);
    }
    .btn-primary {
      background: #0A84FF;
      color: #fff;
      border-color: #0A84FF;
      box-shadow: 0 0 20px rgba(0, 132, 255, 0.3);
    }
    .btn-primary:hover {
      background: #00BFFF;
      border-color: #00BFFF;
      transform: scale(1.02);
      box-shadow: 0 0 30px #00BFFF;
    }
    .btn-outline {
      border-color: #3B82F6;
      color: #b0c7d9;
    }
    .btn-outline:hover {
      background: #1a2a3a;
      border-color: #00BFFF;
      color: #fff;
      box-shadow: 0 0 24px #3B82F6;
    }

    /* stats cards */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 1.5rem;
      margin-top: 3rem;
      max-width: 700px;
    }
    .stat-item {
      background: rgba(22, 31, 43, 0.5);
      backdrop-filter: blur(4px);
      border: 1px solid rgba(0, 191, 255, 0.2);
      border-radius: 18px;
      padding: 1rem 0.6rem;
      text-align: center;
      transition: 0.2s;
    }
    .stat-item:hover {
      border-color: #00BFFF;
      box-shadow: 0 0 20px rgba(0, 191, 255, 0.2);
      transform: translateY(-4px);
    }
    .stat-number {
      font-size: 2rem;
      font-weight: 700;
      color: #00BFFF;
      font-family: 'JetBrains Mono', monospace;
    }
    .stat-label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: #8b9bb5;
    }

    /* floating icons */
    .tech-icons {
      display: flex;
      flex-wrap: wrap;
      gap: 0.9rem 1.5rem;
      margin-top: 2.2rem;
      max-width: 600px;
    }
    .tech-icons i, .tech-icons span {
      font-size: 1.8rem;
      color: #3B82F6;
      filter: drop-shadow(0 0 6px rgba(0, 191, 255, 0.3));
      animation: glowFloat 4s infinite alternate;
      transition: 0.2s;
      cursor: default;
    }
    .tech-icons i:hover {
      color: #00BFFF;
      transform: scale(1.2);
    }
    @keyframes glowFloat {
      0% { filter: drop-shadow(0 0 4px rgba(0, 191, 255, 0.2)); }
      100% { filter: drop-shadow(0 0 16px #00BFFF); }
    }

    /* fingerprint + network animation container */
    .hero-visual {
      position: absolute;
      right: 0;
      top: 0;
      width: 60%;
      height: 100%;
      pointer-events: none;
      z-index: 1;
      overflow: hidden;
    }
    canvas#fingerprintCanvas {
      position: absolute;
      right: -2%;
      top: 10%;
      width: 90%;
      height: 80%;
      opacity: 0.55;
    }

    /* floating code blur fragments */
    .code-float {
      position: absolute;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.9rem;
      color: #3B82F6;
      opacity: 0.13;
      filter: blur(1.2px);
      white-space: nowrap;
      pointer-events: none;
      z-index: 0;
      animation: drift 28s linear infinite;
      letter-spacing: 0.5px;
    }
    @keyframes drift {
      0% { transform: translate(0, 0) rotate(0deg); opacity: 0.08; }
      25% { opacity: 0.18; }
      50% { transform: translate(-30px, -20px) rotate(2deg); opacity: 0.12; }
      75% { opacity: 0.2; }
      100% { transform: translate(20px, 10px) rotate(-1deg); opacity: 0.08; }
    }

    /* footer */
    footer {
      padding: 2.5rem 4rem;
      border-top: 1px solid rgba(0, 191, 255, 0.15);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1.5rem;
      background: rgba(13, 17, 23, 0.8);
      backdrop-filter: blur(8px);
    }
    footer a {
      color: #8ab4f8;
      margin: 0 1rem 0 0;
      text-decoration: none;
      font-size: 1.2rem;
      transition: 0.2s;
    }
    footer a:hover { color: #00BFFF; text-shadow: 0 0 12px #00BFFF; }
    footer span { color: #4b5d73; font-size: 0.9rem; }

    /* responsive */
    @media (max-width: 1000px) {
      .hero { flex-direction: column; padding: 6rem 2rem 2rem; }
      .hero-visual { width: 100%; height: 50%; position: relative; right: auto; top: auto; margin-top: 1rem; }
      .hero-content { max-width: 100%; }
      .stats-grid { grid-template-columns: repeat(2,1fr); }
      .nav-links a { margin-left: 1.2rem; }
    }
    @media (max-width: 600px) {
      nav { padding: 0.8rem 1.2rem; flex-wrap: wrap; }
      .hero h1 { font-size: 2.8rem; }
      .hero-typing { font-size: 1rem; white-space: normal; }
      .btn-group { flex-direction: column; align-items: stretch; }
      .stats-grid { grid-template-columns: 1fr 1fr; gap: 0.8rem; }
    }

    /* matrix & scanning effect overlay */
    .matrix-bg {
      position: absolute;
      top: 0; left: 0; width: 100%; height: 100%;
      background: radial-gradient(circle at 30% 40%, rgba(0, 191, 255, 0.02) 0%, transparent 70%);
      pointer-events: none;
      z-index: 0;
    }
    .scan-line {
      position: absolute;
      top: 0; left: 0; width: 100%; height: 2px;
      background: linear-gradient(90deg, transparent, #00BFFF, transparent);
      opacity: 0.15;
      animation: scan 6s linear infinite;
      z-index: 0;
    }
    @keyframes scan {
      0% { top: -2px; opacity: 0.05; }
      50% { opacity: 0.25; }
      100% { top: 100%; opacity: 0.05; }
    }
  </style>
</head>
<body>
  <nav id="navbar">
    <div class="nav-logo"><i class="fas fa-shield-halved"></i> M.SAULOS</div>
    <div class="nav-links">
      <a href="#"><i class="fas fa-code"></i> Work</a>
      <a href="#"><i class="fas fa-network-wired"></i> Network</a>
      <a href="#"><i class="fas fa-lock"></i> Cyber</a>
    </div>
  </nav>

  <section class="hero" id="hero">
    <div class="matrix-bg"></div>
    <div class="scan-line"></div>

    <!-- floating code fragments -->
    <div class="code-float" style="top:12%; left:5%;">git clone · git push origin main</div>
    <div class="code-float" style="top:28%; left:70%;">ssh-keygen -t rsa · nmap -sV</div>
    <div class="code-float" style="bottom:18%; left:8%;">sudo apt update · python3 exploit.py</div>
    <div class="code-float" style="bottom:35%; right:5%;">SELECT * FROM users; · npm install</div>
    <div class="code-float" style="top:50%; left:45%;">docker build -t secure .</div>
    <div class="code-float" style="top:75%; left:25%;">git commit -m "patch" · iptables -L</div>

    <!-- main content -->
    <div class="hero-content">
      <h1>Madalitso Saulos</h1>
      <div class="hero-typing" id="typingText"></div>
      <div class="hero-desc">
        <i class="fas fa-shield" style="color:#00BFFF; margin-right:10px;"></i>
        Building secure, scalable, and innovative digital solutions through software engineering, networking, and cybersecurity.
      </div>
      <div class="btn-group">
        <a href="#" class="btn btn-primary"><i class="fas fa-rocket"></i> Explore Projects</a>
        <a href="#" class="btn btn-outline"><i class="fab fa-github"></i> View GitHub Profile</a>
      </div>

      <!-- stats -->
      <div class="stats-grid">
        <div class="stat-item"><div class="stat-number">24</div><div class="stat-label">Repositories</div></div>
        <div class="stat-item"><div class="stat-number">1.2k</div><div class="stat-label">Commits</div></div>
        <div class="stat-item"><div class="stat-number">14</div><div class="stat-label">Technologies</div></div>
        <div class="stat-item"><div class="stat-number">6</div><div class="stat-label">Certifications</div></div>
      </div>

      <!-- floating tech icons -->
      <div class="tech-icons">
        <i class="fab fa-git-alt"></i><i class="fab fa-github"></i><i class="fab fa-linux"></i><i class="fab fa-python"></i>
        <i class="fab fa-js"></i><i class="fab fa-html5"></i><i class="fab fa-css3-alt"></i><i class="fab fa-js"></i>
        <i class="fab fa-docker"></i><i class="fas fa-database"></i><i class="fas fa-network-wired"></i><i class="fas fa-terminal"></i>
        <i class="fas fa-code"></i><i class="fas fa-wifi"></i>
        <span style="font-size:1.6rem; color:#3B82F6;">⚡</span>
      </div>
    </div>

    <!-- fingerprint + network canvas -->
    <div class="hero-visual">
      <canvas id="fingerprintCanvas"></canvas>
    </div>
  </section>

  <footer>
    <div>
      <a href="#"><i class="fab fa-github"></i></a>
      <a href="#"><i class="fab fa-linkedin"></i></a>
      <a href="#"><i class="fas fa-envelope"></i></a>
      <a href="#"><i class="fas fa-globe"></i></a>
    </div>
    <span>© 2026 Madalitso Saulos · secure · scalable · innovative</span>
  </footer>

  <script>
    // navbar scroll blur
    window.addEventListener('scroll', () => {
      const nav = document.getElementById('navbar');
      if (window.scrollY > 40) nav.classList.add('scrolled');
      else nav.classList.remove('scrolled');
    });

    // typing animation
    const roles = [
      'Software Developer',
      'Network Engineer',
      'Cybersecurity Student',
      'Open Source Contributor',
      'Problem Solver'
    ];
    let idx = 0, charIdx = 0, isDeleting = false;
    const el = document.getElementById('typingText');
    function typeEffect() {
      const current = roles[idx];
      if (!isDeleting) {
        el.textContent = current.substring(0, charIdx+1);
        charIdx++;
        if (charIdx === current.length) {
          isDeleting = true;
          setTimeout(typeEffect, 1800);
          return;
        }
        setTimeout(typeEffect, 110);
      } else {
        el.textContent = current.substring(0, charIdx-1);
        charIdx--;
        if (charIdx === 0) {
          isDeleting = false;
          idx = (idx+1) % roles.length;
          setTimeout(typeEffect, 400);
          return;
        }
        setTimeout(typeEffect, 60);
      }
    }
    typeEffect();

    // Fingerprint + network nodes animation (canvas)
    const canvas = document.getElementById('fingerprintCanvas');
    const ctx = canvas.getContext('2d');
    let w, h;
    function resize() {
      const rect = canvas.parentElement.getBoundingClientRect();
      w = canvas.width = rect.width * 0.9;
      h = canvas.height = rect.height * 0.8;
    }
    resize();
    window.addEventListener('resize', resize);

    // nodes & packets
    const nodes = [];
    const numNodes = 28;
    for (let i=0; i<numNodes; i++) {
      nodes.push({
        x: Math.random() * w,
        y: Math.random() * h,
        r: 2 + Math.random() * 4,
        vx: (Math.random()-0.5)*0.4,
        vy: (Math.random()-0.5)*0.4,
      });
    }

    // fingerprint path (abstract)
    function drawFingerprint(t) {
      ctx.save();
      ctx.shadowColor = '#00BFFF';
      ctx.shadowBlur = 20;
      ctx.strokeStyle = '#00BFFF';
      ctx.lineWidth = 1.8;
      const cx = w*0.5, cy = h*0.5;
      for (let i=0; i<40; i++) {
        const angle = i * 0.25 + t * 0.008;
        const rad = 60 + 30 * Math.sin(i*0.3 + t*0.01);
        const x = cx + rad * Math.cos(angle + 0.6);
        const y = cy + rad * Math.sin(angle * 0.8 + 0.2);
        ctx.beginPath();
        ctx.arc(x, y, 2 + 1.2*Math.sin(i*0.5 + t*0.02), 0, Math.PI*2);
        ctx.fillStyle = '#3B82F6';
        ctx.shadowBlur = 28;
        ctx.fill();
        // connecting lines
        if (i>0) {
          const px = cx + (60 + 30 * Math.sin((i-1)*0.3 + t*0.01)) * Math.cos((i-1)*0.25 + t*0.008 + 0.6);
          const py = cy + (60 + 30 * Math.sin((i-1)*0.3 + t*0.01)) * Math.sin((i-1)*0.25 *0.8 + 0.2);
          ctx.beginPath();
          ctx.moveTo(px, py);
          ctx.lineTo(x, y);
          ctx.strokeStyle = `rgba(0, 191, 255, ${0.15+0.1*Math.sin(i+t*0.02)})`;
          ctx.lineWidth = 0.6;
          ctx.shadowBlur = 10;
          ctx.stroke();
        }
      }
      ctx.restore();
    }

    // network lines and packets
    let packets = [];
    for (let i=0; i<12; i++) {
      const a = Math.floor(Math.random()*numNodes);
      let b = Math.floor(Math.random()*numNodes);
      while (b===a) b = (b+1)%numNodes;
      packets.push({
        from: a,
        to: b,
        progress: Math.random(),
        speed: 0.002 + Math.random()*0.003,
      });
    }

    function animate() {
      ctx.clearRect(0, 0, w, h);
      const t = Date.now();

      // draw network lines
      ctx.save();
      ctx.shadowBlur = 16;
      ctx.shadowColor = '#3B82F6';
      nodes.forEach((n, i) => {
        // moving nodes
        n.x += n.vx;
        n.y += n.vy;
        if (n.x<0 || n.x>w) n.vx *= -1;
        if (n.y<0 || n.y>h) n.vy *= -1;
        // draw node
        ctx.beginPath();
        ctx.arc(n.x, n.y, n.r, 0, Math.PI*2);
        ctx.fillStyle = '#3B82F6';
        ctx.shadowBlur = 28;
        ctx.fill();
      });

      // draw connections with packets
      ctx.shadowBlur = 10;
      packets.forEach(p => {
        const from = nodes[p.from];
        const to = nodes[p.to];
        if (!from || !to) return;
        const dx = to.x - from.x, dy = to.y - from.y;
        const px = from.x + dx * p.progress;
        const py = from.y + dy * p.progress;
        // line
        ctx.beginPath();
        ctx.moveTo(from.x, from.y);
        ctx.lineTo(to.x, to.y);
        ctx.strokeStyle = 'rgba(0, 191, 255, 0.12)';
        ctx.lineWidth = 1;
        ctx.shadowBlur = 4;
        ctx.stroke();
        // packet
        ctx.beginPath();
        ctx.arc(px, py, 3.5, 0, Math.PI*2);
        ctx.fillStyle = '#00BFFF';
        ctx.shadowBlur = 30;
        ctx.fill();
        // small glow
        ctx.beginPath();
        ctx.arc(px, py, 8, 0, Math.PI*2);
        ctx.fillStyle = 'rgba(0, 191, 255, 0.08)';
        ctx.fill();

        p.progress += p.speed;
        if (p.progress > 1) {
          p.progress = 0;
          p.from = Math.floor(Math.random()*numNodes);
          p.to = Math.floor(Math.random()*numNodes);
          while (p.to === p.from) p.to = (p.to+1)%numNodes;
        }
      });
      ctx.restore();

      // fingerprint overlay
      drawFingerprint(t);

      // pulse wave
      ctx.save();
      const pulse = 0.5 + 0.5 * Math.sin(t * 0.002);
      ctx.beginPath();
      ctx.arc(w*0.5, h*0.5, 70 + 20*pulse, 0, Math.PI*2);
      ctx.strokeStyle = `rgba(0, 191, 255, ${0.08+0.04*pulse})`;
      ctx.lineWidth = 1.5;
      ctx.shadowBlur = 40;
      ctx.shadowColor = '#00BFFF';
      ctx.stroke();
      ctx.restore();

      requestAnimationFrame(animate);
    }
    animate();
  </script>
</body>
</html>
