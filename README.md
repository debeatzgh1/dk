<iframe src="https://msha.ke/debeatzgh#about-4" width="100%" height="400" frameborder="0" allowfullscreen></iframe>






<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>G-Dev Portfolio | Hiring Portal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Google+Sans:wght@400;500;700&display=swap');

        :root {
            --g-blue: #8ab4f8;
            --g-green: #34A853;
            --dark-bg: #1a1c1e;
            --dark-card: #2d2f31;
            --glass-border: rgba(255, 255, 255, 0.08);
        }

        body { font-family: 'Google Sans', sans-serif; background: #121212; margin: 0; }

        /* 1. LAUNCHER */
        #gdev-launcher {
            position: fixed; left: 20px; top: 50%; transform: translateY(-50%);
            display: flex; align-items: center; gap: 12px;
            background: var(--dark-card); padding: 8px 18px 8px 8px;
            border-radius: 40px; cursor: pointer; z-index: 9999;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid var(--glass-border);
        }

        #gdev-launcher:hover { transform: translateY(-50%) scale(1.08) translateX(5px); border-color: var(--g-blue); }

        .dev-avatar {
            width: 42px; height: 42px; background: #121212; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            border: 2px solid var(--g-blue); color: var(--g-blue); position: relative;
        }

        .status-dot {
            position: absolute; bottom: 2px; right: 2px; width: 10px; height: 10px;
            background: var(--g-green); border-radius: 50%; border: 2px solid var(--dark-card);
        }

        .status-glow {
            position: absolute; inset: 0; background: var(--g-green);
            border-radius: 50%; animation: status-pulse 2s infinite;
        }

        @keyframes status-pulse { 0% { transform: scale(1); opacity: 0.8; } 100% { transform: scale(2.5); opacity: 0; } }

        /* 2. OVERLAY MODAL */
        #gdev-overlay {
            position: fixed; inset: 0; background: rgba(0,0,0,0.85);
            backdrop-filter: blur(12px); display: none; z-index: 10000;
            justify-content: center; align-items: center; padding: 20px;
            opacity: 0; transition: opacity 0.4s ease;
        }

        #gdev-overlay.active { display: flex; opacity: 1; }

        .gdev-modal {
            width: 100%; max-width: 950px; height: 92vh;
            background: var(--dark-bg); border-radius: 28px;
            display: flex; flex-direction: column; overflow: hidden;
            border: 1px solid var(--glass-border); position: relative;
        }

        /* 3. IFRAME & FOOTER */
        #gdev-frame { flex-grow: 1; width: 100%; border: none; background: #fff; }

        .close-gdev {
            position: absolute; top: 20px; right: 25px; width: 40px; height: 30px;
            background: var(--dark-card); border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; color: #fff; z-index: 20;
        }

        /* CONTACT ME BUTTON STYLE */
        .hire-btn {
            background: var(--g-green);
            color: white;
            padding: 8px 18px;
            border-radius: 20px;
            font-size: 11px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: 0.3s;
            box-shadow: 0 4px 15px rgba(52, 168, 83, 0.3);
        }
        .hire-btn:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(52, 168, 83, 0.4); background: #2e964a; }

        @media (max-width: 768px) {
            .gdev-modal { height: 100vh; border-radius: 0; }
            .footer-controls { flex-direction: column; gap: 10px; padding: 15px; }
        }
    </style>
