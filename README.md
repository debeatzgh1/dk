
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --ui-accent: #00f2ff; /* Cyber Cyan */
            --ui-bg: rgba(10, 10, 12, 0.9);
            --ui-glow: rgba(0, 242, 255, 0.4);
            --text-light: #f0f6fc;
        }

        /* --- TOPMOST FLOATING BANNER --- */
        .ui-browser-banner {
            position: fixed;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            width: 310px;
            height: 48px;
            background: var(--ui-bg);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(0, 242, 255, 0.2);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 8px 0 15px;
            z-index: 10001; /* Higher than other banners */
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.8), 0 0 10px var(--ui-glow);
            overflow: hidden;
        }

        /* Auto-Slide Text Container */
        .ui-slider-box {
            flex: 1;
            overflow: hidden;
            position: relative;
            height: 20px;
            margin-right: 10px;
        }

        .ui-slider-content {
            display: flex;
            flex-direction: column;
            animation: slideText 6s cubic-bezier(0.645, 0.045, 0.355, 1) infinite;
        }

        .ui-slider-content span {
            height: 20px;
            font-family: 'Monaco', 'Consolas', monospace;
            font-size: 0.75rem;
            color: var(--ui-accent);
            display: flex;
            align-items: center;
            gap: 6px;
            letter-spacing: 1px;
            font-weight: bold;
        }

        /* Action Button */
        .ui-open-btn {
            background: var(--ui-accent);
            color: #000;
            border: none;
            padding: 6px 14px;
            border-radius: 6px;
            font-size: 0.7rem;
            font-weight: 900;
            cursor: pointer;
            text-transform: uppercase;
            transition: 0.3s ease;
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .ui-open-btn:hover {
            background: #fff;
            box-shadow: 0 0 15px #fff;
            transform: scale(1.05);
        }

        /* --- OVERLAY IFRAME --- */
        #ui-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.95);
            display: none;
            flex-direction: column;
            z-index: 20000;
            animation: overlayFade 0.4s ease;
        }

        .ui-overlay-nav {
            height: 50px;
            background: #111;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
            border-bottom: 2px solid var(--ui-accent);
        }

        .ui-frame {
            width: 100%;
            flex-grow: 1;
            border: none;
            background: #fff;
        }

        /* --- ANIMATIONS --- */
        @keyframes slideText {
            0%, 20% { transform: translateY(0); }
            33%, 53% { transform: translateY(-20px); }
            66%, 86% { transform: translateY(-40px); }
            100% { transform: translateY(0); }
        }

        @keyframes overlayFade {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .pulse-icon {
            width: 6px;
            height: 6px;
            background: var(--ui-accent);
            border-radius: 50%;
            box-shadow: 0 0 8px var(--ui-accent);
        }
    </style>
</head>
<body>

    <div class="ui-browser-banner">
        <div class="ui-slider-box">
            <div class="ui-slider-content">
                <span><div class="pulse-icon"></div> Browse UI & Interfaces</span>
                <span><div class="pulse-icon"></div> Discover Experience</span>
                <span><div class="pulse-icon"></div> Portfolio Access</span>
            </div>
        </div>
        <button class="ui-open-btn" onclick="openUIHub()">
            Explore <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
        </button>
    </div>

    <div id="ui-overlay">
        <div class="ui-overlay-nav">
            <span style="color: var(--ui-accent); font-family: monospace; font-weight: bold; font-size: 0.8rem;">DEBEATZGH // UI_INTERFACES</span>
            <button onclick="closeUIHub()" style="background:none; border: 1px solid #444; color: #888; padding: 4px 12px; cursor: pointer; border-radius: 4px; font-size: 0.7rem;">CLOSE [ESC]</button>
        </div>
        <iframe class="ui-frame" id="ui-iframe"></iframe>
    </div>

    <script>
        const uiOverlay = document.getElementById('ui-overlay');
        const uiIframe = document.getElementById('ui-iframe');

        function openUIHub() {
            uiIframe.src = "https://debeatzgh1.github.io/Home-/";
            uiOverlay.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        function closeUIHub() {
            uiOverlay.style.display = 'none';
            uiIframe.src = "";
            document.body.style.overflow = 'auto';
        }

        // Close on Escape key
        document.addEventListener('keydown', (e) => {
            if (e.key === "Escape") closeUIHub();
        });
    </script>
</body>
</html>


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --nav-bg: rgba(13, 17, 23, 0.95);
            --nav-border: #30363d;
            --nav-accent: #58a6ff;
            --nav-hover: #1f6feb;
            --glow-color: rgba(88, 166, 255, 0.6);
        }

        /* Dock Container */
        .nav-dock {
            position: fixed;
            right: 20px;
            bottom: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            z-index: 10000;
        }

        /* Launcher (Button with the > icon) */
        #nav-launcher {
            width: 40px;
            height: 40px;
            background: var(--nav-bg);
            border: 1px solid var(--nav-border);
            color: var(--nav-accent);
            border-radius: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
            outline: none;
        }

        #nav-launcher.open {
            transform: rotate(-180deg);
            background: var(--nav-hover);
            color: white;
            border-color: var(--nav-accent);
        }

        /* Button Group Hidden State */
        .nav-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
            visibility: hidden;
            pointer-events: none;
        }

        .nav-group.active {
            visibility: visible;
            pointer-events: auto;
        }

        /* Navigator Tiny Arrows */
        .nav-btn {
            width: 36px;
            height: 36px;
            background: var(--nav-bg);
            border: 1px solid var(--nav-border);
            color: #c9d1d9;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transform: scale(0.5) translateX(40px);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            position: relative;
        }

        .nav-group.active .nav-btn {
            opacity: 1;
            transform: scale(1) translateX(0);
        }

        /* Heartbeat Glow Animation */
        @keyframes heartbeatGlow {
            0% { box-shadow: 0 0 0 0 var(--glow-color); transform: scale(1); }
            50% { box-shadow: 0 0 20px 8px var(--glow-color); transform: scale(1.15); }
            100% { box-shadow: 0 0 0 0 var(--glow-color); transform: scale(1); }
        }

        .pulse {
            animation: heartbeatGlow 1.2s ease-in-out;
        }

        .nav-btn:hover {
            background: var(--nav-hover);
            color: white;
            border-color: var(--nav-accent);
        }

        /* Staggered transition delays */
        .nav-group.active .nav-btn:nth-child(1) { transition-delay: 0.1s; }
        .nav-group.active .nav-btn:nth-child(2) { transition-delay: 0.2s; }
        .nav-group.active .nav-btn:nth-child(3) { transition-delay: 0.3s; }

        svg { width: 18px; height: 18px; fill: none; stroke: currentColor; stroke-width: 3; stroke-linecap: round; stroke-linejoin: round; }
    </style>
