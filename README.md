<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Anand Awasthi — Frontend Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
/* ============================================================
   ANAND AWASTHI — PORTFOLIO  |  Single-File Edition
   Theme : Neon-Terminal · Dark Futuristic
   Fonts : Syne (display) · DM Sans (body) · JetBrains Mono
============================================================ */
:root{
  --bg0:#050810; --bg1:#080f1c; --bg2:#0c1524; --bg3:#101d31; --bg4:#14233d;
  --b0:rgba(34,197,94,.08); --b1:rgba(34,197,94,.18); --b2:rgba(34,197,94,.35);
  --tx0:#f1f5f9; --tx1:#94a3b8; --tx2:#475569;
  --neon:#22c55e; --neon2:rgba(34,197,94,.12); --neon3:rgba(34,197,94,.28);
  --cyan:#06b6d4; --amber:#fbbf24; --violet:#a78bfa; --rose:#f43f5e;
  --fd:'Syne',sans-serif; --fb:'DM Sans',sans-serif; --fm:'JetBrains Mono',monospace;
  --ease:cubic-bezier(.16,1,.3,1); --dur:.38s;
  --r:12px; --rl:20px;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:var(--bg0);color:var(--tx0);font-family:var(--fb);font-weight:300;line-height:1.7;overflow-x:hidden;-webkit-font-smoothing:antialiased}
::selection{background:rgba(34,197,94,.2);color:#f0fdf4}
::-webkit-scrollbar{width:3px}
::-webkit-scrollbar-track{background:var(--bg0)}
::-webkit-scrollbar-thumb{background:var(--neon);border-radius:3px}
a{color:inherit;text-decoration:none}
ul{list-style:none}
button{cursor:pointer;border:none;background:none;font:inherit}

/* ── CURSOR ─────────────────────────────── */
#cdot,#cring{
  position:fixed;border-radius:50%;pointer-events:none;
  z-index:10000;left:-99px;top:-99px;
}
#cdot{width:8px;height:8px;background:var(--neon);box-shadow:0 0 10px var(--neon),0 0 22px rgba(34,197,94,.35);transition:transform .1s}
#cring{width:30px;height:30px;border:1.5px solid rgba(34,197,94,.4);transition:width .25s var(--ease),height .25s var(--ease),border-color .25s}
#cring.big{width:46px;height:46px;border-color:rgba(34,197,94,.65)}
@media(hover:none){#cdot,#cring{display:none}body,a,button{cursor:auto !important}}

/* ── NOISE OVERLAY ──────────────────────── */
body::before{
  content:'';position:fixed;inset:0;z-index:9999;pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='f'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23f)'/%3E%3C/svg%3E");
  background-size:180px;opacity:.025;
}

/* ── UTILITIES ──────────────────────────── */
.container{max-width:1180px;margin:0 auto;padding:0 2rem}
.glass{background:rgba(8,15,28,.7);backdrop-filter:blur(16px);-webkit-backdrop-filter:blur(16px);border:1px solid var(--b0)}
.section{padding:7rem 0}
.sec-hdr{display:flex;align-items:center;gap:1rem;margin-bottom:3.5rem}
.sec-idx{font-family:var(--fm);font-size:.7rem;color:var(--neon);letter-spacing:.12em}
.sec-ttl{font-family:var(--fd);font-weight:800;font-size:clamp(1.9rem,3.5vw,2.8rem);letter-spacing:-.02em}
.sec-line{flex:1;height:1px;background:linear-gradient(90deg,rgba(34,197,94,.25),transparent);max-width:220px}
.mono-hint{font-family:var(--fm);font-size:.7rem;color:var(--tx2);letter-spacing:.1em;margin-bottom:2.5rem}
.mono-hint span{color:var(--neon)}
.grad-text{
  background:linear-gradient(135deg,#f1f5f9 30%,#4ade80 68%,#22d3ee 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}

/* ── BUTTONS ───────────────────────────── */
.btn{display:inline-flex;align-items:center;gap:.5rem;padding:.8rem 1.9rem;border-radius:6px;font-family:var(--fm);font-size:.78rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;transition:all var(--dur) var(--ease)}
.btn-p{background:linear-gradient(135deg,#22c55e,#16a34a);color:#050810;border:none;box-shadow:0 0 22px rgba(34,197,94,.32)}
.btn-p:hover{box-shadow:0 0 38px rgba(34,197,94,.55),0 0 72px rgba(34,197,94,.18);transform:translateY(-2px)}
.btn-g{background:transparent;color:var(--neon);border:1px solid rgba(34,197,94,.38)}
.btn-g:hover{background:rgba(34,197,94,.08);border-color:rgba(34,197,94,.7);transform:translateY(-2px)}

/* ── REVEAL ─────────────────────────────── */
.rv,.rv-l,.rv-r{opacity:0;transition:opacity .75s var(--ease),transform .75s var(--ease)}
.rv{transform:translateY(30px)}
.rv-l{transform:translateX(-36px)}
.rv-r{transform:translateX(36px)}
.rv.on,.rv-l.on,.rv-r.on{opacity:1;transform:none}
.d1{transition-delay:.1s!important}.d2{transition-delay:.18s!important}
.d3{transition-delay:.26s!important}.d4{transition-delay:.34s!important}
.d5{transition-delay:.42s!important}.d6{transition-delay:.5s!important}

/* ============================================================
   NAV
============================================================ */
#nav{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  padding:1.3rem 2rem;
  transition:background var(--dur),border-color var(--dur),padding var(--dur);
}
#nav.sc{
  background:rgba(5,8,16,.88);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);
  border-bottom:1px solid var(--b0);padding:.85rem 2rem;
}
.nav-in{max-width:1180px;margin:0 auto;display:flex;align-items:center;justify-content:space-between}
.nav-logo{font-family:var(--fm);font-size:.92rem;font-weight:500;letter-spacing:.06em;color:var(--tx0)}
.nav-logo em{color:var(--neon);font-style:normal}
.nav-links{display:flex;gap:2.2rem}
.nav-links a{
  font-family:var(--fm);font-size:.72rem;letter-spacing:.1em;text-transform:uppercase;
  color:var(--tx2);position:relative;transition:color var(--dur);
}
.nav-links a::after{content:'';position:absolute;bottom:-3px;left:0;width:0;height:1px;background:var(--neon);box-shadow:0 0 6px var(--neon);transition:width var(--dur)}
.nav-links a:hover,.nav-links a.act{color:var(--tx0)}
.nav-links a:hover::after,.nav-links a.act::after{width:100%}
.nav-hire{font-family:var(--fm);font-size:.7rem;letter-spacing:.1em;text-transform:uppercase;padding:.42rem 1.1rem;border-radius:5px;border:1px solid rgba(34,197,94,.35);color:var(--neon);transition:all var(--dur)}
.nav-hire:hover{background:rgba(34,197,94,.09);border-color:rgba(34,197,94,.7)}
.hbg{display:none;flex-direction:column;gap:5px;padding:4px;background:none;border:none}
.hbg span{display:block;width:21px;height:1.5px;background:var(--tx0);transition:var(--dur) var(--ease);border-radius:2px}
.hbg.open span:nth-child(1){transform:translateY(6.5px) rotate(45deg)}
.hbg.open span:nth-child(2){opacity:0;transform:scaleX(0)}
.hbg.open span:nth-child(3){transform:translateY(-6.5px) rotate(-45deg)}

/* Mobile nav */
#mnav{
  position:fixed;top:0;right:-100%;bottom:0;width:min(280px,80vw);z-index:999;
  background:rgba(5,8,16,.97);backdrop-filter:blur(24px);-webkit-backdrop-filter:blur(24px);
  border-left:1px solid var(--b0);
  display:flex;flex-direction:column;justify-content:center;padding:2.5rem;
  transition:right var(--dur) var(--ease);
}
#mnav.open{right:0}
#mnav a{font-family:var(--fd);font-weight:700;font-size:1.7rem;color:var(--tx1);display:block;padding:.5rem 0;transition:color var(--dur)}
#mnav a:hover{color:var(--neon)}
#mbk{display:none;position:fixed;inset:0;z-index:998;background:rgba(0,0,0,.6);backdrop-filter:blur(3px)}
#mbk.on{display:block}

/* ============================================================
   HERO
============================================================ */
#hero{
  min-height:100vh;display:flex;align-items:center;
  padding:9rem 2rem 5rem;position:relative;overflow:hidden;
  background:var(--bg0);
}
.h-grid{
  position:absolute;inset:0;pointer-events:none;
  background-image:linear-gradient(rgba(34,197,94,.032) 1px,transparent 1px),linear-gradient(90deg,rgba(34,197,94,.032) 1px,transparent 1px);
  background-size:60px 60px;
}
.h-blob{position:absolute;border-radius:50%;filter:blur(70px);pointer-events:none;animation:blobFloat 9s ease-in-out infinite}
.h-blob1{width:520px;height:520px;top:5%;left:-8%;background:radial-gradient(circle,rgba(34,197,94,.07) 0%,transparent 70%)}
.h-blob2{width:440px;height:440px;bottom:5%;right:-5%;background:radial-gradient(circle,rgba(6,182,212,.055) 0%,transparent 70%);animation-delay:-4s;animation-direction:reverse}
@keyframes blobFloat{
  0%,100%{transform:translate(0,0) scale(1)}
  33%{transform:translate(25px,-18px) scale(1.04)}
  66%{transform:translate(-18px,14px) scale(.97)}
}
.h-scan{
  position:absolute;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(34,197,94,.55),transparent);
  pointer-events:none;opacity:.35;z-index:2;
  animation:scanLine 7s linear infinite;
}
@keyframes scanLine{0%{top:-1px;opacity:0}4%{opacity:.35}94%{opacity:.35}100%{top:100vh;opacity:0}}

.h-content{max-width:1180px;margin:0 auto;position:relative;z-index:3;width:100%}
.h-badge{
  display:inline-flex;align-items:center;gap:.55rem;
  font-family:var(--fm);font-size:.72rem;color:var(--tx2);letter-spacing:.1em;
  padding:.32rem .95rem;border-radius:50px;background:rgba(8,15,28,.8);border:1px solid var(--b0);
  margin-bottom:1.6rem;
  animation:fdDown .7s var(--ease) .1s both;
}
.h-dot{width:7px;height:7px;border-radius:50%;background:var(--neon);box-shadow:0 0 8px var(--neon);animation:dotPulse 2.4s ease-in-out infinite}
@keyframes dotPulse{0%,100%{box-shadow:0 0 6px var(--neon)}50%{box-shadow:0 0 16px var(--neon),0 0 26px rgba(34,197,94,.35)}}
.h-pre{font-family:var(--fm);font-size:.82rem;color:var(--neon);letter-spacing:.1em;margin-bottom:.85rem;animation:fdDown .7s var(--ease) .2s both}
.h-name{
  font-family:var(--fd);font-weight:800;line-height:.95;letter-spacing:-.03em;
  font-size:clamp(3.4rem,10vw,7.8rem);margin-bottom:1.1rem;
  animation:fdDown .85s var(--ease) .3s both;
}
.h-role{
  display:flex;align-items:center;gap:.7rem;
  font-family:var(--fd);font-weight:600;font-size:clamp(1.15rem,2.8vw,1.9rem);
  color:var(--tx1);margin-bottom:1.75rem;
  animation:fdDown .7s var(--ease) .44s both;
}
.h-role-txt{color:var(--neon)}
.h-cur{display:inline-block;width:2px;height:.9em;background:var(--neon);margin-left:2px;vertical-align:middle;box-shadow:0 0 8px var(--neon);animation:curBlink 1s step-end infinite}
@keyframes curBlink{0%,100%{opacity:1}50%{opacity:0}}
.h-bio{font-size:1.02rem;color:var(--tx1);max-width:570px;line-height:1.9;margin-bottom:2.4rem;animation:fdDown .7s var(--ease) .54s both}
.h-bio strong{color:var(--neon);font-weight:400}
.h-btns{display:flex;flex-wrap:wrap;gap:.9rem;margin-bottom:3.2rem;animation:fdDown .7s var(--ease) .64s both}
.h-stats{display:flex;flex-wrap:wrap;gap:2.8rem;animation:fdDown .7s var(--ease) .74s both}
.h-stat-n{font-family:var(--fd);font-weight:800;font-size:2.1rem;color:var(--neon);display:block;line-height:1}
.h-stat-l{font-family:var(--fm);font-size:.62rem;color:var(--tx2);letter-spacing:.12em;text-transform:uppercase;margin-top:.2rem;display:block}
.h-deco{position:absolute;right:2rem;top:50%;transform:translateY(-50%);animation:fdDown 1s var(--ease) .9s both}
.h-card{
  border-radius:var(--r);padding:1.5rem 1.75rem;min-width:220px;position:relative;overflow:hidden;
}
.h-card::before{content:'';position:absolute;top:0;left:20%;right:20%;height:1px;background:linear-gradient(90deg,transparent,rgba(34,197,94,.7),transparent)}
.deco-lbl{font-family:var(--fm);font-size:.63rem;color:var(--tx2);letter-spacing:.08em;margin-bottom:.35rem}
.deco-val{font-family:var(--fm);font-size:.78rem;color:var(--tx1);margin-bottom:.9rem}
.deco-bar{height:3px;background:var(--bg4);border-radius:4px;overflow:hidden;margin-bottom:.2rem}
.deco-fill{height:100%;border-radius:4px;animation:growBar 2s var(--ease) 1.6s both}
@keyframes growBar{from{width:0!important}}
.h-scroll{
  position:absolute;bottom:2rem;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:.4rem;
  animation:fdUp 1s var(--ease) 1.7s both;cursor:pointer;
}
.h-scroll-lbl{font-family:var(--fm);font-size:.6rem;color:var(--tx2);letter-spacing:.15em;text-transform:uppercase}
.h-scroll-bar{width:1px;height:38px;background:linear-gradient(to bottom,var(--neon),transparent);animation:scrollPulse 2.1s ease-in-out infinite}
@keyframes scrollPulse{0%,100%{transform:scaleY(1);transform-origin:top;opacity:.5}50%{transform:scaleY(.6);transform-origin:top;opacity:1}}

