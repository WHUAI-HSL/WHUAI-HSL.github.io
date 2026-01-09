---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<style>
  /* =========================================
     1. 【核心修复】暴力越狱代码
     这部分代码专门用来破坏模板原本的宽度限制
     ========================================= */
  
  /* 强制所有父级容器撑开到 100% 宽度 */
  body, html, 
  .initial-content, 
  #main, 
  .page, 
  .page__inner-wrap, 
  .archive,
  .wrapper {
    width: 100% !important;
    max-width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    overflow-x: hidden !important; /* 允许横向内容存在，但隐藏滚动条 */
  }

  /* 隐藏可能存在的默认边距 */
  .page__content {
    padding: 0 !important;
    margin: 0 !important;
    width: 100% !important;
  }

  /* 隐藏原来模板的标题 */
  .page__title, .breadcrumbs { display: none !important; }

  /* =========================================
     2. Apple 风格核心设计
     ========================================= */
  
  /* 全局黑色背景 */
  body { 
    background-color: #000 !important; 
    font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
    color: #f5f5f7;
  }

  /* 通用全屏容器 */
  section {
    width: 100vw; /* 强制视口宽度 */
    position: relative;
    left: 50%;
    right: 50%;
    margin-left: -50vw; /* 经典的 CSS 居中破局法 */
    margin-right: -50vw;
    overflow: hidden;
    box-sizing: border-box;
  }

  /* --- Hero 首屏 --- */
  #hero {
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    /* 这里使用了你上传的深色背景图，如果没有就用纯黑兜底 */
    background: #000 url('/images/dark-bg.png') no-repeat center center;
    background-size: cover;
    text-align: center;
    padding: 0 20px;
  }
  
  .hero-content { 
    z-index: 2; 
    position: relative; 
    width: 100%; 
    max-width: 1400px; /* 内容最大宽度，但背景是全屏的 */
  }
  
  .hero-title {
    font-size: clamp(48px, 6vw, 100px); /* 响应式字体，防止手机上爆开 */
    font-weight: 700;
    background: linear-gradient(180deg, #fff, #888);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin: 0 auto 20px;
    line-height: 1.1;
    letter-spacing: -0.02em;
    opacity: 0;
    animation: fadeUp 1s 0.2s forwards;
  }

  .hero-subtitle {
    font-size: clamp(18px, 2vw, 28px);
    color: #a1a1a6;
    margin-bottom: 40px;
    font-weight: 400;
    opacity: 0;
    animation: fadeUp 1s 0.5s forwards;
  }

  .cta-btn {
    padding: 14px 30px;
    background: #2997ff;
    color: white !important;
    border-radius: 30px;
    font-size: 18px;
    text-decoration: none;
    display: inline-block;
    transition: all 0.3s ease;
    opacity: 0;
    animation: fadeUp 1s 0.8s forwards;
  }
  .cta-btn:hover { background: #007aff; transform: scale(1.05); }

  /* 机器人悬浮 */
  .robot-float {
    margin-top: 40px;
    width: 100%;
    height: 45vh; /* 占据屏幕高度的45% */
    background: url('/images/Robot_1.png') no-repeat center top;
    background-size: contain;
    animation: floatMove 4s infinite alternate ease-in-out;
  }

  /* --- Bento Grid (修正版) --- */
  #bento {
    background: #000;
    padding: 100px 20px;
    display: flex;
    justify-content: center;
  }
  
  .grid-wrapper {
    width: 100%;
    max-width: 1400px; /* 限制内容宽度，不限制背景 */
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); /* 自动换行布局 */
    gap: 25px;
  }

  /* 卡片基础样式 */
  .card {
    background: #1c1c1e;
    border-radius: 30px;
    padding: 40px;
    position: relative;
    min-height: 420px;
    border: 1px solid #333;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: transform 0.1s;
    overflow: hidden; /* 关键：防止内部元素溢出遮挡 */
  }
  
  .card:hover { border-color: #555; z-index: 5; }
  
  /* 宽卡片 */
  .card-wide { grid-column: span 2; }
  @media (max-width: 900px) { .card-wide { grid-column: span 1; } }

  .card-label { font-size: 13px; color: #86868b; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 15px; }
  .card-title { font-size: 42px; font-weight: 700; color: #f5f5f7; line-height: 1.1; margin: 0 0 15px 0; }
  .card-desc { font-size: 18px; color: #a1a1a6; line-height: 1.5; }

  /* --- 交互图表 (柱状图) --- */
  .chart-box {
    display: flex;
    align-items: flex-end;
    gap: 12px;
    height: 180px;
    margin-top: 20px;
    padding-bottom: 10px;
  }
  .bar {
    flex: 1;
    background: linear-gradient(180deg, #2997ff, #007aff);
    border-radius: 6px 6px 0 0;
    height: 10%; /* 默认高度 */
    transition: height 1s cubic-bezier(0.34, 1.56, 0.64, 1);
    position: relative;
    opacity: 0.8;
  }
  /* 鼠标放上去时的效果：生长 */
  .card:hover .bar { height: var(--h) !important; opacity: 1; }
  
  /* --- 动画 --- */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(40px); } to { opacity: 1; transform: translateY(0); } }
  @keyframes floatMove { from { transform: translateY(0); } to { transform: translateY(-20px); } }

</style>

<script>
document.addEventListener("DOMContentLoaded", function() {
  // 3D 卡片倾斜逻辑
  const cards = document.querySelectorAll('.card');
  cards.forEach(card => {
    card.addEventListener('mousemove', (e) => {
      const rect = card.getBoundingClientRect();
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;
      card.style.transform = `perspective(1000px) rotateX(${(y - rect.height/2) / -20}deg) rotateY(${(x - rect.width/2) / 20}deg) scale(1.02)`;
    });
    card.addEventListener('mouseleave', () => {
      card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) scale(1)';
    });
  });
});
</script>

<section id="hero">
  <div class="hero-content">
    <h1 class="hero-title">WHUAI · INVIC</h1>
    <p class="hero-subtitle">Redefining the Future of RoboCup.</p>
    <a href="#bento" class="cta-btn">View Highlights</a>
    <div class="robot-float"></div>
  </div>
</section>

<section id="bento">
  <div class="grid-wrapper">
    
    <div class="card">
      <div>
        <span class="card-label">The Team</span>
        <h3 class="card-title">Interdisciplinary<br>Powerhouse.</h3>
        <p class="card-desc">Elite students from EE, CS, Robotics, and Surveying schools.</p>
      </div>
    </div>

    <div class="card card-wide">
      <div>
        <span class="card-label">Performance</span>
        <h3 class="card-title">Domination on Field.</h3>
        <p class="card-desc">Consistent National First Prizes.</p>
      </div>
      
      <div class="chart-box">
        <div class="bar" style="--h: 40%"></div>
        <div class="bar" style="--h: 60%"></div>
        <div class="bar" style="--h: 80%"></div>
        <div class="bar" style="--h: 100%"></div> </div>
    </div>

    <div class="card">
      <div>
        <span class="card-label">Our Spirit</span>
        <h3 class="card-title">Self-reliance &<br>Innovation.</h3>
        <p class="card-desc">Overcoming limits through seamless collaboration.</p>
      </div>
    </div>

    <div class="card card-wide">
      <div>
        <span class="card-label">Vision</span>
        <h3 class="card-title">Beyond the Game.</h3>
        <p class="card-desc">Advancing general purpose robotics intelligence.</p>
      </div>
    </div>

  </div>
</section>