</head>
<body>

    <div class="nav-dock">
        <button id="nav-launcher" onclick="toggleNav()">
            <svg viewBox="0 0 24 24"><polyline points="9 18 15 12 9 6"></polyline></svg>
        </button>

        <div class="nav-group" id="navGroup">
            <button class="nav-btn" onclick="window.scrollTo({top: 0, behavior: 'smooth'})" title="Scroll to Top">
                <svg viewBox="0 0 24 24"><polyline points="18 15 12 9 6 15"></polyline></svg>
            </button>

            <a href="https://debeatzgh1.github.io/Home-/" class="nav-btn" title="Go Home">
                <svg viewBox="0 0 24 24" stroke-width="2.5"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
            </a>

            <button class="nav-btn" onclick="window.scrollTo({top: document.body.scrollHeight, behavior: 'smooth'})" title="Scroll to Bottom">
                <svg viewBox="0 0 24 24"><polyline points="6 9 12 15 18 9"></polyline></svg>
            </button>
        </div>
    </div>

    <script>
        function toggleNav() {
            const group = document.getElementById('navGroup');
            const launcher = document.getElementById('nav-launcher');
            const buttons = document.querySelectorAll('.nav-btn');
            
            const isOpening = group.classList.toggle('active');
            launcher.classList.toggle('open');

            if (isOpening) {
                buttons.forEach((btn, index) => {
                    // Reset animation state
                    btn.classList.remove('pulse');
                    // Force a tiny delay so the browser sees the removal
                    setTimeout(() => {
                        // Apply heartbeat pulse
                        btn.classList.add('pulse');
                    }, (index + 1) * 150);
                });
            }
        }
    </script>
</body>
</html>