@keyframes fdDown{from{opacity:0;transform:translateY(-22px)}to{opacity:1;transform:translateY(0)}}
@keyframes fdUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}

/* ============================================================
   ABOUT
============================================================ */
#about{background:var(--bg0)}
.abt-grid{display:grid;grid-template-columns:1fr 1fr;gap:4.5rem;align-items:center}
.abt-txt p{color:var(--tx1);font-size:.99rem;line-height:1.9;margin-bottom:1.3rem}
.abt-vals{display:grid;grid-template-columns:1fr 1fr;gap:.7rem;margin-top:1.8rem}
.val-pill{
  display:flex;align-items:center;gap:.6rem;
  padding:.65rem .95rem;border-radius:8px;
  font-family:var(--fm);font-size:.7rem;color:var(--tx1);letter-spacing:.05em;
  transition:border-color var(--dur),transform var(--dur);
}
.val-pill:hover{border-color:var(--b1)!important;transform:translateY(-2px)}
.vd{width:8px;height:8px;border-radius:50%;flex-shrink:0}
.prof-card{border-radius:var(--rl);padding:1.9rem;position:relative;overflow:hidden;margin-bottom:1.2rem}
.prof-card::before{content:'';position:absolute;top:0;left:22%;right:22%;height:1px;background:linear-gradient(90deg,transparent,rgba(34,197,94,.65),transparent)}
.prof-row{display:flex;gap:.9rem;padding:.45rem 0;border-bottom:1px solid rgba(255,255,255,.03)}
.prof-row:last-child{border:none}
.pk{font-family:var(--fm);font-size:.7rem;color:var(--tx2);min-width:90px}
.pv{font-family:var(--fm);font-size:.75rem;color:#86efac}
.stats-g{display:grid;grid-template-columns:1fr 1fr;gap:1rem}
.stat-c{
  border-radius:var(--r);padding:1.2rem;text-align:center;
  transition:border-color var(--dur),transform var(--dur);
}
.stat-c:hover{border-color:var(--b1)!important;transform:translateY(-3px)}
.stat-n{font-family:var(--fd);font-weight:800;font-size:2.1rem;color:var(--neon);display:block;line-height:1}
.stat-l{font-family:var(--fm);font-size:.6rem;color:var(--tx2);letter-spacing:.1em;text-transform:uppercase;margin-top:.3rem;display:block}

/* ============================================================
   SKILLS
============================================================ */
#skills{background:rgba(8,15,28,.5);border-top:1px solid var(--b0);border-bottom:1px solid var(--b0)}
.sk-filters{display:flex;flex-wrap:wrap;gap:.6rem;margin-bottom:2.2rem}
.sk-f{
  font-family:var(--fm);font-size:.7rem;letter-spacing:.08em;text-transform:uppercase;
  padding:.42rem 1.1rem;border-radius:50px;border:1px solid rgba(34,197,94,.18);
  color:var(--tx2);background:transparent;
  transition:all var(--dur) var(--ease);
}
.sk-f:hover{border-color:rgba(34,197,94,.45);color:var(--tx1)}
.sk-f.act{background:var(--neon);color:var(--bg0);border-color:var(--neon);font-weight:500}
.sk-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:1rem}
.sk-card{
  border-radius:var(--r);padding:1.35rem;position:relative;overflow:hidden;
  transition:border-color var(--dur),transform var(--dur),box-shadow var(--dur);
}
.sk-card:hover{border-color:var(--b1)!important;transform:translateY(-4px);box-shadow:0 20px 50px rgba(0,0,0,.4)}
.sk-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:.95rem}
.sk-dn{display:flex;align-items:center;gap:.55rem}
.sk-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}
.sk-nm{font-family:var(--fm);font-size:.8rem;color:var(--tx1)}
.sk-pct{font-family:var(--fm);font-size:.68rem;color:var(--tx2)}
.sk-track{height:3px;background:var(--bg4);border-radius:4px;overflow:hidden;margin-bottom:.95rem}
.sk-bar{height:100%;border-radius:4px;width:0;transition:width 1.3s var(--ease)}
.sk-tag{font-family:var(--fm);font-size:.6rem;padding:.18rem .55rem;border-radius:4px;letter-spacing:.05em;border:1px solid transparent}

/* ============================================================
   PROJECTS
============================================================ */
#projects{background:var(--bg0)}
.pj-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(340px,1fr));gap:1.5rem}
.pj-card{
  border-radius:var(--rl);overflow:hidden;display:flex;flex-direction:column;
  transition:transform var(--dur) var(--ease),box-shadow var(--dur),border-color var(--dur);
  position:relative;
}
.pj-card:hover{transform:translateY(-8px);box-shadow:0 30px 60px rgba(0,0,0,.5)}
.pj-top{position:relative;height:200px;overflow:hidden;display:flex;align-items:center;justify-content:center}
.pj-top svg{width:100%;height:100%;transition:transform var(--dur) var(--ease)}
.pj-card:hover .pj-top svg{transform:scale(1.06)}
.pj-ov{
  position:absolute;inset:0;display:flex;align-items:center;justify-content:center;gap:.9rem;
  background:rgba(5,8,16,.82);opacity:0;transition:opacity var(--dur);
}
.pj-card:hover .pj-ov{opacity:1}
.ov-btn{
  display:flex;align-items:center;gap:.4rem;
  font-family:var(--fm);font-size:.7rem;
  padding:.5rem 1.05rem;border-radius:6px;transition:transform .2s;
}
.ov-btn:hover{transform:scale(1.07)}
.ov-ghost{background:rgba(8,15,28,.85);border:1px solid rgba(255,255,255,.14);color:var(--tx1)}
.pj-num{
  position:absolute;top:.75rem;left:.75rem;
  font-family:var(--fm);font-size:.62rem;padding:.18rem .5rem;
  border-radius:4px;background:rgba(5,8,16,.75);border:1px solid rgba(255,255,255,.1);
}
.pj-feat{
  position:absolute;top:.75rem;right:.75rem;
  font-family:var(--fm);font-size:.58rem;padding:.18rem .55rem;
  border-radius:4px;background:rgba(251,191,36,.14);color:#fbbf24;border:1px solid rgba(251,191,36,.25);
}
.pj-body{padding:1.45rem;display:flex;flex-direction:column;gap:.7rem;flex:1}
.pj-ttl{font-family:var(--fd);font-weight:700;font-size:1.18rem;color:var(--tx0)}
.pj-short{font-family:var(--fm);font-size:.7rem}
.pj-desc{font-size:.87rem;color:var(--tx1);line-height:1.75}
.pj-tags{display:flex;flex-wrap:wrap;gap:.4rem}
.pj-tag{font-family:var(--fm);font-size:.62rem;padding:.18rem .52rem;border-radius:4px;border:1px solid transparent}
.pj-links{display:flex;gap:.8rem;margin-top:auto;padding-top:.9rem;border-top:1px solid rgba(255,255,255,.05)}
.pj-lnk{
  display:flex;align-items:center;gap:.38rem;
  font-family:var(--fm);font-size:.7rem;padding:.33rem .8rem;
  border-radius:5px;border:1px solid var(--b0);color:var(--tx1);
  transition:all var(--dur);
}
.pj-lnk:hover{border-color:var(--b1);color:var(--tx0)}
.pj-lnk-a{border-color:transparent!important;margin-left:auto;font-weight:500}

/* ============================================================
   SOCIALS
============================================================ */
#socials{background:rgba(8,15,28,.4);border-top:1px solid var(--b0);border-bottom:1px solid var(--b0)}
.sc-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.1rem}
.sc-card{
  border-radius:var(--rl);padding:1.9rem 1.4rem;
  display:flex;flex-direction:column;align-items:center;text-align:center;gap:.9rem;
  position:relative;overflow:hidden;
  transition:transform var(--dur) var(--ease),border-color var(--dur);
}
.sc-card:hover{transform:translateY(-5px)}
.sc-glow{position:absolute;inset:0;border-radius:inherit;opacity:0;transition:opacity var(--dur);pointer-events:none}
.sc-card:hover .sc-glow{opacity:1}
.sc-icon{
  width:54px;height:54px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  position:relative;z-index:1;transition:transform var(--dur);
}
.sc-card:hover .sc-icon{transform:scale(1.1)}
.sc-name{font-family:var(--fd);font-weight:600;font-size:.98rem;color:var(--tx0);position:relative;z-index:1}
.sc-handle{font-family:var(--fm);font-size:.67rem;color:var(--tx2);position:relative;z-index:1}
.sc-desc{font-size:.78rem;color:var(--tx2);font-weight:300;position:relative;z-index:1}
.sc-arrow{position:absolute;top:.9rem;right:.9rem;font-size:.95rem;transition:transform var(--dur),color var(--dur);z-index:1;color:var(--tx2)}
.sc-card:hover .sc-arrow{transform:translate(2px,-2px)}

/* ============================================================
   CONTACT
============================================================ */
#contact{background:var(--bg0);position:relative;overflow:hidden;text-align:center}
.ct-glow{
  position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  width:650px;height:430px;border-radius:50%;
  background:radial-gradient(ellipse,rgba(34,197,94,.046) 0%,transparent 70%);
  filter:blur(40px);pointer-events:none;
}
.ct-corner{position:absolute;pointer-events:none}
.ct-inner{max-width:660px;margin:0 auto;position:relative;z-index:1}
.ct-ttl{font-family:var(--fd);font-weight:800;font-size:clamp(2.5rem,7vw,4.8rem);line-height:1;letter-spacing:-.03em;margin-bottom:1.3rem}
.ct-body{color:var(--tx1);font-size:1rem;line-height:1.85;max-width:480px;margin:0 auto 2.2rem;font-weight:300}
.em-card{border-radius:var(--rl);padding:1.4rem 1.8rem;margin-bottom:2.2rem;position:relative;overflow:hidden}
.em-card::before{content:'';position:absolute;top:0;left:22%;right:22%;height:1px;background:linear-gradient(90deg,transparent,rgba(34,197,94,.65),transparent)}
.em-row{display:flex;align-items:center;justify-content:center;gap:1.4rem;flex-wrap:wrap}
.em-info{display:flex;align-items:center;gap:.85rem}
.em-ico{width:40px;height:40px;border-radius:50%;background:rgba(34,197,94,.12);border:1px solid rgba(34,197,94,.28);display:flex;align-items:center;justify-content:center}
.em-lbl{font-family:var(--fm);font-size:.62rem;color:var(--tx2);letter-spacing:.1em;display:block}
.em-addr{font-family:var(--fm);font-size:.88rem;color:var(--tx1)}
.em-acts{display:flex;gap:.7rem}
.cp-btn{
  display:flex;align-items:center;gap:.38rem;
  font-family:var(--fm);font-size:.7rem;padding:.5rem .95rem;
  border-radius:6px;border:1px solid var(--b0);color:var(--tx1);
  background:transparent;transition:all var(--dur);
}
.cp-btn:hover{border-color:var(--b1);color:var(--tx0)}
.cp-btn.ok{color:var(--neon);border-color:rgba(34,197,94,.35)}
.sd-btn{
  display:flex;align-items:center;gap:.38rem;
  font-family:var(--fm);font-size:.7rem;padding:.5rem 1.15rem;
  border-radius:6px;background:var(--neon);color:var(--bg0);font-weight:500;
  box-shadow:0 0 18px rgba(34,197,94,.3);transition:all var(--dur);
}
.sd-btn:hover{box-shadow:0 0 30px rgba(34,197,94,.5);transform:scale(1.04)}
.ct-meta{display:flex;align-items:center;justify-content:center;gap:2rem;font-family:var(--fm);font-size:.7rem;color:var(--tx2);flex-wrap:wrap}
.ct-meta span{display:flex;align-items:center;gap:.45rem}

