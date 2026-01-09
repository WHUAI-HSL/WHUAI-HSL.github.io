---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<style>
  /* --- 0. 全局清洗 --- */
  .page__title, .breadcrumbs { display: none !important; }
  .archive { width: 100% !important; padding: 0 !important; max-width: 100% !important; margin: 0 !important; }
  body { background-color: #f5f5f7; /* Apple 经典的浅灰背景 */ }
  
  /* --- 1. 英雄区域 (Hero) --- */
  .apple-hero {
    position: relative;
    width: 100vw;
    margin-left: calc(-50vw + 50%);
    background: #fff;
    padding-top: 120px;
    padding-bottom: 0px;
    text-align: center;
    overflow: hidden;
    border-bottom-left-radius: 40px; /* 底部圆角设计 */
    border-bottom-right-radius: 40px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.05);
    z-index: 10;
  }

  .hero-title {
    font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "Helvetica Neue", sans-serif;
    font-size: 86px; /* 极致巨大 */
    font-weight: 700;
    letter-spacing: -0.03em;
    color: #1d1d1f;
    line-height: 1.0;
    margin-bottom: 10px;
  }

  .hero-subtitle {
    font-family: "SF Pro Text", sans-serif;
    font-size: 28px;
    color: #6e6e73;
    font-weight: 400;
    margin-bottom: 40px;
  }

  /* 修复按钮被遮挡的问题：增加 margin-bottom */
  .hero-cta-container {
    margin-bottom: 80px; 
    position: relative;
    z-index: 20; /* 确保按钮在最上层 */
  }

  .apple-btn {
    background: #0071e3;
    color: #fff !important;
    padding: 16px 36px;
    border-radius: 980px;
    font-size: 19px;
    font-weight: 600;
    text-decoration: none;
    transition: transform 0.3s ease;
  }
  .apple-btn:hover {
    background: #0077ed;
    transform: scale(1.05);
  }

  /* 机器人大图：调整位置和层级 */
  .hero-robot-img {
    width: 100%;
    max-width: 1000px;
    height: 650px;
    margin: 0 auto;
    background-image: url('/images/Robot_1.png');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center bottom;
    transform: translateY(20px); /* 稍微下沉，产生落地感 */
    /* 这里的动画让它慢慢浮现 */
    animation: floatIn 1.5s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
  }

  /* --- 2. Bento Grid 内容区 (花里胡哨的核心) --- */
  .content-section {
    max-width: 1200px;
    margin: 60px auto;
    padding: 0 20px;
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* 两列布局 */
    gap: 30px;
  }

  /* 卡片通用样式 */
  .bento-card {
    background: #fff;
    border-radius: 30px;
    padding: 50px;
    transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
    box-shadow: 0 4px 6px rgba(0,0,0,0.02);
    overflow: hidden;
    position: relative;
  }
  .bento-card:hover {
    transform: scale(1.02); /* 悬停轻微放大 */
    box-shadow: 0 20px 40px rgba(0,0,0,0.08);
  }

  /* 跨两列的大卡片 */
  .full-width { grid-column: span 2; }

  /* 黑色卡片 (强调成就) */
  .dark-card {
    background: #1d1d1f;
    color: #fff;
  }
  .dark-card h3 { color: #fff !important; }
  .dark-card p { color: #a1a1a6 !important; }

  /* 卡片内的文字排版 */
  .bento-tag {
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
    color: #86868b;
    margin-bottom: 10px;
    display: block;
  }
  .bento-title {
    font-family: -apple-system, sans-serif;
    font-size: 40px;
    font-weight: 700;
    line-height: 1.1;
    margin-bottom: 20px;
    color: #1d1d1f;
  }
  .bento-text {
    font-size: 18px;
    line-height: 1.6;
    color: #424245;
  }

  /* 装饰用的超大数字或图标 */
  .big-stat {
    font-size: 80px;
    font-weight: 800;
    background: linear-gradient(135deg, #FFD700, #FFA500);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-top: 20px;
    display: block;
  }

  @keyframes floatIn {
    from { opacity: 0; transform: translateY(50px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* 移动端适配 */
  @media (max-width: 768px) {
    .content-section { grid-template-columns: 1fr; }
    .full-width { grid-column: span 1; }
    .hero-title { font-size: 48px; }
  }
</style>

<div class="apple-hero">
  <h1 class="hero-title">WHUAI · INVIC</h1>
  <p class="hero-subtitle">Redefining the Future of RoboCup.</p>
  
  <div class="hero-cta-container">
    <a href="#team" class="apple-btn">Meet the Team</a>
  </div>

  <div class="hero-robot-img"></div>
</div>

<div class="content-section" id="team">
  
  <div class="bento-card">
    <span class="bento-tag">The Team</span>
    <h3 class="bento-title">Multidisciplinary<br>Powerhouse.</h3>
    <p class="bento-text">
      Comprising six elite students from Electronic Information, Electrical Engineering, Robotics, and Surveying.
    </p>
  </div>

  <div class="bento-card">
    <span class="bento-tag">Our Spirit</span>
    <h3 class="bento-title">Self-reliance &<br>Innovation.</h3>
    <p class="bento-text">
      Guided by "Truth-seeking", we leverage interdisciplinary collaboration to overcome technical limits.
    </p>
  </div>

  <div class="bento-card full-width dark-card">
    <span class="bento-tag" style="color:#86868b">Achievements</span>
    <h3 class="bento-title">Proven Excellence<br>on the Field.</h3>
    <div style="display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap;">
      <div>
        <p class="bento-text" style="max-width: 500px;">
          Secured National 2nd Prize at the 2025 China Robot Competition & RoboCup China. Achieved National 1st Prize in the Robotics Competition at CRAIC.
        </p>
      </div>
      <div style="text-align: right;">
        <span class="big-stat">#1</span>
        <span style="color: #fff; font-weight: 600;">National Prize</span>
      </div>
    </div>
  </div>

</div>
