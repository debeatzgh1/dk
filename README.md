<!-- 🔵 Floating SIGN UP NOW Button -->
<style>
  #signup-now-btn {
    position: fixed;
    bottom: 28px;
    left: 28px;
    background: linear-gradient(135deg, #2563eb, #1e40af);
    color: #fff;
    border: none;
    border-radius: 40px;
    padding: 14px 22px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    box-shadow: 0 4px 14px rgba(0,0,0,0.35);
    z-index: 999;
    transition: transform 0.15s ease, box-shadow 0.15s ease;
  }
  #signup-now-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 18px rgba(0,0,0,0.45);
  }
</style>

<button id="signup-now-btn" onclick="window.open('https://github.com/apps/dkonsult', '_blank')">
  🚀 Sign Up Now
</button>


<p align="center">
  <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg"
       alt="DebeatzGH Digital Branding"
       style="max-width:100%; height:auto; border-radius:12px;"/>
</p>

# 🌐 DebeatzGH Digital Hub  
### Elevate Your Digital Journey With AI • Automation • Online Business • E-Commerce

Welcome to the **DebeatzGH Digital Hub**, your central access point for professional tools, digital services, online business systems, and AI-powered solutions.

Our mission is to provide **accessible, modern, and user-friendly digital solutions** for creators, online hustlers, marketers, students, and businesses looking to scale online.

Use the **floating “📚” button** to open the interactive carousel where you can explore:  
- 🌍 **Official Website & Portfolio**  
- 📝 **Order Form for Services**  
- 🧩 **DKonsult – AI & Tech Sign-Up Portal**  

Each page opens inside a **clean iframe viewer** for easy navigation and a modern user experience.

---

## 🔗 Quick Highlights

| Section | Description |
|--------|-------------|
| **Official Website** | A complete digital portfolio showcasing services, tools, products, AI automations, and business solutions. |
| **DKonsult App** | Sign up for AI-powered consultations, project support, and tech setup services. |
| **Order Form** | A streamlined request system for websites, videos, branding, and other digital services. |

---

<div id="blog-carousel-container"></div>
<!-- Carousel + Floating Button UI -->
<style>
  #blog-carousel-overlay {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(0,0,0,0.8);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 1000;
  }
  #blog-carousel {
    background: #ffffff;
    width: 90%;
    max-width: 850px;
    max-height: 90%;
    overflow-y: auto;
    border-radius: 12px;
    padding: 28px;
    box-shadow: 0 6px 20px rgba(0,0,0,0.35);
  }
  .blog-card {
    border: 1px solid #e5e7eb;
    border-radius: 10px;
    padding: 18px;
    margin-bottom: 18px;
    background: #f9fafb;
  }
  .blog-card h3 {
    margin: 0 0 10px;
    font-size: 20px;
    color: #111827;
  }
  .blog-card p {
    margin: 0 0 14px;
    color: #4b5563;
    font-size: 15px;
  }
  .blog-card button {
    padding: 10px 14px;
    background: #2563eb;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 14px;
  }
  .blog-card button:hover {
    background: #1e3a8a;
  }
  #open-carousel-btn {
    position: fixed;
    bottom: 28px;
    right: 28px;
    background: #2563eb;
    color: #fff;
    border: none;
    border-radius: 50%;
    width: 58px;
    height: 58px;
    font-size: 26px;
    cursor: pointer;
    box-shadow: 0 3px 16px rgba(0,0,0,0.4);
    z-index: 999;
  }
</style>

<button id="open-carousel-btn" title="Open Menu">📚</button>

<div id="blog-carousel-overlay">
  <div id="blog-carousel">
    <button id="close-carousel-btn"
            style="float:right; font-size:20px; background:transparent; border:none; cursor:pointer;">✖️</button>
    <h2 style="margin-bottom:20px;">DebeatzGH Digital Hub Menu</h2>

    <!-- CARD 1 -->
    <div class="blog-card">
      <h3>🌍 DebeatzGH Official Website</h3>
      <p>Explore the complete portfolio for digital products, tech tools, online business systems, branding, and AI-powered creative solutions.</p>
      <button onclick="openInIframe('https://msha.ke/debeatzgh')">Open Website</button>
    </div>

    <!-- CARD 2 -->
    <div class="blog-card">
      <h3>🧩 DKonsult – AI App Sign-Up</h3>
      <p>Sign up to access professional AI consultations, project building, automation, API tools, and digital systems setup by DebeatzGH.</p>
      <button onclick="openInIframe('https://github.com/apps/dkonsult')">Open DKonsult</button>
    </div>

    <!-- CARD 3 -->
    <div class="blog-card">
      <h3>📝 Order Form – Digital Services</h3>
      <p>Request professional services including websites, branding, AI prompts, blogs, videos, logos, slides, and automation tools.</p>
      <button onclick="openInIframe('https://forms.gle/GigqTKeUmTX9r8Yw6')">Open Order Form</button>
    </div>

  </div>
</div>

<!-- Iframe overlay -->
<div id="iframe-overlay"
     style="display:none; position:fixed; top:0; left:0; right:0; bottom:0; background:rgba(0,0,0,0.9); z-index:1100; align-items:center; justify-content:center;">
  <div style="position: relative; width:90%; height:90%; max-width:1050px; max-height:850px; background:#fff; border-radius:12px; overflow:hidden;">
    <button id="close-iframe-btn"
            style="position:absolute; top:10px; right:10px; z-index:1200; background:#ef4444; color:white; border:none;
            font-size:24px; padding:4px 12px; border-radius:6px; cursor:pointer;">✖</button>
    <iframe id="blog-iframe" src="" style="width:100%; height:100%; border:none;"></iframe>
  </div>
</div>

<script>
  const openBtn = document.getElementById('open-carousel-btn');
  const overlay = document.getElementById('blog-carousel-overlay');
  const closeBtn = document.getElementById('close-carousel-btn');
  const iframeOverlay = document.getElementById('iframe-overlay');
  const iframe = document.getElementById('blog-iframe');
  const closeIframeBtn = document.getElementById('close-iframe-btn');

  openBtn.onclick = () => overlay.style.display = 'flex';
  closeBtn.onclick = () => overlay.style.display = 'none';

  function openInIframe(url) {
    iframe.src = url;
    overlay.style.display = 'none';
    iframeOverlay.style.display = 'flex';
  }

  closeIframeBtn.onclick = () => {
    iframe.src = '';
    iframeOverlay.style.display = 'none';
  };
</script>
