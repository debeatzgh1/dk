
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Kumah David | Digital Portfolio Hub</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

<style>
:root{
    --bg:#07111f;
    --card:#101c2e;
    --card2:#13243d;
    --primary:#3b82f6;
    --secondary:#8b5cf6;
    --accent:#06b6d4;
    --text:#f8fafc;
    --muted:#94a3b8;
    --border:rgba(255,255,255,0.08);
    --shadow:0 10px 40px rgba(0,0,0,0.35);
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:'Inter',sans-serif;
    background:linear-gradient(180deg,#06101d 0%, #0b1728 100%);
    color:var(--text);
    overflow-x:hidden;
}

/* ================= HERO ================= */

.hero{
    position:relative;
    min-height:100vh;
    padding:40px 6%;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:50px;
    overflow:hidden;
}

.hero::before{
    content:'';
    position:absolute;
    width:500px;
    height:500px;
    background:radial-gradient(circle,var(--primary),transparent 70%);
    opacity:.15;
    top:-150px;
    right:-100px;
    filter:blur(40px);
}

.hero::after{
    content:'';
    position:absolute;
    width:450px;
    height:450px;
    background:radial-gradient(circle,var(--secondary),transparent 70%);
    opacity:.12;
    bottom:-200px;
    left:-120px;
    filter:blur(50px);
}

.hero-content{
    position:relative;
    z-index:2;
    max-width:650px;
}

.badge{
    display:inline-flex;
    align-items:center;
    gap:10px;
    padding:10px 18px;
    border-radius:999px;
    background:rgba(59,130,246,.12);
    border:1px solid rgba(59,130,246,.25);
    color:#bfdbfe;
    font-size:.85rem;
    margin-bottom:25px;
}

.dot{
    width:10px;
    height:10px;
    border-radius:50%;
    background:#22c55e;
    animation:pulse 2s infinite;
}

@keyframes pulse{
    0%{transform:scale(1);opacity:1;}
    50%{transform:scale(1.6);opacity:.5;}
    100%{transform:scale(1);opacity:1;}
}

.hero h1{
    font-size:clamp(2.8rem,7vw,5rem);
    line-height:1.05;
    font-weight:900;
    margin-bottom:20px;
}

.hero h1 span{
    background:linear-gradient(90deg,var(--primary),var(--accent));
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
}

.hero p{
    color:var(--muted);
    font-size:1.08rem;
    line-height:1.8;
    margin-bottom:35px;
}

.hero-actions{
    display:flex;
    flex-wrap:wrap;
    gap:15px;
}

.btn{
    padding:15px 24px;
    border:none;
    border-radius:14px;
    font-weight:700;
    cursor:pointer;
    text-decoration:none;
    display:inline-flex;
    align-items:center;
    gap:10px;
    transition:.3s ease;
}

.btn-primary{
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    color:white;
    box-shadow:0 10px 30px rgba(59,130,246,.35);
}

.btn-primary:hover{
    transform:translateY(-4px);
}

.btn-outline{
    border:1px solid rgba(255,255,255,.15);
    background:rgba(255,255,255,.04);
    color:white;
}

.btn-outline:hover{
    background:rgba(255,255,255,.08);
}

.hero-preview{
    position:relative;
    z-index:2;
    width:450px;
    max-width:100%;
}

.preview-card{
    background:rgba(255,255,255,.05);
    backdrop-filter:blur(14px);
    border:1px solid rgba(255,255,255,.08);
    border-radius:30px;
    overflow:hidden;
    box-shadow:var(--shadow);
}

.preview-image{
    width:100%;
    height:280px;
    object-fit:cover;
}

.preview-content{
    padding:25px;
}

.preview-content h3{
    font-size:1.5rem;
    margin-bottom:10px;
}

.preview-content p{
    color:var(--muted);
    line-height:1.7;
}

/* ================= SECTION ================= */

.section{
    padding:90px 6%;
}

.section-header{
    margin-bottom:45px;
}

.section-tag{
    color:#60a5fa;
    text-transform:uppercase;
    letter-spacing:2px;
    font-size:.82rem;
    margin-bottom:15px;
    display:block;
}

.section-title{
    font-size:clamp(2rem,5vw,3rem);
    font-weight:900;
    margin-bottom:15px;
}

.section-desc{
    color:var(--muted);
    max-width:720px;
    line-height:1.8;
}

/* ================= GRID ================= */

.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
    gap:24px;
}

.card{
    background:linear-gradient(180deg,var(--card),var(--card2));
    border:1px solid var(--border);
    border-radius:24px;
    overflow:hidden;
    transition:.35s ease;
    position:relative;
}

.card:hover{
    transform:translateY(-8px);
    border-color:rgba(59,130,246,.35);
    box-shadow:0 20px 45px rgba(0,0,0,.3);
}

.card img{
    width:100%;
    height:200px;
    object-fit:cover;
}

.card-body{
    padding:24px;
}