/* ============================================================
   FOOTER
============================================================ */
footer{border-top:1px solid var(--b0);padding:2.5rem 0;background:rgba(5,8,16,.85)}
.ft-in{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem}
.ft-logo{font-family:var(--fm);font-size:.88rem;color:var(--tx2)}
.ft-logo em{color:var(--neon);font-style:normal}
.ft-copy{font-family:var(--fm);font-size:.7rem;color:var(--tx2);display:flex;align-items:center;gap:.4rem}
.ft-top{display:flex;align-items:center;gap:.5rem;font-family:var(--fm);font-size:.7rem;color:var(--tx2);transition:color var(--dur)}
.ft-top:hover{color:var(--neon)}
.ft-top-ico{width:26px;height:26px;border-radius:50%;border:1px solid var(--b0);display:flex;align-items:center;justify-content:center;transition:border-color var(--dur)}
.ft-top:hover .ft-top-ico{border-color:rgba(34,197,94,.45)}
.ft-btm{text-align:center;margin-top:1.5rem;font-family:var(--fm);font-size:.65rem;color:rgba(71,85,105,.4)}

/* ============================================================
   RESPONSIVE
============================================================ */
@media(max-width:1050px){
  .h-deco{display:none}
  .abt-grid{grid-template-columns:1fr;gap:3rem}
}
@media(max-width:800px){
  .nav-links,.nav-hire{display:none}
  .hbg{display:flex}
  .sc-grid{grid-template-columns:1fr 1fr}
  .pj-grid{grid-template-columns:1fr}
  .abt-vals{grid-template-columns:1fr}
}
@media(max-width:500px){
  .container{padding:0 1.2rem}
  .section{padding:5rem 0}
  .h-btns{flex-direction:column}
  .sc-grid{grid-template-columns:1fr 1fr}
  .sk-grid{grid-template-columns:1fr}
  .ct-ttl{font-size:2.2rem}
  .em-row{flex-direction:column;gap:1rem}
  .ft-in{flex-direction:column;text-align:center}
  .ft-btm{display:none}
}
@media(prefers-reduced-motion:reduce){
  *,*::before,*::after{animation-duration:.01ms!important;transition-duration:.01ms!important}
  .rv,.rv-l,.rv-r{opacity:1!important;transform:none!important}
}
</style>
</head>
<body>

<!-- Cursor -->
<div id="cdot"></div>
<div id="cring"></div>

<!-- ============================================================
     NAV
============================================================ -->
<nav id="nav">
  <div class="nav-in">
    <a href="#hero" class="nav-logo" onclick="ss(event,'#hero')"><em>[</em>AA<em>]</em></a>
    <ul class="nav-links">
      <li><a href="#about"    onclick="ss(event,'#about')">About</a></li>
      <li><a href="#skills"   onclick="ss(event,'#skills')">Skills</a></li>
      <li><a href="#projects" onclick="ss(event,'#projects')">Projects</a></li>
      <li><a href="#socials"  onclick="ss(event,'#socials')">Social</a></li>
      <li><a href="#contact"  onclick="ss(event,'#contact')">Contact</a></li>
    </ul>
    <a href="#contact" class="nav-hire" onclick="ss(event,'#contact')">Hire Me</a>
    <button class="hbg" id="hbg" aria-label="Menu" onclick="toggleMobile()">
      <span></span><span></span><span></span>
    </button>
  </div>
</nav>
<div id="mbk" onclick="closeMobile()"></div>
<div id="mnav">
  <div style="font-family:var(--fm);font-size:.62rem;color:var(--tx2);letter-spacing:.12em;margin-bottom:2rem">// navigation</div>
  <a href="#about"    onclick="ss(event,'#about')">About</a>
  <a href="#skills"   onclick="ss(event,'#skills')">Skills</a>
  <a href="#projects" onclick="ss(event,'#projects')">Projects</a>
  <a href="#socials"  onclick="ss(event,'#socials')">Social</a>
  <a href="#contact"  onclick="ss(event,'#contact')">Contact</a>
  <div style="position:absolute;bottom:2rem;left:2.5rem;font-family:var(--fm);font-size:.62rem;color:rgba(71,85,105,.4)">/* anand awasthi */</div>
</div>

<!-- ============================================================
     HERO
============================================================ -->
<section id="hero">
  <div class="h-grid"></div>
  <div class="h-blob h-blob1"></div>
  <div class="h-blob h-blob2"></div>
  <div class="h-scan"></div>
  <!-- Corner lines -->
  <div style="position:absolute;bottom:0;right:0;width:1px;height:110px;background:linear-gradient(to top,transparent,rgba(34,197,94,.2),transparent);pointer-events:none"></div>
  <div style="position:absolute;bottom:0;right:0;width:110px;height:1px;background:linear-gradient(to left,transparent,rgba(34,197,94,.2),transparent);pointer-events:none"></div>

  <div class="h-content">
    <div class="h-badge">
      <div class="h-dot"></div>
      📍 Lucknow, India &nbsp;·&nbsp; Open to Opportunities
    </div>
    <p class="h-pre">&gt;&gt; Hello, World! I'm</p>
    <h1 class="h-name grad-text">Anand<br>Awasthi</h1>
    <div class="h-role">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#22c55e" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="flex-shrink:0"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
      <span class="h-role-txt" id="tw"></span><span class="h-cur"></span>
    </div>
    <p class="h-bio">
      Building fast, beautiful web experiences — one pixel at a time.<br>
      Hard work, curiosity, and a drive to build things that <strong>matter</strong>.
    </p>
    <div class="h-btns">
      <a href="#projects" class="btn btn-p" onclick="ss(event,'#projects')">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="5 3 19 12 5 21 5 3"/></svg>
        View Projects
      </a>
      <a href="#contact" class="btn btn-g" onclick="ss(event,'#contact')">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Contact Me
      </a>
    </div>
    <div class="h-stats">
      <div><span class="h-stat-n">3+</span><span class="h-stat-l">Projects</span></div>
      <div><span class="h-stat-n">1yr</span><span class="h-stat-l">Coding</span></div>
      <div><span class="h-stat-n">100%</span><span class="h-stat-l">Committed</span></div>
    </div>
  </div>

  <!-- Decorative card (desktop) -->
  <div class="h-deco">
    <div class="h-card glass">
      <div class="deco-lbl">// currently building</div>
      <div class="deco-val">React · Tailwind · Figma</div>
      <div class="deco-bar"><div class="deco-fill" style="width:74%;background:linear-gradient(90deg,#22c55e,#4ade80);box-shadow:0 0 8px rgba(34,197,94,.4)"></div></div>
      <div class="deco-lbl" style="margin-top:.55rem">// focus areas</div>
      <div class="deco-val" style="margin-bottom:0">UI/UX · Web Perf · A11y</div>
    </div>
  </div>

  <div class="h-scroll" onclick="ss(event,'#about')">
    <span class="h-scroll-lbl">scroll</span>
    <div class="h-scroll-bar"></div>
  </div>
</section>

<!-- ============================================================
     ABOUT
============================================================ -->
<section id="about" class="section">
  <div class="container">
    <div class="sec-hdr">
      <span class="sec-idx">01</span>
      <h2 class="sec-ttl">About Me</h2>
      <div class="sec-line"></div>
    </div>
    <div class="abt-grid">
      <!-- Left -->
      <div class="rv-l">
        <div class="mono-hint"><span>$</span> cat about.txt</div>
        <div class="abt-txt">
          <p>I come from a middle-class background where hard work and determination shape every step forward. My passion for technology started with curiosity and has grown into a mission to build things that are useful and impactful.</p>
          <p>I enjoy learning, experimenting, and turning ideas into real projects. My goal is simple: keep improving, keep building, and create technology that can help people in meaningful ways.</p>
        </div>
        <div class="abt-vals">
          <div class="val-pill glass" style="border-color:var(--b0)"><div class="vd" style="background:#22c55e;box-shadow:0 0 7px #22c55e"></div>Clean Code</div>
          <div class="val-pill glass" style="border-color:var(--b0)"><div class="vd" style="background:#fbbf24;box-shadow:0 0 7px #fbbf24"></div>Creative Thinking</div>
          <div class="val-pill glass" style="border-color:var(--b0)"><div class="vd" style="background:#60a5fa;box-shadow:0 0 7px #60a5fa"></div>Goal-Driven</div>
          <div class="val-pill glass" style="border-color:var(--b0)"><div class="vd" style="background:#a78bfa;box-shadow:0 0 7px #a78bfa"></div>User-Focused</div>
        </div>
        <a href="#contact" class="btn btn-g" style="margin-top:2rem;display:inline-flex" onclick="ss(event,'#contact')">Let's Connect →</a>
      </div>
      <!-- Right -->
      <div class="rv-r">
        <div class="prof-card glass">
          <div class="mono-hint"><span>// </span>profile.json</div>
          <div class="prof-row"><span class="pk">name:</span><span class="pv">"Anand Awasthi"</span></div>
          <div class="prof-row"><span class="pk">role:</span><span class="pv">"B.Tech Student"</span></div>
          <div class="prof-row"><span class="pk">focus:</span><span class="pv">"Frontend + UI/UX"</span></div>
          <div class="prof-row"><span class="pk">location:</span><span class="pv">"Lucknow, IN"</span></div>
          <div class="prof-row"><span class="pk">status:</span><span class="pv" style="color:#4ade80">"🟢 Open to Work"</span></div>
        </div>
        <div class="stats-g">
          <div class="stat-c glass" style="border-color:var(--b0)"><span class="stat-n">3+</span><span class="stat-l">Projects</span></div>
          <div class="stat-c glass" style="border-color:var(--b0)"><span class="stat-n">∞</span><span class="stat-l">Curiosity</span></div>
          <div class="stat-c glass" style="border-color:var(--b0)"><span class="stat-n">1yr</span><span class="stat-l">Coding</span></div>
          <div class="stat-c glass" style="border-color:var(--b0)"><span class="stat-n">100%</span><span class="stat-l">Committed</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================================================
     SKILLS
============================================================ -->
<section id="skills" class="section">
  <div class="container">
    <div class="sec-hdr rv">
      <span class="sec-idx">02</span>
      <h2 class="sec-ttl">Skills</h2>
      <div class="sec-line"></div>
    </div>
    <div class="mono-hint rv"><span>$</span> ls ./skills --all</div>
    <div class="sk-filters rv">
      <button class="sk-f act" onclick="filterSkills('all',this)">All</button>
      <button class="sk-f" onclick="filterSkills('frontend',this)">Frontend</button>
      <button class="sk-f" onclick="filterSkills('design',this)">Design</button>
      <button class="sk-f" onclick="filterSkills('tools',this)">Tools</button>
    </div>
    <div class="sk-grid" id="sk-grid"></div>
  </div>
</section>

<!-- ============================================================
     PROJECTS
