from pathlib import Path

html = r'''<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Ghaleb Alshaer — Aspiring Software Engineer & Full-Stack Developer">
<title>Ghaleb Alshaer | Developer Portfolio</title>

<style>
:root{
  --bg:#070b14;
  --panel:#0d1424;
  --panel2:#111a2e;
  --text:#eef4ff;
  --muted:#94a3b8;
  --line:rgba(148,163,184,.16);
  --primary:#60a5fa;
  --secondary:#8b5cf6;
  --success:#34d399;
  --cyan:#22d3ee;
  --shadow:0 20px 70px rgba(0,0,0,.35);
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
  font-family:Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
  background:
    radial-gradient(circle at 15% 10%,rgba(96,165,250,.12),transparent 28%),
    radial-gradient(circle at 85% 20%,rgba(139,92,246,.13),transparent 28%),
    var(--bg);
  color:var(--text);
  line-height:1.7;
}
a{color:inherit;text-decoration:none}
.container{width:min(1160px,92%);margin:auto}
nav{
  position:sticky;top:0;z-index:50;
  backdrop-filter:blur(18px);
  background:rgba(7,11,20,.72);
  border-bottom:1px solid var(--line);
}
.nav-inner{height:72px;display:flex;align-items:center;justify-content:space-between}
.logo{font-weight:800;font-size:1.15rem;letter-spacing:.4px}
.logo span{color:var(--primary)}
.nav-links{display:flex;gap:25px;color:var(--muted);font-size:.93rem}
.nav-links a:hover{color:white}
.hero{
  min-height:760px;display:grid;grid-template-columns:1.2fr .8fr;
  align-items:center;gap:50px;padding:85px 0;
}
.badge{
  display:inline-flex;align-items:center;gap:9px;padding:7px 13px;
  border:1px solid rgba(52,211,153,.25);background:rgba(52,211,153,.07);
  border-radius:999px;color:#a7f3d0;font-size:.86rem;margin-bottom:22px
}
.dot{width:8px;height:8px;border-radius:50%;background:var(--success);box-shadow:0 0 14px var(--success)}
h1{font-size:clamp(3rem,7vw,6.1rem);line-height:.98;letter-spacing:-4px;margin-bottom:25px}
.gradient{background:linear-gradient(100deg,#fff,var(--primary),#a78bfa);-webkit-background-clip:text;background-clip:text;color:transparent}
.hero p{font-size:1.12rem;color:var(--muted);max-width:700px}
.cta{display:flex;gap:13px;flex-wrap:wrap;margin-top:32px}
.btn{
  padding:12px 19px;border-radius:12px;border:1px solid var(--line);
  background:var(--panel);font-weight:700;transition:.25s
}
.btn.primary{background:linear-gradient(135deg,var(--primary),var(--secondary));border:0}
.btn:hover{transform:translateY(-2px);box-shadow:0 10px 30px rgba(0,0,0,.25)}
.code-card{
  background:linear-gradient(145deg,rgba(17,26,46,.94),rgba(8,13,24,.96));
  border:1px solid var(--line);border-radius:22px;box-shadow:var(--shadow);
  overflow:hidden;transform:rotate(1deg)
}
.window{height:44px;border-bottom:1px solid var(--line);display:flex;align-items:center;gap:7px;padding:0 15px}
.window i{width:10px;height:10px;border-radius:50%;background:#475569}
.code{padding:25px;font-family:"SFMono-Regular",Consolas,monospace;font-size:.87rem;color:#cbd5e1}
.code .blue{color:#60a5fa}.code .purple{color:#c084fc}.code .green{color:#34d399}.code .yellow{color:#fbbf24}
section{padding:90px 0}
.section-title{font-size:2.2rem;letter-spacing:-1px;margin-bottom:12px}
.section-sub{color:var(--muted);max-width:720px;margin-bottom:38px}
.grid{display:grid;grid-template-columns:repeat(12,1fr);gap:18px}
.card{
  background:linear-gradient(145deg,rgba(17,26,46,.82),rgba(10,15,27,.9));
  border:1px solid var(--line);border-radius:20px;padding:25px;
  box-shadow:0 12px 40px rgba(0,0,0,.15)
}
.about-card{grid-column:span 7}.focus-card{grid-column:span 5}
.card h3{margin-bottom:10px}.muted{color:var(--muted)}
.skills{display:flex;flex-wrap:wrap;gap:9px;margin-top:20px}
.skill{padding:8px 12px;border:1px solid var(--line);border-radius:10px;background:rgba(255,255,255,.025);font-size:.86rem}
.chart-wrap{display:grid;grid-template-columns:1fr 1fr;gap:18px}
.bar{margin:17px 0}.bar-top{display:flex;justify-content:space-between;color:#cbd5e1;font-size:.9rem;margin-bottom:7px}
.track{height:9px;background:#172033;border-radius:99px;overflow:hidden}
.fill{height:100%;border-radius:99px;background:linear-gradient(90deg,var(--primary),var(--secondary));width:var(--w);animation:grow 1.4s ease}
@keyframes grow{from{width:0}to{width:var(--w)}}
.ring{
  width:175px;height:175px;border-radius:50%;margin:auto;
  display:grid;place-items:center;
  background:conic-gradient(var(--primary) 0 72%,#182338 72% 100%);
  position:relative
}
.ring:after{content:"";position:absolute;width:126px;height:126px;border-radius:50%;background:var(--panel)}
.ring strong{position:relative;z-index:2;font-size:2rem}.ring small{position:absolute;z-index:2;margin-top:58px;color:var(--muted)}
.projects{grid-column:span 6}
.project-icon{font-size:1.7rem;margin-bottom:14px}
.project-meta{display:flex;gap:7px;flex-wrap:wrap;margin-top:18px}
.project-meta span{font-size:.76rem;color:#bfdbfe;background:rgba(96,165,250,.08);padding:5px 8px;border-radius:7px}
.timeline{border-left:1px solid var(--line);padding-left:25px}
.step{position:relative;margin-bottom:28px}
.step:before{content:"";position:absolute;left:-31px;top:9px;width:10px;height:10px;border-radius:50%;background:var(--primary);box-shadow:0 0 16px rgba(96,165,250,.7)}
.step h3{font-size:1rem}.step p{color:var(--muted);font-size:.9rem}
.contact{
  text-align:center;padding:65px;border-radius:26px;
  background:linear-gradient(135deg,rgba(96,165,250,.1),rgba(139,92,246,.11));
  border:1px solid var(--line)
}
.contact-links{display:flex;justify-content:center;gap:12px;flex-wrap:wrap;margin-top:25px}
footer{border-top:1px solid var(--line);padding:30px 0;color:var(--muted);text-align:center;font-size:.85rem}
.reveal{opacity:0;transform:translateY(20px);transition:.7s}.reveal.show{opacity:1;transform:none}
@media(max-width:850px){
  .hero{grid-template-columns:1fr;padding:65px 0}.code-card{transform:none}
  .nav-links{display:none}.about-card,.focus-card,.projects{grid-column:span 12}
  .chart-wrap{grid-template-columns:1fr}h1{letter-spacing:-2px}
}
</style>
</head>

<body>
<nav>
  <div class="container nav-inner">
    <a class="logo" href="#">Ghaleb<span>.</span>Alshaer</a>
    <div class="nav-links">
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#roadmap">Roadmap</a>
      <a href="#contact">Contact</a>
    </div>
  </div>
</nav>

<main>
<section class="hero container">
  <div>
    <div class="badge"><span class="dot"></span> Open to learning & building</div>
    <h1>Ghaleb<br><span class="gradient">Alshaer</span></h1>
    <p>
      Aspiring Software Engineer & Full-Stack Developer in progress.
      I enjoy analyzing problems, designing systems, and turning ideas into practical software.
    </p>
    <div class="cta">
      <a class="btn primary" href="#projects">Explore My Projects</a>
      <a class="btn" href="https://github.com/GhalebAlshaer" target="_blank">GitHub ↗</a>
    </div>
  </div>

  <div class="code-card">
    <div class="window"><i></i><i></i><i></i></div>
    <div class="code">
      <div><span class="purple">const</span> developer = {</div>
      <br>
      <div>&nbsp;&nbsp;name: <span class="green">"Ghaleb Alshaer"</span>,</div>
      <div>&nbsp;&nbsp;level: <span class="green">"Beginner Developer"</span>,</div>
      <div>&nbsp;&nbsp;focus: <span class="green">"Software Engineering"</span>,</div>
      <div>&nbsp;&nbsp;goal: <span class="green">"Full-Stack Developer"</span>,</div>
      <div>&nbsp;&nbsp;mindset: <span class="green">"Analyze → Build → Improve"</span></div>
      <br>
      <div>};</div>
    </div>
  </div>
</section>

<section id="about">
<div class="container reveal">
  <h2 class="section-title">About Me</h2>
  <p class="section-sub">Building a strong foundation today for bigger systems tomorrow.</p>
  <div class="grid">
    <div class="card about-card">
      <h3>👨‍💻 Who I Am</h3>
      <p class="muted">
        I'm Ghaleb Alshaer, a beginner developer passionate about programming,
        system analysis, software development, and problem solving.
        My goal is to become a developer who understands not only how to write code,
        but also how to analyze requirements, design systems, and build maintainable solutions.
      </p>
      <div class="skills">
        <span class="skill">Problem Solving</span><span class="skill">System Analysis</span>
        <span class="skill">OOP</span><span class="skill">Software Design</span>
        <span class="skill">Data Management</span>
      </div>
    </div>
    <div class="card focus-card">
      <h3>🎯 Current Direction</h3>
      <p class="muted">Software Engineering + Full-Stack Development</p>
      <div class="bar"><div class="bar-top"><span>Programming Foundations</span><b>75%</b></div><div class="track"><div class="fill" style="--w:75%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>Web Development</span><b>65%</b></div><div class="track"><div class="fill" style="--w:65%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>System Thinking</span><b>70%</b></div><div class="track"><div class="fill" style="--w:70%"></div></div></div>
    </div>
  </div>
</div>
</section>

<section id="skills">
<div class="container reveal">
  <h2 class="section-title">Technical Skills</h2>
  <p class="section-sub">A visual snapshot of the technologies I'm currently learning and practicing.</p>
  <div class="chart-wrap">
    <div class="card">
      <h3>Technology Progress</h3>
      <div class="bar"><div class="bar-top"><span>C++</span><b>78%</b></div><div class="track"><div class="fill" style="--w:78%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>HTML</span><b>85%</b></div><div class="track"><div class="fill" style="--w:85%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>CSS</span><b>75%</b></div><div class="track"><div class="fill" style="--w:75%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>JavaScript</span><b>68%</b></div><div class="track"><div class="fill" style="--w:68%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>SQL</span><b>65%</b></div><div class="track"><div class="fill" style="--w:65%"></div></div></div>
      <div class="bar"><div class="bar-top"><span>Java / OOP</span><b>60%</b></div><div class="track"><div class="fill" style="--w:60%"></div></div></div>
    </div>

    <div class="card" style="display:grid;place-items:center;text-align:center">
      <div class="ring"><strong>6</strong><small>Core Skills</small></div>
      <h3 style="margin-top:22px">Growing Every Day</h3>
      <p class="muted">Learning through projects, experimentation and continuous improvement.</p>
    </div>
  </div>
</div>
</section>

<section id="projects">
<div class="container reveal">
  <h2 class="section-title">Featured Projects</h2>
  <p class="section-sub">Practical projects that represent my journey from programming fundamentals to real-world applications.</p>
  <div class="grid">
    <article class="card projects">
      <div class="project-icon">🏫</div><h3>School Management System</h3>
      <p class="muted">A C++ system for managing school-related data and practicing structured programming, OOP and system logic.</p>
      <div class="project-meta"><span>C++</span><span>OOP</span><span>System Design</span></div>
    </article>
    <article class="card projects">
      <div class="project-icon">📦</div><h3>Product Management System</h3>
      <p class="muted">A practical application for organizing product information and applying data-management concepts.</p>
      <div class="project-meta"><span>C++</span><span>Data Management</span></div>
    </article>
    <article class="card projects">
      <div class="project-icon">💊</div><h3>Pharmacy Inventory System</h3>
      <p class="muted">A pharmacy-oriented inventory system designed to manage medicine information and improve organization.</p>
      <div class="project-meta"><span>C++</span><span>OOP</span><span>Inventory</span></div>
    </article>
    <article class="card projects">
      <div class="project-icon">🏥</div><h3>Hospital Certificates & Reports</h3>
      <p class="muted">A web project for creating editable hospital certificates and reports with professional printable layouts.</p>
      <div class="project-meta"><span>HTML</span><span>CSS</span><span>JavaScript</span></div>
    </article>
  </div>
</div>
</section>

<section id="roadmap">
<div class="container reveal">
  <h2 class="section-title">My Developer Roadmap</h2>
  <p class="section-sub">The direction I'm following to become a strong software engineer and full-stack developer.</p>
  <div class="card timeline">
    <div class="step"><h3>01 — Strong Programming Fundamentals</h3><p>C++, problem solving, algorithms and data structures.</p></div>
    <div class="step"><h3>02 — Object-Oriented Design</h3><p>Deepen OOP with C++ and Java and learn cleaner system structure.</p></div>
    <div class="step"><h3>03 — Databases & Backend</h3><p>SQL, database design, APIs and server-side development.</p></div>
    <div class="step"><h3>04 — Modern Frontend</h3><p>Build responsive and interactive interfaces with JavaScript and modern tools.</p></div>
    <div class="step"><h3>05 — Full-Stack Development</h3><p>Connect frontend, backend and databases into complete applications.</p></div>
    <div class="step"><h3>06 — Software Engineering</h3><p>Architecture, testing, maintainability, scalability and professional development practices.</p></div>
  </div>
</div>
</section>

<section id="contact">
<div class="container reveal">
  <div class="contact">
    <h2 class="section-title">Let's Connect</h2>
    <p class="muted">I'm always learning, building and looking for the next problem to solve.</p>
    <div class="contact-links">
      <a class="btn primary" href="mailto:dev.ghaleb2026@gmail.com">Email Me</a>
      <a class="btn" href="https://github.com/GhalebAlshaer" target="_blank">GitHub</a>
      <a class="btn" href="https://www.linkedin.com/in/GhalebALshaer/" target="_blank">LinkedIn</a>
      <a class="btn" href="https://t.me/Dev_AL_shaer" target="_blank">Telegram</a>
    </div>
  </div>
</div>
</section>
</main>

<footer>
  <div class="container">© <span id="year"></span> Ghaleb Alshaer · Built with HTML, CSS & JavaScript</div>
</footer>

<script>
document.getElementById("year").textContent = new Date().getFullYear();

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if(entry.isIntersecting) entry.target.classList.add("show");
  });
},{threshold:.12});

document.querySelectorAll(".reveal").forEach(el => observer.observe(el));
</script>
</body>
</html>
'''

path = Path("/mnt/data/Ghaleb_Alshaer_Profile.html")
path.write_text(html, encoding="utf-8")
print(f"Created: {path}")
