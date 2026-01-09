---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<style>
  /* --- 1. 全局暴力重置 --- */
  .page__title, .breadcrumbs { display: none !important; }
  .archive { width: 100% !important; padding: 0 !important; max-width: 100% !important; margin: 0 !important; }
  
  /* --- 2. 核心容器：加入微妙的径向渐变背景 --- */
  .apple-hero-section {
    position: relative;
    width: 100vw; /* 强制占满视口宽度 */
    margin-left: calc(-50vw + 50%); /* 强制突破父容器限制，全屏显示 */
    min-height: 90vh; /* 占据90%的屏幕高度 */
    background: radial-gradient(circle at center, #ffffff 0%, #f2f2f2 100%); /* 只有高手才懂的微妙光影 */
    font-family: -apple-system, "SF Pro Display", "Helvetica Neue", sans-serif;
    text-align: center;
    overflow: hidden; /* 防止动画溢出 */
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding-top: 60px;
  }

  /* --- 3. 标题：巨大化 + 入场动画 --- */
  .hero-headline {
    font-size: 80px; /* 再次加大！ */
    font-weight: 700;
    letter-spacing: -0.02em;
    line-height: 1.0;
    margin-bottom: 10px;
    color: #1d1d1f;
    opacity: 0; /* 初始隐藏 */
    animation: fadeUp 1s cubic-bezier(0.2, 0.8, 0.2, 1) forwards; /* 只有Apple才用的缓动曲线 */
    animation-delay: 0.2s;
  }

  /* --- 4. 副标题：更优雅的灰色 --- */
  .hero-subhead {
    font-size: 28px;
    font-weight: 400;
    color: #86868b;
    margin-bottom: 30px;
    opacity: 0;
    animation: fadeUp 1s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
    animation-delay: 0.4s; /* 比标题晚一点出现 */
  }

  /* --- 5. 按钮：悬浮感增强 --- */
  .apple-button {
    display: inline-block;
    background-color: #0071e3;
    color: #fff !important;
    padding: 14px 32px;
    border-radius: 980px;
    font-size: 19px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.3s ease;
    opacity: 0;
    animation: fadeUp 1s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
    animation-delay: 0.6s;
  }
  .apple-button:hover {
    background-color: #0077ed;
    transform: scale(1.05) translateY(-2px); /* 悬停时稍微上浮 */
    box-shadow: 0 10px 20px rgba(0,113,227,0.3); /* 蓝色辉光 */
  }

  /* --- 6. 图片容器：视觉欺骗 --- */
  .product-image-container {
    width: 100%;
    max-width: 1200px;
    height: 700px; /* 增加高度 */
    margin-top: -20px; /* 让图片稍微向上“侵入”文字区域，产生紧凑感 */
    background-image: url('/images/Robot_1.png'); 
    background-size: contain; 
    background-repeat: no-repeat;
    background-position: center top; /* 顶部对齐 */
    opacity: 0;
    animation: zoomIn 1.2s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
    animation-delay: 0.8s; /* 图片最后登场 */
  }

  /* --- 动画关键帧定义 --- */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(40px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes zoomIn {
    from { opacity: 0; transform: scale(0.95); }
    to { opacity: 1; transform: scale(1); }
  }

  /* 移动端适配 */
  @media (max-width: 768px) {
    .hero-headline { font-size: 48px; }
    .product-image-container { height: 400px; margin-top: 20px;}
  }
</style>

<div class="apple-hero-section">
  <h1 class="hero-headline">WHUAI · INVIC</h1>
  <p class="hero-subhead">Redefining the Future of RoboCup.</p>
  
  <div>
    <a href="#introduction" class="apple-button">Meet the Team</a>
  </div>

  <div class="product-image-container"></div>
</div>

<div id="introduction" style="max-width: 800px; margin: 0 auto; padding: 100px 20px; font-size: 18px; line-height: 1.7; color: #333;">
  <h2 style="font-size: 36px; font-weight: 700; text-align: center; margin-bottom: 40px;">About Us</h2>
  <p>
    We are a multidisciplinary team with extensive competition experience, comprising six students from different schools at Wuhan University. Our members hail from the School of Electronic Information, School of Electrical Engineering and Automation, School of Robotics, and School of Surveying and Mapping. Leveraging seamless teamwork and the unique advantages of interdisciplinary collaboration, we overcome various technical challenges.
  </p>
  <p>
    Our team possesses substantial and diverse robotics competition experience, having competed together in multiple national-level events. We secured a national second prize at the 2025 China Robot Competition and RoboCup China, and achieved a national first prize in the Robotics Competition at the China Robot and Artificial Intelligence Contest, accumulating mature robot development capabilities and on-site adaptability.
  </p>
</div>
