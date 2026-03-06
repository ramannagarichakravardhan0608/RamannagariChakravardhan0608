<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ramannagari Chakravardhan — AI Engineer | Open to Work</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800;900&family=JetBrains+Mono:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
<style>
:root {
  --cyan:       #00E5FF;
  --cyan2:      #00BFFF;
  --cyan-soft:  rgba(0,229,255,0.12);
  --cyan-glow:  rgba(0,229,255,0.06);
  --green:      #22c55e;
  --green-soft: rgba(34,197,94,0.12);
  --bg:         #020912;
  --bg2:        #080f1d;
  --bg3:        #0c1526;
  --border:     #162032;
  --border2:    #1e2e45;
  --text:       #ccd6f6;
  --muted:      #7a8ba8;
  --white:      #ffffff;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
html{scroll-behavior:smooth;}
body{
  background:var(--bg);
  color:var(--text);
  font-family:'JetBrains Mono',monospace;
  overflow-x:hidden;
  cursor:none;
}

/* ─── CURSOR ─── */
#cur{position:fixed;width:10px;height:10px;background:var(--cyan);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:width .2s,height .2s;mix-blend-mode:screen;}
#cur-ring{position:fixed;width:34px;height:34px;border:1px solid var(--cyan);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);opacity:.45;transition:width .3s,height .3s,opacity .3s;}
a:hover~#cur,button:hover~#cur{width:18px;height:18px;}

/* ─── CANVAS ─── */
#cvs{position:fixed;inset:0;z-index:0;pointer-events:none;}

/* ─── OPEN TO WORK BANNER ─── */
.otw-bar{
  position:fixed;top:0;left:0;right:0;z-index:200;
  background:linear-gradient(90deg,var(--green) 0%,#16a34a 50%,var(--green) 100%);
  background-size:200% 100%;
  animation:barShine 3s linear infinite;
  text-align:center;
  padding:9px 16px;
  font-family:'Syne',sans-serif;
  font-size:13px;
  font-weight:700;
  letter-spacing:.12em;
  color:#fff;
  display:flex;align-items:center;justify-content:center;gap:12px;
}
@keyframes barShine{0%{background-position:0%}100%{background-position:200%}}
.otw-dot{width:8px;height:8px;border-radius:50%;background:#fff;animation:pulse 1.4s ease-in-out infinite;}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(.6)}}
.otw-bar a{color:#fff;text-decoration:underline;underline-offset:2px;font-weight:800;cursor:pointer;}

/* ─── NAV ─── */
nav{
  position:fixed;top:36px;left:0;right:0;z-index:100;
  background:rgba(2,9,18,.88);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border);
  padding:13px 40px;
  display:flex;align-items:center;justify-content:space-between;
}
.nav-logo{font-family:'Syne',sans-serif;font-weight:900;font-size:18px;color:var(--white);}
.nav-logo span{color:var(--cyan);}
.nav-links{display:flex;gap:32px;}
.nav-links a{font-size:11px;color:var(--muted);text-decoration:none;letter-spacing:.1em;text-transform:uppercase;transition:color .2s;}
.nav-links a:hover{color:var(--cyan);}
.nav-hire{
  display:inline-flex;align-items:center;gap:7px;
  background:var(--cyan);color:var(--bg);
  padding:8px 18px;border-radius:6px;
  font-family:'Syne',sans-serif;font-weight:800;font-size:11px;
  text-decoration:none;letter-spacing:.08em;
  transition:all .25s;
  box-shadow:0 0 20px rgba(0,229,255,.3);
}
.nav-hire:hover{background:#fff;box-shadow:0 0 40px rgba(0,229,255,.5);transform:translateY(-1px);}
@media(max-width:680px){.nav-links{display:none;}}

/* ─── LAYOUT ─── */
.wrap{max-width:1080px;margin:0 auto;padding:0 28px;position:relative;z-index:1;}

/* ─── HERO ─── */
.hero{
  min-height:100vh;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  text-align:center;
  padding:120px 28px 80px;
  position:relative;
}
.hero-grid{
  position:absolute;inset:0;
  background-image:
    linear-gradient(rgba(0,229,255,.035) 1px,transparent 1px),
    linear-gradient(90deg,rgba(0,229,255,.035) 1px,transparent 1px);
  background-size:55px 55px;
  mask-image:radial-gradient(ellipse 75% 75% at 50% 50%,black 20%,transparent 100%);
}
.hero-radial{
  position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  width:800px;height:600px;
  background:radial-gradient(ellipse,rgba(0,229,255,.07) 0%,transparent 65%);
  pointer-events:none;
}

.otw-chip{
  display:inline-flex;align-items:center;gap:9px;
  background:var(--green-soft);border:1px solid rgba(34,197,94,.35);
  border-radius:999px;padding:7px 20px;
  font-size:12px;color:var(--green);letter-spacing:.1em;font-weight:700;
  margin-bottom:30px;
  animation:fadeUp .8s ease both;
}
.otw-chip-dot{width:7px;height:7px;border-radius:50%;background:var(--green);box-shadow:0 0 10px var(--green);animation:pulse 1.4s ease-in-out infinite;}

.hero-name{
  font-family:'Syne',sans-serif;
  font-size:clamp(2.6rem,6.5vw,5.2rem);
  font-weight:900;line-height:1.02;
  letter-spacing:-.025em;color:var(--white);
  animation:fadeUp .9s .08s ease both;
}
.hero-name .grad{
  background:linear-gradient(135deg,var(--cyan) 0%,var(--cyan2) 45%,#a5f3fc 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}

.hero-typerow{
  margin-top:16px;
  font-size:clamp(.85rem,2vw,1.05rem);
  color:var(--muted);
  letter-spacing:.04em;
  min-height:1.6em;
  animation:fadeUp .9s .16s ease both;
}
.hero-typerow .typed{color:var(--cyan);}
.blink{border-right:2px solid var(--cyan);animation:blink .8s step-end infinite;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.hero-para{
  max-width:580px;margin:20px auto 0;
  font-size:.9rem;color:var(--muted);line-height:1.9;
  animation:fadeUp .9s .24s ease both;
}
.hero-para strong{color:var(--text);}

.hero-chips{
  display:flex;flex-wrap:wrap;gap:10px;justify-content:center;
  margin-top:32px;
  animation:fadeUp .9s .32s ease both;
}
.chip{
  display:inline-flex;align-items:center;gap:7px;
  background:var(--bg2);border:1px solid var(--border2);
  border-radius:7px;padding:8px 16px;font-size:11px;color:var(--muted);
  letter-spacing:.04em;transition:all .25s;
}
.chip:hover{border-color:var(--cyan);color:var(--cyan);background:var(--cyan-soft);transform:translateY(-2px);}

.hero-cta{
  display:flex;gap:14px;flex-wrap:wrap;justify-content:center;
  margin-top:40px;
  animation:fadeUp .9s .4s ease both;
}
.btn-p{
  display:inline-flex;align-items:center;gap:9px;
  background:var(--cyan);color:var(--bg);
  padding:13px 30px;border-radius:8px;
  font-family:'Syne',sans-serif;font-weight:800;font-size:13px;
  text-decoration:none;letter-spacing:.06em;
  transition:all .25s;
  box-shadow:0 0 35px rgba(0,229,255,.3);
}
.btn-p:hover{background:#fff;transform:translateY(-3px);box-shadow:0 0 60px rgba(0,229,255,.55);}
.btn-o{
  display:inline-flex;align-items:center;gap:9px;
  background:transparent;color:var(--cyan);
  padding:13px 30px;border-radius:8px;
  font-family:'Syne',sans-serif;font-weight:700;font-size:13px;
  text-decoration:none;letter-spacing:.06em;
  border:1.5px solid rgba(0,229,255,.5);
  transition:all .25s;
}
.btn-o:hover{background:var(--cyan-soft);border-color:var(--cyan);transform:translateY(-3px);box-shadow:0 0 30px rgba(0,229,255,.12);}

.scroll-ind{
  position:absolute;bottom:36px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  color:var(--muted);font-size:10px;letter-spacing:.14em;
  animation:fadeIn 1.2s 1.2s both;
}
.scroll-track{width:22px;height:34px;border:1.5px solid var(--border2);border-radius:999px;display:flex;align-items:flex-start;justify-content:center;padding-top:5px;}
.scroll-track::after{content:'';width:4px;height:9px;background:var(--cyan);border-radius:2px;animation:scrollBounce 2s ease-in-out infinite;}
@keyframes scrollBounce{0%,100%{transform:translateY(0);opacity:1}60%{transform:translateY(10px);opacity:.2}}

/* ─── SECTIONS ─── */
section{padding:96px 0;}
.sec-tag{font-size:11px;letter-spacing:.18em;color:var(--cyan);text-transform:uppercase;margin-bottom:6px;display:flex;align-items:center;gap:10px;}
.sec-tag::after{content:'';flex:1;max-width:50px;height:1px;background:var(--cyan);opacity:.35;}
.sec-h{font-family:'Syne',sans-serif;font-size:clamp(1.7rem,3.5vw,2.5rem);font-weight:800;color:var(--white);margin-bottom:48px;}
.sec-h span{color:var(--cyan);}

/* ─── IDENTITY CARD ─── */
.id-card{
  background:var(--bg2);border:1px solid var(--border2);
  border-radius:16px;padding:36px 40px;
  position:relative;overflow:hidden;
}
.id-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--cyan),transparent);animation:sweep 3s ease-in-out infinite;}
@keyframes sweep{0%,100%{opacity:.4}50%{opacity:1}}
.id-card::after{content:'';position:absolute;top:-80px;right:-80px;width:200px;height:200px;background:radial-gradient(circle,rgba(0,229,255,.04),transparent 70%);pointer-events:none;}
.id-row{display:grid;grid-template-columns:110px 16px 1fr;align-items:baseline;padding:4px 0;gap:0;}
.id-k{color:var(--cyan);font-size:13px;}
.id-a{color:var(--muted);font-size:13px;text-align:center;}
.id-v{color:var(--text);font-size:13px;}
.id-v.g{color:var(--green);font-weight:700;}
.id-v.c{color:var(--cyan);}
.id-v a{color:inherit;text-decoration:none;}
.id-v a:hover{text-decoration:underline;}

/* ─── HIGHLIGHT CARDS ─── */
.hi-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:14px;margin-top:32px;}
.hi-card{
  background:var(--bg2);border:1px solid var(--border2);
  border-radius:12px;padding:22px 20px;
  display:flex;align-items:flex-start;gap:14px;
  transition:all .3s;
}
.hi-card:hover{border-color:var(--border2);background:var(--bg3);transform:translateY(-3px);box-shadow:0 8px 40px rgba(0,229,255,.05);}
.hi-icon{font-size:22px;flex-shrink:0;margin-top:2px;}
.hi-label{font-family:'Syne',sans-serif;font-size:13px;font-weight:700;color:var(--white);}
.hi-sub{font-size:11px;color:var(--muted);margin-top:4px;line-height:1.6;}

/* ─── SKILLS ─── */
.tech-group{margin-bottom:32px;}
.tech-group-label{font-size:11px;letter-spacing:.12em;color:var(--muted);text-transform:uppercase;margin-bottom:12px;}
.tech-row{display:flex;flex-wrap:wrap;gap:9px;}
.tech-pill{
  display:inline-flex;align-items:center;gap:8px;
  background:var(--bg2);border:1px solid var(--border2);
  border-radius:8px;padding:9px 16px;font-size:12px;color:var(--muted);
  transition:all .22s;
}
.tech-pill:hover{border-color:var(--cyan);color:var(--cyan);background:var(--cyan-glow);transform:translateY(-2px);}
.tech-pill .ic{width:9px;height:9px;border-radius:50%;flex-shrink:0;}

.skill-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:14px;margin-top:36px;}
.sk-card{background:var(--bg2);border:1px solid var(--border2);border-radius:12px;padding:24px;transition:all .3s;position:relative;overflow:hidden;}
.sk-card::after{content:'';position:absolute;inset:0;background:radial-gradient(circle at 85% 15%,rgba(0,229,255,.05),transparent 55%);opacity:0;transition:opacity .3s;}
.sk-card:hover{border-color:var(--border2);transform:translateY(-4px);box-shadow:0 10px 40px rgba(0,229,255,.06);}
.sk-card:hover::after{opacity:1;}
.sk-em{font-size:26px;margin-bottom:12px;}
.sk-title{font-family:'Syne',sans-serif;font-weight:800;font-size:14px;color:var(--white);margin-bottom:12px;}
.tags{display:flex;flex-wrap:wrap;gap:6px;}
.tag{background:rgba(0,229,255,.07);border:1px solid rgba(0,229,255,.14);color:var(--cyan);font-size:11px;padding:3px 10px;border-radius:4px;letter-spacing:.03em;}

/* ─── PROJECTS ─── */
.proj-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(470px,1fr));gap:24px;}
@media(max-width:540px){.proj-grid{grid-template-columns:1fr;}}
.proj-card{
  background:var(--bg2);border:1px solid var(--border2);
  border-radius:18px;padding:34px;
  display:flex;flex-direction:column;gap:18px;
  transition:all .35s;position:relative;overflow:hidden;
}
.proj-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,var(--cyan),var(--cyan2),#a5f3fc);
  transform:scaleX(0);transform-origin:left;transition:transform .45s ease;
}
.proj-card::after{content:'';position:absolute;top:-60px;right:-60px;width:180px;height:180px;background:radial-gradient(circle,rgba(0,229,255,.04),transparent 60%);pointer-events:none;}
.proj-card:hover{border-color:var(--border2);transform:translateY(-8px);box-shadow:0 20px 70px rgba(0,229,255,.09);}
.proj-card:hover::before{transform:scaleX(1);}
.proj-em{font-size:36px;}
.proj-title{font-family:'Syne',sans-serif;font-weight:900;font-size:1.25rem;color:var(--white);}
.proj-sub{font-size:11px;color:var(--cyan);letter-spacing:.1em;text-transform:uppercase;margin-top:2px;}
.proj-meta{background:var(--bg);border:1px solid var(--border);border-radius:8px;padding:14px 18px;font-size:12px;line-height:2.1;}
.mk{color:var(--muted);}
.mv{color:var(--cyan);}
.proj-desc{font-size:13px;color:var(--muted);line-height:1.85;}
.proj-feats{list-style:none;display:flex;flex-direction:column;gap:8px;}
.proj-feats li{font-size:13px;color:var(--text);display:flex;gap:10px;align-items:flex-start;}
.proj-feats li::before{content:'▸';color:var(--cyan);flex-shrink:0;margin-top:1px;}
.proj-links{display:flex;gap:10px;margin-top:4px;flex-wrap:wrap;}
.proj-btn{
  display:inline-flex;align-items:center;gap:8px;
  background:transparent;border:1px solid var(--border2);
  color:var(--muted);padding:9px 18px;border-radius:7px;
  font-size:12px;text-decoration:none;letter-spacing:.04em;
  transition:all .22s;
}
.proj-btn:hover{border-color:var(--cyan);color:var(--cyan);background:var(--cyan-soft);}
.proj-btn.primary{background:var(--cyan-soft);border-color:rgba(0,229,255,.4);color:var(--cyan);}
.proj-btn.primary:hover{background:var(--cyan);color:var(--bg);font-weight:700;}

