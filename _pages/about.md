---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>

<style>
  /* * 暴力隐藏原来的所有内容，只保留我们的新图层 
   * 防止原来的滚动条和内容干扰
   */
  body > *:not(#apple-portal-root) {
    display: none !important; 
  }
  
  body {
    background: #000 !important;
    overflow: hidden !important; /* 暂时禁止body滚动，由我们的容器接管 */
  }

  /* * 核心容器：覆盖层 (Portal)
   * 这是一个浮在一切之上的独立世界
   */
  #apple-portal-root {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: #000;
    z-index: 99999;
    overflow-y: auto; /* 允许内部滚动 */
    overflow-x: hidden;
    font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
    color: #f5f5f7;
    -webkit-font-smoothing: antialiased;
  }

  /* --- 以下是 V6.0 的核心设计 --- */
  
  /* 通用 */
  *, *::before, *::after { box-sizing: border-box; }
  section { position: relative; width: 100%; overflow: hidden; }

  /* 1. Hero Section */
  #hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 10;
  }
  .hero-bg-layer {
    position: absolute;
    top: 0; left: 0; width: 100%; height: 100%;
    /* 【已修正为 .png】引用首屏背景图 */
    background: url('/images/hero-bg.png') no-repeat center center;
    background-size: cover;
    opacity: 0.6;
    transform: scale(1.1);
  }
  .hero-content { position: relative; z-index: 2; text-align: center; padding: 0 20px; }
  .hero-title {
    font-size: clamp(60px, 10vw, 120px);
    font-weight: 700;
    line-height: 1.0;
    letter-spacing: -0.03em;
    background: linear-gradient(135deg, #fff 0%, #a1a1a6 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 20px;
    opacity: 0; transform: translateY(50px);
  }
  .hero-subtitle {
    font-size: clamp(24px, 3vw, 36px); color: #86868b; font-weight: 400; margin-bottom: 50px;
    opacity: 0; transform: translateY(30px);
  }
  .hero-scroll-indicator {
    position: absolute; bottom: 40px; left: 50%; transform: translateX(-50%);
    opacity: 0; animation: bounce 2s infinite;
  }
  .arrow-down { width: 30px; height: 30px; border-bottom: 2px solid #fff; border-right: 2px solid #fff; transform: rotate(45deg); }

  /* 2. Scrollytelling Section */
  #story-section {
    position: relative;
    background: #000;
    display: flex;
    height: 300vh; /* 3倍屏高用于滚动叙事 */
  }
  .story-text-col { width: 50%; position: relative; z-index: 5; padding: 0 5%; }
  .story-block {
    height: 100vh; display: flex; flex-direction: column; justify-content: center;
    opacity: 0.3; transition: opacity 0.5s;
  }
  .story-block.active { opacity: 1; }
  .story-eyebrow { font-size: 18px; color: #2997ff; font-weight: 700; text-transform: uppercase; margin-bottom: 10px; }
  .story-heading { font-size: 56px; font-weight: 700; margin-bottom: 20px; color: #fff; }
  .story-p { font-size: 24px; color: #86868b; line-height: 1.6; }

  .story-visual-col {
    width: 50%; height: 100vh;
    position: sticky; top: 0; /* 这里的 sticky 在 portal 中会生效 */
    display: flex; justify-content: center; align-items: center; overflow: hidden;
  }
  .visual-wrapper { position: relative; width: 80%; height: 80%; }
  .visual-img {
    position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    object-fit: contain; opacity: 0; transform: scale(0.8);
    transition: all 1s cubic-bezier(0.16, 1, 0.3, 1);
  }
  /* 第一张图 */
  .visual-img.v1 { opacity: 1; transform: scale(1); background-image: url('/images/Robot_1.png'); background-size: contain; background-repeat: no-repeat; background-position: center; }
  /* 第二张图 (爆炸图，确保你也上传了这个 png) */
  .visual-img.v2 { background-image: url('/images/robot-explode.png'); background-size: contain; background-repeat: no-repeat; background-position: center; filter: contrast(1.2); }
  /* 如果没有爆炸图，这段代码会让第二张图显示为数据可视化圆环，防止空白 */
  .visual-img.v3 { 
    background: radial-gradient(circle, rgba(41,151,255,0.2) 0%, rgba(0,0,0,0) 70%);
    border: 1px solid rgba(41,151,255,0.5); border-radius: 50%; box-shadow: 0 0 50px #2997ff; 
  }

  /* 3. Bento Grid Section */
  #grid-section { background: #050505; padding: 150px 20px; position: relative; }
  .bento-header { text-align: center; margin-bottom: 100px; }
  .bento-h2 { font-size: 80px; font-weight: 700; color: #fff; letter-spacing: -0.02em; }
  .bento-container {
    display: grid; grid-template-columns: repeat(3, 1fr); grid-template-rows: repeat(2, 500px);
    gap: 30px; max-width: 1400px; margin: 0 auto;
  }
  .bento-item {
    background: #111; border-radius: 40px; padding: 50px; position: relative;
    overflow: hidden; border: 1px solid #222; transition: border-color 0.3s;
  }
  .bento-item:hover { border-color: #444; }
  .span-2 { grid-column: span 2; } .span-row-2 { grid-row: span 2; }
  
  .bento-bg-anim {
    position: absolute; top: -50%; left: -50%; width: 200%; height: 200%;
    background: radial-gradient(circle, rgba(255,255,255,0.05) 0%, rgba(0,0,0,0) 50%);
    transform: scale(0.8); opacity: 0; transition: opacity 0.5s;
  }
  .bento-item:hover .bento-bg-anim { opacity: 1; }
  .bento-content { position: relative; z-index: 2; height: 100%; display: flex; flex-direction: column; justify-content: space-between; }
  .bento-label { font-size: 14px; font-weight: 700; color: #666; text-transform: uppercase; letter-spacing: 2px; }
  .bento-title { font-size: 48px; font-weight: 600; color: #fff; margin-top: 10px; }
  .chart-wrapper { display: flex; align-items: flex-end; gap: 10px; height: 200px; margin-top: auto; }
  .chart-bar { flex: 1; background: #222; border-radius: 8px 8px 0 0; height: 0; transition: height 1.5s cubic-bezier(0.22, 1, 0.36, 1); }

  /* 4. Vision Section */
  #vision-section {
    height: 120vh; position: relative; overflow: hidden; display: flex; justify-content: center; align-items: center;
  }
  .vision-bg {
    position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    /* 【已修正为 .png】引用愿景背景图 */
    background: url('/images/vision-bg.png') no-repeat center center;
    background-size: cover; z-index: 1; transform: scale(1.5);
  }
  .vision-overlay {
    position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    background: linear-gradient(to bottom, #000 0%, transparent 20%, transparent 80%, #000 100%); z-index: 2;
  }
  .vision-text { position: relative; z-index: 3; text-align: center; mix-blend-mode: overlay; }
  .vision-big { font-size: 20vw; font-weight: 900; color: #fff; line-height: 0.8; opacity: 0; }

  @keyframes bounce { 0%, 20%, 50%, 80%, 100% {transform: translateX(-50%) translateY(0);} 40% {transform: translateX(-50%) translateY(-10px);} 60% {transform: translateX(-50%) translateY(-5px);} }

  @media (max-width: 1024px) {
    .bento-container { grid-template-columns: 1fr; grid-template-rows: auto; }
    .span-2, .span-row-2 { grid-column: span 1; grid-row: span 1; }
    #story-section { height: auto; flex-direction: column; }
    .story-text-col, .story-visual-col { width: 100%; }
    .story-visual-col { height: 50vh; position: relative; }
    .story-block { height: auto; margin-bottom: 80px; opacity: 1; }
  }
</style>

<div id="apple-portal-root">

  <section id="hero">
    <div class="hero-bg-layer"></div>
    <div class="hero-content">
      <h1 class="hero-title">WHUAI · INVIC</h1>
      <p class="hero-subtitle">Redefining the boundaries of autonomous intelligence.</p>
    </div>
    <div class="hero-scroll-indicator"><div class="arrow-down"></div></div>
  </section>

  <section id="story-section">
    <div class="story-text-col">
      <div class="story-block" id="story-1">
        <div class="story-eyebrow">The Foundation</div>
        <h2 class="story-heading">Engineered for<br>Perfection.</h2>
        <p class="story-p">Every curve of the robot is designed with aerodynamics in mind. The composite shell provides industrial-grade protection.</p>
      </div>
      <div class="story-block" id="story-2">
        <div class="story-eyebrow">Inner Core</div>
        <h2 class="story-heading">Neural Processing<br>Unleashed.</h2>
        <p class="story-p">Powered by NVIDIA Jetson modules, our proprietary algorithm processes visual data at 120fps.</p>
      </div>
      <div class="story-block" id="story-3">
        <div class="story-eyebrow">The System</div>
        <h2 class="story-heading">Hive Mind<br>Intelligence.</h2>
        <p class="story-p">It's not just one robot. It's a synchronized legion. Our swarm communication protocol allows seamless data sharing.</p>
      </div>
    </div>
    <div class="story-visual-col">
      <div class="visual-wrapper">
        <div class="visual-img v1"></div>
        <div class="visual-img v2"></div>
        <div class="visual-img v3"></div>
      </div>
    </div>
  </section>

  <section id="grid-section">
    <div class="bento-header"><h2 class="bento-h2">Unrivaled Performance.</h2></div>
    <div class="bento-container">
      <div class="bento-item span-2">
        <div class="bento-bg-anim"></div>
        <div class="bento-content">
          <div><div class="bento-label">Growth</div><div class="bento-title">National Dominance.</div></div>
          <div class="chart-wrapper">
            <div class="chart-bar" style="background:#333; height:30%"></div>
            <div class="chart-bar" style="background:#444; height:50%"></div>
            <div class="chart-bar" style="background:#555; height:70%"></div>
            <div class="chart-bar" style="background:#2997ff; height:100%; box-shadow: 0 0 20px #2997ff;"></div>
          </div>
        </div>
      </div>
      <div class="bento-item span-row-2">
        <div class="bento-content">
          <div class="bento-label">The Team</div><div class="bento-title">Elite<br>Squad.</div>
          <div style="margin-top:20px; font-size:18px; color:#888;">Six minds. Four disciplines.<br><span style="color:#fff">EE · CS · RS · Automation</span></div>
        </div>
      </div>
      <div class="bento-item">
        <div class="bento-content">
          <div class="bento-label">Rank</div><div class="bento-title" style="font-size:80px; color:#2997ff;">#1</div><div style="color:#666">CRAIC National First Prize</div>
        </div>
      </div>
      <div class="bento-item">
        <div class="bento-content">
          <div class="bento-label">Speed</div><div class="bento-title">2ms</div><div style="color:#666">Ultra-low Latency Control Loop</div>
        </div>
      </div>
    </div>
  </section>

  <section id="vision-section">
    <div class="vision-bg"></div><div class="vision-overlay"></div>
    <div class="vision-text"><div class="vision-big">THE<br>FUTURE</div></div>
  </section>

</div>

<script>
window.addEventListener('load', () => {
  // 1. 搬运工：将我们的 Portal 移到 Body 最外层，打破所有布局限制
  const portal = document.getElementById('apple-portal-root');
  if (portal) {
    document.body.appendChild(portal);
  }

  // 2. 注册 GSAP 插件
  gsap.registerPlugin(ScrollTrigger);

  // 告诉 ScrollTrigger 我们的滚动容器是 portal，而不是 body
  ScrollTrigger.defaults({
    scroller: "#apple-portal-root" 
  });

  // Hero 动画
  const tlHero = gsap.timeline();
  tlHero.to(".hero-title", { opacity: 1, y: 0, duration: 1.5, ease: "power4.out" })
        .to(".hero-subtitle", { opacity: 1, y: 0, duration: 1.5, ease: "power4.out" }, "-=1")
        .to(".hero-scroll-indicator", { opacity: 1, duration: 1 }, "-=0.5");

  gsap.to(".hero-bg-layer", {
    yPercent: 30, ease: "none",
    scrollTrigger: { trigger: "#hero", start: "top top", end: "bottom top", scrub: true }
  });

  // Story 动画 (Pinning)
  ScrollTrigger.create({
    trigger: "#story-section",
    start: "top top",
    end: "bottom bottom",
    pin: ".story-visual-col",
  });

  // Story 场景切换
  const storyAnims = [
    { id: "#story-1", img: ".v1", next: ".v2" },
    { id: "#story-2", img: ".v2", next: ".v3" },
    { id: "#story-3", img: ".v3", next: null }
  ];

  storyAnims.forEach((scene, i) => {
    gsap.to(scene.img, {
      scrollTrigger: {
        trigger: scene.id,
        start: "top center",
        end: "bottom center",
        onEnter: () => {
          gsap.to(scene.id, {opacity: 1});
          gsap.to(scene.img, {opacity: 1, scale: 1});
          if(i > 0) gsap.to(storyAnims[i-1].img, {opacity: 0}); // 隐藏上一个
        },
        onLeave: () => gsap.to(scene.id, {opacity: 0.3}),
        onEnterBack: () => {
          gsap.to(scene.id, {opacity: 1});
          gsap.to(scene.img, {opacity: 1, scale: 1});
          if(scene.next) gsap.to(scene.next, {opacity: 0});
        }
      }
    });
  });

  // Bento 柱状图
  gsap.utils.toArray(".chart-bar").forEach(bar => {
    gsap.from(bar, {
      height: 0, duration: 1.5, ease: "power3.out",
      scrollTrigger: { trigger: "#grid-section", start: "top 70%" }
    });
  });

  // Vision 动画
  gsap.to(".vision-big", {
    opacity: 1, scale: 1,
    scrollTrigger: { trigger: "#vision-section", start: "top 80%", end: "center center", scrub: 1 }
  });
  gsap.to(".vision-bg", {
    scale: 1,
    scrollTrigger: { trigger: "#vision-section", start: "top bottom", end: "bottom top", scrub: true }
  });
  
  ScrollTrigger.refresh();
});
</script>