<style>
  /* 🌟 Fade Slide Animation */
  @keyframes fadeSlideUp {
    0% { opacity: 0; transform: translateY(0) translateX(20px); }
    100% { opacity: 1; transform: translateY(0) translateX(0); }
  }

  /* ❤️ Heartbeat Animation */
  @keyframes heartbeat {
    0% { transform: scale(1); }
    25% { transform: scale(1.08); }
    50% { transform: scale(1); }
    75% { transform: scale(1.08); }
    100% { transform: scale(1); }
  }

  .floating-btn-group {
    animation: fadeSlideUp 0.6s ease-out;
  }

  /* Iframe Modal Styles */
  #iframe-modal {
    display: none;
    position: fixed;
    z-index: 9999;
    left: 0;
    bottom: 0;
    width: 110%;
    height: 120%;
    background: rgba(0,0,0,0.6);
    backdrop-filter: blur(4px);
  }

  .modal-content {
    position: relative;
    margin: 2% auto;
    background: #fff;
    border-radius: 16px;
    width: 95%;
    height: 90%;
    box-shadow: 0 8px 24px rgba(0,0,0,0.3);
    overflow: hidden;
    animation: fadeIn 0.3s ease;
  }

  #modal-iframe {
    width: 100%;
    height: 105%;
    border: none;
  }

  .close-btn {
    position: absolute;
    bottom: 10px;
    right: 18px;
    font-size: 30px;
    color: #333;
    cursor: pointer;
    transition: color 0.2s;
    z-index: 10;
  }

  .close-btn:hover {
    color: #e11d48;
  }

  @keyframes fadeIn {
    from {opacity: 0; transform: translateY(-10px);}
    to {opacity: 1; transform: translateY(0);}
  }
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {

  // 🔹 Floating Button at TOP-LEFT
  const btnGroup = document.createElement("div");
  btnGroup.className = "floating-btn-group";
  Object.assign(btnGroup.style, {
    position: "fixed",
    bottom: "20px",          // Top-left positioning
    left: "20px",
    zIndex: "9999",
    animation: "heartbeat 2.5s infinite ease-in-out, fadeSlideUp 0.6s ease-out forwards"
  });

  // -------------------------------------------------------
  // 📌 Updates Button
  // -------------------------------------------------------
  const button = document.createElement("a");
  button.href = "#";
  button.innerText = "📌 Port-";
  Object.assign(button.style, {
    background: "#16a34a",
    color: "#fff",
    padding: "12px 24px",
    borderRadius: "30px",
    textDecoration: "none",
    fontSize: "15px",
    fontWeight: "700",
    boxShadow: "0 4px 10px rgba(0,0,0,0.25)",
    whiteSpace: "nowrap",
  });

  // 🔹 Iframe Modal
  const modal = document.createElement("div");
  modal.id = "iframe-modal";
  modal.innerHTML = `
    <div class="modal-content">
      <span class="close-btn">&times;</span>
      <iframe id="modal-iframe" src="" loading="lazy"></iframe>
    </div>
  `;

  document.body.appendChild(modal);

  // 🔹 Open Iframe on click
  button.addEventListener("click", function (e) {
    e.preventDefault();
    document.getElementById("modal-iframe").src = "https://debeatzgh1.github.io/Personal-Portfolio-site-/";
    modal.style.display = "block";
  });

  btnGroup.appendChild(button);
  document.body.appendChild(btnGroup);

  // 🔹 Close Modal
  document.addEventListener("click", function (e) {
    if (e.target.classList.contains("close-btn") || e.target.id === "iframe-modal") {
      modal.style.display = "none";
      document.getElementById("modal-iframe").src = "";
    }
  });

  // 🔹 Auto-open external ads in a new tab
  document.getElementById("modal-iframe").addEventListener("load", function () {
    try {
      const links = this.contentDocument.querySelectorAll("a");
      links.forEach(link => {
        if (!link.href.includes("debeatzgh.wordpress.com")) {
          link.setAttribute("target", "_blank");
          link.setAttribute("rel", "noopener");
        }
      });
    } catch (err) {
      console.warn("External site - cannot rewrite links");
    }
  });

});
</script>






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


<p align="center">
  <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/12/screenshot_20251129-211026_14052189003624658858.png"
       alt="DebeatzGH Digital Branding"
       style="max-width:100%; height:auto; border-radius:12px;"/>
</p>

# 🌐 My Digital Hub  
### Elevate Your Digital Journey With AI • Automation • Online Business • E-Commerce

Welcome to the **My Digital Hub**, your central access point for professional tools, digital services, online business systems, and AI-powered solutions.

My mission is to provide **accessible, modern, and user-friendly digital solutions** for creators, online hustlers, marketers, students, and businesses looking to scale online.

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
    <h2 style="margin-bottom:20px;">My Digital Hub Menu</h2>

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