============================================================ -->
<section id="projects" class="section">
  <div class="container">
    <div class="sec-hdr rv">
      <span class="sec-idx">03</span>
      <h2 class="sec-ttl">Projects</h2>
      <div class="sec-line"></div>
    </div>
    <div class="mono-hint rv"><span>$</span> ls ./projects --featured</div>
    <div class="pj-grid" id="pj-grid"></div>
  </div>
</section>

<!-- ============================================================
     SOCIALS
============================================================ -->
<section id="socials" class="section">
  <div class="container">
    <div class="sec-hdr rv">
      <span class="sec-idx">04</span>
      <h2 class="sec-ttl">Find Me</h2>
      <div class="sec-line"></div>
    </div>
    <div class="mono-hint rv"><span>$</span> find /social --name "@anand.awasthi10"</div>
    <div class="sc-grid" id="sc-grid"></div>
  </div>
</section>

<!-- ============================================================
     CONTACT
============================================================ -->
<section id="contact" class="section">
  <div class="ct-glow"></div>
  <!-- Corner decorations -->
  <div class="ct-corner" style="top:3rem;left:3rem;width:1px;height:55px;background:linear-gradient(to bottom,rgba(34,197,94,.4),transparent)"></div>
  <div class="ct-corner" style="top:3rem;left:3rem;width:55px;height:1px;background:linear-gradient(to right,rgba(34,197,94,.4),transparent)"></div>
  <div class="ct-corner" style="bottom:3rem;right:3rem;width:1px;height:55px;background:linear-gradient(to top,rgba(34,197,94,.4),transparent)"></div>
  <div class="ct-corner" style="bottom:3rem;right:3rem;width:55px;height:1px;background:linear-gradient(to left,rgba(34,197,94,.4),transparent)"></div>

  <div class="container">
    <div class="ct-inner rv">
      <p style="font-family:var(--fm);font-size:.7rem;color:var(--neon);letter-spacing:.12em;margin-bottom:1.4rem">05 // contact</p>
      <h2 class="ct-ttl">Let's Build<br><span class="grad-text">Something Together.</span></h2>
      <p class="ct-body">I'm open to internships, collaborations, and interesting projects. Whether you have an idea or just want to say hello — my inbox is open.</p>

      <div class="em-card glass">
        <div class="em-row">
          <div class="em-info">
            <div class="em-ico">
              <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="#22c55e" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            </div>
            <div style="text-align:left">
              <span class="em-lbl">EMAIL</span>
              <span class="em-addr">anandawasthi610@gmail.com</span>
            </div>
          </div>
          <div class="em-acts">
            <button class="cp-btn" id="cp-btn" onclick="copyEmail()">
              <svg id="cp-ico" width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="9" y="9" width="13" height="13" rx="2" ry="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/></svg>
              <span id="cp-lbl">Copy</span>
            </button>
            <a href="mailto:anandawasthi610@gmail.com" class="sd-btn">
              <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
              Send Email
            </a>
          </div>
        </div>
      </div>

      <div class="ct-meta">
        <span>
          <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="#22c55e" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>
          Lucknow, India
        </span>
        <span>
          <span style="width:7px;height:7px;border-radius:50%;background:#22c55e;box-shadow:0 0 8px #22c55e;display:inline-block;animation:dotPulse 2.4s infinite"></span>
          Open to Work
        </span>
      </div>

      <p style="font-family:var(--fm);font-size:.68rem;color:rgba(71,85,105,.45);margin-top:2rem;letter-spacing:.08em">
        <span style="color:rgba(34,197,94,.3)">// </span>thank you for visiting
      </p>
    </div>
  </div>
</section>

<!-- ============================================================
     FOOTER
============================================================ -->
<footer>
  <div class="container">
    <div class="ft-in">
      <div class="ft-logo"><em>[</em>AA<em>]</em></div>
      <p class="ft-copy">
        Built with
        <svg width="12" height="12" viewBox="0 0 24 24" fill="#ef4444" stroke="none"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
        by <strong style="color:var(--tx1);font-weight:500">Anand Awasthi</strong> &nbsp;·&nbsp; 2025
      </p>
      <button class="ft-top" onclick="window.scrollTo({top:0,behavior:'smooth'})">
        Back to top
        <div class="ft-top-ico">
          <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="19" x2="12" y2="5"/><polyline points="5 12 12 5 19 12"/></svg>
        </div>
      </button>
    </div>
    <div class="ft-btm">/* keep building, keep shipping */</div>
  </div>
</footer>

<!-- ============================================================
     SCRIPTS
============================================================ -->
<script>
'use strict';

/* ── DATA ──────────────────────────────────────────────────── */
const SKILLS = [
  {name:'HTML5',        cat:'frontend', lvl:90, col:'#e34f26'},
  {name:'CSS3',         cat:'frontend', lvl:88, col:'#1572b6'},
  {name:'JavaScript',   cat:'frontend', lvl:82, col:'#f7df1e'},
  {name:'React',        cat:'frontend', lvl:70, col:'#61dafb'},
  {name:'Figma',        cat:'design',   lvl:78, col:'#f24e1e'},
  {name:'UI/UX Design', cat:'design',   lvl:75, col:'#a259ff'},
  {name:'Tailwind CSS', cat:'design',   lvl:80, col:'#38bdf8'},
  {name:'Git & GitHub', cat:'tools',    lvl:76, col:'#f05032'},
  {name:'REST APIs',    cat:'tools',    lvl:70, col:'#22c55e'},
  {name:'VS Code',      cat:'tools',    lvl:92, col:'#007acc'},
];

const PROJECTS = [
  {
    id:1, title:'Weather App', short:'Real-time weather at your fingertips.',
    desc:'A sleek application that fetches live meteorological data via API, displaying temperature, conditions, humidity, and forecasts in a clean, readable interface.',
    tech:['HTML','CSS','JavaScript','Weather API'],
    col:'#fbbf24', bg:'rgba(251,191,36,0.08)', bd:'rgba(251,191,36,0.22)',
    gh:'https://github.com/anandawasthi610-design', live:'__weather__', featured:true,
  },
  {
    id:2, title:'To-Do List', short:'Productivity, redesigned.',
    desc:'A focused task management app with add, complete, and delete functionality. Features persistent localStorage and smooth transitions for daily workflows.',
    tech:['HTML','CSS','JavaScript','localStorage'],
    col:'#34d399', bg:'rgba(52,211,153,0.08)', bd:'rgba(52,211,153,0.22)',
    gh:'https://github.com/anandawasthi610-design', live:'__todo__', featured:true,
  },
  {
    id:3, title:'Calculator', short:'Clean maths, zero clutter.',
    desc:'A fully functional calculator supporting arithmetic operations and keyboard input — built with vanilla web tech and a polished glass UI.',
    tech:['HTML','CSS','JavaScript'],
    col:'#a78bfa', bg:'rgba(167,139,250,0.08)', bd:'rgba(167,139,250,0.22)',
    gh:'https://github.com/anandawasthi610-design', live:'__calc__', featured:false,
  },
];

const SOCIALS = [
  {name:'GitHub',      handle:'@anandawasthi610-design', url:'https://github.com/anandawasthi610-design',                          col:'#e2e8f0', desc:'Open-source & code'},
  {name:'LinkedIn',    handle:'Anand Awasthi',           url:'https://www.linkedin.com/in/anand-awasthi-5284453b7',               col:'#0a66c2', desc:'Professional network'},
  {name:'X (Twitter)', handle:'@anand_awasthi10',        url:'https://x.com/anand_awasthi10',                                     col:'#e7e9ea', desc:'Thoughts on tech'},
  {name:'Instagram',   handle:'@anand.awasthi10',        url:'https://www.instagram.com/anand.awasthi10?igsh=dXhzaDIzcTl1cWVl', col:'#e1306c', desc:'Life & design vibes'},
];

/* ── TYPEWRITER ────────────────────────────────────────────── */
(function(){
  const words=['Frontend Developer','UI/UX Designer','Web Developer','Problem Solver','B.Tech Student'];
  const el=document.getElementById('tw');
  let wi=0,ci=0,del=false;
  function tick(){
    const w=words[wi%words.length];
    if(!del){
      el.textContent=w.slice(0,ci+1);
      if(ci+1===w.length){setTimeout(()=>{del=true;tick()},1800);return;}
      ci++;
    } else {
      el.textContent=w.slice(0,ci-1);
      if(ci-1===0){del=false;wi++;ci=0;}
      else ci--;
    }
    setTimeout(tick,del?40:78);
  }
  tick();
})();

/* ── CUSTOM CURSOR ─────────────────────────────────────────── */
(function(){
  const dot=document.getElementById('cdot');
  const ring=document.getElementById('cring');
  // Touch devices: bail out
  if(window.matchMedia('(hover:none)').matches) return;
  document.body.style.cursor='none';
  let rx=-99,ry=-99,mx=-99,my=-99;
  document.addEventListener('mousemove',e=>{
    mx=e.clientX; my=e.clientY;
    dot.style.left=mx+'px'; dot.style.top=my+'px';
  });
  function loop(){
    rx+=(mx-rx)*.16; ry+=(my-ry)*.16;
    ring.style.left=rx+'px'; ring.style.top=ry+'px';
    requestAnimationFrame(loop);
  }
  loop();
  // Big ring on interactive elements
  document.addEventListener('mouseover',e=>{
    if(e.target.closest('a,button')) ring.classList.add('big');
  });
  document.addEventListener('mouseout',e=>{
    if(e.target.closest('a,button')) ring.classList.remove('big');
  });
})();

/* ── NAV SCROLL + ACTIVE ───────────────────────────────────── */
(function(){
  const nav=document.getElementById('nav');
  const links=document.querySelectorAll('.nav-links a');
  const sectionIds=['about','skills','projects','socials','contact'];
  function update(){
    nav.classList.toggle('sc',window.scrollY>60);
    let cur='';
    sectionIds.forEach(id=>{
      const el=document.getElementById(id);
      if(el && window.scrollY>=el.offsetTop-180) cur=id;
    });
    links.forEach(a=>{
      a.classList.toggle('act',a.getAttribute('href')==='#'+cur);
    });
  }
  window.addEventListener('scroll',update,{passive:true});
  update();
})();

/* ── MOBILE NAV ─────────────────────────────────────────────── */
function toggleMobile(){
  const open=document.getElementById('mnav').classList.toggle('open');
  document.getElementById('mbk').classList.toggle('on',open);
  document.getElementById('hbg').classList.toggle('open',open);
  document.body.style.overflow=open?'hidden':'';
}
function closeMobile(){
  document.getElementById('mnav').classList.remove('open');
  document.getElementById('mbk').classList.remove('on');
  document.getElementById('hbg').classList.remove('open');
  document.body.style.overflow='';
}
document.querySelectorAll('#mnav a').forEach(a=>a.addEventListener('click',closeMobile));

/* ── SMOOTH SCROLL ─────────────────────────────────────────── */
function ss(e,sel){
  e.preventDefault();
  closeMobile();
  const el=document.querySelector(sel);
  if(el) window.scrollTo({top:el.getBoundingClientRect().top+window.scrollY-76,behavior:'smooth'});
}

/* ── REVEAL ON SCROLL ──────────────────────────────────────── */
function initReveal(){
  const els=document.querySelectorAll('.rv,.rv-l,.rv-r');
  if(!els.length) return;
  const obs=new IntersectionObserver(entries=>{
    entries.forEach(en=>{
      if(en.isIntersecting){en.target.classList.add('on');obs.unobserve(en.target);}
    });
  },{threshold:.1,rootMargin:'0px 0px -30px 0px'});
  els.forEach(el=>obs.observe(el));
}