</head>
<body>

    <div id="gdev-launcher" onclick="toggleGDev()">
        <div class="dev-avatar">
            <i class="fab fa-google"></i>
            <div class="status-dot"><div class="status-glow"></div></div>
        </div>
        <div class="hidden sm:block">
            <div class="flex items-center gap-2">
                <span class="text-[9px] text-[#34A853] font-bold uppercase tracking-widest">Active</span>
            </div>
            <p class="text-[14px] font-medium text-gray-200">@debeatzgh</p>
        </div>
    </div>

    <div id="gdev-overlay">
        <div class="gdev-modal">
            <div class="close-gdev" onclick="toggleGDev()"><i class="fas fa-times"></i></div>
            
            <iframe id="gdev-frame" src=""></iframe>

            <div class="footer-controls p-4 bg-[#1a1c1e] border-t border-white/5 flex justify-between items-center px-8">
                <span class="text-[9px] text-gray-600 font-bold uppercase tracking-[2px]">G-Dev Protocol v4.0</span>
                
                <div class="flex items-center gap-3">
                    <button id="copy-btn" class="text-[11px] text-[#8ab4f8] font-bold px-4 py-2 hover:text-white transition" onclick="copyProfileLink()">
                        Copy Profile
                    </button>
                    <a href="https://wa.me/233549757544?text=Hi%20DeBeatz,%20I%20saw%20your%20Google%20Dev%20profile%20and%20would%20like%20to%20discuss%20a%20project." 
                       target="_blank" class="hire-btn">
                        <i class="fas fa-briefcase"></i> Contact Me
                    </a>
                </div>
            </div>
        </div>
    </div>

    <script>
        const overlay = document.getElementById('gdev-overlay');
        const frame = document.getElementById('gdev-frame');
        const profileUrl = "https://g.dev/debeatzgh";

        function toggleGDev() {
            if (overlay.style.display === 'flex') {
                overlay.classList.remove('active');
                setTimeout(() => { overlay.style.display = 'none'; frame.src = ""; }, 400);
                document.body.style.overflow = 'auto';
            } else {
                overlay.style.display = 'flex';
                setTimeout(() => overlay.classList.add('active'), 10);
                frame.src = profileUrl;
                document.body.style.overflow = 'hidden';
            }
        }

        async function copyProfileLink() {
            await navigator.clipboard.writeText(profileUrl);
            const btn = document.getElementById('copy-btn');
            btn.innerText = "Copied!";
            setTimeout(() => { btn.innerText = "Copy Profile"; }, 2000);
        }

        overlay.onclick = (e) => { if (e.target === overlay) toggleGDev(); };
    </script>
</body>
</html>



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Debeatzgh Ultimate Ecosystem</title>
    <style>
        :root {
            --yt-red: #FF0000;
            --spotify-green: #1DB954;
            --cyber-cyan: #00f2ff;
            --deep-pink: #FF1493;
            --bg-dark: #0d1117;
            --glass: rgba(15, 15, 15, 0.9);
        }

        body { 
            margin: 0; 
            font-family: 'Inter', system-ui, -apple-system, sans-serif; 
            background: var(--bg-dark); 
            color: white;
            overflow-x: hidden;
        }

        /* --- GLOBAL TOP BANNER SYSTEM --- */
        .master-banner-container {
            position: fixed;
            top: 15px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 10000;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }

        .floating-banner {
            width: 350px;
            height: 52px;
            background: var(--glass);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 50px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 6px 0 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* --- THEMES --- */
        .banner-productivity { border-color: var(--deep-pink); box-shadow: 0 0 15px rgba(255, 20, 147, 0.3); }
        .banner-entertainment { border-color: var(--yt-red); box-shadow: 0 0 15px rgba(255, 0, 0, 0.3); }
        .banner-ui { border-color: var(--cyber-cyan); box-shadow: 0 0 15px rgba(0, 242, 255, 0.3); }

        .banner-text-slider {
            flex: 1;
            height: 20px;
            overflow: hidden;
            margin-right: 10px;
        }

        .slide-inner {
            display: flex;
            flex-direction: column;
            animation: verticalSlide 6s infinite;
        }

        .slide-inner span {
            height: 20px;
            font-size: 0.75rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
        }

        @keyframes verticalSlide {
            0%, 25% { transform: translateY(0); }
            33%, 58% { transform: translateY(-20px); }
            66%, 91% { transform: translateY(-40px); }
            100% { transform: translateY(0); }
        }

        /* --- BUTTONS --- */
        .action-btn {
            padding: 8px 18px;
            border-radius: 50px;
            border: none;
            color: white;
            font-weight: 900;
            font-size: 0.7rem;
            cursor: pointer;
            text-transform: uppercase;
        }

        /* --- IFRAME OVERLAY --- */
        #master-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.97);
            z-index: 20000;
            display: none;
            flex-direction: column;
        }

        .overlay-header {
            height: 60px;
            padding: 0 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: #111;
            border-bottom: 2px solid #333;
        }

        #master-frame { width: 100%; flex-grow: 1; border: none; background: white; }

        /* --- SMART TOGGLE DOCK --- */
        .mode-dock {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--glass);
            padding: 8px;
            border-radius: 20px;
            display: flex;
            gap: 10px;
            border: 1px solid rgba(255,255,255,0.1);
            z-index: 9999;
        }

        .dock-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            cursor: pointer;
            transition: 0.3s;
        }

        .dot-pink { background: var(--deep-pink); }
        .dot-red { background: var(--yt-red); }
        .dot-cyan { background: var(--cyber-cyan); }
        .dock-dot:hover { transform: scale(1.4); }

    </style>
