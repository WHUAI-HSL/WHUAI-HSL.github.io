---
permalink: /
title: "Welcome!"
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<style>
  /* --- 核心：打破模板限制 --- */
  /* 隐藏原来丑陋的标题和导航路径 */
  .page__title, .breadcrumbs { display: none !important; }
  
  /* 强制内容区域全宽，撑满屏幕 */
  .archive { 
    width: 100% !important; 
    padding-right: 0 !important; 
    max-width: 100% !important; 
    margin: 0 !important;
  }
  
  /* --- Apple 风格组件 --- */
  /* 主容器：极简白底，居中对齐 */
  .apple-hero-section {
    font-family: "SF Pro Display", "SF Pro Text", -apple-system, BlinkMacSystemFont, "Helvetica Neue", Helvetica, Arial, sans-serif;
    text-align: center;
    padding: 100px 20px 60px; /* 顶部留出足够空间 */
    background-color: #fff;
    color: #1d1d1f;
  }

  /* 巨大的主标题：模仿 iPhone/Mac 标题 */
  .hero-headline {
    font-size: 64px; /* 超大字号 */
    font-weight: 700;
    letter-spacing: -0.015em;
    line-height: 1.05;
    margin: 0 auto 15px;
    max-width: 800px;
  }

  /* 优雅的副标题：灰色，简洁 */
  .hero-subhead {
    font-size: 28px;
    font-weight: 400;
    color: #86868b;
    margin: 0 auto 40px;
    max-width: 600px;
  }

  /* 按钮区域 */
  .cta-container {
    margin-bottom: 60px;
  }

  /* 蓝色行动按钮 */
  .apple-button {
    display: inline-block;
    background-color: #0071e3; /* Apple 官方蓝 */
    color: #fff !important;
    padding: 12px 26px;
    border-radius: 980px; /* 圆角胶囊 */
    font-size: 17px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.3s ease;
  }
  .apple-button:hover {
    background-color: #0077ed;
    transform: scale(1.02); /* 悬停微放大效果 */
    text-decoration: none;
  }

  /* --- 产品大图区域 (已关联你的 Robot_1.png) --- */
  .product-image-container {
    width: 100%;
    max-width: 1100px; /* 控制最大宽度 */
    height: 600px;     /* 高度 */
    margin: 0 auto;
    background-color: #fff; /* 纯白背景 */
    border-radius: 24px;
    
    /* 这里已经自动填好了你刚才上传的图片地址 */
    background-image: url('/images/Robot_1.png'); 
    background-size: contain; /* 保证图片完整显示 */
    background-repeat: no-repeat;
    background-position: center;
  }
</style>

<div class="apple-hero-section">
  <h1 class="hero-headline">WHUAI · INVIC</h1>
  
  <p class="hero-subhead">Redefining the Future of RoboCup.</p>
  
  <div class="cta-container">
    <a href="#introduction" class="apple-button">Meet the Team ></a>
  </div>

  <div class="product-image-container"></div>
</div>

<div id="introduction" style="max-width: 800px; margin: 100px auto; text-align: left; font-size: 18px; line-height: 1.7; color: #333; padding: 0 20px;">
  <h2 style="font-size: 36px; font-weight: 700; text-align: center; margin-bottom: 40px;">About Us</h2>
  <p>
    We are a multidisciplinary team with extensive competition experience, comprising six students from different schools at Wuhan University. Our members hail from the School of Electronic Information, School of Electrical Engineering and Automation, School of Robotics, and School of Surveying and Mapping. Leveraging seamless teamwork and the unique advantages of interdisciplinary collaboration, we overcome various technical challenges.
  </p>
  <p>
    Our team possesses substantial and diverse robotics competition experience, having competed together in multiple national-level events. We secured a national second prize at the 2025 China Robot Competition and RoboCup China, and achieved a national first prize in the Robotics Competition at the China Robot and Artificial Intelligence Contest, accumulating mature robot development capabilities and on-site adaptability.
  </p>
  <p>
    Leveraging the premium platform of Wuhan University's Undergraduate Engineering Training and Innovation Practice Center, the team benefits from professional guidance and remains dedicated to advancing robotics technology through practical application. Guided by the principles of "Self-reliance, Perseverance, Truth-seeking, and Innovation," we build upon our competitive experience to continually explore new frontiers in robotics. This commitment showcases our solid professional expertise, efficient collaborative spirit, and robust innovative capabilities.
  </p>
</div>