/* ── SKILLS ─────────────────────────────────────────────────── */
function renderSkills(cat='all'){
  const grid=document.getElementById('sk-grid');
  const list=cat==='all'?SKILLS:SKILLS.filter(s=>s.cat===cat);
  grid.innerHTML=list.map((s,i)=>`
    <div class="sk-card glass rv" style="border-color:rgba(255,255,255,.05);transition-delay:${i*.06}s">
      <div class="sk-top">
        <div class="sk-dn">
          <div class="sk-dot" style="background:${s.col};box-shadow:0 0 7px ${s.col}"></div>
          <span class="sk-nm">${s.name}</span>
        </div>
        <span class="sk-pct">${s.lvl}%</span>
      </div>
      <div class="sk-track">
        <div class="sk-bar" data-lvl="${s.lvl}" style="background:${s.col};box-shadow:0 0 8px ${s.col}60"></div>
      </div>
      <span class="sk-tag" style="background:${s.col}18;color:${s.col};border-color:${s.col}30">${s.cat}</span>
    </div>
  `).join('');
  initReveal();
  // Animate bars after a frame
  requestAnimationFrame(()=>{
    requestAnimationFrame(()=>{
      grid.querySelectorAll('.sk-bar').forEach(b=>{b.style.width=b.dataset.lvl+'%';});
    });
  });
}

function filterSkills(cat,btn){
  document.querySelectorAll('.sk-f').forEach(b=>b.classList.remove('act'));
  btn.classList.add('act');
  renderSkills(cat);
}

/* ── PROJECT SVG ILLUSTRATIONS ─────────────────────────────── */
function svgWeather(c){
  const rays=[0,45,90,135,180,225,270,315].map(d=>{
    const r=Math.PI*d/180;
    return `<line x1="${(160+48*Math.cos(r)).toFixed(1)}" y1="${(85+48*Math.sin(r)).toFixed(1)}" x2="${(160+59*Math.cos(r)).toFixed(1)}" y2="${(85+59*Math.sin(r)).toFixed(1)}" stroke="${c}" stroke-width="2" stroke-linecap="round" opacity=".7"/>`;
  }).join('');
  return `<svg viewBox="0 0 320 200" fill="none" xmlns="http://www.w3.org/2000/svg">
    <circle cx="160" cy="85" r="44" fill="${c}" fill-opacity=".1" stroke="${c}" stroke-opacity=".4" stroke-width="1.5"/>
    <circle cx="160" cy="85" r="27" fill="${c}" fill-opacity=".18"/>
    ${rays}
    <path d="M95 150 Q122 122 150 134 Q158 112 178 114 Q200 116 202 134 Q222 130 224 150Z" fill="rgba(148,163,184,.1)" stroke="rgba(148,163,184,.3)" stroke-width="1"/>
    <line x1="115" y1="163" x2="112" y2="177" stroke="${c}" stroke-width="1.5" stroke-linecap="round" opacity=".6"/>
    <line x1="140" y1="163" x2="137" y2="177" stroke="${c}" stroke-width="1.5" stroke-linecap="round" opacity=".6"/>
    <line x1="165" y1="163" x2="162" y2="177" stroke="${c}" stroke-width="1.5" stroke-linecap="round" opacity=".6"/>
    <line x1="190" y1="163" x2="187" y2="177" stroke="${c}" stroke-width="1.5" stroke-linecap="round" opacity=".6"/>
    <text x="250" y="62" fill="${c}" fill-opacity=".85" font-family="JetBrains Mono,monospace" font-size="13">28°C</text>
    <text x="250" y="80" fill="rgba(148,163,184,.5)" font-family="JetBrains Mono,monospace" font-size="9">Partly Cloudy</text>
    <text x="250" y="97" fill="rgba(148,163,184,.4)" font-family="JetBrains Mono,monospace" font-size="9">Lucknow, IN</text>
  </svg>`;
}

function svgTodo(c){
  const items=[{done:true,w:130},{done:true,w:100},{done:false,w:115},{done:false,w:90},{done:false,w:75}];
  const rows=items.map((it,i)=>`
    <g transform="translate(60,${16+i*34})">
      <rect width="200" height="24" rx="5" fill="${it.done?c:'rgba(15,23,42,.5)'}" fill-opacity="${it.done?.1:.9}" stroke="${it.done?c:'rgba(100,116,139,.2)'}" stroke-opacity="${it.done?.35:1}" stroke-width="1"/>
      <circle cx="14" cy="12" r="7" fill="${it.done?c:'rgba(30,41,59,.8)'}" fill-opacity="${it.done?.25:1}" stroke="${it.done?c:'rgba(100,116,139,.3)'}" stroke-opacity="${it.done?.7:1}" stroke-width="1.5"/>
      ${it.done?`<polyline points="10,12 13,15 19,9" stroke="${c}" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>`:''}
      <line x1="28" y1="12" x2="${28+it.w}" y2="12" stroke="${it.done?c:'rgba(100,116,139,.25)'}" stroke-opacity="${it.done?.5:1}" stroke-width="1.5" stroke-linecap="round"/>
    </g>`).join('');
  return `<svg viewBox="0 0 320 200" fill="none" xmlns="http://www.w3.org/2000/svg">${rows}</svg>`;
}

function svgCalc(c){
  const btns=[0,1,2,3].map(row=>[0,1,2,3].map(col=>`
    <rect x="${108+col*28}" y="${78+row*26}" width="22" height="20" rx="4"
      fill="${col===3?c:'rgba(51,65,85,.6)'}" fill-opacity="${col===3?.3:.9}"
      stroke="${col===3?c:'rgba(100,116,139,.22)'}" stroke-opacity="${col===3?.55:1}" stroke-width="1"/>`
  ).join('')).join('');
  return `<svg viewBox="0 0 320 200" fill="none" xmlns="http://www.w3.org/2000/svg">
    <rect x="95" y="20" width="130" height="160" rx="12" fill="${c}" fill-opacity=".05" stroke="${c}" stroke-opacity=".3" stroke-width="1.5"/>
    <rect x="108" y="32" width="104" height="34" rx="5" fill="${c}" fill-opacity=".1" stroke="${c}" stroke-opacity=".2" stroke-width="1"/>
    <text x="202" y="55" fill="${c}" fill-opacity=".85" font-family="JetBrains Mono,monospace" font-size="16" text-anchor="end">42</text>
    ${btns}
  </svg>`;
}

/* ── RENDER PROJECTS ─────────────────────────────────────────── */
function renderProjects(){
  const svgs={1:svgWeather,2:svgTodo,3:svgCalc};
  document.getElementById('pj-grid').innerHTML=PROJECTS.map((p,i)=>`
    <article class="pj-card glass rv" style="border-color:rgba(255,255,255,.06);transition-delay:${i*.12}s">
      <div class="pj-top" style="background:radial-gradient(ellipse at 50% 40%,${p.bg},transparent 70%),var(--bg2)">
        ${svgs[p.id](p.col)}
        <div class="pj-ov">
          <a href="${p.gh}" target="_blank" class="ov-btn ov-ghost">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
            GitHub
          </a>
          <a href="#" onclick="openProject('${p.live}');return false;" class="ov-btn" style="background:${p.col};color:#050810;font-weight:500">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
            Live
          </a>
        </div>
        <div class="pj-num" style="color:${p.col}">${String(i+1).padStart(2,'0')}</div>
        ${p.featured?`<div class="pj-feat">★ Featured</div>`:''}
      </div>
      <div class="pj-body">
        <div>
          <h3 class="pj-ttl">${p.title}</h3>
          <p class="pj-short" style="color:${p.col}">${p.short}</p>
        </div>
        <p class="pj-desc">${p.desc}</p>
        <div class="pj-tags">${p.tech.map(t=>`<span class="pj-tag" style="background:${p.bg};color:${p.col};border-color:${p.bd}">${t}</span>`).join('')}</div>
        <div class="pj-links">
          <a href="${p.gh}" target="_blank" class="pj-lnk">
            <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
            View Code
          </a>
          <a href="#" onclick="openProject('${p.live}');return false;" class="pj-lnk pj-lnk-a" style="color:${p.col}">Live Demo →</a>
        </div>
      </div>
    </article>
  `).join('');
  initReveal();
}

/* ── SOCIAL ICON SVGs ───────────────────────────────────────── */
function iconSVG(name,c){
  if(name==='GitHub')     return `<svg width="25" height="25" viewBox="0 0 24 24" fill="${c}"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>`;
  if(name==='LinkedIn')   return `<svg width="25" height="25" viewBox="0 0 24 24" fill="${c}"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>`;
  if(name==='X (Twitter)')return `<svg width="25" height="25" viewBox="0 0 24 24" fill="${c}"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>`;
  if(name==='Instagram')  return `<svg width="25" height="25" viewBox="0 0 24 24" fill="none" stroke="${c}" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>`;
  return '';
}

/* ── RENDER SOCIALS ─────────────────────────────────────────── */
function renderSocials(){
  document.getElementById('sc-grid').innerHTML=SOCIALS.map((s,i)=>`
    <a href="${s.url}" target="_blank" rel="noopener noreferrer"
      class="sc-card glass rv" style="border-color:rgba(255,255,255,.06);transition-delay:${i*.1}s">
      <div class="sc-glow" style="background:radial-gradient(ellipse at 50% 0%,${s.col}20,transparent 70%)"></div>
      <div class="sc-icon" style="background:${s.col}18;border:1px solid ${s.col}30">${iconSVG(s.name,s.col)}</div>
      <span class="sc-name">${s.name}</span>
      <span class="sc-handle">${s.handle}</span>
      <span class="sc-desc">${s.desc}</span>
      <span class="sc-arrow" style="color:${s.col}">↗</span>
    </a>
  `).join('');
  // Hover glow
  document.querySelectorAll('.sc-card').forEach(c=>{
    const g=c.querySelector('.sc-glow');
    c.addEventListener('mouseenter',()=>g.style.opacity='1');
    c.addEventListener('mouseleave',()=>g.style.opacity='0');
  });
  initReveal();
}

/* ── PROJECT LAUNCHER — opens any embedded app in new tab ───── */
function openProject(key){
  const map={__calc__:calcHTML,__weather__:weatherHTML,__todo__:todoHTML};
  const html=map[key];
  if(!html) return;
  const blob=new Blob([html],{type:'text/html'});
  window.open(URL.createObjectURL(blob),'_blank');
}