/* ─── STATS ─── */
.stats-row{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:14px;margin-bottom:44px;}
.st-card{background:var(--bg2);border:1px solid var(--border2);border-radius:12px;padding:26px;text-align:center;transition:all .25s;}
.st-card:hover{border-color:rgba(0,229,255,.35);transform:translateY(-3px);box-shadow:0 8px 30px rgba(0,229,255,.07);}
.st-num{font-family:'Syne',sans-serif;font-size:2.4rem;font-weight:900;color:var(--cyan);}
.st-lbl{font-size:11px;color:var(--muted);margin-top:5px;letter-spacing:.08em;text-transform:uppercase;}

.analytics-wrap{display:flex;flex-direction:column;gap:18px;align-items:center;}
.analytics-row{display:flex;flex-wrap:wrap;gap:18px;justify-content:center;width:100%;}
.analytics-wrap img{border-radius:12px;border:1px solid var(--border2);max-width:100%;}

/* ─── CONNECT ─── */
.connect-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:16px;}
.con-card{
  background:var(--bg2);border:1px solid var(--border2);
  border-radius:14px;padding:28px 24px;
  text-decoration:none;color:inherit;
  display:flex;align-items:center;gap:20px;
  transition:all .3s;position:relative;overflow:hidden;
}
.con-card::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(0,229,255,.03),transparent 60%);opacity:0;transition:opacity .3s;}
.con-card:hover{transform:translateY(-5px);box-shadow:0 14px 50px rgba(0,229,255,.1);}
.con-card:hover::before{opacity:1;}
.con-card.github:hover{border-color:rgba(255,255,255,.25);}
.con-card.gmail:hover{border-color:rgba(234,67,53,.4);}
.con-card.linkedin:hover{border-color:rgba(10,102,194,.5);}
.con-icon{width:52px;height:52px;border-radius:13px;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:24px;}
.con-title{font-family:'Syne',sans-serif;font-weight:800;font-size:16px;color:var(--white);}
.con-sub{font-size:12px;color:var(--muted);margin-top:4px;line-height:1.5;word-break:break-all;}
.con-arrow{margin-left:auto;color:var(--muted);flex-shrink:0;font-size:18px;transition:transform .2s,color .2s;}
.con-card:hover .con-arrow{transform:translateX(4px);color:var(--cyan);}

