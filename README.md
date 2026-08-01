<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Kierby Antonio M. — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;600;700;800&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#071019;
    --accent-1:#22d3ee;
    --accent-2:#6366f1;
    --text-main:#ffffff;
    --text-muted:#9fb3c8;
    --card:rgba(255,255,255,0.05);
    --border:rgba(255,255,255,0.10);
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    font-family:'Inter',sans-serif;
    background:var(--bg);
    color:var(--text-main);
    overflow-x:hidden;
  }
  h1,h2,h3,.logo,.nav a,.btn{font-family:'Poppins',sans-serif;}

  #bg-canvas{
    position:fixed;
    top:0;left:0;
    width:100%;height:100%;
    z-index:0;
  }
  header, section, footer{position:relative;z-index:1;}

  header{
    display:flex;align-items:center;justify-content:space-between;
    padding:24px 50px;
    position:sticky;top:0;z-index:50;
    backdrop-filter:blur(12px);
    background:rgba(7,16,25,0.6);
    border-bottom:1px solid var(--border);
  }
  .logo{font-size:22px;font-weight:800;}
  .logo span{color:var(--accent-1);}
  .nav{display:flex;gap:32px;}
  .nav a{color:#fff;text-decoration:none;font-weight:600;font-size:15px;transition:.2s;}
  .nav a:hover{color:var(--accent-1);}
  .menu-toggle{display:none;flex-direction:column;gap:5px;cursor:pointer;}
  .menu-toggle span{width:24px;height:3px;background:#fff;border-radius:3px;}

  .hero{
    min-height:85vh;
    display:flex;flex-direction:column;justify-content:center;
    padding:0 50px;max-width:900px;
  }
  .profile-pic{
    width:120px;height:120px;
    border-radius:50%;
    object-fit:cover;
    border:3px solid var(--accent-1);
    box-shadow:0 0 30px rgba(34,211,238,0.35);
    margin-bottom:22px;
  }
  .eyebrow{
    color:var(--accent-1);font-weight:600;font-size:13px;
    letter-spacing:2px;text-transform:uppercase;margin-bottom:16px;
  }
  .hero h1{font-size:56px;font-weight:800;line-height:1.1;margin-bottom:12px;}
  .hero h2{font-size:24px;font-weight:600;color:var(--text-muted);margin-bottom:20px;}
  .hero p{font-size:17px;color:var(--text-muted);max-width:560px;margin-bottom:34px;}
  .btn-row{display:flex;gap:14px;flex-wrap:wrap;}
  .btn{
    padding:14px 28px;border-radius:10px;
    background:linear-gradient(90deg,var(--accent-2),var(--accent-1));
    color:#fff;text-decoration:none;font-weight:700;font-size:14.5px;
    border:none;cursor:pointer;transition:.25s;
  }
  .btn:hover{opacity:0.85;transform:translateY(-2px);}
  .btn.ghost{background:transparent;border:1.5px solid var(--border);}
  .btn.ghost:hover{border-color:var(--accent-1);}

  section{padding:90px 50px;}
  .section-head{margin-bottom:44px;max-width:600px;}
  .section-head h2{font-size:32px;font-weight:800;margin-bottom:8px;}
  .section-head p{color:var(--text-muted);font-size:15px;}

  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:40px;}
  .card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:30px;}
  .card h3{font-size:18px;margin-bottom:16px;color:var(--accent-1);}
  .card p{color:var(--text-muted);line-height:1.7;font-size:15px;margin-bottom:12px;}
  .info-row{display:flex;justify-content:space-between;padding:9px 0;border-bottom:1px solid var(--border);font-size:14px;}
  .info-row span:first-child{color:var(--text-muted);}
  .info-row span:last-child{font-weight:600;}
  .pills{display:flex;flex-wrap:wrap;gap:8px;margin-top:6px;}
  .pill{padding:8px 16px;border-radius:20px;background:rgba(34,211,238,0.1);border:1px solid rgba(34,211,238,0.3);font-size:13px;font-weight:600;}

  .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:22px;}
  .item{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:26px;transition:.25s;}
  .item:hover{transform:translateY(-5px);border-color:var(--accent-1);}
  .item h3{font-size:17px;margin-bottom:8px;}
  .item p{color:var(--text-muted);font-size:14px;line-height:1.6;margin-bottom:14px;}
  .item a{
    display:inline-block;padding:8px 18px;border-radius:8px;
    background:linear-gradient(90deg,var(--accent-2),var(--accent-1));
    color:#fff;text-decoration:none;font-weight:700;font-size:13px;
  }
  .icon{font-size:24px;margin-bottom:12px;display:block;}

  .contact-box{
    background:var(--card);border:1px solid var(--border);border-radius:16px;
    padding:44px;display:flex;flex-wrap:wrap;justify-content:space-between;gap:30px;align-items:center;
  }
  .contact-box h2{font-size:26px;margin-bottom:8px;}
  .contact-box p{color:var(--text-muted);}
  .social-row{display:flex;gap:12px;flex-wrap:wrap;}
  .social-row a{
    padding:10px 20px;border-radius:8px;border:1.5px solid var(--border);
    color:#fff;text-decoration:none;font-weight:600;font-size:13.5px;transition:.2s;
  }
  .social-row a:hover{border-color:var(--accent-1);background:rgba(34,211,238,0.08);}

  footer{padding:28px 50px;text-align:center;color:var(--text-muted);font-size:13px;border-top:1px solid var(--border);}

  @media(max-width:900px){.about-grid{grid-template-columns:1fr;}}
  @media(max-width:768px){
    header{padding:20px 24px;}
    .nav{
      position:fixed;top:72px;left:0;right:0;flex-direction:column;
      background:rgba(7,16,25,0.98);padding:24px;gap:18px;display:none;
      border-bottom:1px solid var(--border);
    }
    .nav.open{display:flex;}
    .menu-toggle{display:flex;}
    .hero{padding:0 24px;}
    .hero h1{font-size:38px;}
    section{padding:60px 24px;}
    .contact-box{padding:28px;}
  }