/* ── WEATHER APP HTML ────────────────────────────────────────── */
const weatherHTML=`<!DOCTYPE html>
<html lang="en"><head><meta charset="UTF-8"/><meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Weather App — Anand Awasthi</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=JetBrains+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
body{min-height:100vh;background:#050810;font-family:'DM Sans',sans-serif;font-weight:300;color:#f1f5f9;display:flex;flex-direction:column;align-items:center;padding:2rem 1rem 3rem;position:relative;overflow-x:hidden;}
body::before{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(251,191,36,.025) 1px,transparent 1px),linear-gradient(90deg,rgba(251,191,36,.025) 1px,transparent 1px);background-size:55px 55px;pointer-events:none;z-index:0;}
.blob{position:fixed;border-radius:50%;filter:blur(80px);pointer-events:none;z-index:0;}
.b1{width:500px;height:500px;top:-150px;left:-150px;background:radial-gradient(circle,rgba(251,191,36,.06),transparent 70%);}
.b2{width:400px;height:400px;bottom:-100px;right:-100px;background:radial-gradient(circle,rgba(251,191,36,.04),transparent 70%);}
header{position:relative;z-index:1;text-align:center;margin-bottom:2rem;animation:fdIn .6s ease both;}
header h1{font-family:'Syne',sans-serif;font-weight:800;font-size:1.6rem;background:linear-gradient(135deg,#f1f5f9 30%,#fbbf24 70%,#f97316 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
header p{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:#475569;letter-spacing:.1em;margin-top:.3rem;}
.search-wrap{position:relative;z-index:1;width:100%;max-width:480px;margin-bottom:1.8rem;animation:fdIn .7s ease .1s both;}
.search-box{display:flex;gap:.6rem;}
.search-input{flex:1;background:rgba(8,15,28,.85);border:1px solid rgba(251,191,36,.15);border-radius:12px;padding:.85rem 1.2rem;font-family:'JetBrains Mono',monospace;font-size:.85rem;color:#f1f5f9;outline:none;transition:border-color .3s,box-shadow .3s;}
.search-input::placeholder{color:#334155;}
.search-input:focus{border-color:rgba(251,191,36,.5);box-shadow:0 0 20px rgba(251,191,36,.1);}
.search-btn{background:linear-gradient(135deg,#fbbf24,#f59e0b);color:#050810;border:none;border-radius:12px;padding:.85rem 1.4rem;font-family:'JetBrains Mono',monospace;font-size:.82rem;font-weight:500;cursor:pointer;transition:all .3s;white-space:nowrap;}
.search-btn:hover{box-shadow:0 0 24px rgba(251,191,36,.4);transform:translateY(-1px);}
.err-msg{font-family:'JetBrains Mono',monospace;font-size:.72rem;color:#f87171;text-align:center;margin-top:.6rem;min-height:1.1rem;}
.card{position:relative;z-index:1;width:100%;max-width:480px;background:rgba(8,15,28,.85);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);border:1px solid rgba(251,191,36,.12);border-radius:24px;padding:2rem;box-shadow:0 32px 80px rgba(0,0,0,.5);overflow:hidden;animation:slideUp .7s cubic-bezier(.16,1,.3,1) .15s both;}
.card::before{content:'';position:absolute;top:0;left:15%;right:15%;height:1px;background:linear-gradient(90deg,transparent,rgba(251,191,36,.6),transparent);}
.card-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:1.5rem;}
.city-name{font-family:'Syne',sans-serif;font-weight:800;font-size:1.8rem;line-height:1;}
.country{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:#fbbf24;letter-spacing:.1em;margin-top:.3rem;}
.weather-icon{font-size:3.5rem;line-height:1;animation:float 4s ease-in-out infinite;}
.temp-row{display:flex;align-items:flex-end;gap:1rem;margin-bottom:.5rem;}
.temp-main{font-family:'Syne',sans-serif;font-weight:800;font-size:4.5rem;line-height:1;letter-spacing:-.03em;color:#fbbf24;text-shadow:0 0 30px rgba(251,191,36,.3);}
.temp-feels{font-size:.8rem;color:#64748b;padding-bottom:.6rem;}
.condition{font-size:1.1rem;color:#94a3b8;font-weight:400;margin-bottom:1.8rem;text-transform:capitalize;}
.divider{height:1px;background:linear-gradient(90deg,transparent,rgba(251,191,36,.15),transparent);margin-bottom:1.5rem;}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;margin-bottom:1.5rem;}
.stat{background:rgba(5,8,16,.5);border:1px solid rgba(251,191,36,.07);border-radius:12px;padding:1rem;text-align:center;}
.stat-icon{font-size:1.4rem;margin-bottom:.35rem;}
.stat-val{font-family:'JetBrains Mono',monospace;font-size:.9rem;font-weight:500;color:#e2e8f0;display:block;}
.stat-lbl{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:#475569;letter-spacing:.08em;text-transform:uppercase;margin-top:.2rem;display:block;}
.forecast-title{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:#fbbf24;letter-spacing:.12em;text-transform:uppercase;margin-bottom:.9rem;opacity:.7;}
.forecast{display:grid;grid-template-columns:repeat(5,1fr);gap:.6rem;}
.fc-day{background:rgba(5,8,16,.5);border:1px solid rgba(251,191,36,.06);border-radius:10px;padding:.7rem .4rem;text-align:center;}
.fc-name{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:#64748b;letter-spacing:.06em;margin-bottom:.35rem;}
.fc-icon{font-size:1.2rem;margin-bottom:.35rem;}
.fc-t{font-family:'JetBrains Mono',monospace;font-size:.75rem;color:#e2e8f0;font-weight:500;}
.loading{display:none;position:absolute;inset:0;background:rgba(5,8,16,.7);border-radius:24px;z-index:10;align-items:center;justify-content:center;flex-direction:column;gap:.8rem;backdrop-filter:blur(4px);}
.loading.show{display:flex;}
.spinner{width:32px;height:32px;border:2px solid rgba(251,191,36,.15);border-top-color:#fbbf24;border-radius:50%;animation:spin .8s linear infinite;}
.loading-txt{font-family:'JetBrains Mono',monospace;font-size:.7rem;color:#fbbf24;letter-spacing:.1em;}
.default-msg{text-align:center;padding:2rem 0;}
.default-msg .big-icon{font-size:4rem;margin-bottom:1rem;display:block;animation:float 4s ease-in-out infinite;}
.default-msg p{color:#334155;font-family:'JetBrains Mono',monospace;font-size:.75rem;letter-spacing:.08em;}
footer-lnk{display:block;position:relative;z-index:1;margin-top:1.5rem;text-align:center;font-family:'JetBrains Mono',monospace;font-size:.65rem;color:#334155;letter-spacing:.08em;animation:fdIn .8s ease .4s both;}
footer-lnk a{color:#fbbf24;text-decoration:none;}
@keyframes fdIn{from{opacity:0}to{opacity:1}}
@keyframes slideUp{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:translateY(0)}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
@keyframes spin{to{transform:rotate(360deg)}}
</style></head><body>
<div class="blob b1"></div><div class="blob b2"></div>
<header><h1>⛅ Weather App</h1><p>by Anand Awasthi · HTML · CSS · JavaScript</p></header>
<div class="search-wrap">
  <div class="search-box">
    <input class="search-input" id="city-input" type="text" placeholder="Enter city name..." autocomplete="off" onkeydown="if(event.key==='Enter')getWeather()"/>
    <button class="search-btn" onclick="getWeather()">Search</button>
  </div>
  <div class="err-msg" id="err-msg"></div>
</div>
<div class="card" id="weather-card">
  <div class="loading" id="loading"><div class="spinner"></div><div class="loading-txt">Fetching weather...</div></div>
  <div id="weather-content">
    <div class="default-msg">
      <span class="big-icon">🌍</span>
      <p>Search for a city to see weather</p>
    </div>
  </div>
</div>
<footer-lnk>Part of <a href="https://github.com/anandawasthi610-design" target="_blank">Anand's portfolio</a></footer-lnk>
<script>
const API_KEY='bd5e378503939ddaee76f12ad7a97608';
const icons={Clear:'☀️',Clouds:'☁️',Rain:'🌧️',Drizzle:'🌦️',Thunderstorm:'⛈️',Snow:'❄️',Mist:'🌫️',Fog:'🌫️',Haze:'🌫️',Smoke:'🌫️',Dust:'🌪️',Sand:'🌪️',Ash:'🌋',Squall:'💨',Tornado:'🌪️'};
const days=['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
function getWeather(){
  const city=document.getElementById('city-input').value.trim();
  if(!city){setErr('Please enter a city name.');return;}
  setErr('');showLoad(true);
  fetch('https://api.openweathermap.org/data/2.5/weather?q='+encodeURIComponent(city)+'&appid='+API_KEY+'&units=metric')
    .then(r=>{if(!r.ok)throw new Error(r.status===404?'City not found. Try another name.':'Failed to fetch. Check your connection.');return r.json();})
    .then(d=>{
      return fetch('https://api.openweathermap.org/data/2.5/forecast?q='+encodeURIComponent(city)+'&appid='+API_KEY+'&units=metric')
        .then(r2=>r2.json()).then(f=>{showLoad(false);renderWeather(d,f);});
    })
    .catch(e=>{showLoad(false);setErr(e.message);});
}
function renderWeather(d,f){
  const ic=icons[d.weather[0].main]||'🌡️';
  const fcDays=[];
  const seen=new Set();
  f.list.forEach(item=>{
    const date=new Date(item.dt*1000);
    const day=days[date.getDay()];
    if(!seen.has(day)&&fcDays.length<5){seen.add(day);fcDays.push({day,icon:icons[item.weather[0].main]||'🌡️',temp:Math.round(item.main.temp)});}
  });
  document.getElementById('weather-content').innerHTML=\`
    <div class="card-top">
      <div><div class="city-name">\${d.name}</div><div class="country">\${d.sys.country} · \${new Date().toLocaleDateString('en-US',{weekday:'long',month:'short',day:'numeric'})}</div></div>
      <div class="weather-icon">\${ic}</div>
    </div>
    <div class="temp-row">
      <div class="temp-main">\${Math.round(d.main.temp)}°</div>
      <div class="temp-feels">Feels like \${Math.round(d.main.feels_like)}°C</div>
    </div>
    <div class="condition">\${d.weather[0].description}</div>
    <div class="divider"></div>
    <div class="stats">
      <div class="stat"><div class="stat-icon">💧</div><span class="stat-val">\${d.main.humidity}%</span><span class="stat-lbl">Humidity</span></div>
      <div class="stat"><div class="stat-icon">💨</div><span class="stat-val">\${Math.round(d.wind.speed)} m/s</span><span class="stat-lbl">Wind</span></div>
      <div class="stat"><div class="stat-icon">👁️</div><span class="stat-val">\${(d.visibility/1000).toFixed(1)} km</span><span class="stat-lbl">Visibility</span></div>
    </div>
    <div class="forecast-title">5-Day Forecast</div>
    <div class="forecast">\${fcDays.map(fc=>\`<div class="fc-day"><div class="fc-name">\${fc.day}</div><div class="fc-icon">\${fc.icon}</div><div class="fc-t">\${fc.temp}°</div></div>\`).join('')}</div>
  \`;
}
function showLoad(v){document.getElementById('loading').classList.toggle('show',v);}
function setErr(m){document.getElementById('err-msg').textContent=m;}
document.getElementById('city-input').addEventListener('keydown',e=>{if(e.key==='Enter')getWeather();});
<\/script></body></html>`;