</head>
<body>

    <div class="master-banner-container">
        
        <div id="banner-prod" class="floating-banner banner-productivity">
            <div class="banner-text-slider">
                <div class="slide-inner">
                    <span style="color: var(--deep-pink);">🚀 Lifestyle Productivity</span>
                    <span style="color: var(--deep-pink);">💡 Tools & Ideas</span>
                    <span style="color: var(--deep-pink);">📈 All in one place!</span>
                </div>
            </div>
            <button class="action-btn" style="background: var(--deep-pink);" onclick="launch('https://msha.ke/debeatzgh', 'Productivity Hub')">Open Hub</button>
        </div>

        <div id="banner-ent" class="floating-banner banner-entertainment" style="display: none;">
            <div class="banner-text-slider">
                <div class="slide-inner">
                    <span style="color: var(--yt-red);">🎬 Entertainment Hub</span>
                    <span style="color: var(--yt-red);">🎵 Stream Playlists</span>
                    <span style="color: var(--yt-red);">🔴 Live Updates</span>
                </div>
            </div>
            <button class="action-btn" style="background: var(--yt-red);" onclick="launch('https://debeatzgh1.github.io/E-Hub-/', 'Entertainment Player')">Watch</button>
        </div>

        <div id="banner-ui" class="floating-banner banner-ui" style="display: none;">
            <div class="banner-text-slider">
                <div class="slide-inner">
                    <span style="color: var(--cyber-cyan);">🖥️ Browse UI & Interfaces</span>
                    <span style="color: var(--cyber-cyan);">🎨 Modern Styling</span>
                    <span style="color: var(--cyber-cyan);">📂 Design Systems</span>
                </div>
            </div>
            <button class="action-btn" style="background: var(--cyber-cyan); color: #000;" onclick="launch('https://debeatzgh1.github.io/me-/', 'UI Portfolio')">Explore</button>
        </div>

    </div>

    <div id="master-overlay">
        <div class="overlay-header" id="overlay-header-bar">
            <span id="overlay-title" style="font-weight: bold; text-transform: uppercase; font-size: 0.8rem;">Resource View</span>
            <div style="display:flex; gap: 10px;">
                <button onclick="closeOverlay()" style="background: #444; color: white; border: none; padding: 6px 15px; border-radius: 4px; cursor: pointer;">Close</button>
            </div>
        </div>
        <iframe id="master-frame" src=""></iframe>
    </div>

    <div class="mode-dock">
        <div class="dock-dot dot-pink" title="Productivity Mode" onclick="switchMode('prod')"></div>
        <div class="dock-dot dot-red" title="Entertainment Mode" onclick="switchMode('ent')"></div>
        <div class="dock-dot dot-cyan" title="UI/UX Mode" onclick="switchMode('ui')"></div>
    </div>

    <script>
        const banners = {
            prod: document.getElementById('banner-prod'),
            ent: document.getElementById('banner-ent'),
            ui: document.getElementById('banner-ui')
        };

        const overlay = document.getElementById('master-overlay');
        const frame = document.getElementById('master-frame');
        const header = document.getElementById('overlay-header-bar');

        // Switch Banner Modes
        function switchMode(mode) {
            Object.values(banners).forEach(b => b.style.display = 'none');
            banners[mode].style.display = 'flex';
            // Save preference
            localStorage.setItem('master-mode', mode);
        }

        // Launch Iframe
        function launch(url, title) {
            document.getElementById('overlay-title').innerText = title;
            frame.src = url;
            overlay.style.display = 'flex';
            document.body.style.overflow = 'hidden';

            // Change header color based on active mode
            const activeMode = localStorage.getItem('master-mode');
            const colors = { prod: '#FF1493', ent: '#FF0000', ui: '#00f2ff' };
            header.style.borderBottomColor = colors[activeMode];
        }

        function closeOverlay() {
            overlay.style.display = 'none';
            frame.src = '';
            document.body.style.overflow = 'auto';
        }

        // Load saved mode or default to prod
        window.onload = () => {
            const saved = localStorage.getItem('master-mode') || 'prod';
            switchMode(saved);
        };
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

            <a href="https://debeatzgh1.github.io/blogs/" class="nav-btn" title="Go Home">
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
      <iframe id="modal-iframe" src="https://form.svhrt.com/60f4a0aeedc1993c8c7b3989" loading="lazy"></iframe>
    </div>
  `;

  document.body.appendChild(modal);

  // 🔹 Open Iframe on click
  button.addEventListener("click", function (e) {
    e.preventDefault();
    document.getElementById("modal-iframe").src = "https://form.svhrt.com/60f4a0aeedc1993c8c7b3989";
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


<iframe src="https://debeatzgh.wordpress.com/key-offers/" width="100%" height="400" frameborder="0" allowfullscreen></iframe>