/* ─── OPEN TO WORK SECTION ─── */
.otw-section{
  background:linear-gradient(135deg,rgba(34,197,94,.08) 0%,rgba(0,229,255,.05) 100%);
  border:1px solid rgba(34,197,94,.25);
  border-radius:20px;padding:48px 44px;
  text-align:center;
  position:relative;overflow:hidden;
  margin-top:24px;
}
.otw-section::before{content:'';position:absolute;top:-80px;left:50%;transform:translateX(-50%);width:400px;height:200px;background:radial-gradient(ellipse,rgba(34,197,94,.08),transparent 70%);}
.otw-title{font-family:'Syne',sans-serif;font-size:clamp(1.6rem,3vw,2.4rem);font-weight:900;color:var(--white);margin-bottom:14px;}
.otw-title .g{color:var(--green);}
.otw-para{font-size:14px;color:var(--muted);max-width:540px;margin:0 auto 28px;line-height:1.8;}
.otw-roles{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-bottom:32px;}
.role-pill{background:rgba(34,197,94,.1);border:1px solid rgba(34,197,94,.25);color:var(--green);font-size:12px;padding:7px 18px;border-radius:999px;letter-spacing:.06em;font-weight:600;}
.otw-cta{display:flex;gap:14px;flex-wrap:wrap;justify-content:center;}
.btn-hire{
  display:inline-flex;align-items:center;gap:9px;
  background:var(--green);color:#fff;
  padding:14px 32px;border-radius:9px;
  font-family:'Syne',sans-serif;font-weight:800;font-size:14px;
  text-decoration:none;letter-spacing:.06em;
  transition:all .25s;
  box-shadow:0 0 35px rgba(34,197,94,.3);
}
.btn-hire:hover{background:#16a34a;transform:translateY(-3px);box-shadow:0 0 60px rgba(34,197,94,.5);}
.btn-resume{
  display:inline-flex;align-items:center;gap:9px;
  background:transparent;color:var(--green);
  padding:14px 32px;border-radius:9px;
  font-family:'Syne',sans-serif;font-weight:700;font-size:14px;
  text-decoration:none;letter-spacing:.06em;
  border:1.5px solid rgba(34,197,94,.5);
  transition:all .25s;
}
.btn-resume:hover{background:rgba(34,197,94,.1);transform:translateY(-3px);}

/* ─── QUOTE ─── */
.quote-box{
  background:var(--bg2);border:1px solid var(--border2);
  border-left:3px solid var(--cyan);
  border-radius:0 14px 14px 0;padding:30px 36px;margin-top:40px;
}
.q-text{font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:600;color:var(--white);font-style:italic;line-height:1.75;}
.q-by{font-size:12px;color:var(--cyan);margin-top:12px;letter-spacing:.1em;}

/* ─── FOOTER ─── */
footer{border-top:1px solid var(--border);padding:44px 0;text-align:center;color:var(--muted);}
.ft-name{font-family:'Syne',sans-serif;font-weight:900;font-size:18px;color:var(--white);margin-bottom:8px;}
.ft-tag{color:var(--cyan);letter-spacing:.08em;font-size:13px;margin-bottom:14px;}
.ft-links{display:flex;gap:24px;justify-content:center;flex-wrap:wrap;margin-top:18px;}
.ft-links a{font-size:12px;color:var(--muted);text-decoration:none;transition:color .2s;}
.ft-links a:hover{color:var(--cyan);}
.ft-copy{font-size:11px;color:var(--border2);margin-top:16px;}

/* ─── DIVIDER ─── */
.div{height:1px;background:linear-gradient(90deg,transparent,var(--border),transparent);margin:0;}

/* ─── ANIMATIONS ─── */
@keyframes fadeUp{from{opacity:0;transform:translateY(26px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
.rev{opacity:0;transform:translateY(28px);transition:opacity .7s ease,transform .7s ease;}
.rev.on{opacity:1;transform:translateY(0);}
</style>
</head>
<body>

<canvas id="cvs"></canvas>
<div id="cur"></div>
<div id="cur-ring"></div>

<!-- OPEN TO WORK TOP BAR -->
<div class="otw-bar">
  <div class="otw-dot"></div>
  🚀 &nbsp;ACTIVELY LOOKING FOR OPPORTUNITIES — AI / ML / Data Science Roles&nbsp;&nbsp;
  <a href="mailto:chakravardhanramannagari06@gmail.com">Hire Me →</a>
  <div class="otw-dot"></div>
</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">RC<span>.</span></div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#stats">Stats</a>
    <a href="#connect">Connect</a>
  </div>
  <a class="nav-hire" href="mailto:chakravardhanramannagari06@gmail.com">
    ✉ Hire Me
  </a>
</nav>

<!-- ══════ HERO ══════ -->
<section class="hero" id="hero">
  <div class="hero-grid"></div>
  <div class="hero-radial"></div>

  <div class="otw-chip">
    <div class="otw-chip-dot"></div>
    ✅ &nbsp;OPEN TO WORK — Actively Seeking Roles
  </div>

  <h1 class="hero-name">
    Ramannagari<br/><span class="grad">Chakravardhan</span>
  </h1>

  <div class="hero-typerow">
    <span class="typed" id="typed"></span><span class="blink">&nbsp;</span>
  </div>

  <p class="hero-para">
    AI / Machine Learning Engineer building <strong>scalable, production-grade intelligent systems</strong> — from raw data pipelines to deployed models that solve real-world problems at scale.
  </p>

  <div class="hero-chips">
    <div class="chip">📍 Hyderabad, India 🇮🇳</div>
    <div class="chip">🧠 NLP · Computer Vision · Deep Learning</div>
    <div class="chip">⚡ LangChain · FastAPI · Streamlit</div>
    <div class="chip">✉ chakravardhanramannagari06@gmail.com</div>
  </div>

  <div class="hero-cta">
    <a class="btn-p" href="mailto:chakravardhanramannagari06@gmail.com">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      Hire Me — Let's Talk
    </a>
    <a class="btn-o" href="https://github.com/ramannagarichakravardhan0608" target="_blank">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
      View GitHub
    </a>
  </div>

  <div class="scroll-ind">
    <div class="scroll-track"></div>
    SCROLL
  </div>
</section>

<div class="div"></div>

<!-- ══════ ABOUT ══════ -->
<section id="about">
  <div class="wrap">
    <div class="rev"><div class="sec-tag">01 &nbsp;About</div><h2 class="sec-h">Who <span>I Am</span></h2></div>
    <div class="rev" style="transition-delay:.1s">
      <div class="id-card">
        <div class="id-row"><span class="id-k">Name    </span><span class="id-a">→</span><span class="id-v">Ramannagari Chakravardhan</span></div>
        <div class="id-row"><span class="id-k">Role    </span><span class="id-a">→</span><span class="id-v">AI Engineer · ML Engineer · Data Scientist</span></div>
        <div class="id-row"><span class="id-k">Focus   </span><span class="id-a">→</span><span class="id-v">End-to-End ML Pipelines · NLP · CV · Deployment</span></div>
        <div class="id-row"><span class="id-k">Location</span><span class="id-a">→</span><span class="id-v">Hyderabad, Telangana, India 🇮🇳</span></div>
        <div class="id-row"><span class="id-k">Email   </span><span class="id-a">→</span><span class="id-v c"><a href="mailto:chakravardhanramannagari06@gmail.com">chakravardhanramannagari06@gmail.com</a></span></div>
        <div class="id-row"><span class="id-k">GitHub  </span><span class="id-a">→</span><span class="id-v c"><a href="https://github.com/ramannagarichakravardhan0608" target="_blank">github.com/ramannagarichakravardhan0608</a></span></div>
        <div class="id-row"><span class="id-k">Status  </span><span class="id-a">→</span><span class="id-v g">🟢 Actively Looking for Opportunities</span></div>
        <div class="id-row"><span class="id-k">Mission </span><span class="id-a">→</span><span class="id-v">Build AI that scales, ships &amp; solves real problems</span></div>
      </div>
    </div>

    <div class="hi-grid rev" style="transition-delay:.18s">
      <div class="hi-card"><div class="hi-icon">🔁</div><div><div class="hi-label">End-to-End Pipelines</div><div class="hi-sub">Data ingestion → Training → Serving</div></div></div>
      <div class="hi-card"><div class="hi-icon">⚙️</div><div><div class="hi-label">Model Deployment</div><div class="hi-sub">Flask · FastAPI · Streamlit</div></div></div>
      <div class="hi-card"><div class="hi-icon">🧠</div><div><div class="hi-label">NLP &amp; LLMs</div><div class="hi-sub">LangChain · Transformers · LSTM</div></div></div>
      <div class="hi-card"><div class="hi-icon">👁️</div><div><div class="hi-label">Computer Vision</div><div class="hi-sub">OpenCV · CNN · Feature Extraction</div></div></div>
    </div>

    <div class="rev" style="transition-delay:.24s">
      <div class="quote-box">
        <div class="q-text">"To engineer intelligent, production-ready AI systems that operate reliably at scale — solving real business problems with measurable, data-backed, and lasting impact."</div>
        <div class="q-by">— Ramannagari Chakravardhan</div>
      </div>
    </div>
  </div>
</section>

<div class="div"></div>

<!-- ══════ SKILLS ══════ -->
<section id="skills">
  <div class="wrap">
    <div class="rev"><div class="sec-tag">02 &nbsp;Arsenal</div><h2 class="sec-h">Technical <span>Stack</span></h2></div>

    <div class="rev" style="transition-delay:.1s">
      <div class="tech-group">
        <div class="tech-group-label">▸ Languages &amp; Frameworks</div>
        <div class="tech-row">
          <div class="tech-pill"><div class="ic" style="background:#3776ab"></div>Python</div>
          <div class="tech-pill"><div class="ic" style="background:#FF6F00"></div>TensorFlow</div>
          <div class="tech-pill"><div class="ic" style="background:#EE4C2C"></div>PyTorch</div>
          <div class="tech-pill"><div class="ic" style="background:#F7931E"></div>Scikit-Learn</div>
          <div class="tech-pill"><div class="ic" style="background:#5C3EE8"></div>OpenCV</div>
          <div class="tech-pill"><div class="ic" style="background:var(--cyan)"></div>LangChain</div>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-group-label">▸ Data · APIs · Deployment</div>
        <div class="tech-row">
          <div class="tech-pill"><div class="ic" style="background:#150458"></div>Pandas</div>
          <div class="tech-pill"><div class="ic" style="background:#4db6ac"></div>NumPy</div>
          <div class="tech-pill"><div class="ic" style="background:#009688"></div>FastAPI</div>
          <div class="tech-pill"><div class="ic" style="background:#aaa"></div>Flask</div>
          <div class="tech-pill"><div class="ic" style="background:#FF4B4B"></div>Streamlit</div>
        </div>
      </div>
      <div class="tech-group">
        <div class="tech-group-label">▸ Databases &amp; DevTools</div>
        <div class="tech-row">
          <div class="tech-pill"><div class="ic" style="background:#4479A1"></div>MySQL</div>
          <div class="tech-pill"><div class="ic" style="background:#F05032"></div>Git</div>
          <div class="tech-pill"><div class="ic" style="background:#fff"></div>GitHub</div>
          <div class="tech-pill"><div class="ic" style="background:#007ACC"></div>VS Code</div>
        </div>
      </div>
    </div>

    <div class="skill-grid rev" style="transition-delay:.18s">
      <div class="sk-card"><div class="sk-em">🎯</div><div class="sk-title">Classical ML</div><div class="tags"><span class="tag">Linear Regression</span><span class="tag">Logistic Regression</span><span class="tag">Decision Trees</span><span class="tag">Random Forest</span><span class="tag">XGBoost</span><span class="tag">AdaBoost</span></div></div>
      <div class="sk-card"><div class="sk-em">🧬</div><div class="sk-title">Deep Learning</div><div class="tags"><span class="tag">CNN</span><span class="tag">RNN</span><span class="tag">LSTM</span><span class="tag">GRU</span><span class="tag">Transformers</span></div></div>
      <div class="sk-card"><div class="sk-em">🗣️</div><div class="sk-title">NLP</div><div class="tags"><span class="tag">Tokenization</span><span class="tag">Embeddings</span><span class="tag">Text Classification</span><span class="tag">LangChain</span><span class="tag">Semantic Search</span></div></div>
      <div class="sk-card"><div class="sk-em">📸</div><div class="sk-title">Computer Vision</div><div class="tags"><span class="tag">OpenCV</span><span class="tag">Image Processing</span><span class="tag">Feature Extraction</span><span class="tag">Object Detection</span></div></div>
    </div>
  </div>
</section>

<div class="div"></div>

<!-- ══════ PROJECTS ══════ -->
<section id="projects">
  <div class="wrap">
    <div class="rev"><div class="sec-tag">03 &nbsp;Work</div><h2 class="sec-h">Featured <span>Projects</span></h2></div>
    <div class="proj-grid">

      <div class="proj-card rev" style="transition-delay:.1s">
        <div class="proj-em">🤖</div>
        <div><div class="proj-title">AI Chatbot Mentor</div><div class="proj-sub">Restricted Learning Assistant</div></div>
        <div class="proj-meta">
          <div><span class="mk">Stack </span>→ <span class="mv">LangChain · Streamlit · Python</span></div>
          <div><span class="mk">Type  </span>→ <span class="mv">NLP Application</span></div>
          <div><span class="mk">Mode  </span>→ <span class="mv">Production-Ready</span></div>
        </div>
        <p class="proj-desc">A domain-scoped AI chatbot enforcing controlled knowledge boundaries — built for structured, safe, and guided learning environments.</p>
        <ul class="proj-feats">
          <li>Secure prompt routing &amp; scoped context via <strong>LangChain</strong></li>
          <li>Real-time interactive UI built with <strong>Streamlit</strong></li>
          <li>Modular architecture — easy to extend per domain</li>
          <li>Topic guards prevent hallucination drift</li>
        </ul>
        <div class="proj-links">
          <a class="proj-btn primary" href="https://github.com/ramannagarichakravardhan0608/AI-Chatbot-Mentor-Module-Restricted-Learning-Assistant-using-Streamlit-LangChain" target="_blank">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            Open on GitHub ↗
          </a>
        </div>
      </div>

      <div class="proj-card rev" style="transition-delay:.2s">
        <div class="proj-em">🎮</div>
        <div><div class="proj-title">n8n Auto Game Generator</div><div class="proj-sub">AI Workflow Automation Pipeline</div></div>
        <div class="proj-meta">
          <div><span class="mk">Stack </span>→ <span class="mv">n8n · Python · AI APIs</span></div>
          <div><span class="mk">Type  </span>→ <span class="mv">Automation Pipeline</span></div>
          <div><span class="mk">Mode  </span>→ <span class="mv">Zero-Touch Execution</span></div>
        </div>
        <p class="proj-desc">Fully automated AI-powered pipeline that generates, writes, and executes Python game logic — completely hands-free from trigger to output.</p>
        <ul class="proj-feats">
          <li>End-to-end orchestration via <strong>n8n</strong> workflows</li>
          <li>AI-generated game logic via prompt engineering</li>
          <li>Zero-touch: trigger → generate → execute</li>
          <li>Extensible architecture — add new game types easily</li>
        </ul>
        <div class="proj-links">
          <a class="proj-btn primary" href="https://github.com/ramannagarichakravardhan0608/n8n-auto-game-generator" target="_blank">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            Open on GitHub ↗
          </a>
        </div>
      </div>

    </div>
  </div>
</section>

<div class="div"></div>

<!-- ══════ STATS ══════ -->
<section id="stats">
  <div class="wrap">
    <div class="rev"><div class="sec-tag">04 &nbsp;Analytics</div><h2 class="sec-h">GitHub <span>Stats</span></h2></div>

    <div class="stats-row rev" style="transition-delay:.1s">
      <div class="st-card"><div class="st-num" id="s-repos">—</div><div class="st-lbl">Public Repos</div></div>
      <div class="st-card"><div class="st-num" id="s-followers">—</div><div class="st-lbl">Followers</div></div>
      <div class="st-card"><div class="st-num" id="s-following">—</div><div class="st-lbl">Following</div></div>
      <div class="st-card"><div class="st-num">2+</div><div class="st-lbl">AI Projects</div></div>
      <div class="st-card"><div class="st-num">100%</div><div class="st-lbl">Python</div></div>
    </div>

    <div class="analytics-wrap rev" style="transition-delay:.16s">
      <div class="analytics-row">
        <img src="https://github-readme-stats.vercel.app/api?username=ramannagarichakravardhan0608&show_icons=true&theme=github_dark&title_color=00E5FF&icon_color=00E5FF&border_color=162032&bg_color=020912&include_all_commits=true&count_private=true&rank_icon=github" height="170" alt="GitHub Stats"/>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ramannagarichakravardhan0608&layout=compact&theme=github_dark&title_color=00E5FF&border_color=162032&bg_color=020912&langs_count=8" height="170" alt="Top Langs"/>
      </div>
      <div class="analytics-row">
        <img src="https://github-readme-streak-stats.herokuapp.com?user=ramannagarichakravardhan0608&theme=dark&background=020912&border=162032&ring=00E5FF&fire=00BFFF&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=00E5FF&sideLabels=8892B0&dates=7a8ba8" height="170" alt="Streak"/>
      </div>
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=ramannagarichakravardhan0608&bg_color=020912&color=00E5FF&line=00E5FF&point=ffffff&area=true&area_color=003355&border_color=162032&custom_title=Contribution+Activity" style="width:100%;max-width:960px;border-radius:12px;border:1px solid #162032;" alt="Activity"/>
      <img src="https://github-profile-trophy.vercel.app/?username=ramannagarichakravardhan0608&theme=darkhub&no-frame=true&no-bg=true&margin-w=6&column=7" style="width:100%;max-width:960px;" alt="Trophies"/>
    </div>
  </div>
</section>

<div class="div"></div>

<!-- ══════ CONNECT ══════ -->
<section id="connect">
  <div class="wrap">
    <div class="rev"><div class="sec-tag">05 &nbsp;Connect</div><h2 class="sec-h">Let's <span>Work Together</span></h2></div>

    <!-- OPEN TO WORK BOX -->
    <div class="otw-section rev" style="transition-delay:.1s">
      <div class="otw-title">🟢 I'm <span class="g">Open to Work</span></div>
      <p class="otw-para">I'm actively seeking full-time, part-time, freelance, or internship roles in AI, ML, Data Science, and related fields. If you're building something incredible — let's talk.</p>
      <div class="otw-roles">
        <div class="role-pill">AI Engineer</div>
        <div class="role-pill">ML Engineer</div>
        <div class="role-pill">Data Scientist</div>
        <div class="role-pill">NLP Engineer</div>
        <div class="role-pill">Computer Vision Engineer</div>
        <div class="role-pill">MLOps Engineer</div>
      </div>
      <div class="otw-cta">
        <a class="btn-hire" href="mailto:chakravardhanramannagari06@gmail.com">
          ✉ &nbsp;Email Me Now
        </a>
        <a class="btn-resume" href="https://github.com/ramannagarichakravardhan0608" target="_blank">
          View My Work →
        </a>
      </div>
    </div>

    <br/><br/>

    <div class="connect-grid rev" style="transition-delay:.2s">

      <a class="con-card github" href="https://github.com/ramannagarichakravardhan0608" target="_blank">
        <div class="con-icon" style="background:rgba(255,255,255,.07)">
          <svg width="26" height="26" viewBox="0 0 24 24" fill="white"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
        </div>
        <div style="flex:1">
          <div class="con-title">GitHub</div>
          <div class="con-sub">ramannagarichakravardhan0608<br/><span style="color:var(--cyan);font-size:11px;">View all projects & code ↗</span></div>
        </div>
        <div class="con-arrow">→</div>
      </a>

      <a class="con-card gmail" href="mailto:chakravardhanramannagari06@gmail.com">
        <div class="con-icon" style="background:rgba(234,67,53,.1)">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#EA4335" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        </div>
        <div style="flex:1">
          <div class="con-title">Gmail</div>
          <div class="con-sub">chakravardhanramannagari06@gmail.com<br/><span style="color:#EA4335;font-size:11px;">Click to send email directly ↗</span></div>
        </div>
        <div class="con-arrow">→</div>
      </a>

      <a class="con-card linkedin" href="https://linkedin.com/in/ramannagarichakravardhan" target="_blank">
        <div class="con-icon" style="background:rgba(10,102,194,.1)">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="#0A66C2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        </div>
        <div style="flex:1">
          <div class="con-title">LinkedIn</div>
          <div class="con-sub">Ramannagari Chakravardhan<br/><span style="color:#0A66C2;font-size:11px;">Connect professionally ↗</span></div>
        </div>
        <div class="con-arrow">→</div>
      </a>

    </div>
  </div>
</section>

<!-- ══════ FOOTER ══════ -->
<footer>
  <div class="wrap">
    <div class="ft-name">Ramannagari Chakravardhan</div>
    <div class="ft-tag">✦ Engineering Intelligence — Built for Production ✦</div>
    <div style="color:var(--muted);font-size:12px;">AI Engineer · ML Engineer · Data Scientist &nbsp;|&nbsp; Hyderabad, India</div>
    <div class="ft-links">
      <a href="https://github.com/ramannagarichakravardhan0608" target="_blank">GitHub ↗</a>
      <a href="mailto:chakravardhanramannagari06@gmail.com">Email ↗</a>
      <a href="https://linkedin.com/in/ramannagarichakravardhan" target="_blank">LinkedIn ↗</a>
      <a href="#hero">Back to Top ↑</a>
    </div>
    <div class="ft-copy">chakravardhanramannagari06@gmail.com · Open to Work · 2025</div>
  </div>
</footer>

<script>
/* ── PARTICLES ── */
const cvs=document.getElementById('cvs'),ctx=cvs.getContext('2d');
let W,H,pts=[];
function resize(){W=cvs.width=window.innerWidth;H=cvs.height=window.innerHeight;}
resize();window.addEventListener('resize',resize);
class P{
  constructor(){this.reset();}
  reset(){this.x=Math.random()*W;this.y=Math.random()*H;this.r=Math.random()*1.4+.3;this.vx=(Math.random()-.5)*.28;this.vy=(Math.random()-.5)*.28;this.a=Math.random()*.35+.05;this.life=Math.random()*250+100;this.ml=this.life;}
  step(){this.x+=this.vx;this.y+=this.vy;this.life--;if(this.x<0||this.x>W||this.y<0||this.y>H||this.life<0)this.reset();}
  draw(){ctx.save();ctx.globalAlpha=this.a*(this.life/this.ml);ctx.fillStyle='#00E5FF';ctx.beginPath();ctx.arc(this.x,this.y,this.r,0,Math.PI*2);ctx.fill();ctx.restore();}
}
for(let i=0;i<100;i++)pts.push(new P());
function frame(){
  ctx.clearRect(0,0,W,H);
  pts.forEach(p=>{p.step();p.draw();});
  for(let i=0;i<pts.length;i++)for(let j=i+1;j<pts.length;j++){
    const dx=pts[i].x-pts[j].x,dy=pts[i].y-pts[j].y,d=Math.sqrt(dx*dx+dy*dy);
    if(d<90){ctx.save();ctx.globalAlpha=(1-d/90)*.055;ctx.strokeStyle='#00E5FF';ctx.lineWidth=.4;ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);ctx.stroke();ctx.restore();}
  }
  requestAnimationFrame(frame);
}
frame();

/* ── CURSOR ── */
const cur=document.getElementById('cur'),ring=document.getElementById('cur-ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px';});
(function animRing(){rx+=(mx-rx)*.11;ry+=(my-ry)*.11;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(animRing);})();
document.querySelectorAll('a,button,.proj-card,.sk-card,.hi-card,.st-card,.con-card,.chip,.tech-pill,.role-pill').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cur.style.width='18px';cur.style.height='18px';ring.style.width='52px';ring.style.height='52px';ring.style.opacity='.85';});
  el.addEventListener('mouseleave',()=>{cur.style.width='10px';cur.style.height='10px';ring.style.width='34px';ring.style.height='34px';ring.style.opacity='.45';});
});

