
<style>
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Mono:wght@400;500&family=Manrope:wght@400;500;600&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .profile-root {
    font-family: 'Manrope', sans-serif;
    background: #0d0d0d;
    color: #e8e4dc;
    min-height: 100vh;
    padding: 0 0 60px;
  }

  .hero {
    padding: 52px 40px 40px;
    border-bottom: 1px solid #222;
    position: relative;
    overflow: hidden;
  }

  .hero-grid {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 24px;
    align-items: start;
    max-width: 860px;
  }

  .badge-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 20px;
  }

  .badge {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 3px;
    letter-spacing: 0.04em;
  }

  .badge-green { background: #1a3320; color: #4ade80; border: 1px solid #25472e; }
  .badge-amber { background: #2e1f08; color: #f59e0b; border: 1px solid #3d2a0a; }
  .badge-blue  { background: #0e1f32; color: #60a5fa; border: 1px solid #162b42; }

  h1.name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(38px, 6vw, 64px);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.02em;
    color: #f0ece4;
    margin-bottom: 14px;
  }

  h1.name span { color: #f59e0b; }

  .tagline {
    font-size: 15px;
    color: #888;
    line-height: 1.6;
    max-width: 500px;
    margin-bottom: 28px;
  }

  .stat-row {
    display: flex;
    gap: 28px;
    flex-wrap: wrap;
  }

  .stat { text-align: left; }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 26px;
    font-weight: 700;
    color: #f0ece4;
  }
  .stat-label {
    font-size: 11px;
    color: #555;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-top: 2px;
  }

  .avatar-block {
    width: 88px;
    height: 88px;
    border-radius: 50%;
    background: linear-gradient(135deg, #f59e0b, #ef4444);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 800;
    color: #0d0d0d;
    flex-shrink: 0;
    margin-top: 8px;
  }

  .section {
    padding: 44px 40px 0;
    max-width: 900px;
  }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #555;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: #222;
    max-width: 200px;
  }

  .featured-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .proj-card {
    background: #141414;
    border: 1px solid #222;
    border-radius: 8px;
    padding: 22px 22px 18px;
    cursor: pointer;
    transition: border-color 0.2s, transform 0.15s;
    position: relative;
    overflow: hidden;
  }
  .proj-card:hover { border-color: #444; transform: translateY(-2px); }
  .proj-card.featured { grid-column: span 2; }

  .proj-accent {
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
  }

  .accent-amber { background: #f59e0b; }
  .accent-blue  { background: #3b82f6; }
  .accent-green { background: #22c55e; }

  .proj-icon {
    font-size: 22px;
    margin-bottom: 12px;
    display: block;
  }

  .proj-title {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: #f0ece4;
    margin-bottom: 6px;
  }

  .proj-desc {
    font-size: 13px;
    color: #666;
    line-height: 1.6;
    margin-bottom: 16px;
  }

  .proj-tags {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .proj-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 3px;
    background: #1c1c1c;
    color: #888;
    border: 1px solid #282828;
  }

  .proj-link {
    position: absolute;
    top: 18px; right: 18px;
    font-size: 16px;
    color: #444;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 10px;
  }

  .skill-item {
    background: #141414;
    border: 1px solid #1e1e1e;
    border-radius: 6px;
    padding: 14px 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .skill-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }
  .skill-name {
    font-size: 13px;
    color: #aaa;
    font-weight: 500;
  }

  .other-repos {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 10px;
  }

  .mini-repo {
    background: #141414;
    border: 1px solid #1e1e1e;
    border-radius: 6px;
    padding: 14px 16px;
    cursor: pointer;
    transition: border-color 0.18s;
  }
  .mini-repo:hover { border-color: #333; }

  .mini-repo-name {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: #60a5fa;
    margin-bottom: 4px;
  }
  .mini-repo-desc {
    font-size: 12px;
    color: #555;
  }

  .footer-strip {
    margin: 48px 40px 0;
    padding-top: 24px;
    border-top: 1px solid #1a1a1a;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }

  .footer-handle {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: #444;
  }

  .footer-link {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: #f59e0b;
    text-decoration: none;
    padding: 6px 14px;
    border: 1px solid #3d2a0a;
    border-radius: 4px;
    background: #2e1f08;
    cursor: pointer;
  }
  .footer-link:hover { background: #3d2a0a; }
</style>

<div class="profile-root">

  <div class="hero">
    <div class="hero-grid">
      <div>
        <div class="badge-row">
          <span class="badge badge-green">● Open to Work</span>
          <span class="badge badge-amber">Full-Stack Dev</span>
          <span class="badge badge-blue">11 Repositories</span>
        </div>
        <h1 class="name">Durgesh<br><span>Borole</span></h1>
        <p class="tagline">Building real-world systems — from library management to enterprise solutions and construction platforms. Turning ideas into structured, working software.</p>
        <div class="stat-row">
          <div class="stat">
            <div class="stat-num">11</div>
            <div class="stat-label">Repositories</div>
          </div>
          <div class="stat">
            <div class="stat-num">3</div>
            <div class="stat-label">Featured Projects</div>
          </div>
          <div class="stat">
            <div class="stat-num">HTML</div>
            <div class="stat-label">Primary Stack</div>
          </div>
        </div>
      </div>
      <div class="avatar-block">DB</div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">Featured Projects</div>
    <div class="featured-grid">

      <div class="proj-card featured" onclick="openLink('https://github.com/durgeshborole/Library_system')">
        <div class="proj-accent accent-amber"></div>
        <span class="proj-link">↗</span>
        <span class="proj-icon">📚</span>
        <div class="proj-title">Library Management System</div>
        <div class="proj-desc">A complete library management solution with book cataloguing, member registration, borrow/return tracking, and fine calculation. Built to handle real-world library workflows end-to-end with a clean, intuitive interface.</div>
        <div class="proj-tags">
          <span class="proj-tag">HTML</span>
          <span class="proj-tag">CSS</span>
          <span class="proj-tag">JavaScript</span>
          <span class="proj-tag">CRUD</span>
          <span class="proj-tag">Records Management</span>
        </div>
      </div>

      <div class="proj-card" onclick="openLink('https://github.com/durgeshborole/managementsystem')">
        <div class="proj-accent accent-blue"></div>
        <span class="proj-link">↗</span>
        <span class="proj-icon">⚙️</span>
        <div class="proj-title">Management System</div>
        <div class="proj-desc">Enterprise-grade management system for handling operations, data records, and workflows — demonstrating strong backend logic and system design thinking.</div>
        <div class="proj-tags">
          <span class="proj-tag">Full-Stack</span>
          <span class="proj-tag">Database</span>
          <span class="proj-tag">CRUD</span>
        </div>
      </div>

      <div class="proj-card" onclick="openLink('https://github.com/durgeshborole')">
        <div class="proj-accent accent-green"></div>
        <span class="proj-link">↗</span>
        <span class="proj-icon">🏗️</span>
        <div class="proj-title">Construction Site Showcase</div>
        <div class="proj-desc">A visually rich construction company showcase website — responsive design, service sections, project portfolio, and contact flows built for real-world presentation.</div>
        <div class="proj-tags">
          <span class="proj-tag">HTML</span>
          <span class="proj-tag">CSS</span>
          <span class="proj-tag">Responsive</span>
          <span class="proj-tag">UI Design</span>
        </div>
      </div>

    </div>
  </div>

  <div class="section" style="margin-top: 12px;">
    <div class="section-label">Tech Stack</div>
    <div class="skills-grid">
      <div class="skill-item"><div class="skill-dot" style="background:#f59e0b;"></div><span class="skill-name">HTML5</span></div>
      <div class="skill-item"><div class="skill-dot" style="background:#3b82f6;"></div><span class="skill-name">CSS3</span></div>
      <div class="skill-item"><div class="skill-dot" style="background:#22c55e;"></div><span class="skill-name">JavaScript</span></div>
      <div class="skill-item"><div class="skill-dot" style="background:#a78bfa;"></div><span class="skill-name">DevOps</span></div>
      <div class="skill-item"><div class="skill-dot" style="background:#fb923c;"></div><span class="skill-name">Database</span></div>
      <div class="skill-item"><div class="skill-dot" style="background:#f472b6;"></div><span class="skill-name">UI Design</span></div>
    </div>
  </div>

  <div class="section" style="margin-top: 36px;">
    <div class="section-label">Other Repositories</div>
    <div class="other-repos">
      <div class="mini-repo" onclick="openLink('https://github.com/durgeshborole/StackIt-A-Minimal-Q-A-Forum-Platform')">
        <div class="mini-repo-name">StackIt Q&A Forum</div>
        <div class="mini-repo-desc">Minimal Q&A forum platform</div>
      </div>
      <div class="mini-repo" onclick="openLink('https://github.com/durgeshborole/Library_system_New')">
        <div class="mini-repo-name">Library System v2</div>
        <div class="mini-repo-desc">Improved iteration of library system</div>
      </div>
      <div class="mini-repo" onclick="openLink('https://github.com/durgeshborole/Devops_practical')">
        <div class="mini-repo-name">DevOps Practical</div>
        <div class="mini-repo-desc">DevOps tools & configurations</div>
      </div>
      <div class="mini-repo" onclick="openLink('https://github.com/durgeshborole/Birthday')">
        <div class="mini-repo-name">Birthday</div>
        <div class="mini-repo-desc">Creative HTML project</div>
      </div>
    </div>
  </div>

  <div class="footer-strip">
    <span class="footer-handle">github.com/durgeshborole</span>
    <a class="footer-link" onclick="openLink('https://github.com/durgeshborole')">View Full Profile ↗</a>
  </div>

</div>