</style>
</head>
<body>

<canvas id="bg-canvas"></canvas>

<header>
  <div class="logo">Kierby<span>.</span></div>
  <nav class="nav" id="nav">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#achievements">Achievements</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
  <div class="menu-toggle" id="menuToggle"><span></span><span></span><span></span></div>
</header>

<section class="hero" id="home">
  <img src="profile.jpg" alt="Kierby Antonio M." class="profile-pic">
  <span class="eyebrow">Portfolio</span>
  <h1>Hi, I'm Kierby Antonio M.</h1>
  <h2>2nd Year BS Information Technology Student</h2>
  <p>Building projects and activities one line of code at a time.</p>
  <div class="btn-row">
    <a href="#projects" class="btn">View Projects</a>
    <a href="#contact" class="btn ghost">Contact Me</a>
  </div>
</section>

<section id="about">
  <div class="section-head">
    <h2>About Me</h2>
    <p>A quick look at who I am and what I'm learning.</p>
  </div>
  <div class="about-grid">
    <div class="card">
      <h3>Quick Info</h3>
      <div class="info-row"><span>Name</span><span>Kierby Antonio M.</span></div>
      <div class="info-row"><span>Course</span><span>BS Information Technology</span></div>
      <div class="info-row"><span>Year Level</span><span>2nd Year</span></div>
      <div class="info-row"><span>Focus</span><span>Web Development</span></div>
    </div>
    <div class="card">
      <h3>My Story</h3>
      <p>[Edit me] A short paragraph about yourself — how you got into IT, what you enjoy building, and what you're currently learning.</p>
      <div class="pills">
        <span class="pill">HTML</span>
        <span class="pill">CSS</span>
        <span class="pill">JavaScript</span>
        <span class="pill">Git & GitHub</span>
      </div>
    </div>
  </div>
</section>

<section id="achievements">
  <div class="section-head">
    <h2>Achievements</h2>
    <p>Edit these with your real recognitions and milestones.</p>
  </div>
  <div class="grid">
    <div class="item">
      <span class="icon">🎓</span>
      <h3>Generative AI for Everyone</h3>
      <p>Course certificate by DeepLearning.AI, offered through Coursera. Completed Feb 11, 2026.</p>
      <a href="https://coursera.org/verify/JK0I1PTR6QBK" target="_blank">Verify Certificate →</a>
    </div>
    <div class="item">
      <span class="icon">☁️</span>
      <h3>Introduction to Generative AI</h3>
      <p>Course certificate by Google Cloud, offered through Coursera. Completed Feb 11, 2026.</p>
      <a href="https://coursera.org/verify/XCMVIV73SSEA" target="_blank">Verify Certificate →</a>
    </div>
  </div>