/* ── SCROLL REVEAL ── */
const obs=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting)e.target.classList.add('on');}),{threshold:.08});
document.querySelectorAll('.rev').forEach(r=>obs.observe(r));

/* ── TYPING EFFECT ── */
const titles=['AI Engineer','ML Engineer','Data Scientist','NLP Specialist','CV Engineer','Production AI Builder'];
let ti=0,ci=0,del=false;
const tel=document.getElementById('typed');
function type(){
  const cur=titles[ti];
  if(!del){ci++;if(ci>cur.length){del=true;setTimeout(type,1800);return;}}
  else{ci--;if(ci<0){del=false;ci=0;ti=(ti+1)%titles.length;}}
  tel.textContent=cur.slice(0,ci);
  setTimeout(type,del?55:85);
}
type();

/* ── LIVE GITHUB STATS ── */
fetch('https://api.github.com/users/ramannagarichakravardhan0608')
  .then(r=>r.json())
  .then(d=>{
    if(d.public_repos!==undefined){
      document.getElementById('s-repos').textContent=d.public_repos;
      document.getElementById('s-followers').textContent=d.followers;
      document.getElementById('s-following').textContent=d.following;
    }
  }).catch(()=>{});

/* ── COUNTER ANIMATION ── */
function animCount(el,target){
  if(isNaN(target))return;
  let n=0;const step=Math.ceil(target/40);
  const iv=setInterval(()=>{n=Math.min(n+step,target);el.textContent=n;if(n>=target)clearInterval(iv);},40);
}
const statsObs=new IntersectionObserver(es=>es.forEach(e=>{
  if(e.isIntersecting){
    const r=document.getElementById('s-repos'),f=document.getElementById('s-followers'),fw=document.getElementById('s-following');
    setTimeout(()=>{
      fetch('https://api.github.com/users/ramannagarichakravardhan0608').then(r=>r.json()).then(d=>{
        if(d.public_repos)animCount(r,d.public_repos);
        if(d.followers!==undefined)animCount(f,d.followers);
        if(d.following!==undefined)animCount(fw,d.following);
      }).catch(()=>{});
    },300);
    statsObs.disconnect();
  }
}),{threshold:.2});
const statsEl=document.getElementById('s-repos');
if(statsEl)statsObs.observe(statsEl.closest('section'));
</script>
</body>
</html>