.card-tag{
    display:inline-block;
    padding:7px 14px;
    border-radius:999px;
    background:rgba(59,130,246,.12);
    color:#bfdbfe;
    font-size:.72rem;
    margin-bottom:15px;
    font-weight:700;
}

.card h3{
    font-size:1.3rem;
    margin-bottom:12px;
}

.card p{
    color:var(--muted);
    line-height:1.7;
    margin-bottom:22px;
}

.card-actions{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
}

.small-btn{
    padding:11px 18px;
    border-radius:12px;
    text-decoration:none;
    font-weight:700;
    font-size:.9rem;
}

.view-btn{
    background:var(--primary);
    color:white;
}

.external-btn{
    background:rgba(255,255,255,.06);
    color:white;
    border:1px solid rgba(255,255,255,.08);
}

/* ================= STATS ================= */

.stats{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:24px;
}

.stat-box{
    background:rgba(255,255,255,.04);
    border:1px solid rgba(255,255,255,.06);
    border-radius:24px;
    padding:30px;
    text-align:center;
}

.stat-box h2{
    font-size:2.8rem;
    margin-bottom:10px;
    color:#60a5fa;
}

.stat-box p{
    color:var(--muted);
}

/* ================= FOOTER ================= */

footer{
    padding:50px 6%;
    border-top:1px solid rgba(255,255,255,.06);
    text-align:center;
}

footer p{
    color:var(--muted);
    line-height:1.8;
}

/* ================= IFRAME MODAL ================= */

.modal{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.92);
    z-index:9999;
    display:none;
    flex-direction:column;
}

.modal-header{
    height:65px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 20px;
    background:#0f172a;
    border-bottom:1px solid rgba(255,255,255,.08);
}

.modal-header h3{
    font-size:1rem;
}

.close-btn{
    background:#ef4444;
    color:white;
    border:none;
    padding:10px 18px;
    border-radius:12px;
    cursor:pointer;
    font-weight:700;
}

iframe{
    width:100%;
    height:100%;
    border:none;
    background:white;
}

/* ================= MOBILE ================= */

@media(max-width:900px){

.hero{
    flex-direction:column;
    justify-content:center;
    padding-top:120px;
}

.hero-preview{
    width:100%;
}

.hero-actions{
    flex-direction:column;
    align-items:flex-start;
}

.btn{
    width:100%;
    justify-content:center;
}
}
</style>
</head>

<body>

<!-- HERO -->
<section class="hero">

    <div class="hero-content">

        <div class="badge">
            <span class="dot"></span>
            Professional Digital Portfolio & Resource Ecosystem
        </div>

        <h1>
            Build. Showcase.
            <span>Scale Your Brand.</span>
        </h1>

        <p>
            Modern landing page experience for creators, developers,
            entrepreneurs, and AI innovators. Showcase projects,
            premium tools, services, portfolio work, side hustle ideas,
            and digital products professionally on GitHub Pages.
        </p>

        <div class="hero-actions">
            <a href="#projects" class="btn btn-primary">
                Explore Portfolio
            </a>

            <a href="https://debeatzgh1.github.io/" target="_blank" class="btn btn-outline">
                Open Main Hub
            </a>
        </div>

    </div>

    <div class="hero-preview">
        <div class="preview-card">

            <img class="preview-image"
            src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=1200&auto=format&fit=crop"
            alt="Portfolio">

            <div class="preview-content">
                <h3>AI + Creative Portfolio</h3>

                <p>
                    Present your projects with modern visuals,
                    live previews, GitHub integrations,
                    embedded workspaces, and premium landing page sections.
                </p>
            </div>

        </div>
    </div>

</section>

<!-- STATS -->
<section class="section">

    <div class="stats">

        <div class="stat-box">
            <h2>20+</h2>
            <p>Digital Projects</p>
        </div>

        <div class="stat-box">
            <h2>10K+</h2>
            <p>Community Reach</p>
        </div>

        <div class="stat-box">
            <h2>AI</h2>
            <p>Automation Solutions</p>
        </div>

        <div class="stat-box">
            <h2>24/7</h2>
            <p>Online Accessibility</p>
        </div>

    </div>

</section>

