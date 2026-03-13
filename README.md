<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Fab Compean | Engineering Portfolio</title>
  <meta
    name="description"
    content="Engineering portfolio of Fab Compean, a Mechanical Engineering student showcasing design, analysis, CAD, and engineering projects."
  />
  <style>
    :root {
      --bg: #0b1020;
      --bg-soft: #121933;
      --card: rgba(255, 255, 255, 0.06);
      --card-border: rgba(255, 255, 255, 0.12);
      --text: #f4f7fb;
      --muted: #b3bdd1;
      --accent: #7cc7ff;
      --accent-2: #8bffcb;
      --shadow: 0 18px 50px rgba(0, 0, 0, 0.32);
      --max-width: 1120px;
      --radius: 22px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background:
        radial-gradient(circle at top left, rgba(124, 199, 255, 0.12), transparent 28%),
        radial-gradient(circle at top right, rgba(139, 255, 203, 0.08), transparent 22%),
        linear-gradient(180deg, #09101f 0%, #0b1020 48%, #0d1426 100%);
      color: var(--text);
      line-height: 1.6;
      min-height: 100vh;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.035) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.035) 1px, transparent 1px);
      background-size: 36px 36px;
      mask-image: linear-gradient(to bottom, rgba(0,0,0,0.55), rgba(0,0,0,0.1));
      pointer-events: none;
      z-index: -1;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(92%, var(--max-width));
      margin: 0 auto;
    }

    .nav {
      position: sticky;
      top: 0;
      z-index: 100;
      backdrop-filter: blur(14px);
      background: rgba(9, 16, 31, 0.72);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .nav-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1rem 0;
    }

    .brand {
      font-weight: 800;
      letter-spacing: 0.04em;
      font-size: 1rem;
    }

    .brand span {
      color: var(--accent);
    }

    .nav-links {
      display: flex;
      gap: 1.3rem;
      align-items: center;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: var(--muted);
      font-size: 0.95rem;
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .hero {
      padding: 6.5rem 0 4rem;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.35fr 0.95fr;
      gap: 2rem;
      align-items: stretch;
    }

    .hero-copy,
    .hero-panel,
    .section-card,
    .project-card,
    .contact-card {
      background: var(--card);
      border: 1px solid var(--card-border);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }

    .hero-copy {
      padding: 2.4rem;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.4rem 0.8rem;
      border-radius: 999px;
      border: 1px solid rgba(124, 199, 255, 0.2);
      color: var(--accent);
      background: rgba(124, 199, 255, 0.08);
      font-size: 0.85rem;
      margin-bottom: 1.25rem;
    }

    h1 {
      font-size: clamp(2.6rem, 5vw, 4.6rem);
      line-height: 1.02;
      letter-spacing: -0.04em;
      margin-bottom: 1rem;
    }

    .hero-copy p {
      color: var(--muted);
      max-width: 62ch;
      font-size: 1.05rem;
      margin-bottom: 1.6rem;
    }

    .button-row {
      display: flex;
      flex-wrap: wrap;
      gap: 0.9rem;
      margin-bottom: 1.8rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.9rem 1.2rem;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,0.12);
      font-weight: 700;
      transition: transform 0.18s ease, background 0.2s ease, border-color 0.2s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--accent), #96d9ff);
      color: #07101f;
      border-color: transparent;
    }

    .btn-secondary {
      background: rgba(255, 255, 255, 0.04);
      color: var(--text);
    }

    .stat-row {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.9rem;
    }

    .stat {
      padding: 1rem;
      border-radius: 16px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
    }

    .stat strong {
      display: block;
      font-size: 1.2rem;
      margin-bottom: 0.15rem;
    }

    .stat span {
      color: var(--muted);
      font-size: 0.92rem;
    }

    .hero-panel {
      padding: 1.3rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .panel-image {
      min-height: 260px;
      border-radius: 18px;
      background:
        linear-gradient(135deg, rgba(124,199,255,0.22), rgba(139,255,203,0.12)),
        linear-gradient(180deg, rgba(255,255,255,0.08), rgba(255,255,255,0.02));
      border: 1px solid rgba(255,255,255,0.08);
      display: grid;
      place-items: center;
      padding: 1.5rem;
      text-align: center;
      color: #dceffd;
    }

    .panel-image .wireframe {
      width: 100%;
      height: 100%;
      min-height: 220px;
      border-radius: 16px;
      border: 1px dashed rgba(255,255,255,0.22);
      display: grid;
      place-items: center;
      font-weight: 700;
      letter-spacing: 0.05em;
    }

    .mini-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }

    .mini-card {
      padding: 1rem;
      border-radius: 18px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
    }

    .mini-card h3 {
      font-size: 0.92rem;
      margin-bottom: 0.55rem;
      color: var(--accent-2);
    }

    .mini-card p {
      color: var(--muted);
      font-size: 0.92rem;
    }

    section {
      padding: 1.5rem 0 0.5rem;
    }

    .section-heading {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 1rem;
      margin-bottom: 1.25rem;
    }

    .section-heading h2 {
      font-size: clamp(1.8rem, 3vw, 2.5rem);
      letter-spacing: -0.03em;
    }

    .section-heading p {
      color: var(--muted);
      max-width: 55ch;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 1.25rem;
    }

    .project-card {
      overflow: hidden;
      transition: transform 0.18s ease, border-color 0.18s ease;
    }

    .project-card:hover {
      transform: translateY(-4px);
      border-color: rgba(124, 199, 255, 0.34);
    }

    .project-image {
      aspect-ratio: 16 / 9;
      background:
        linear-gradient(135deg, rgba(124, 199, 255, 0.18), rgba(139, 255, 203, 0.10)),
        #131c34;
      border-bottom: 1px solid rgba(255,255,255,0.08);
      display: grid;
      place-items: center;
      color: #d9f1ff;
      font-weight: 700;
      letter-spacing: 0.04em;
      padding: 1rem;
      text-align: center;
    }

    .project-content {
      padding: 1.3rem;
    }

    .project-tag {
      display: inline-block;
      font-size: 0.78rem;
      color: var(--accent);
      background: rgba(124, 199, 255, 0.08);
      border: 1px solid rgba(124, 199, 255, 0.14);
      padding: 0.3rem 0.55rem;
      border-radius: 999px;
      margin-bottom: 0.9rem;
    }

    .project-content h3 {
      margin-bottom: 0.7rem;
      font-size: 1.24rem;
    }

    .project-content p {
      color: var(--muted);
      margin-bottom: 1rem;
      font-size: 0.97rem;
    }

    .tool-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.55rem;
      margin-bottom: 1rem;
    }

    .tool-list span,
    .skill-chip {
      padding: 0.45rem 0.72rem;
      border-radius: 999px;
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.09);
      font-size: 0.85rem;
      color: #dbe6f8;
    }

    .project-links {
      display: flex;
      gap: 0.8rem;
      flex-wrap: wrap;
    }

    .project-links a {
      font-weight: 700;
      color: var(--accent);
      font-size: 0.92rem;
    }

    .about-grid,
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.25rem;
    }

    .section-card,
    .contact-card {
      padding: 1.4rem;
    }

    .section-card h3,
    .contact-card h3 {
      margin-bottom: 0.8rem;
      font-size: 1.15rem;
    }

    .section-card p,
    .contact-card p,
    .section-card li {
      color: var(--muted);
    }

    .skills-wrap {
      display: flex;
      gap: 0.65rem;
      flex-wrap: wrap;
      margin-top: 0.9rem;
    }

    .timeline {
      list-style: none;
      display: grid;
      gap: 0.9rem;
      margin-top: 0.5rem;
    }

    .timeline li {
      padding-left: 1rem;
      border-left: 2px solid rgba(124, 199, 255, 0.25);
    }

    .contact-line {
      display: flex;
      justify-content: space-between;
      gap: 1rem;
      padding: 0.85rem 0;
      border-bottom: 1px solid rgba(255,255,255,0.08);
      flex-wrap: wrap;
    }

    .contact-line:last-child {
      border-bottom: 0;
      padding-bottom: 0;
    }

    footer {
      padding: 2.8rem 0 3.5rem;
      color: var(--muted);
      text-align: center;
    }

    .reveal {
      opacity: 0;
      transform: translateY(18px);
      transition: opacity 0.55s ease, transform 0.55s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 920px) {
      .hero-grid,
      .projects-grid,
      .about-grid,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .stat-row {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 640px) {
      .hero {
        padding-top: 4.8rem;
      }

      .hero-copy,
      .hero-panel,
      .section-card,
      .contact-card {
        padding: 1.15rem;
      }

      .nav-inner {
        align-items: start;
        gap: 0.9rem;
        flex-direction: column;
      }

      .nav-links {
        gap: 0.9rem;
      }

      .button-row {
        flex-direction: column;
      }

      .btn {
        width: 100%;
      }

      .mini-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <nav class="nav">
    <div class="container nav-inner">
      <a href="#top" class="brand">Fab <span>Compean</span></a>
      <div class="nav-links">
        <a href="#projects">Projects</a>
        <a href="#about">About</a>
        <a href="#resume">Resume</a>
        <a href="#contact">Contact</a>
      </div>
    </div>
  </nav>

  <header class="hero" id="top">
    <div class="container hero-grid">
      <div class="hero-copy reveal">
        <div class="eyebrow">Mechanical Engineering Student • Texas A&amp;M University</div>
        <h1>Designing engineering projects that connect analysis, CAD, and real-world problem solving.</h1>
        <p>
          I’m Fab Compean, an engineering student interested in mechanical design, vehicle systems, manufacturing, and experimental analysis. This portfolio highlights projects where I worked through design tradeoffs, used technical tools, and turned engineering ideas into clear results.
        </p>

        <div class="button-row">
          <a class="btn btn-primary" href="#projects">View Projects</a>
          <a class="btn btn-secondary" href="resume.pdf" target="_blank" rel="noopener">Download Resume</a>
          <a class="btn btn-secondary" href="https://github.com/yourusername" target="_blank" rel="noopener">GitHub</a>
          <a class="btn btn-secondary" href="https://www.linkedin.com/in/your-linkedin" target="_blank" rel="noopener">LinkedIn</a>
        </div>

        <div class="stat-row">
          <div class="stat">
            <strong>CAD + Design</strong>
            <span>SolidWorks, assemblies, drawings, FEA, design iteration</span>
          </div>
          <div class="stat">
            <strong>Analysis</strong>
            <span>Engineering calculations, uncertainty, vibrations, data interpretation</span>
          </div>
          <div class="stat">
            <strong>Build Mindset</strong>
            <span>Interested in motorsports, manufacturing, and practical mechanical systems</span>
          </div>
        </div>
      </div>

      <div class="hero-panel reveal">
        <div class="panel-image">
          <div class="wireframe">ADD CAD RENDER, LAB PHOTO, OR HEADSHOT HERE</div>
        </div>
        <div class="mini-grid">
          <div class="mini-card">
            <h3>Current Focus</h3>
            <p>Mechanical design, engineering analysis, vehicle-related systems, and portfolio-ready project communication.</p>
          </div>
          <div class="mini-card">
            <h3>What I Value</h3>
            <p>Clear thinking, strong technical foundations, clean documentation, and designs that work in the real world.</p>
          </div>
        </div>
      </div>
    </div>
  </header>

  <main>
    <section id="projects">
      <div class="container">
        <div class="section-heading reveal">
          <div>
            <h2>Selected Projects</h2>
          </div>
          <p>
            These projects show how I approach engineering problems through design, testing, analysis, and communication.
          </p>
        </div>

        <div class="projects-grid">
          <article class="project-card reveal">
            <div class="project-image">PROJECT IMAGE / GRAPH / CAD SCREENSHOT</div>
            <div class="project-content">
              <span class="project-tag">Experimental Mechanics</span>
              <h3>Cantilever Beam Vibration Analysis</h3>
              <p>
                Determined natural frequency and damping ratio of a cantilever beam using sensor data, theoretical modeling, and comparison between predicted and measured response.
              </p>
              <div class="tool-list">
                <span>Excel</span>
                <span>LVDT</span>
                <span>Accelerometer</span>
                <span>Uncertainty Analysis</span>
              </div>
              <div class="project-links">
                <a href="#">Case Study</a>
                <a href="#">Report PDF</a>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-image">SOLIDWORKS ASSEMBLY OR FEA PLOT</div>
            <div class="project-content">
              <span class="project-tag">Mechanical Design</span>
              <h3>Vehicle / Chassis Design Work</h3>
              <p>
                Explored chassis-related design decisions involving structural tradeoffs, manufacturability, and integration with other vehicle subsystems.
              </p>
              <div class="tool-list">
                <span>SolidWorks</span>
                <span>Design Tradeoffs</span>
                <span>Structures</span>
                <span>Manufacturing</span>
              </div>
              <div class="project-links">
                <a href="#">Design Summary</a>
                <a href="#">Images</a>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-image">DAQ SETUP / CIRCUIT / DATA PLOT</div>
            <div class="project-content">
              <span class="project-tag">Instrumentation</span>
              <h3>DAQ and Sensor-Based Measurement Project</h3>
              <p>
                Worked through data acquisition concepts, signal interpretation, and measurement resolution while connecting hardware limits to engineering decision making.
              </p>
              <div class="tool-list">
                <span>DAQ</span>
                <span>Sensors</span>
                <span>Data Analysis</span>
                <span>Engineering Measurement</span>
              </div>
              <div class="project-links">
                <a href="#">Overview</a>
                <a href="#">Results</a>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-image">GEAR RATIO CHART / POWERTRAIN VISUAL</div>
            <div class="project-content">
              <span class="project-tag">Systems Thinking</span>
              <h3>Powertrain Ratio Selection Project</h3>
              <p>
                Evaluated gear and final drive ratio choices by connecting speed targets, acceleration goals, and engine operating range to a practical drivetrain strategy.
              </p>
              <div class="tool-list">
                <span>Vehicle Dynamics</span>
                <span>Excel</span>
                <span>Ratios</span>
                <span>Performance Tradeoffs</span>
              </div>
              <div class="project-links">
                <a href="#">Project Notes</a>
                <a href="#">Analysis</a>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-heading reveal">
          <div>
            <h2>About</h2>
          </div>
          <p>
            A quick look at what I work on, what tools I use, and how I like to approach engineering problems.
          </p>
        </div>

        <div class="about-grid">
          <div class="section-card reveal">
            <h3>Engineering Approach</h3>
            <p>
              I like projects where I can connect calculations, CAD, testing, and communication into one complete story. I’m especially interested in mechanical systems where design decisions involve real tradeoffs like stiffness versus weight, performance versus simplicity, or analysis versus manufacturability.
            </p>
            <div class="skills-wrap">
              <span class="skill-chip">Mechanical Design</span>
              <span class="skill-chip">CAD Modeling</span>
              <span class="skill-chip">Engineering Analysis</span>
              <span class="skill-chip">Technical Communication</span>
              <span class="skill-chip">Problem Solving</span>
            </div>
          </div>

          <div class="section-card reveal">
            <h3>Tools & Skills</h3>
            <div class="skills-wrap">
              <span class="skill-chip">SolidWorks</span>
              <span class="skill-chip">Excel</span>
              <span class="skill-chip">MATLAB</span>
              <span class="skill-chip">C++</span>
              <span class="skill-chip">FEA</span>
              <span class="skill-chip">Lab Instrumentation</span>
              <span class="skill-chip">Data Analysis</span>
              <span class="skill-chip">Technical Reports</span>
            </div>
          </div>

          <div class="section-card reveal">
            <h3>What I’m Building Toward</h3>
            <ul class="timeline">
              <li>Stronger portfolio-ready engineering case studies</li>
              <li>More vehicle-focused design experience</li>
              <li>Clear documentation of project decisions and outcomes</li>
            </ul>
          </div>

          <div class="section-card reveal" id="resume">
            <h3>Resume</h3>
            <p>
              Put your resume PDF in the same GitHub repository and name it <strong>resume.pdf</strong> so the button at the top works immediately.
            </p>
            <div class="button-row" style="margin-top: 1rem; margin-bottom: 0;">
              <a class="btn btn-primary" href="resume.pdf" target="_blank" rel="noopener">Open Resume</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="section-heading reveal">
          <div>
            <h2>Contact</h2>
          </div>
          <p>
            Make it easy for recruiters, teams, and employers to reach you quickly.
          </p>
        </div>

        <div class="contact-grid">
          <div class="contact-card reveal">
            <h3>Get in Touch</h3>
            <div class="contact-line">
              <strong>Email</strong>
              <a href="mailto:youremail@example.com">youremail@example.com</a>
            </div>
            <div class="contact-line">
              <strong>LinkedIn</strong>
              <a href="https://www.linkedin.com/in/your-linkedin" target="_blank" rel="noopener">linkedin.com/in/your-linkedin</a>
            </div>
            <div class="contact-line">
              <strong>GitHub</strong>
              <a href="https://github.com/yourusername" target="_blank" rel="noopener">github.com/yourusername</a>
            </div>
          </div>

          <div class="contact-card reveal">
            <h3>Quick Note</h3>
            <p>
              This portfolio is designed to be easy to maintain. As you finish better projects, replace placeholders with real screenshots, measurable results, and short writeups that explain your engineering choices.
            </p>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <p>© 2026 Fab Compean • Built for GitHub Pages</p>
    </div>
  </footer>

  <script>
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, { threshold: 0.12 });

    document.querySelectorAll('.reveal').forEach((el) => observer.observe(el));
  </script>
</body>
</html>