/* ── TO-DO LIST HTML ─────────────────────────────────────────── */
const todoHTML=`<!DOCTYPE html>
<html lang="en"><head><meta charset="UTF-8"/><meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>To-Do List — Anand Awasthi</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=JetBrains+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
body{min-height:100vh;background:#050810;font-family:"DM Sans",sans-serif;font-weight:300;color:#f1f5f9;display:flex;flex-direction:column;align-items:center;padding:2rem 1rem 3rem;position:relative;overflow-x:hidden;}
body::before{content:"";position:fixed;inset:0;background-image:linear-gradient(rgba(52,211,153,.025) 1px,transparent 1px),linear-gradient(90deg,rgba(52,211,153,.025) 1px,transparent 1px);background-size:55px 55px;pointer-events:none;z-index:0;}
.blob{position:fixed;border-radius:50%;filter:blur(80px);pointer-events:none;z-index:0;}
.b1{width:500px;height:500px;top:-150px;left:-150px;background:radial-gradient(circle,rgba(52,211,153,.06),transparent 70%);}
.b2{width:400px;height:400px;bottom:-100px;right:-100px;background:radial-gradient(circle,rgba(16,185,129,.04),transparent 70%);}
header{position:relative;z-index:1;text-align:center;margin-bottom:2rem;animation:fdIn .6s ease both;}
header h1{font-family:"Syne",sans-serif;font-weight:800;font-size:1.6rem;background:linear-gradient(135deg,#f1f5f9 30%,#34d399 70%,#06b6d4 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
header p{font-family:"JetBrains Mono",monospace;font-size:.65rem;color:#475569;letter-spacing:.1em;margin-top:.3rem;}
.app{position:relative;z-index:1;width:100%;max-width:500px;animation:slideUp .7s cubic-bezier(.16,1,.3,1) .1s both;}
.add-box{display:flex;gap:.6rem;margin-bottom:1.2rem;}
.add-input{flex:1;background:rgba(8,15,28,.85);border:1px solid rgba(52,211,153,.15);border-radius:12px;padding:.85rem 1.2rem;font-family:"DM Sans",sans-serif;font-size:.9rem;font-weight:300;color:#f1f5f9;outline:none;transition:border-color .3s,box-shadow .3s;}
.add-input::placeholder{color:#334155;}
.add-input:focus{border-color:rgba(52,211,153,.45);box-shadow:0 0 20px rgba(52,211,153,.08);}
.add-btn{background:linear-gradient(135deg,#34d399,#10b981);color:#050810;border:none;border-radius:12px;padding:.85rem 1.3rem;font-family:"JetBrains Mono",monospace;font-size:1.2rem;font-weight:700;cursor:pointer;transition:all .3s;flex-shrink:0;}
.add-btn:hover{box-shadow:0 0 24px rgba(52,211,153,.4);transform:translateY(-1px);}
.filters{display:flex;gap:.5rem;margin-bottom:1.5rem;}
.fbtn{font-family:"JetBrains Mono",monospace;font-size:.68rem;letter-spacing:.08em;text-transform:uppercase;padding:.38rem 1rem;border-radius:50px;border:1px solid rgba(52,211,153,.15);color:#475569;background:transparent;cursor:pointer;transition:all .3s;}
.fbtn:hover{border-color:rgba(52,211,153,.4);color:#94a3b8;}
.fbtn.act{background:#34d399;color:#050810;border-color:#34d399;font-weight:500;}
.stats-bar{display:flex;gap:1.2rem;margin-bottom:1.5rem;padding:1rem 1.2rem;background:rgba(8,15,28,.7);border:1px solid rgba(52,211,153,.08);border-radius:12px;}
.si{font-family:"JetBrains Mono",monospace;font-size:.68rem;color:#475569;display:flex;align-items:center;gap:.4rem;}
.si span{color:#34d399;font-weight:500;}
.todo-list{display:flex;flex-direction:column;gap:.6rem;min-height:60px;}
.ti{display:flex;align-items:center;gap:.9rem;padding:1rem 1.2rem;background:rgba(8,15,28,.8);border:1px solid rgba(52,211,153,.08);border-radius:14px;transition:all .3s;}
.ti:hover{border-color:rgba(52,211,153,.2);transform:translateX(3px);}
.ti.done{opacity:.5;}
.ti.done .tt{text-decoration:line-through;color:#334155;}
.cbtn{width:22px;height:22px;border-radius:50%;border:1.5px solid rgba(52,211,153,.4);background:transparent;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all .25s;font-size:.7rem;color:#34d399;}
.cbtn:hover{border-color:#34d399;background:rgba(52,211,153,.1);}
.ti.done .cbtn{background:#34d399;border-color:#34d399;box-shadow:0 0 12px rgba(52,211,153,.3);color:#050810;}
.tt{flex:1;font-size:.92rem;line-height:1.5;color:#e2e8f0;word-break:break-word;}
.tm{font-family:"JetBrains Mono",monospace;font-size:.6rem;color:#1e293b;flex-shrink:0;}
.dbtn{width:26px;height:26px;border-radius:6px;border:1px solid rgba(248,113,113,.15);background:transparent;cursor:pointer;color:#475569;display:flex;align-items:center;justify-content:center;font-size:.85rem;line-height:1;flex-shrink:0;transition:all .25s;}
.dbtn:hover{background:rgba(248,113,113,.12);border-color:rgba(248,113,113,.35);color:#f87171;}
.empty{text-align:center;padding:3rem 1rem;font-family:"JetBrains Mono",monospace;font-size:.75rem;color:#1e293b;letter-spacing:.08em;}
.empty .ei{font-size:2.5rem;margin-bottom:.8rem;display:block;opacity:.4;}
.clr-btn{margin-top:1rem;width:100%;padding:.65rem;background:transparent;border:1px solid rgba(248,113,113,.12);border-radius:10px;font-family:"JetBrains Mono",monospace;font-size:.68rem;color:#475569;letter-spacing:.08em;cursor:pointer;transition:all .3s;text-transform:uppercase;}
.clr-btn:hover{border-color:rgba(248,113,113,.3);color:#f87171;}
.ft{display:block;position:relative;z-index:1;margin-top:1.5rem;text-align:center;font-family:"JetBrains Mono",monospace;font-size:.65rem;color:#334155;letter-spacing:.08em;}
.ft a{color:#34d399;text-decoration:none;}
@keyframes fdIn{from{opacity:0}to{opacity:1}}
@keyframes slideUp{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:translateY(0)}}
</style></head><body>
<div class="blob b1"></div><div class="blob b2"></div>
<header><h1>To-Do List</h1><p>by Anand Awasthi &nbsp;· HTML &nbsp;· CSS &nbsp;· JavaScript</p></header>
<div class="app">
  <div class="add-box">
    <input class="add-input" id="inp" type="text" placeholder="Add a new task..." autocomplete="off" maxlength="120"/>
    <button class="add-btn" id="add-btn">+</button>
  </div>
  <div class="filters">
    <button class="fbtn act" id="f-all">All</button>
    <button class="fbtn" id="f-active">Active</button>
    <button class="fbtn" id="f-done">Done</button>
  </div>
  <div class="stats-bar">
    <div class="si">Total: <span id="st">0</span></div>
    <div class="si">Done: <span id="sd">0</span></div>
    <div class="si">Left: <span id="sl">0</span></div>
  </div>
  <div class="todo-list" id="list"></div>
  <button class="clr-btn" id="clr-btn">Clear completed</button>
</div>
<div class="ft">Part of <a href="https://github.com/anandawasthi610-design" target="_blank">Anand portfolio</a></div>
<script>
(function(){
  var tasks=[];
  var flt='all';
  var nextId=1;

  function safe(s){
    return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
  }
  function now(){
    var d=new Date();
    var h=d.getHours(),m=d.getMinutes();
    var ampm=h>=12?'PM':'AM';
    h=h%12||12;
    return h+':'+(m<10?'0'+m:m)+' '+ampm;
  }
  function addTask(){
    var inp=document.getElementById('inp');
    var text=inp.value.trim();
    if(!text)return;
    tasks.unshift({id:nextId++,text:text,done:false,time:now()});
    inp.value='';
    inp.focus();
    render();
  }
  function toggleTask(id){
    for(var i=0;i<tasks.length;i++){
      if(tasks[i].id===id){tasks[i].done=!tasks[i].done;break;}
    }
    render();
  }
  function delTask(id){
    tasks=tasks.filter(function(t){return t.id!==id;});
    render();
  }
  function clearDone(){
    tasks=tasks.filter(function(t){return !t.done;});
    render();
  }
  function setFilter(f){
    flt=f;
    document.querySelectorAll('.fbtn').forEach(function(b){b.classList.remove('act');});
    document.getElementById('f-'+f).classList.add('act');
    render();
  }
  function render(){
    var visible;
    if(flt==='all') visible=tasks;
    else if(flt==='done') visible=tasks.filter(function(t){return t.done;});
    else visible=tasks.filter(function(t){return !t.done;});
    document.getElementById('st').textContent=tasks.length;
    document.getElementById('sd').textContent=tasks.filter(function(t){return t.done;}).length;
    document.getElementById('sl').textContent=tasks.filter(function(t){return !t.done;}).length;
    var list=document.getElementById('list');
    if(!visible.length){
      var icons={all:'📝',active:'🚀',done:'🎉'};
      var msgs={all:'No tasks yet — add one above',active:'All tasks completed!',done:'No completed tasks yet'};
      list.innerHTML='<div class="empty"><span class="ei">'+icons[flt]+'</span><p>'+msgs[flt]+'</p></div>';
      return;
    }
    var html='';
    for(var i=0;i<visible.length;i++){
      var t=visible[i];
      html+='<div class="ti'+(t.done?' done':'')+'">';
      html+='<button class="cbtn" data-id="'+t.id+'">'+(t.done?'&#10003;':'')+'</button>';
      html+='<span class="tt">'+safe(t.text)+'</span>';
      html+='<span class="tm">'+t.time+'</span>';
      html+='<button class="dbtn" data-del="'+t.id+'">&times;</button>';
      html+='</div>';
    }
    list.innerHTML=html;
    list.querySelectorAll('.cbtn').forEach(function(b){
      b.addEventListener('click',function(){toggleTask(Number(this.dataset.id));});
    });
    list.querySelectorAll('.dbtn').forEach(function(b){
      b.addEventListener('click',function(){delTask(Number(this.dataset.del));});
    });
  }
  document.getElementById('add-btn').addEventListener('click',addTask);
  document.getElementById('inp').addEventListener('keydown',function(e){if(e.key==='Enter')addTask();});
  document.getElementById('f-all').addEventListener('click',function(){setFilter('all');});
  document.getElementById('f-active').addEventListener('click',function(){setFilter('active');});
  document.getElementById('f-done').addEventListener('click',function(){setFilter('done');});
  document.getElementById('clr-btn').addEventListener('click',clearDone);
  render();
})();
<\/script></body></html>`;