</section>

<section id="projects">
  <div class="section-head">
    <h2>Projects & Activities</h2>
    <p>Linked to their folders in this repo.</p>
  </div>
  <div class="grid">
    <div class="item">
      <span class="icon">👗</span>
      <h3>Fashion Blog</h3>
      <p>Activity 1.1 — A styled fashion blog page, "An Insider's Guide to NYFW," built with HTML and CSS.</p>
      <a href="./Activity1.1/Fashion/">Open →</a>
    </div>
    <div class="item">
      <span class="icon">🍷</span>
      <h3>Wine Festival Schedule</h3>
      <p>Activity 1.2 — A clean event schedule table listing wine festival activities by time.</p>
      <a href="./Activity 1.2/Wine Festival Schedule/index.html">Open →</a>
    </div>
    <div class="item">
      <span class="icon">🍔</span>
      <h3>Davie's Burgers</h3>
      <p>Activity 2.1 — A restaurant landing page for a burger brand, with menu nav and nutrition facts.</p>
      <a href="./Activity2.1/Burger/index.html">Open →</a>
    </div>
  </div>
</section>

<section id="contact">
  <div class="section-head">
    <h2>Contact</h2>
  </div>
  <div class="contact-box">
    <div>
      <h2>Let's connect</h2>
      <p>[Edit me] Reach out for collaborations or just to say hi.</p>
    </div>
    <div class="social-row">
      <a href="https://github.com/kantonio250000000109-code" target="_blank">GitHub</a>
      <a href="mailto:youremail@example.com">Email</a>
      <a href="#">LinkedIn</a>
    </div>
  </div>
</section>

<footer>© <span id="year"></span> Kierby Antonio M.</footer>

<script>
document.getElementById('year').textContent = new Date().getFullYear();

const nav = document.getElementById('nav');
document.getElementById('menuToggle').addEventListener('click', () => nav.classList.toggle('open'));
nav.querySelectorAll('a').forEach(a => a.addEventListener('click', () => nav.classList.remove('open')));

const canvas = document.getElementById('bg-canvas');
const ctx = canvas.getContext('2d');
let w, h, particles;

function resize(){
  w = canvas.width = window.innerWidth;
  h = canvas.height = window.innerHeight;
}
window.addEventListener('resize', resize);
resize();

function initParticles(){
  const count = Math.floor((w * h) / 14000);
  particles = Array.from({length: count}, () => ({
    x: Math.random() * w,
    y: Math.random() * h,
    vx: (Math.random() - 0.5) * 0.4,
    vy: (Math.random() - 0.5) * 0.4,
    r: Math.random() * 1.6 + 0.6
  }));
}
initParticles();
window.addEventListener('resize', initParticles);

function animate(){
  ctx.clearRect(0, 0, w, h);

  const grad = ctx.createRadialGradient(w*0.5, h*0.4, 0, w*0.5, h*0.4, Math.max(w,h)*0.7);
  grad.addColorStop(0, 'rgba(34,211,238,0.05)');
  grad.addColorStop(1, 'rgba(7,16,25,0)');
  ctx.fillStyle = grad;
  ctx.fillRect(0, 0, w, h);

  for (let p of particles){
    p.x += p.vx;
    p.y += p.vy;
    if (p.x < 0 || p.x > w) p.vx *= -1;
    if (p.y < 0 || p.y > h) p.vy *= -1;

    ctx.beginPath();
    ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
    ctx.fillStyle = 'rgba(159,179,200,0.6)';
    ctx.fill();
  }

  for (let i=0; i<particles.length; i++){
    for (let j=i+1; j<particles.length; j++){
      const a = particles[i], b = particles[j];
      const dx = a.x-b.x, dy = a.y-b.y;
      const dist = Math.sqrt(dx*dx+dy*dy);
      if (dist < 120){
        ctx.beginPath();
        ctx.moveTo(a.x, a.y);
        ctx.lineTo(b.x, b.y);
        ctx.strokeStyle = `rgba(34,211,238,${0.15 * (1 - dist/120)})`;
        ctx.lineWidth = 1;
        ctx.stroke();
      }
    }
  }

  requestAnimationFrame(animate);
}
animate();
</script>

</body>
</html>
