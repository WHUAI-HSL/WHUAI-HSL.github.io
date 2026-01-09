---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<style>
  /* --- 0. 核心重置 (Reset) --- */
  .page__title, .breadcrumbs { display: none !important; }
  .archive { width: 100% !important; padding: 0 !important; max-width: 100% !important; margin: 0 !important; }
  html { scroll-behavior: smooth; background: #000; }
  body { 
    font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif; 
    margin: 0; padding: 0; overflow-x: hidden; 
    background-color: #000; /* 全黑背景 */
    color: #f5f5f7;
  }
  
  /* --- 1. 全局布局修正 --- */
  section {
    position: relative;
    width: 100vw;
    margin-left: calc(-50vw + 50%); /* 强制突破容器，全屏显示 */
    overflow: hidden;
  }

  /* --- 2. 首屏 Hero (暗黑钛金风格) --- */
  #hero {
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: url('/images/dark-bg.png') no-repeat center center;
    background-size: cover;
    text-align: center;
  }
  
  .hero-content { z-index: 2; position: relative; width: 90%; max-width: 1400px; }
  
  .hero-title {
    font-size: clamp(60px, 8vw, 120px); /* 响应式超大字体 */
    font-weight: 700;
    background: linear-gradient(180deg, #fff, #888); /* 钛金渐变文字 */
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin: 0;
    line-height: 1.05;
    letter-spacing: -0.03em;
    opacity: 0;
    animation: fadeUp 1s 0.2s forwards;
  }

  .hero-subtitle {
    font-size: clamp(20px, 3vw, 32px);
    color: #a1a1a6;
    margin-top: 20px;
    font-weight: 400;
    opacity: 0;
    animation: fadeUp 1s 0.5s forwards;
  }

  .cta-btn {
    margin-top: 40px;
    padding: 15px 35px;
    background: #2997ff; /* iPhone 15 Pro Blue */
    color: white !important;
    border-radius: 30px;
    font-size: 20px;
    text-decoration: none;
    display: inline-block;
    transition: all 0.3s ease;
    opacity: 0;
    animation: fadeUp 1s 0.8s forwards;
  }
  .cta-btn:hover { background: #007aff; transform: scale(1.05); box-shadow: 0 0 20px rgba(41, 151, 255, 0.4); }

  /* 机器人浮动 */
  .robot-float {
    margin-top: 60px;
    width: 80%;
    max-width: 900px;
    height: 50vh;
    background: url('/images/Robot_1.png') no-repeat center top;
    background-size: contain;
    animation: floatMove 3s infinite alternate ease-in-out; /* 上下悬浮动画 */
    filter: drop-shadow(0 0 30px rgba(255,255,255,0.1)); /* 给机器人加个微光，防止融入黑色背景 */
  }

  /* --- 3. 核心 Bento Grid (3D 交互版) --- */
  #bento {
    background: #000;
    padding: 100px 0;
  }
  
  .grid-wrapper {
    width: 90%; /* 占比 90%，解决太窄的问题 */
    max-width: 1600px; /* 最大宽度放宽到 1600px */
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 变成 3 列，铺满屏幕 */
    gap: 30px;
  }

  /* 3D 卡片容器 */
  .card {
    background: #1c1c1e; /* 高级深灰 */
    border-radius: 30px;
    padding: 40px; /* 增加内边距，解决文字遮挡 */
    position: relative;
    overflow: hidden; /* 防止内容溢出 */
    transition: transform 0.1s; /* JS 3D控制 */
    min-height: 400px;
    border: 1px solid #333;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  
  /* 鼠标悬停高亮边框 */
  .card:hover { border-color: #555; }

  .card-col-2 { grid-column: span 2; } /* 跨两列的大卡片 */
  .card-col-3 { grid-column: span 3; } /* 跨全屏的横幅 */

  .card-label { font-size: 14px; color: #86868b; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 10px; }
  .card-title { font-size: 48px; font-weight: 700; color: #f5f5f7; line-height: 1.1; margin: 0 0 20px 0; }
  .card-desc { font-size: 20px; color: #a1a1a6; line-height: 1.6; max-width: 90%; word-wrap: break-word; /* 防止文字溢出 */ }

  /* --- 4. 炫酷交互：动态图表 --- */
  .chart-container {
    display: flex;
    align-items: flex-end;
    gap: 15px;
    height: 200px;
    margin-top: 30px;
  }
  .bar {
    width: 40px;
    background: linear-gradient(to top, #2997ff, #007aff);
    border-radius: 8px 8px 0 0;
    height: 0; /* 初始为 0 */
    transition: height 1s cubic-bezier(0.175, 0.885, 0.32, 1.275); /* 弹性动画 */
    position: relative;
  }
  .bar::after {
    content: attr(data-val);
    position: absolute;
    top: -25px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 14px;
    color: #fff;
    opacity: 0;
    transition: opacity 0.5s 1s;
  }
  /* 鼠标放上去，图表生长 */
  .card:hover .bar { height: var(--h) !important; }
  .card:hover .bar::after { opacity: 1; }

  /* --- 5. 炫酷交互：滑动图片墙 --- */
  .scroll-gallery {
    display: flex;
    gap: 20px;
    overflow-x: auto;
    padding-bottom: 20px;
    scrollbar-width: none;
    margin-top: 30px;
  }
  .scroll-gallery::-webkit-scrollbar { display: none; }
  .gallery-img {
    min-width: 300px;
    height: 200px;
    background: #333;
    border-radius: 16px;
    background-size: cover;
    background-position: center;
    transition: transform 0.3s;
    cursor: pointer;
  }
  .gallery-img:hover { transform: scale(1.05); }

  /* --- 动画关键帧 --- */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(50px); } to { opacity: 1; transform: translateY(0); } }
  @keyframes floatMove { 0% { transform: translateY(0px); } 100% { transform: translateY(-20px); } }

  /* 移动端适配 */
  @media (max-width: 1024px) {
    .grid-wrapper { grid-template-columns: 1fr; }
    .card-col-2, .card-col-3 { grid-column: span 1; }
    .hero-title { font-size: 60px; }
  }
</style>

<script>
document.addEventListener("DOMContentLoaded", function() {
  // 1. 滚动检测 (Scroll Observer)
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        // 如果是图表卡片进入视野，自动触发图表生长
        if(entry.target.querySelector('.bar')) {
           const bars = entry.target.querySelectorAll('.bar');
           bars.forEach(bar => bar.style.height = bar.getAttribute('style').replace('height:','')); 
        }
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('section, .card').forEach(el => observer.observe(el));

  // 2. 3D 卡片倾斜效果 (Tilt Effect)
  const cards = document.querySelectorAll('.card');
  cards.forEach(card => {
    card.addEventListener('mousemove', (e) => {
      const rect = card.getBoundingClientRect();
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;
      const centerX = rect.width / 2;
      const centerY = rect.height / 2;
      
      // 计算旋转角度 (稍微轻微一点，更高级)
      const rotateX = ((y - centerY) / centerY) * -5;
      const rotateY = ((x - centerX) / centerX) * 5;

      card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.02)`;
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
    <p class="hero-subtitle">Pro-level autonomy. Unrivaled performance.</p>
    <a href="#bento" class="cta-btn">View Highlights</a>
    <div class="robot-float"></div>
  </div>
</section>

<section id="bento">
  <div class="grid-wrapper">
    
    <div class="card">
      <div>
        <span class="card-label">The Team</span>
        <h3 class="card-title">6 Minds.<br>1 Mission.</h3>
        <p class="card-desc">Elite engineers from Wuhan University uniting Electronics, CS, and Robotics.</p>
      </div>
      <div style="width:100px; height:100px; border: 8px solid #2997ff; border-radius:50%; align-self:flex-end; opacity:0.5;"></div>
    </div>

    <div class="card card-col-2">
      <div>
        <span class="card-label">Performance</span>
        <h3 class="card-title">Domination on Field.</h3>
        <p class="card-desc">Consistently ranking top tier in national competitions.</p>
      </div>
      
      <div class="chart-container">
        <div class="bar" style="--h: 60%;" data-val="2023"></div>
        <div class="bar" style="--h: 80%;" data-val="2024"></div>
        <div class="bar" style="--h: 100%;" data-val="2025"></div>
        <div class="bar" style="--h: 90%;" data-val="Rank 1"></div>
        <div style="color:#555; align-self:center; margin-left:10px; font-size:14px;">National Prize Growth</div>
      </div>
    </div>

    <div class="card card-col-3" style="background: linear-gradient(90deg, #1c1c1e 0%, #000 100%);">
      <div style="display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap;">
        <div style="flex:1; min-width:300px;">
          <span class="card-label">Core Tech</span>
          <h3 class="card-title">Neural Engine Inside.</h3>
          <p class="card-desc">Powered by advanced Computer Vision and Reinforcement Learning algorithms.</p>
        </div>
        <div style="background:#111; padding:20px; border-radius:12px; font-family:monospace; color:#0f0; font-size:14px; opacity:0.8;">
          > init_system()<br>
          > loading_modules...<br>
          > vision_core: ONLINE<br>
          > motion_control: READY<br>
          <span style="animation: blink 1s infinite">_</span>
        </div>
      </div>
    </div>

    <div class="card card-col-2">
      <div>
        <span class="card-label">Gallery</span>
        <h3 class="card-title">Highlights.</h3>
      </div>
      <div class="scroll-gallery">
        <div class="gallery-img" style="background-image:url('https://placehold.co/300x200/222/fff?text=Moment+1')"></div>
        <div class="gallery-img" style="background-image:url('https://placehold.co/300x200/333/fff?text=Moment+2')"></div>
        <div class="gallery-img" style="background-image:url('https://placehold.co/300x200/444/fff?text=Moment+3')"></div>
        <div class="gallery-img" style="background-image:url('https://placehold.co/300x200/555/fff?text=Moment+4')"></div>
      </div>
    </div>

    <div class="card">
      <span class="card-label">Vision</span>
      <h3 class="card-title">Beyond Soccer.</h3>
      <p class="card-desc">Advancing general purpose robotics intelligence.</p>
      <div style="margin-top:auto; font-size:40px; color:#333;">➔</div>
    </div>

  </div>
</section>

<section style="background:#000; padding:100px 0; text-align:center;">
  <h2 style="color:#fff; font-size:40px;">Ready to collaborate?</h2>
  <a href="mailto:contact@whuai.com" class="cta-btn" style="background:#333; margin-top:20px;">Contact Us</a>
</section>