/* ── CALCULATOR HTML ─────────────────────────────────────────── */
const calcHTML=`<!DOCTYPE html>
<html lang="en"><head><meta charset="UTF-8"/><meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Calculator — Anand Awasthi</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%;width:100%}
body{min-height:100vh;background:#050810;display:flex;flex-direction:column;align-items:center;justify-content:center;font-family:'JetBrains Mono',monospace;overflow:hidden;position:relative;}
body::after{content:'';position:fixed;inset:0;pointer-events:none;z-index:0;background-image:linear-gradient(rgba(34,197,94,.03) 1px,transparent 1px),linear-gradient(90deg,rgba(34,197,94,.03) 1px,transparent 1px);background-size:50px 50px;}
.blob{position:fixed;border-radius:50%;filter:blur(80px);pointer-events:none;z-index:0}
.blob1{width:400px;height:400px;top:-100px;left:-100px;background:radial-gradient(circle,rgba(34,197,94,.07),transparent 70%)}
.blob2{width:350px;height:350px;bottom:-80px;right:-80px;background:radial-gradient(circle,rgba(167,139,250,.06),transparent 70%)}
.page-header{position:relative;z-index:1;text-align:center;margin-bottom:1.8rem;animation:fadeIn .6s ease both;}
.page-header h1{font-family:'Syne',sans-serif;font-weight:800;font-size:1.6rem;letter-spacing:-.02em;background:linear-gradient(135deg,#f1f5f9 30%,#4ade80 70%,#22d3ee 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.page-header p{font-size:.65rem;color:#475569;letter-spacing:.1em;margin-top:.3rem}
.calc-wrap{position:relative;z-index:1;animation:slideUp .7s cubic-bezier(.16,1,.3,1) .1s both;}
.calc{width:340px;background:rgba(8,15,28,.85);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);border:1px solid rgba(34,197,94,.12);border-radius:24px;padding:1.5rem;box-shadow:0 32px 80px rgba(0,0,0,.6),0 0 0 1px rgba(255,255,255,.04) inset;position:relative;overflow:hidden;}
.calc::before{content:'';position:absolute;top:0;left:15%;right:15%;height:1px;background:linear-gradient(90deg,transparent,rgba(34,197,94,.6),transparent);}
.display{background:rgba(5,8,16,.7);border:1px solid rgba(34,197,94,.08);border-radius:14px;padding:1.1rem 1.3rem;margin-bottom:1.2rem;min-height:90px;display:flex;flex-direction:column;justify-content:flex-end;align-items:flex-end;position:relative;overflow:hidden;}
.expr{font-size:.72rem;color:#475569;min-height:1rem;text-align:right;word-break:break-all;margin-bottom:.3rem;letter-spacing:.04em;transition:all .2s ease;max-width:100%;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
.result{font-size:2.4rem;font-weight:600;color:#f1f5f9;letter-spacing:-.02em;text-align:right;transition:all .15s ease;max-width:100%;overflow:hidden;word-break:break-all;line-height:1.1;}
.result.medium{font-size:1.8rem}.result.small{font-size:1.3rem}
.result.neon{color:#22c55e;text-shadow:0 0 20px rgba(34,197,94,.4)}.result.err{color:#f87171;font-size:1.1rem}
.btns{display:grid;grid-template-columns:repeat(4,1fr);gap:.55rem;}
.btn{height:64px;border-radius:12px;border:none;font-family:'JetBrains Mono',monospace;font-size:1rem;font-weight:500;cursor:pointer;display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden;transition:transform .12s cubic-bezier(.16,1,.3,1),box-shadow .2s,background .2s;-webkit-tap-highlight-color:transparent;user-select:none;}
.btn::after{content:'';position:absolute;inset:0;border-radius:inherit;background:rgba(255,255,255,.08);opacity:0;transition:opacity .15s;}
.btn:active::after{opacity:1}.btn:active{transform:scale(.93)!important}
.btn-num{background:rgba(20,35,61,.8);color:#e2e8f0;border:1px solid rgba(255,255,255,.06);box-shadow:0 2px 8px rgba(0,0,0,.3),0 1px 0 rgba(255,255,255,.05) inset;}
.btn-num:hover{background:rgba(28,48,80,.9);border-color:rgba(255,255,255,.1);transform:translateY(-1px);box-shadow:0 6px 16px rgba(0,0,0,.35);}
.btn-op{background:rgba(34,197,94,.12);color:#4ade80;border:1px solid rgba(34,197,94,.2);box-shadow:0 2px 8px rgba(0,0,0,.2);}
.btn-op:hover{background:rgba(34,197,94,.2);border-color:rgba(34,197,94,.4);transform:translateY(-1px);box-shadow:0 6px 20px rgba(0,0,0,.25),0 0 20px rgba(34,197,94,.12);}
.btn-eq{background:linear-gradient(135deg,#22c55e,#16a34a);color:#050810;font-weight:700;border:none;box-shadow:0 0 24px rgba(34,197,94,.35),0 4px 12px rgba(0,0,0,.3);font-size:1.3rem;}
.btn-eq:hover{box-shadow:0 0 36px rgba(34,197,94,.55),0 6px 18px rgba(0,0,0,.3);transform:translateY(-2px);}
.btn-clr{background:rgba(248,113,113,.1);color:#fca5a5;border:1px solid rgba(248,113,113,.18);}
.btn-clr:hover{background:rgba(248,113,113,.18);border-color:rgba(248,113,113,.35);transform:translateY(-1px);}
.btn-func{background:rgba(14,23,40,.7);color:#94a3b8;border:1px solid rgba(255,255,255,.06);}
.btn-func:hover{background:rgba(20,32,55,.85);color:#e2e8f0;border-color:rgba(255,255,255,.1);transform:translateY(-1px);}
.span2{grid-column:span 2}
.history{margin-top:1rem;background:rgba(5,8,16,.5);border:1px solid rgba(34,197,94,.07);border-radius:12px;padding:.75rem 1rem;max-height:90px;overflow-y:auto;}
.history::-webkit-scrollbar{width:2px}.history::-webkit-scrollbar-thumb{background:rgba(34,197,94,.3);border-radius:2px}
.history-title{font-size:.6rem;color:#334155;letter-spacing:.1em;margin-bottom:.4rem;text-transform:uppercase}
.history-item{font-size:.7rem;color:#475569;padding:.15rem 0;border-bottom:1px solid rgba(255,255,255,.03);display:flex;justify-content:space-between;align-items:center;cursor:pointer;transition:color .15s;}
.history-item:last-child{border:none}.history-item:hover{color:#94a3b8}.history-item span:last-child{color:#22c55e;font-weight:500}
.history-empty{font-size:.68rem;color:#334155;text-align:center;padding:.3rem 0}
.kb-hint{margin-top:.85rem;text-align:center;font-size:.6rem;color:#1e293b;letter-spacing:.1em;}
.footer-link{position:relative;z-index:1;margin-top:1.5rem;text-align:center;font-size:.65rem;color:#334155;letter-spacing:.08em;animation:fadeIn .8s ease .4s both;}
.footer-link a{color:#22c55e;text-decoration:none;transition:color .2s}.footer-link a:hover{color:#4ade80}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@keyframes slideUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
@keyframes resultPop{0%{transform:scale(1)}40%{transform:scale(1.06)}100%{transform:scale(1)}}
.pop{animation:resultPop .2s cubic-bezier(.16,1,.3,1)}
@media(max-width:380px){.calc{width:300px;padding:1.2rem}.btn{height:56px;font-size:.9rem}.result{font-size:2rem}}
</style></head><body>
<div class="blob blob1"></div><div class="blob blob2"></div>
<div class="page-header"><h1>Calculator</h1><p>by Anand Awasthi &nbsp;·&nbsp; HTML · CSS · JavaScript</p></div>
<div class="calc-wrap"><div class="calc">
<div class="display"><div class="expr" id="expr"></div><div class="result" id="result">0</div></div>
<div class="btns">
<button class="btn btn-clr" data-action="clear">AC</button>
<button class="btn btn-func" data-action="sign">+/−</button>
<button class="btn btn-func" data-action="percent">%</button>
<button class="btn btn-op" data-action="op" data-op="÷">÷</button>
<button class="btn btn-num" data-action="num" data-val="7">7</button>
<button class="btn btn-num" data-action="num" data-val="8">8</button>
<button class="btn btn-num" data-action="num" data-val="9">9</button>
<button class="btn btn-op" data-action="op" data-op="×">×</button>
<button class="btn btn-num" data-action="num" data-val="4">4</button>
<button class="btn btn-num" data-action="num" data-val="5">5</button>
<button class="btn btn-num" data-action="num" data-val="6">6</button>
<button class="btn btn-op" data-action="op" data-op="−">−</button>
<button class="btn btn-num" data-action="num" data-val="1">1</button>
<button class="btn btn-num" data-action="num" data-val="2">2</button>
<button class="btn btn-num" data-action="num" data-val="3">3</button>
<button class="btn btn-op" data-action="op" data-op="+">+</button>
<button class="btn btn-num span2" data-action="num" data-val="0">0</button>
<button class="btn btn-num" data-action="decimal">.</button>
<button class="btn btn-eq" data-action="equals">=</button>
</div>
<div class="history" id="history-panel"><div class="history-title">History</div><div id="history-list"><div class="history-empty">No calculations yet</div></div></div>
<div class="kb-hint">↑ keyboard supported</div>
</div></div>
<div class="footer-link">Part of <a href="https://github.com/anandawasthi610-design" target="_blank">Anand's portfolio</a></div>
<script>
'use strict';
const state={current:'0',operator:null,previous:null,expression:'',freshInput:false,justEvaled:false};
const history=[];
const resultEl=document.getElementById('result');
const exprEl=document.getElementById('expr');
const histList=document.getElementById('history-list');
function fmt(v){if(v==='Error')return v;const n=parseFloat(v);if(isNaN(n))return v;if(v.endsWith('.'))return v;if(Math.abs(n)>=1e13||(Math.abs(n)<1e-6&&n!==0))return n.toExponential(4);const p=v.split('.');p[0]=p[0].replace(/\\B(?=(\\d{3})+(?!\\d))/g,',');return p.join('.');}
function upd(pop){const l=state.current.length;resultEl.className='result '+(l>12?'small':l>8?'medium':'');resultEl.textContent=fmt(state.current);exprEl.textContent=state.expression;if(pop){resultEl.classList.remove('pop');void resultEl.offsetWidth;resultEl.classList.add('pop');}}
function inputDigit(d){if(state.current==='Error')clear();if(state.freshInput||state.justEvaled){state.current=d;state.freshInput=false;state.justEvaled=false;}else{const r=state.current.replace('-','').replace('.','');if(r.length>=15)return;state.current=state.current==='0'?d:state.current+d;}upd();}
function inputDecimal(){if(state.current==='Error')clear();if(state.freshInput||state.justEvaled){state.current='0.';state.freshInput=false;state.justEvaled=false;upd();return;}if(!state.current.includes('.')){state.current+='.';upd();}}
function handleOp(op){if(state.current==='Error'){clear();return;}const curr=parseFloat(state.current);if(state.operator&&!state.freshInput&&!state.justEvaled){const r=compute(parseFloat(state.previous),curr,state.operator);if(r===null){showErr();return;}state.previous=String(r);state.current=String(r);}else{state.previous=state.current;}state.operator=op;state.freshInput=true;state.justEvaled=false;state.expression=fmt(state.previous)+' '+op;upd();}
function handleEq(){if(!state.operator||state.current==='Error')return;const a=parseFloat(state.previous),b=parseFloat(state.current);const expr=fmt(state.previous)+' '+state.operator+' '+fmt(state.current)+' =';const r=compute(a,b,state.operator);if(r===null){showErr();return;}addHist(expr,r);state.expression=expr;state.current=String(r);state.operator=null;state.previous=null;state.freshInput=false;state.justEvaled=true;upd(true);resultEl.classList.add('neon');setTimeout(()=>resultEl.classList.remove('neon'),600);}
function compute(a,b,op){let r;if(op==='+')r=a+b;else if(op==='−')r=a-b;else if(op==='×')r=a*b;else if(op==='÷'){if(b===0)return null;r=a/b;}return parseFloat(r.toPrecision(12));}
function toggleSign(){if(state.current==='0'||state.current==='Error')return;state.current=state.current.startsWith('-')?state.current.slice(1):'-'+state.current;upd();}
function handlePct(){if(state.current==='Error')return;state.current=String(parseFloat((parseFloat(state.current)/100).toPrecision(12)));state.justEvaled=false;upd();}
function clear(){state.current='0';state.operator=null;state.previous=null;state.expression='';state.freshInput=false;state.justEvaled=false;resultEl.classList.remove('neon','err');upd();}
function showErr(){state.current='Error';state.operator=null;state.previous=null;state.expression='Cannot divide by zero';state.freshInput=false;state.justEvaled=false;resultEl.classList.add('err');upd();}
function addHist(expr,r){history.unshift({expr:expr.replace(' =',''),result:fmt(String(r))});if(history.length>10)history.pop();renderHist();}
function renderHist(){if(!history.length){histList.innerHTML='<div class="history-empty">No calculations yet</div>';return;}histList.innerHTML=history.map((h,i)=>'<div class="history-item" onclick="recallHist('+i+')" ><span>'+h.expr+'</span><span>'+h.result+'</span></div>').join('');}
function recallHist(i){state.current=history[i].result.replace(/,/g,'');state.freshInput=false;state.justEvaled=true;state.expression=history[i].expr+' =';upd();}
document.querySelectorAll('.btn').forEach(b=>{b.addEventListener('click',()=>{const a=b.dataset.action;if(a==='num')inputDigit(b.dataset.val);if(a==='decimal')inputDecimal();if(a==='op')handleOp(b.dataset.op);if(a==='equals')handleEq();if(a==='clear')clear();if(a==='sign')toggleSign();if(a==='percent')handlePct();});});
const km={'0':'0','1':'1','2':'2','3':'3','4':'4','5':'5','6':'6','7':'7','8':'8','9':'9','+':'+','-':'−','*':'×','/':'÷','Enter':'=','=':'=','.':'.','Escape':'AC','Backspace':'back','%':'%'};
document.addEventListener('keydown',e=>{const m=km[e.key];if(!m)return;e.preventDefault();if('0123456789'.includes(m)){inputDigit(m);return;}if(m==='.'){inputDecimal();return;}if(['+','−','×','÷'].includes(m)){handleOp(m);return;}if(m==='='){handleEq();return;}if(m==='AC'){clear();return;}if(m==='%'){handlePct();return;}if(m==='back'){if(state.current==='Error'||state.freshInput||state.justEvaled)return;state.current=state.current.length>1?state.current.slice(0,-1):'0';upd();}});
upd();
<\/script></body></html>`;

/* ── COPY EMAIL ─────────────────────────────────────────────── */
function copyEmail(){
  const fallback=()=>{
    const ta=document.createElement('textarea');
    ta.value='anandawasthi610@gmail.com';
    document.body.appendChild(ta);ta.select();
    document.execCommand('copy');document.body.removeChild(ta);
    showCopied();
  };
  if(navigator.clipboard){
    navigator.clipboard.writeText('anandawasthi610@gmail.com').then(showCopied).catch(fallback);
  } else { fallback(); }
}
function showCopied(){
  const btn=document.getElementById('cp-btn');
  const lbl=document.getElementById('cp-lbl');
  const ico=document.getElementById('cp-ico');
  btn.classList.add('ok');
  lbl.textContent='Copied!';
  ico.innerHTML='<polyline points="20 6 9 17 4 12" stroke="#22c55e" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>';
  setTimeout(()=>{
    btn.classList.remove('ok');
    lbl.textContent='Copy';
    ico.innerHTML='<rect x="9" y="9" width="13" height="13" rx="2" ry="2"/><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"/>';
  },2200);
}

/* ── 3D CARD TILT ───────────────────────────────────────────── */
function initTilt(){
  document.querySelectorAll('.pj-card,.sk-card,.stat-c').forEach(card=>{
    card.addEventListener('mousemove',e=>{
      const r=card.getBoundingClientRect();
      const x=(e.clientX-r.left-r.width/2)/(r.width/2);
      const y=(e.clientY-r.top-r.height/2)/(r.height/2);
      card.style.transform=`perspective(700px) rotateX(${-y*5}deg) rotateY(${x*5}deg) translateY(-4px)`;
    });
    card.addEventListener('mouseleave',()=>{card.style.transform='';});
  });
}

/* ── INIT ───────────────────────────────────────────────────── */
window.addEventListener('DOMContentLoaded',()=>{
  renderSkills();
  renderProjects();
  renderSocials();
  initReveal();
  setTimeout(initTilt,600);
});
</script>
</body>
</html>