<!-- PROJECTS -->
<section class="section" id="projects">

    <div class="section-header">
        <span class="section-tag">Featured Portfolio</span>

        <h2 class="section-title">
            Modern Showcase Projects
        </h2>

        <p class="section-desc">
            Display your best digital products, startup ideas,
            AI tools, blogging resources, design systems,
            and community platforms in one premium interface.
        </p>
    </div>

    <div class="grid">

        <!-- CARD -->

        <div class="card">

            <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1200&auto=format&fit=crop" alt="AI Hub">

            <div class="card-body">

                <span class="card-tag">AI Platform</span>

                <h3>AI Starter Kit</h3>

                <p>
                    Educational AI resources, prompts,
                    productivity systems, and automation workflows
                    for beginners and professionals.
                </p>

                <div class="card-actions">

                    <a href="#" class="small-btn view-btn"
                    onclick="openWorkspace('https://debeatzgh1.github.io/Decode-AI-starter-kit-/','AI Starter Kit')">
                    Live Preview
                    </a>

                    <a href="https://debeatzgh1.github.io/Decode-AI-starter-kit-/"
                    target="_blank"
                    class="small-btn external-btn">
                    Open External
                    </a>

                </div>

            </div>
        </div>

        <!-- CARD -->

        <div class="card">

            <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?q=80&w=1200&auto=format&fit=crop" alt="Business">

            <div class="card-body">

                <span class="card-tag">Business</span>

                <h3>Side Hustle Guide</h3>

                <p>
                    Monetization ideas, digital products,
                    online business systems, and startup resources
                    for creators and entrepreneurs.
                </p>

                <div class="card-actions">

                    <a href="#"
                    class="small-btn view-btn"
                    onclick="openWorkspace('https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/','Side Hustle Guide')">
                    Live Preview
                    </a>

                    <a href="https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/"
                    target="_blank"
                    class="small-btn external-btn">
                    Open External
                    </a>

                </div>

            </div>
        </div>

        <!-- CARD -->

        <div class="card">

            <img src="https://images.unsplash.com/photo-1516321497487-e288fb19713f?q=80&w=1200&auto=format&fit=crop" alt="Portfolio">

            <div class="card-body">

                <span class="card-tag">Creative</span>

                <h3>Personal Portfolio</h3>

                <p>
                    Professional showcase for skills,
                    client projects, UI concepts,
                    development systems, and achievements.
                </p>

                <div class="card-actions">

                    <a href="#"
                    class="small-btn view-btn"
                    onclick="openWorkspace('https://debeatzgh1.github.io/Personal-Portfolio-site-/','Personal Portfolio')">
                    Live Preview
                    </a>

                    <a href="https://debeatzgh1.github.io/Personal-Portfolio-site-/"
                    target="_blank"
                    class="small-btn external-btn">
                    Open External
                    </a>

                </div>

            </div>
        </div>

        <!-- CARD -->

        <div class="card">

            <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=1200&auto=format&fit=crop" alt="Marketing">

            <div class="card-body">

                <span class="card-tag">Marketing</span>

                <h3>Sales & Growth</h3>

                <p>
                    Landing pages, conversion funnels,
                    lead generation tools, and digital
                    marketing interfaces for startups.
                </p>

                <div class="card-actions">

                    <a href="#"
                    class="small-btn view-btn"
                    onclick="openWorkspace('https://debeatzgh1.github.io/sales/','Sales Engine')">
                    Live Preview
                    </a>

                    <a href="https://debeatzgh1.github.io/sales/"
                    target="_blank"
                    class="small-btn external-btn">
                    Open External
                    </a>

                </div>

            </div>
        </div>

    </div>

</section>

<!-- SERVICES -->
<section class="section">

    <div class="section-header">
        <span class="section-tag">Professional Services</span>

        <h2 class="section-title">
            What You Can Showcase
        </h2>
    </div>

    <div class="grid">

        <div class="card">
            <div class="card-body">
                <h3>AI Product Design</h3>
                <p>Create premium AI interfaces, prompt libraries, automation systems, and productivity tools.</p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <h3>Startup Landing Pages</h3>
                <p>Modern responsive pages optimized for GitHub Pages, mobile UX, and fast loading performance.</p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <h3>Digital Product Store</h3>
                <p>Sell ebooks, templates, startup kits, AI prompts, and downloadable digital assets.</p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <h3>Community Platforms</h3>
                <p>Build interactive directories, creator hubs, and resource collections with embedded previews.</p>
            </div>
        </div>

    </div>

</section>

<!-- FOOTER -->
<footer>

    <h2 style="font-size:2rem;margin-bottom:15px;">
        Ready To Build Your Brand?
    </h2>

    <p>
        Professional GitHub Pages landing page optimized for
        creators, developers, startups, side hustlers,
        AI educators, and digital entrepreneurs.
    </p>

    <div style="margin-top:30px;">
        <a href="https://debeatzgh1.github.io/"
        target="_blank"
        class="btn btn-primary">
        Visit Main Ecosystem
        </a>
    </div>

</footer>

<!-- MODAL -->
<div class="modal" id="workspaceModal">

    <div class="modal-header">

        <h3 id="workspaceTitle">
            Workspace Preview
        </h3>

        <button class="close-btn" onclick="closeWorkspace()">
            Close
        </button>

    </div>

    <iframe id="workspaceFrame"></iframe>

</div>

<script>

function openWorkspace(url,title){

    document.getElementById('workspaceModal').style.display='flex';
    document.getElementById('workspaceFrame').src=url;
    document.getElementById('workspaceTitle').innerText=title;

}

function closeWorkspace(){

    document.getElementById('workspaceModal').style.display='none';
    document.getElementById('workspaceFrame').src='';

}

</script>

</body>
</html>
