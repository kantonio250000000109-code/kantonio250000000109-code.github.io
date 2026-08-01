<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Joshua Cister — Juswa.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg-1:#2a1854;
    --bg-2:#3b2170;
    --bg-3:#241249;
    --accent-1:#ec4899;
    --accent-2:#a855f7;
    --text-main:#ffffff;
    --text-muted:#c9b8e8;
    --card-bg:rgba(255,255,255,0.05);
    --card-border:rgba(255,255,255,0.10);
    --radius-lg:28px;
    --radius-pill:999px;
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  html{scroll-behavior:smooth;}

  body{
    font-family:'Inter',sans-serif;
    background:linear-gradient(160deg,var(--bg-2) 0%,var(--bg-1) 55%,var(--bg-3) 100%);
    color:var(--text-main);
    overflow-x:hidden;
    position:relative;
    min-height:100vh;
  }

  h1,h2,h3,.logo,.nav a,.btn,.eyebrow{
    font-family:'Baloo 2',sans-serif;
  }

  .blob{
    position:fixed;
    border-radius:50%;
    filter:blur(110px);
    opacity:0.35;
    z-index:0;
    pointer-events:none;
  }
  .blob-1{width:480px;height:480px;background:var(--accent-2);top:-140px;right:-120px;}
  .blob-2{width:420px;height:420px;background:var(--accent-1);bottom:10%;left:-160px;}
  .blob-3{width:360px;height:360px;background:#6d28d9;top:50%;right:10%;opacity:0.2;}

  header, section, footer{position:relative;z-index:1;}

  header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:28px 60px;
    position:sticky;
    top:0;
    z-index:50;
    backdrop-filter:blur(14px);
    background:rgba(42,24,84,0.55);
    border-bottom:1px solid rgba(255,255,255,0.06);
  }
  .logo{font-size:24px;font-weight:800;letter-spacing:0.5px;}
  .nav{display:flex;gap:36px;}
  .nav a{
    color:var(--text-main);
    text-decoration:none;
    font-weight:600;
    font-size:16px;
    position:relative;
    padding-bottom:4px;
    transition:color .25s ease;
  }
  .nav a::after{
    content:"";
    position:absolute;
    left:0;bottom:0;
    width:0%;height:2px;
    background:linear-gradient(90deg,var(--accent-1),var(--accent-2));
    transition:width .25s ease;
  }
  .nav a:hover{color:#f0a8e8;}
  .nav a:hover::after{width:100%;}
  .nav a.active{background:linear-gradient(90deg,var(--accent-1),var(--accent-2));-webkit-background-clip:text;background-clip:text;color:transparent;}

  .menu-toggle{display:none;flex-direction:column;gap:5px;cursor:pointer;}
  .menu-toggle span{width:26px;height:3px;background:#fff;border-radius:3px;}

  .hero{
    min-height:88vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    padding:0 60px;
    max-width:1000px;
  }
  .eyebrow{
    display:inline-block;
    font-weight:600;
    font-size:14px;
    letter-spacing:1.5px;
    text-transform:uppercase;
    color:var(--text-muted);
    margin-bottom:18px;
    opacity:0;
    animation:riseIn .7s ease forwards;
  }
  .hero h1{
    font-size:64px;
    font-weight:800;
    line-height:1.08;
    margin-bottom:14px;
    opacity:0;
    animation:riseIn .7s ease .1s forwards;
  }
  .hero h2{
    font-size:30px;
    font-weight:700;
    background:linear-gradient(90deg,#f2b6ea,var(--accent-1) 55%,var(--accent-2));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
    margin-bottom:20px;
    opacity:0;
    animation:riseIn .7s ease .2s forwards;
  }
  .hero p{
    font-size:18px;
    color:var(--text-muted);
    max-width:640px;
    margin-bottom:40px;
    opacity:0;
    animation:riseIn .7s ease .3s forwards;
  }
  @keyframes riseIn{
    from{opacity:0;transform:translateY(18px);}
    to{opacity:1;transform:translateY(0);}
  }

  .btn-row{display:flex;flex-wrap:wrap;gap:16px;opacity:0;animation:riseIn .7s ease .4s forwards;}
  .btn{
    padding:16px 30px;
    border-radius:var(--radius-pill);
    background:linear-gradient(120deg,var(--accent-1),var(--accent-2));
    color:#fff;
    text-decoration:none;
    font-weight:700;
    font-size:15px;
    box-shadow:0 0 0 rgba(236,72,153,0);
    transition:box-shadow .3s ease, transform .25s ease;
    display:inline-block;
    border:none;
    cursor:pointer;
  }
  .btn:hover{
    box-shadow:0 0 26px rgba(236,72,153,0.55);
    transform:translateY(-3px);
  }
  .btn.ghost{
    background:transparent;
    border:1.5px solid rgba(255,255,255,0.25);
  }
  .btn.ghost:hover{border-color:var(--accent-1);box-shadow:0 0 20px rgba(168,85,247,0.35);}

  section{padding:110px 60px;}
  .section-head{max-width:640px;margin-bottom:56px;}
  .section-head .eyebrow{margin-bottom:12px;}
  .section-head h2{font-size:38px;font-weight:800;}
  .section-head p{color:var(--text-muted);font-size:16px;margin-top:14px;}

  .reveal{opacity:0;transform:translateY(30px);transition:opacity .7s ease, transform .7s ease;}
  .reveal.in{opacity:1;transform:translateY(0);}

  .about-grid{
    display:grid;
    grid-template-columns:0.9fr 1.1fr;
    gap:60px;
    align-items:start;
  }
  .about-card{
    background:var(--card-bg);
    border:1px solid var(--card-border);
    border-radius:var(--radius-lg);
    padding:36px;
  }
  .about-card h3{font-size:20px;margin-bottom:18px;color:#f0d8f5;}
  .about-card p{color:var(--text-muted);line-height:1.7;font-size:15.5px;margin-bottom:14px;}
  .info-line{display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid rgba(255,255,255,0.08);font-size:14.5px;}
  .info-line span:first-child{color:var(--text-muted);}
  .info-line span:last-child{font-weight:600;}

  .skills-wrap{display:flex;flex-wrap:wrap;gap:10px;margin-top:8px;}
  .skill-pill{
    padding:9px 18px;
    border-radius:var(--radius-pill);
    background:rgba(255,255,255,0.06);
    border:1px solid var(--card-border);
    font-size:13.5px;
    font-weight:600;
    color:var(--text-main);
  }

  .achieve-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
    gap:26px;
  }
  .achieve-card{
    background:var(--card-bg);
    border:1px solid var(--card-border);
    border-radius:var(--radius-lg);
    padding:30px;
    transition:transform .3s ease, box-shadow .3s ease, border-color .3s ease;
  }
  .achieve-card:hover{
    transform:translateY(-6px);
    border-color:rgba(236,72,153,0.4);
    box-shadow:0 14px 40px rgba(0,0,0,0.35);
  }
  .achieve-icon{
    width:48px;height:48px;
    border-radius:14px;
    background:linear-gradient(120deg,var(--accent-1),var(--accent-2));
    display:flex;align-items:center;justify-content:center;
    font-size:22px;
    margin-bottom:18px;
  }
  .achieve-card h3{font-size:18px;margin-bottom:8px;}
  .achieve-card p{color:var(--text-muted);font-size:14.5px;line-height:1.6;}
  .achieve-tag{
    display:inline-block;
    margin-top:14px;
    font-size:12px;
    font-weight:700;
    letter-spacing:0.5px;
    text-transform:uppercase;
    color:#f0a8e8;
  }

  .project-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:28px;
  }
  .project-card{
    background:var(--card-bg);
    border:1px solid var(--card-border);
    border-radius:var(--radius-lg);
    padding:0;
    overflow:hidden;
    display:flex;
    flex-direction:column;
    transition:transform .3s ease, box-shadow .3s ease;
  }
  .project-card:hover{transform:translateY(-6px);box-shadow:0 16px 42px rgba(0,0,0,0.4);}
  .project-thumb{
    height:130px;
    background:linear-gradient(135deg,var(--accent-2),var(--accent-1));
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:15px;
    font-weight:700;
    letter-spacing:0.5px;
  }
  .project-body{padding:26px;flex:1;display:flex;flex-direction:column;}
  .project-body h3{font-size:19px;margin-bottom:8px;}
  .project-body p{color:var(--text-muted);font-size:14.5px;line-height:1.6;margin-bottom:20px;flex:1;}
  .project-link{
    align-self:flex-start;
    padding:10px 22px;
    border-radius:var(--radius-pill);
    background:linear-gradient(120deg,var(--accent-1),var(--accent-2));
    color:#fff;
    text-decoration:none;
    font-weight:700;
    font-size:13.5px;
    transition:box-shadow .25s ease;
  }
  .project-link:hover{box-shadow:0 0 20px rgba(236,72,153,0.5);}

  .contact-wrap{
    background:var(--card-bg);
    border:1px solid var(--card-border);
    border-radius:var(--radius-lg);
    padding:56px;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:50px;
    align-items:center;
  }
  .contact-wrap h2{font-size:32px;font-weight:800;margin-bottom:16px;}
  .contact-wrap p{color:var(--text-muted);margin-bottom:26px;line-height:1.7;}
  .social-row{display:flex;gap:14px;flex-wrap:wrap;}
  .social-pill{
    padding:12px 22px;
    border-radius:var(--radius-pill);
    border:1.5px solid rgba(255,255,255,0.2);
    color:#fff;
    text-decoration:none;
    font-weight:600;
    font-size:14px;
    transition:.25s ease;
  }
  .social-pill:hover{border-color:var(--accent-1);background:rgba(236,72,153,0.12);}

  form{display:flex;flex-direction:column;gap:16px;}
  form input, form textarea{
    background:rgba(255,255,255,0.06);
    border:1px solid var(--card-border);
    border-radius:14px;
    padding:14px 18px;
    color:#fff;
    font-family:'Inter',sans-serif;
    font-size:14.5px;
    resize:none;
  }
  form input::placeholder, form textarea::placeholder{color:#a898c8;}
  form input:focus, form textarea:focus{outline:none;border-color:var(--accent-1);}
  form button{align-self:flex-start;}

  footer{
    padding:34px 60px;
    text-align:center;
    color:var(--text-muted);
    font-size:13.5px;
    border-top:1px solid rgba(255,255,255,0.06);
  }

  @media(max-width:900px){
    .about-grid, .contact-wrap{grid-template-columns:1fr;}
  }
  @media(max-width:768px){
    header{padding:22px 24px;}
    .nav{
      position:fixed;
      top:78px;left:0;right:0;
      flex-direction:column;
      background:rgba(36,18,73,0.98);
      padding:24px;
      gap:20px;
      display:none;
      border-bottom:1px solid rgba(255,255,255,0.08);
    }
    .nav.open{display:flex;}
    .menu-toggle{display:flex;}
    .hero{padding:0 24px;}
    .hero h1{font-size:40px;}
    .hero h2{font-size:22px;}
    section{padding:70px 24px;}
    .contact-wrap{padding:32px;}
  }

  @media (prefers-reduced-motion:reduce){
    *{animation:none !important;transition:none !important;}
  }
</style>
</head>
<body>

<div class="blob blob-1"></div>
<div class="blob blob-2"></div>
<div class="blob blob-3"></div>

<header>
  <div class="logo">Juswa.</div>
  <nav class="nav" id="nav">
    <a href="#home" class="nav-link active">Home</a>
    <a href="#about" class="nav-link">About</a>
    <a href="#achievements" class="nav-link">Achievements</a>
    <a href="#projects" class="nav-link">Projects</a>
    <a href="#contact" class="nav-link">Contact</a>
  </nav>
  <div class="menu-toggle" id="menuToggle">
    <span></span><span></span><span></span>
  </div>
</header>

<section class="hero" id="home">
  <span class="eyebrow">Portfolio</span>
  <h1>Hi, I'm Joshua Cister</h1>
  <h2>2nd Year Information Technology Student</h2>
  <p>An aspiring web developer from the University of the Immaculate Conception, building projects one activity at a time.</p>
  <div class="btn-row">
    <a href="#projects" class="btn">View Projects</a>
    <a href="#contact" class="btn ghost">Get in Touch</a>
  </div>
</section>

<section id="about">
  <div class="section-head reveal">
    <span class="eyebrow">About Me</span>
    <h2>The person behind the code</h2>
    <p>A quick look at who I am, what I'm studying, and what I'm learning to build.</p>
  </div>

  <div class="about-grid">
    <div class="about-card reveal">
      <h3>Quick Info</h3>
      <div class="info-line"><span>Name</span><span>Joshua Cister</span></div>
      <div class="info-line"><span>Course</span><span>BS Information Technology</span></div>
      <div class="info-line"><span>Year Level</span><span>2nd Year</span></div>
      <div class="info-line"><span>School</span><span>Univ. of the Immaculate Conception</span></div>
      <div class="info-line"><span>Based in</span><span>Davao City, Philippines</span></div>
      <div class="info-line"><span>Focus</span><span>Web Development</span></div>
    </div>

    <div class="about-card reveal">
      <h3>My Story</h3>
      <p>[Edit me] I'm a 2nd year IT student who got hooked on building things for the web after my first HTML/CSS class assignment. Since then I've been turning coursework into an excuse to learn something new — from layout systems to interactivity to design.</p>
      <p>[Edit me] Outside of class activities, I like exploring UI design, experimenting with color and motion, and slowly leveling up my front-end skills project by project.</p>
      <h3 style="margin-top:26px;">Skills</h3>
      <div class="skills-wrap">
        <span class="skill-pill">HTML5</span>
        <span class="skill-pill">CSS3</span>
        <span class="skill-pill">JavaScript</span>
        <span class="skill-pill">Responsive Design</span>
        <span class="skill-pill">Git &amp; GitHub</span>
        <span class="skill-pill">UI/UX Basics</span>
      </div>
    </div>
  </div>
</section>

<section id="achievements">
  <div class="section-head reveal">
    <span class="eyebrow">Achievements</span>
    <h2>Milestones so far</h2>
    <p>Edit these cards with your actual recognitions, certificates, or academic milestones.</p>
  </div>

  <div class="achieve-grid">
    <div class="achieve-card reveal">
      <div class="achieve-icon">🏆</div>
      <h3>[Achievement Title]</h3>
      <p>[Edit me] Short description of the award, recognition, or milestone and where it happened.</p>
      <span class="achieve-tag">2025</span>
    </div>
    <div class="achieve-card reveal">
      <div class="achieve-icon">🎓</div>
      <h3>[Achievement Title]</h3>
      <p>[Edit me] Short description — e.g. Dean's Lister, academic scholarship, honors list.</p>
      <span class="achieve-tag">2025</span>
    </div>
    <div class="achieve-card reveal">
      <div class="achieve-icon">💻</div>
      <h3>[Achievement Title]</h3>
      <p>[Edit me] A hackathon, coding competition, or bootcamp certificate goes here.</p>
      <span class="achieve-tag">2024</span>
    </div>
    <div class="achieve-card reveal">
      <div class="achieve-icon">⭐</div>
      <h3>[Achievement Title]</h3>
      <p>[Edit me] Any leadership role, org involvement, or extracurricular win.</p>
      <span class="achieve-tag">2024</span>
    </div>
  </div>
</section>

<section id="projects">
  <div class="section-head reveal">
    <span class="eyebrow">Projects &amp; Activities</span>
    <h2>What I've built</h2>
    <p>Class activities and personal projects — linked straight to their folders in this repo.</p>
  </div>

  <div class="project-grid">
    <div class="project-card reveal">
      <div class="project-thumb">Activity 1.1</div>
      <div class="project-body">
        <h3>Activity 1.1</h3>
        <p>[Edit me] One line about what this activity covers or what you practiced.</p>
        <a href="./Activity1.1/" class="project-link">Open Activity →</a>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-thumb">Activity 1.2</div>
      <div class="project-body">
        <h3>Activity 1.2</h3>
        <p>[Edit me] One line about what this activity covers or what you practiced.</p>
        <a href="./Activity 1.2/" class="project-link">Open Activity →</a>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-thumb">Activity 2.1</div>
      <div class="project-body">
        <h3>Activity 2.1</h3>
        <p>[Edit me] One line about what this activity covers or what you practiced.</p>
        <a href="./Activity2.1/" class="project-link">Open Activity →</a>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-thumb">Financial App</div>
      <div class="project-body">
        <h3>Financial App</h3>
        <p>[Edit me] Short description of this project — what problem it solves and how it works.</p>
        <a href="./Financial App/" class="project-link">Open Project →</a>
      </div>
    </div>

    <div class="project-card reveal">
      <div class="project-thumb">Activity 3.2</div>
      <div class="project-body">
        <h3>Activity 3.2</h3>
        <p>[Edit me] One line about what this activity covers or what you practiced.</p>
        <a href="./Activity3.2/" class="project-link">Open Activity →</a>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="section-head reveal">
    <span class="eyebrow">Contact</span>
    <h2>Let's connect</h2>
  </div>

  <div class="contact-wrap reveal">
    <div>
      <h2>Say hello</h2>
      <p>[Edit me] Whether it's about a project, a collaboration, or just to say hi — feel free to reach out.</p>
      <div class="social-row">
        <a href="https://github.com/kantonio250000000109-code" class="social-pill" target="_blank" rel="noopener">GitHub</a>
        <a href="mailto:youremail@example.com" class="social-pill">Email</a>
        <a href="#" class="social-pill" target="_blank" rel="noopener">LinkedIn</a>
        <a href="#" class="social-pill" target="_blank" rel="noopener">Facebook</a>
      </div>
    </div>
    <form onsubmit="event.preventDefault(); alert('This form is a static demo — connect it to a service like Formspree to receive messages.');">
      <input type="text" placeholder="Your name" required />
      <input type="email" placeholder="Your email" required />
      <textarea rows="4" placeholder="Your message" required></textarea>
      <button type="submit" class="btn">Send Message</button>
    </form>
  </div>
</section>

<footer>
  © <span id="year"></span> Joshua Cister — Juswa. All rights reserved.
</footer>

<script>
  document.getElementById('year').textContent = new Date().getFullYear();

  const nav = document.getElementById('nav');
  const menuToggle = document.getElementById('menuToggle');
  menuToggle.addEventListener('click', () => nav.classList.toggle('open'));
  nav.querySelectorAll('a').forEach(a => a.addEventListener('click', () => nav.classList.remove('open')));

  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-link');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(sec => {
      const top = sec.offsetTop - 120;
      if (window.scrollY >= top) current = sec.getAttribute('id');
    });
    navLinks.forEach(link => {
      link.classList.toggle('active', link.getAttribute('href') === '#' + current);
    });
  });

  const revealEls = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('in');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15 });
  revealEls.forEach(el => observer.observe(el));
</script>

</body>
</html>
