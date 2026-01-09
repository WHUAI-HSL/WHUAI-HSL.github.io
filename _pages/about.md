---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<style>
  /* --- 0. 全局设置 --- */
  .page__title, .breadcrumbs { display: none !important; }
  .archive { width: 100% !important; padding: 0 !important; max-width: 100% !important; margin: 0 !important; }
  html { scroll-behavior: smooth; }
  body { font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "Helvetica Neue", sans-serif; margin: 0; padding: 0; overflow-x: hidden; }
  
  /* 通用板块样式 */
  section {
    padding: 120px 20px;
    position: relative;
    overflow: hidden;
  }

  /* --- 1. 首屏 (Hero) - 纯净白 --- */
  #hero {
    background: #fff;
    text-align: center;
    padding-top: 150px;
    padding-bottom: 0;
    z-index: 10;
  }
  .hero-title {
    font-size: 96px;
    font-weight: 800;
    letter-spacing: -0.03em;
    color: #1d1d1f;
    line-height: 1.0;
    margin-bottom: 10px;
  }
  .hero-subtitle {
    font-size: 32px;
    color: #6e6e73;
    font-weight: 400;
    margin-bottom: 50px;
  }
  .apple-btn {
    background: #0071e3;
    color: #fff !important;
    padding: 18px 42px;
    border-radius: 980px;
    font-size: 21px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    display: inline-block;
  }
  .apple-btn:hover {
    background: #0077ed;
    transform: scale(1.08);
    box-shadow: 0 10px 30px rgba(0,113,227,0.3);
  }
  .hero-robot-img {
    width: 100%;
    max-width: 1100px;
    height: 700px;
    margin: 40px auto 0;
    background-image: url('/images/Robot_1.png'); /* 确保这里是你机器人的文件名 */
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center bottom;
    animation: floatUp 1.2s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
  }

  /* --- 2. Bento Grid 区 - 高级灰 --- */
  #bento-grid {
    background: #f5f5f7; /* Apple 经典浅灰 */
    padding-bottom: 150px;
  }
  .section-header {
    text-align: center;
    max-width: 800px;
    margin: 0 auto 80px;
  }
  .section-tag { color: #0071e3; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; display: block; margin-bottom: 15px; }
  .section-title { font-size: 56px; font-weight: 700; color: #1d1d1f; line-height: 1.1; }
  
  .grid-container {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
  /* 卡片样式修复与增强 */
  .bento-card {
    background: #fff;
    border-radius: 36px;
    padding: 60px; /* 增加内边距，修复遮挡问题 */
    transition: all 0.5s cubic-bezier(0.25, 0.8, 0.25, 1);
    box-shadow: 0 10px 30px rgba(0,0,0,0.03);
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 350px; /* 保证最小高度 */
  }
  .bento-card:hover {
    transform: scale(1.03) translateY(-10px); /* 更明显的悬停上浮感 */
    box-shadow: 0 30px 60px rgba(0,0,0,0.1);
  }
  .full-width { grid-column: span 2; }
  .dark-card { background: #161617; color: #fff; }
  .dark-card .bento-title { color: #fff; }
  .dark-card .bento-text { color: #a1a1a6; }
  
  .bento-tag { font-size: 14px; font-weight: 700; color: #86868b; margin-bottom: 15px; display: block; text-transform: uppercase; }
  .bento-title { font-size: 44px; font-weight: 700; margin-bottom: 20px; }
  .bento-text { font-size: 19px; line-height: 1.5; color: #424245; max-width: 90%; }
  .big-stat { font-size: 100px; font-weight: 800; background: linear-gradient(135deg, #FFD700, #FFA500); -webkit-background-clip: text; -webkit-text-fill-color: transparent; line-height: 1; }

  /* --- 3. 核心技术区 (新) - 科技黑 --- */
  #tech-specs {
    background: #000;
    color: #fff;
  }
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
    max-width: 1200px;
    margin: 80px auto 0;
    text-align: center;
  }
  .tech-item h3 { font-size: 48px; font-weight: 700; color: #0071e3; margin-bottom: 10px; }
  .tech-item p { font-size: 20px; color: #a1a1a6; }

  /* --- 4. 精彩瞬间区 (新) - 图片墙 --- */
  #gallery {
    background: #fff;
    padding: 0;
  }
  .gallery-strip {
    display: flex;
    overflow-x: auto;
    padding: 50px 20px;
    gap: 20px;
    /* 隐藏滚动条但保持功能 */
    scrollbar-width: none; 
    -ms-overflow-style: none; 
  }
  .gallery-strip::-webkit-scrollbar { display: none; }
  
  .gallery-item {
    min-width: 400px;
    height: 600px;
    background-color: #eee; /* 图片占位色 */
    border-radius: 24px;
    flex-shrink: 0;
    background-size: cover;
    background-position: center;
    transition: transform 0.3s ease;
    position: relative;
    overflow: hidden;
  }
  .gallery-item:hover { transform: scale(0.98); }
  /* 这是一个简单的例子，你可以把这些换成真实的比赛照片地址 */
  .g1 { background-image: url('https://placehold.co/400x600/1d1d1f/fff?text=Match+Highlight+1'); }
  .g2 { background-image: url('https://placehold.co/400x600/0071e3/fff?text=Team+Collaboration'); }
  .g3 { background-image: url('https://placehold.co/400x600/333/fff?text=Victory+Moment'); }
  .g4 { background-image: url('https://placehold.co/400x600/555/fff?text=Tech+Debug'); }

  /* --- 5. 未来愿景区 (新) - 视差背景 --- */
  #vision {
    /* 【重要】这里已经改成了 .png */
    background-image: url('/images/tech-bg.png'); 
    background-attachment: fixed; /* 核心：视差滚动效果 */
    background-size: cover;
    background-position: center;
    height: 80vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: #fff;
    position: relative;
  }
  #vision::before { /* 加一个黑色遮罩，让文字更清晰 */
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(0,0,0,0.6);
  }
  .vision-content {
    position: relative;
    z-index: 2;
    max-width: 900px;
  }
  .vision-title {
    font-size: 72px;
    font-weight: 800;
    margin-bottom: 30px;
    background: linear-gradient(to right, #fff, #86868b);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .vision-text { font-size: 24px; line-height: 1.6; color: #d1d1d6; }

  @keyframes floatUp { from { opacity:0; transform:translateY(50px); } to { opacity:1; transform:translateY(0); } }

  /* 移动端适配 */
  @media (max-width: 768px) {
    .hero-title { font-size: 64px; }
    .grid-container, .tech-grid { grid-template-columns: 1fr; }
    .full-width { grid-column: span 1; }
    .bento-card { padding: 40px; min-height: auto; }
    .bento-title { font-size: 36px; }
    .vision-title { font-size: 48px; }
  }
</style>

<section id="hero">
  <h1 class="hero-title">WHUAI · INVIC</h1>
  <p class="hero-subtitle">Unleashing the Future of Autonomous Soccer.</p>
  <a href="#bento-grid" class="apple-btn">Explore the Journey</a>
  <div class="hero-robot-img"></div>
</section>

<section id="bento-grid">
  <div class="section-header">
    <span class="section-tag">Who We Are</span>
    <h2 class="section-title">A synergy of elite minds,<br>driven by innovation.</h2>
  </div>
  
  <div class="grid-container">
    <div class="bento-card">
      <div>
        <span class="bento-tag">The Team</span>
        <h3 class="bento-title">Multidisciplinary<br>Powerhouse.</h3>
      </div>
      <p class="bento-text">Six elite students from EE, CS, Robotics, and Surveying schools, uniting diverse expertise.</p>
    </div>
    
    <div class="bento-card">
      <div>
        <span class="bento-tag">Our Spirit</span>
        <h3 class="bento-title">Self-reliance &<br>Truth-seeking.</h3>
      </div>
      <p class="bento-text">Pushing technical boundaries through relentless innovation and seamless collaboration.</p>
    </div>
    
    <div class="bento-card full-width dark-card">
      <div>
        <span class="bento-tag">Achievements</span>
        <h3 class="bento-title">Domination on the Field.</h3>
      </div>
      <div style="display: flex; justify-content: space-between; align-items: flex-end; margin-top: 40px;">
        <p class="bento-text" style="max-width: 600px; margin-bottom: 0;">
          Secured National 2nd Prize at 2025 China Robot Competition & RoboCup China. <br>Achieved <strong>National 1st Prize</strong> at CRAIC Robotics Competition.
        </p>
        <div style="text-align: right;">
          <span class="big-stat">#1</span>
          <span style="display:block; font-weight:600; margin-top: -10px;">National Rank</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="tech-specs">
  <div class="section-header">
    <span class="section-tag">Under the Hood</span>
    <h2 class="section-title" style="color: #fff;">Engineered for Precision.</h2>
  </div>
  <div class="tech-grid">
    <div class="tech-item">
      <h3><span style="font-size:0.6em">Up to</span> 20</h3>
      <p>Degrees of Freedom</p>
    </div>
    <div class="tech-item">
      <h3>AI</h3>
      <p>Advanced Vision & Planning</p>
    </div>
    <div class="tech-item">
      <h3>ms</h3>
      <p>Ultra-low Latency Response</p>
    </div>
  </div>
</section>

<section id="gallery">
  <div class="section-header" style="margin-bottom: 40px;">
     <h2 class="section-title">Highlights in Motion.</h2>
  </div>
  <div class="gallery-strip">
    <div class="gallery-item g1"></div>
    <div class="gallery-item g2"></div>
    <div class="gallery-item g3"></div>
    <div class="gallery-item g4"></div>
  </div>
</section>

<section id="vision">
  <div class="vision-content">
    <h2 class="vision-title">Beyond the Game.</h2>
    <p class="vision-text">
      We are not just building robots for soccer.<br> We are advancing the frontiers of autonomous intelligence for the real world.
    </p>
  </div>
</section>
