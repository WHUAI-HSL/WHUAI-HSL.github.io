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


  /* --- 0. 核心重置 (Reset) --- */

  .page__title, .breadcrumbs { display: none !important; }

  .archive { width: 100% !important; padding: 0 !important; max-width: 100% !important; margin: 0 !important; }


  html { scroll-behavior: smooth; }


  body { font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "Helvetica Neue", sans-serif; margin: 0; padding: 0; overflow-x: hidden; }


  html { scroll-behavior: smooth; background: #000; }


  body { 


    font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif; 


    margin: 0; padding: 0; overflow-x: hidden; 


    background-color: #000; /* 全黑背景 */


    color: #f5f5f7;


  }




  /* 通用板块样式 */


  /* --- 1. 全局布局修正 --- */

  section {


    padding: 120px 20px;

    position: relative;


    width: 100vw;


    margin-left: calc(-50vw + 50%); /* 强制突破容器，全屏显示 */

    overflow: hidden;

  }




  /* --- 1. 首屏 (Hero) - 纯净白 --- */


  /* --- 2. 首屏 Hero (暗黑钛金风格) --- */

  #hero {


    background: #fff;


    height: 100vh;


    display: flex;


    flex-direction: column;


    align-items: center;


    justify-content: center;


    background: url('/images/dark-bg.png') no-repeat center center;


    background-size: cover;

    text-align: center;


    padding-top: 150px;


    padding-bottom: 0;


    z-index: 10;

  }


  


  .hero-content { z-index: 2; position: relative; width: 90%; max-width: 1400px; }


  

  .hero-title {


    font-size: 96px;


    font-weight: 800;


    font-size: clamp(60px, 8vw, 120px); /* 响应式超大字体 */


    font-weight: 700;


    background: linear-gradient(180deg, #fff, #888); /* 钛金渐变文字 */


    -webkit-background-clip: text;


    -webkit-text-fill-color: transparent;


    margin: 0;


    line-height: 1.05;

    letter-spacing: -0.03em;


    color: #1d1d1f;


    line-height: 1.0;


    margin-bottom: 10px;


    opacity: 0;


    animation: fadeUp 1s 0.2s forwards;

  }




  .hero-subtitle {


    font-size: 32px;


    color: #6e6e73;


    font-size: clamp(20px, 3vw, 32px);


    color: #a1a1a6;


    margin-top: 20px;

    font-weight: 400;


    margin-bottom: 50px;


    opacity: 0;


    animation: fadeUp 1s 0.5s forwards;

  }


  .apple-btn {


    background: #0071e3;


    color: #fff !important;


    padding: 18px 42px;


    border-radius: 980px;


    font-size: 21px;


    font-weight: 600;





  .cta-btn {


    margin-top: 40px;


    padding: 15px 35px;


    background: #2997ff; /* iPhone 15 Pro Blue */


    color: white !important;


    border-radius: 30px;


    font-size: 20px;

    text-decoration: none;


    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);

    display: inline-block;


    transition: all 0.3s ease;


    opacity: 0;


    animation: fadeUp 1s 0.8s forwards;

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


  .cta-btn:hover { background: #007aff; transform: scale(1.05); box-shadow: 0 0 20px rgba(41, 151, 255, 0.4); }





  /* 机器人浮动 */


  .robot-float {


    margin-top: 60px;


    width: 80%;


    max-width: 900px;


    height: 50vh;


    background: url('/images/Robot_1.png') no-repeat center top;

    background-size: contain;


    background-repeat: no-repeat;


    background-position: center bottom;


    animation: floatUp 1.2s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;


    animation: floatMove 3s infinite alternate ease-in-out; /* 上下悬浮动画 */


    filter: drop-shadow(0 0 30px rgba(255,255,255,0.1)); /* 给机器人加个微光，防止融入黑色背景 */

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


  /* --- 3. 核心 Bento Grid (3D 交互版) --- */


  #bento {


    background: #000;


    padding: 100px 0;

  }


  .section-tag { color: #0071e3; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; display: block; margin-bottom: 15px; }


  .section-title { font-size: 56px; font-weight: 700; color: #1d1d1f; line-height: 1.1; }




  .grid-container {


    max-width: 1200px;


  .grid-wrapper {


    width: 90%; /* 占比 90%，解决太窄的问题 */


    max-width: 1600px; /* 最大宽度放宽到 1600px */

    margin: 0 auto;

    display: grid;


    grid-template-columns: repeat(2, 1fr);


    grid-template-columns: repeat(3, 1fr); /* 变成 3 列，铺满屏幕 */

    gap: 30px;

  }


  /* 卡片样式修复与增强 */


  .bento-card {


    background: #fff;


    border-radius: 36px;


    padding: 60px; /* 增加内边距，修复遮挡问题 */


    transition: all 0.5s cubic-bezier(0.25, 0.8, 0.25, 1);


    box-shadow: 0 10px 30px rgba(0,0,0,0.03);





  /* 3D 卡片容器 */


  .card {


    background: #1c1c1e; /* 高级深灰 */


    border-radius: 30px;


    padding: 40px; /* 增加内边距，解决文字遮挡 */

    position: relative;


    overflow: hidden;


    overflow: hidden; /* 防止内容溢出 */


    transition: transform 0.1s; /* JS 3D控制 */


    min-height: 400px;


    border: 1px solid #333;

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


  /* 鼠标悬停高亮边框 */


  .card:hover { border-color: #555; }




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


  .card-col-2 { grid-column: span 2; } /* 跨两列的大卡片 */


  .card-col-3 { grid-column: span 3; } /* 跨全屏的横幅 */




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


  .card-label { font-size: 14px; color: #86868b; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 10px; }


  .card-title { font-size: 48px; font-weight: 700; color: #f5f5f7; line-height: 1.1; margin: 0 0 20px 0; }


  .card-desc { font-size: 20px; color: #a1a1a6; line-height: 1.6; max-width: 90%; word-wrap: break-word; /* 防止文字溢出 */ }




  /* --- 5. 未来愿景区 (新) - 视差背景 --- */


  #vision {


    /* 【重要】这里已经改成了 .png */


    background-image: url('/images/tech-bg.png'); 


    background-attachment: fixed; /* 核心：视差滚动效果 */


    background-size: cover;


    background-position: center;


    height: 80vh;


  /* --- 4. 炫酷交互：动态图表 --- */


  .chart-container {

    display: flex;


    align-items: center;


    justify-content: center;


    text-align: center;


    color: #fff;


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


  #vision::before { /* 加一个黑色遮罩，让文字更清晰 */


    content: '';


  .bar::after {


    content: attr(data-val);

    position: absolute;


    top: 0; left: 0; right: 0; bottom: 0;


    background: rgba(0,0,0,0.6);


    top: -25px;


    left: 50%;


    transform: translateX(-50%);


    font-size: 14px;


    color: #fff;


    opacity: 0;


    transition: opacity 0.5s 1s;

  }


  .vision-content {


    position: relative;


    z-index: 2;


    max-width: 900px;


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


  .vision-title {


    font-size: 72px;


    font-weight: 800;


    margin-bottom: 30px;


    background: linear-gradient(to right, #fff, #86868b);


    -webkit-background-clip: text;


    -webkit-text-fill-color: transparent;


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


  .vision-text { font-size: 24px; line-height: 1.6; color: #d1d1d6; }


  .gallery-img:hover { transform: scale(1.05); }




  @keyframes floatUp { from { opacity:0; transform:translateY(50px); } to { opacity:1; transform:translateY(0); } }


  /* --- 动画关键帧 --- */


  @keyframes fadeUp { from { opacity: 0; transform: translateY(50px); } to { opacity: 1; transform: translateY(0); } }


  @keyframes floatMove { 0% { transform: translateY(0px); } 100% { transform: translateY(-20px); } }



  /* 移动端适配 */


  @media (max-width: 768px) {


    .hero-title { font-size: 64px; }


    .grid-container, .tech-grid { grid-template-columns: 1fr; }


    .full-width { grid-column: span 1; }


    .bento-card { padding: 40px; min-height: auto; }


    .bento-title { font-size: 36px; }


    .vision-title { font-size: 48px; }


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


  <h1 class="hero-title">WHUAI · INVIC</h1>


  <p class="hero-subtitle">Unleashing the Future of Autonomous Soccer.</p>


  <a href="#bento-grid" class="apple-btn">Explore the Journey</a>


  <div class="hero-robot-img"></div>


  <div class="hero-content">


    <h1 class="hero-title">WHUAI · INVIC</h1>


    <p class="hero-subtitle">Pro-level autonomy. Unrivaled performance.</p>


    <a href="#bento" class="cta-btn">View Highlights</a>


    <div class="robot-float"></div>


  </div>

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


<section id="bento">


  <div class="grid-wrapper">




    <div class="bento-card">


    <div class="card">

      <div>


        <span class="bento-tag">Our Spirit</span>


        <h3 class="bento-title">Self-reliance &<br>Truth-seeking.</h3>


        <span class="card-label">The Team</span>


        <h3 class="card-title">6 Minds.<br>1 Mission.</h3>


        <p class="card-desc">Elite engineers from Wuhan University uniting Electronics, CS, and Robotics.</p>

      </div>


      <p class="bento-text">Pushing technical boundaries through relentless innovation and seamless collaboration.</p>


      <div style="width:100px; height:100px; border: 8px solid #2997ff; border-radius:50%; align-self:flex-end; opacity:0.5;"></div>

    </div>


    


    <div class="bento-card full-width dark-card">





    <div class="card card-col-2">

      <div>


        <span class="bento-tag">Achievements</span>


        <h3 class="bento-title">Domination on the Field.</h3>


        <span class="card-label">Performance</span>


        <h3 class="card-title">Domination on Field.</h3>


        <p class="card-desc">Consistently ranking top tier in national competitions.</p>

      </div>


      <div style="display: flex; justify-content: space-between; align-items: flex-end; margin-top: 40px;">


        <p class="bento-text" style="max-width: 600px; margin-bottom: 0;">


          Secured National 2nd Prize at 2025 China Robot Competition & RoboCup China. <br>Achieved <strong>National 1st Prize</strong> at CRAIC Robotics Competition.


        </p>


        <div style="text-align: right;">


          <span class="big-stat">#1</span>


          <span style="display:block; font-weight:600; margin-top: -10px;">National Rank</span>


        </div>


      


      <div class="chart-container">


        <div class="bar" style="--h: 60%;" data-val="2023"></div>


        <div class="bar" style="--h: 80%;" data-val="2024"></div>


        <div class="bar" style="--h: 100%;" data-val="2025"></div>


        <div class="bar" style="--h: 90%;" data-val="Rank 1"></div>


        <div style="color:#555; align-self:center; margin-left:10px; font-size:14px;">National Prize Growth</div>

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


    <div class="tech-item">


      <h3>AI</h3>


      <p>Advanced Vision & Planning</p>





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


    <div class="tech-item">


      <h3>ms</h3>


      <p>Ultra-low Latency Response</p>





    <div class="card">


      <span class="card-label">Vision</span>


      <h3 class="card-title">Beyond Soccer.</h3>


      <p class="card-desc">Advancing general purpose robotics intelligence.</p>


      <div style="margin-top:auto; font-size:40px; color:#333;">➔</div>

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


<section style="background:#000; padding:100px 0; text-align:center;">


  <h2 style="color:#fff; font-size:40px;">Ready to collaborate?</h2>


  <a href="mailto:contact@whuai.com" class="cta-btn" style="background:#333; margin-top:20px;">Contact Us</a>

</section>
