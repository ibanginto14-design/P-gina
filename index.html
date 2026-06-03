<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DeFi Risk Monitor — Aave &amp; Compound Liquidation Risk</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}html{scroll-behavior:smooth}
:root{
  --bg:#05080f;--bg2:#0b0f1a;--bg3:#111827;
  --bdr:rgba(255,255,255,0.06);--bdr2:rgba(255,255,255,0.12);
  --blue:#4f8ef7;--blue2:#7eb3ff;--purple:#7c3aed;--cyan:#38bdf8;
  --green:#22c55e;--red:#ef4444;--orange:#f97316;--yellow:#eab308;
  --t1:#f0f4ff;--t2:#8b9db5;--t3:#3d5068;
  --ease:cubic-bezier(0.16,1,0.3,1);
}
body{background:var(--bg);color:var(--t1);font-family:'Inter',sans-serif;overflow-x:hidden;line-height:1.6}
#aurora{position:fixed;inset:0;z-index:0;pointer-events:none}
body::after{content:'';position:fixed;inset:0;z-index:1;pointer-events:none;opacity:.025;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  background-size:200px 200px}
.rv{opacity:0;transform:translateY(40px);transition:opacity .7s var(--ease),transform .7s var(--ease)}
.rvl{opacity:0;transform:translateX(-50px);transition:opacity .7s var(--ease),transform .7s var(--ease)}
.rvr{opacity:0;transform:translateX(50px);transition:opacity .7s var(--ease),transform .7s var(--ease)}
.rv.on,.rvl.on,.rvr.on{opacity:1;transform:none}
.d1{transition-delay:.07s}.d2{transition-delay:.14s}.d3{transition-delay:.21s}
.d4{transition-delay:.28s}.d5{transition-delay:.35s}.d6{transition-delay:.42s}
.ann{position:relative;z-index:20;background:linear-gradient(90deg,rgba(79,142,247,.08),rgba(124,58,237,.08));
  border-bottom:1px solid rgba(79,142,247,.2);text-align:center;padding:10px 1.5rem;font-size:.79rem;color:var(--t2)}
.ann a{color:var(--blue2);text-decoration:none;font-weight:600;margin-left:6px}
.ann a:hover{text-decoration:underline}
.lang-btn{position:fixed;bottom:28px;right:28px;z-index:600;display:flex;align-items:center;gap:8px;
  background:rgba(11,15,26,.95);border:1px solid var(--bdr2);border-radius:50px;padding:9px 18px;
  font-size:.8rem;font-weight:600;color:var(--t1);cursor:pointer;transition:all .2s;
  box-shadow:0 8px 32px rgba(0,0,0,.5),0 0 0 1px rgba(79,142,247,.1)}
.lang-btn:hover{border-color:var(--blue);color:var(--blue2)}
nav{position:sticky;top:0;z-index:200;background:rgba(5,8,15,.82);backdrop-filter:blur(24px) saturate(180%);
  border-bottom:1px solid var(--bdr);display:flex;align-items:center;justify-content:space-between;
  padding:0 2.5rem;height:64px;transition:all .3s}
nav.scrolled{border-bottom-color:rgba(255,255,255,.1);background:rgba(5,8,15,.92)}
.nav-logo{font-size:1rem;font-weight:700;color:var(--t1);display:flex;align-items:center;gap:10px;text-decoration:none}
.logo-mark{width:32px;height:32px;border-radius:8px;background:linear-gradient(135deg,var(--blue),var(--purple));
  display:flex;align-items:center;justify-content:center;font-size:.72rem;font-weight:800;color:#fff;flex-shrink:0}
.nav-links{display:flex;gap:2px;list-style:none}
.nav-links a{font-size:.84rem;color:var(--t2);text-decoration:none;padding:6px 13px;border-radius:7px;transition:color .15s,background .15s}
.nav-links a:hover{color:var(--t1);background:rgba(255,255,255,.05)}
.nav-right{display:flex;gap:9px;align-items:center}
.btn-ghost{font-size:.82rem;color:var(--t2);font-weight:500;border:1px solid var(--bdr2);background:transparent;
  padding:7px 16px;border-radius:8px;text-decoration:none;transition:all .15s;white-space:nowrap}
.btn-ghost:hover{color:var(--t1);border-color:rgba(255,255,255,.22);background:rgba(255,255,255,.04)}
.btn-cta{font-size:.82rem;color:#fff;font-weight:600;background:var(--blue);padding:7px 18px;border-radius:8px;
  text-decoration:none;transition:all .2s;white-space:nowrap;box-shadow:0 0 20px rgba(79,142,247,.3)}
.btn-cta:hover{background:#3b7de8;transform:translateY(-1px);box-shadow:0 4px 28px rgba(79,142,247,.5)}
.hero{position:relative;min-height:100vh;display:flex;flex-direction:column;align-items:center;
  justify-content:center;text-align:center;padding:7rem 2rem 5rem;overflow:hidden}
.hero-grid{position:absolute;inset:0;z-index:2;
  background-image:linear-gradient(rgba(79,142,247,.04) 1px,transparent 1px),linear-gradient(90deg,rgba(79,142,247,.04) 1px,transparent 1px);
  background-size:60px 60px;
  mask-image:radial-gradient(ellipse 85% 70% at 50% 0%,black 30%,transparent 100%);
  -webkit-mask-image:radial-gradient(ellipse 85% 70% at 50% 0%,black 30%,transparent 100%)}
.orb{position:absolute;border-radius:50%;pointer-events:none;z-index:2}
.orb1{width:600px;height:600px;top:-200px;left:50%;transform:translateX(-50%);
  background:radial-gradient(circle,rgba(79,142,247,.12),transparent 65%);animation:of1 8s ease-in-out infinite}
.orb2{width:350px;height:350px;top:30%;right:-100px;
  background:radial-gradient(circle,rgba(124,58,237,.1),transparent 65%);animation:of2 10s ease-in-out infinite}
.orb3{width:300px;height:300px;top:20%;left:-80px;
  background:radial-gradient(circle,rgba(56,189,248,.08),transparent 65%);animation:of3 12s ease-in-out infinite}
@keyframes of1{0%,100%{transform:translateX(-50%) translateY(0)}50%{transform:translateX(-50%) translateY(-22px)}}
@keyframes of2{0%,100%{transform:translateY(0)}50%{transform:translateY(-28px)}}
@keyframes of3{0%,100%{transform:translateY(0)}50%{transform:translateY(22px)}}
.hero-fade{position:absolute;bottom:0;left:0;right:0;height:260px;background:linear-gradient(transparent,var(--bg));z-index:3;pointer-events:none}
.hero-inner{position:relative;z-index:4;display:flex;flex-direction:column;align-items:center;max-width:900px}
.hero-badge{display:inline-flex;align-items:center;gap:9px;background:rgba(79,142,247,.08);
  border:1px solid rgba(79,142,247,.2);border-radius:50px;padding:7px 18px;font-size:.78rem;color:var(--blue2);
  font-weight:500;margin-bottom:2rem;backdrop-filter:blur(8px)}
.bdot{width:7px;height:7px;border-radius:50%;background:var(--green);
  box-shadow:0 0 0 2px rgba(34,197,94,.3);animation:bd 2s ease-in-out infinite}
@keyframes bd{0%,100%{box-shadow:0 0 0 2px rgba(34,197,94,.3)}50%{box-shadow:0 0 0 5px rgba(34,197,94,.15)}}
h1.hero-h{font-size:clamp(2.8rem,7vw,5.2rem);font-weight:800;line-height:1.06;
  letter-spacing:-.04em;margin-bottom:1.5rem;color:var(--t1)}
h1.hero-h .grad{background:linear-gradient(135deg,#4f8ef7 0%,#a78bfa 45%,#38bdf8 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:300%;animation:ga 6s ease infinite alternate}
@keyframes ga{0%{background-position:0%}100%{background-position:100%}}
.hero-sub{font-size:1.05rem;color:var(--t2);max-width:580px;line-height:1.75;margin-bottom:2.5rem}
.hero-ctas{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-bottom:4.5rem}
.btn-hp{font-size:.92rem;color:#fff;font-weight:600;background:var(--blue);padding:14px 32px;border-radius:10px;
  text-decoration:none;transition:all .25s;box-shadow:0 0 28px rgba(79,142,247,.4)}
.btn-hp:hover{background:#3b7de8;transform:translateY(-2px);box-shadow:0 8px 40px rgba(79,142,247,.6)}
.btn-hs{font-size:.92rem;color:var(--t1);font-weight:500;background:rgba(255,255,255,.05);
  border:1px solid var(--bdr2);padding:14px 32px;border-radius:10px;text-decoration:none;transition:all .2s}
.btn-hs:hover{background:rgba(255,255,255,.09);border-color:rgba(255,255,255,.22)}
.stats-row{display:flex;border:1px solid var(--bdr);border-radius:14px;overflow:hidden;
  background:rgba(11,15,26,.8);backdrop-filter:blur(12px);max-width:720px;width:100%}
.stat{flex:1;padding:1.5rem 1rem;text-align:center;border-right:1px solid var(--bdr);transition:background .2s}
.stat:last-child{border-right:none}
.stat:hover{background:rgba(255,255,255,.03)}
.snum{font-size:1.8rem;font-weight:800;color:var(--t1);display:block;letter-spacing:-.03em;line-height:1}
.slbl{font-size:.68rem;color:var(--t3);text-transform:uppercase;letter-spacing:.1em;margin-top:5px}
.mqs{position:relative;z-index:5;border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr);
  background:rgba(11,15,26,.9);backdrop-filter:blur(12px);padding:1.6rem 0;overflow:hidden}
.mq-lbl{text-align:center;font-size:.68rem;color:var(--t3);text-transform:uppercase;letter-spacing:.14em;margin-bottom:1.2rem}
.mwrap{overflow:hidden;position:relative}
.mwrap::before,.mwrap::after{content:'';position:absolute;top:0;bottom:0;width:140px;z-index:2;pointer-events:none}
.mwrap::before{left:0;background:linear-gradient(90deg,rgba(11,15,26,.9),transparent)}
.mwrap::after{right:0;background:linear-gradient(-90deg,rgba(11,15,26,.9),transparent)}
.mtrack{display:flex;gap:10px;animation:msc 35s linear infinite;width:max-content}
.mtrack:hover{animation-play-state:paused}
@keyframes msc{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
.mchip{display:flex;align-items:center;gap:8px;font-size:.79rem;color:var(--t2);font-weight:500;
  border:1px solid var(--bdr);background:rgba(255,255,255,.02);border-radius:50px;
  padding:7px 16px;white-space:nowrap;flex-shrink:0;transition:all .2s}
.mchip:hover{border-color:var(--bdr2);background:rgba(255,255,255,.05);color:var(--t1)}
.mdot{width:7px;height:7px;border-radius:50%;flex-shrink:0}
.sec{padding:7rem 2rem;position:relative;z-index:5}
.sec-alt{background:linear-gradient(180deg,var(--bg2),rgba(11,15,26,.6));border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr)}
.sin{max-width:1140px;margin:0 auto}
.sec-lbl{font-size:.7rem;color:var(--blue2);font-weight:600;text-transform:uppercase;letter-spacing:.18em;margin-bottom:.75rem}
h2.sh{font-size:clamp(1.9rem,4vw,2.9rem);font-weight:800;letter-spacing:-.03em;color:var(--t1);line-height:1.1;margin-bottom:.9rem}
.ssub{font-size:.97rem;color:var(--t2);max-width:530px;line-height:1.75}
.sh-block{margin-bottom:3.5rem}
.sh-row{display:flex;align-items:flex-end;justify-content:space-between;gap:2rem;flex-wrap:wrap}
.sg-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));
  gap:1px;background:var(--bdr);border:1px solid var(--bdr);border-radius:16px;overflow:hidden}
.sg-card{background:var(--bg2);padding:1.7rem;transition:background .2s,transform .25s var(--ease);
  display:flex;flex-direction:column;gap:1.1rem;position:relative;overflow:hidden;text-decoration:none;color:inherit}
.sg-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;opacity:0;transition:opacity .3s}
.sg-card:hover::before{opacity:1}
.sg-card:hover{background:var(--bg3);transform:translateY(-2px)}
.sg-card::after{content:'';position:absolute;inset:0;opacity:0;transition:opacity .3s;pointer-events:none}
.sg-card:hover::after{opacity:1}
.ceth::before{background:linear-gradient(90deg,#627eea,#9db0ff)}.ceth::after{background:radial-gradient(ellipse at 50% 0%,rgba(98,126,234,.06),transparent 70%)}
.carb::before{background:linear-gradient(90deg,#12aaff,#5ed5ff)}.carb::after{background:radial-gradient(ellipse at 50% 0%,rgba(18,170,255,.06),transparent 70%)}
.cbas::before{background:linear-gradient(90deg,#0052ff,#7aadff)}.cbas::after{background:radial-gradient(ellipse at 50% 0%,rgba(0,82,255,.06),transparent 70%)}
.copt::before{background:linear-gradient(90deg,#ff0420,#ff8a96)}.copt::after{background:radial-gradient(ellipse at 50% 0%,rgba(255,4,32,.06),transparent 70%)}
.cpol::before{background:linear-gradient(90deg,#8247e5,#c28bff)}.cpol::after{background:radial-gradient(ellipse at 50% 0%,rgba(130,71,229,.06),transparent 70%)}
.ccmp::before{background:linear-gradient(90deg,#00d395,#5cffd0)}.ccmp::after{background:radial-gradient(ellipse at 50% 0%,rgba(0,211,149,.06),transparent 70%)}
.sg-top{display:flex;align-items:center;justify-content:space-between;position:relative;z-index:1}
.cpill{font-size:.65rem;font-weight:700;text-transform:uppercase;letter-spacing:.1em;padding:4px 11px;border-radius:50px}
.peth{background:rgba(98,126,234,.15);color:#9db0ff}.parb{background:rgba(18,170,255,.12);color:#5ed5ff}
.pbas{background:rgba(0,82,255,.12);color:#7aadff}.popt{background:rgba(255,4,32,.12);color:#ff8a96}
.ppol{background:rgba(130,71,229,.15);color:#c28bff}.pcmp{background:rgba(0,211,149,.1);color:#5cffd0}
.live-p{display:flex;align-items:center;gap:5px;font-size:.67rem;color:var(--green);font-weight:600}
.live-p::before{content:'';width:5px;height:5px;border-radius:50%;background:var(--green);
  box-shadow:0 0 6px rgba(34,197,94,.8);animation:lp 2s infinite}
@keyframes lp{0%,100%{box-shadow:0 0 4px rgba(34,197,94,.8)}50%{box-shadow:0 0 10px rgba(34,197,94,.5)}}
.sg-name{font-size:.87rem;font-weight:700;color:var(--t1);line-height:1.3;font-family:'Courier New',monospace;position:relative;z-index:1}
.sg-proto{font-size:.73rem;color:var(--t3);margin-top:3px;position:relative;z-index:1}
.sg-hr{border:none;border-top:1px solid var(--bdr);position:relative;z-index:1}
.sg-stats{display:flex;flex-direction:column;gap:9px;position:relative;z-index:1}
.sg-row{display:flex;justify-content:space-between;align-items:center}
.sg-k{font-size:.67rem;color:var(--t3);text-transform:uppercase;letter-spacing:.09em;font-weight:600}
.sg-v{font-size:.84rem;font-weight:700;color:var(--t1)}
.spin{display:inline-block;width:10px;height:10px;border:2px solid var(--bdr2);border-top-color:var(--blue);border-radius:50%;animation:sp .6s linear infinite;vertical-align:middle}
@keyframes sp{to{transform:rotate(360deg)}}
.last-upd{font-size:.69rem;color:var(--t3);margin-top:1rem}
.sticky-wrap{display:grid;grid-template-columns:1fr 1fr;gap:7rem;align-items:start}
.sticky-left{position:sticky;top:100px;height:fit-content}
.feat-box{position:relative;border-radius:20px;overflow:hidden;border:1px solid var(--bdr);
  background:var(--bg3);aspect-ratio:4/3;transition:border-color .4s,box-shadow .4s}
.feat-box:hover{border-color:rgba(79,142,247,.3);box-shadow:0 0 60px rgba(79,142,247,.1)}
.feat-em{width:100%;height:100%;display:flex;align-items:center;justify-content:center;
  font-size:5.5rem;transition:opacity .3s,transform .35s var(--ease)}
.feat-glow{position:absolute;inset:0;opacity:0;transition:opacity .5s;pointer-events:none}
.feat-box:hover .feat-glow{opacity:1}
.corn{position:absolute;width:18px;height:18px;border-color:rgba(79,142,247,.5);border-style:solid;pointer-events:none}
.c-tl{top:14px;left:14px;border-width:2px 0 0 2px}.c-tr{top:14px;right:14px;border-width:2px 2px 0 0}
.c-bl{bottom:14px;left:14px;border-width:0 0 2px 2px}.c-br{bottom:14px;right:14px;border-width:0 2px 2px 0}
.sp{padding:2.75rem 0;border-bottom:1px solid var(--bdr);transition:padding-left .3s,border-left-width .3s}
.sp:first-child{padding-top:0}.sp:last-child{border-bottom:none}
.sp.active-sp{padding-left:1rem;border-left:2px solid var(--blue)}
.sp-num{font-size:.68rem;color:var(--t3);font-weight:700;letter-spacing:.12em;text-transform:uppercase;margin-bottom:.9rem}
.sp-title{font-size:1.2rem;font-weight:700;color:var(--t1);margin-bottom:.6rem;letter-spacing:-.015em}
.sp-desc{font-size:.87rem;color:var(--t2);line-height:1.7;max-width:420px}
.sp-tags{display:flex;flex-wrap:wrap;gap:8px;margin-top:1rem}
.sp-tag{font-size:.7rem;color:var(--t3);border:1px solid var(--bdr);background:rgba(255,255,255,.02);
  border-radius:6px;padding:4px 11px;font-family:'Courier New',monospace;transition:all .2s}
.sp-tag:hover{border-color:rgba(79,142,247,.4);color:var(--blue2)}
.rg{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:12px;margin-bottom:3rem}
.rc{border-radius:12px;padding:1.4rem;border:1px solid transparent;
  transition:transform .25s var(--ease),box-shadow .25s;cursor:default;position:relative;overflow:hidden}
.rc::before{content:'';position:absolute;inset:0;opacity:0;transition:opacity .3s;pointer-events:none}
.rc:hover{transform:translateY(-5px)}.rc:hover::before{opacity:1}
.rcrit{background:rgba(239,68,68,.06);border-color:rgba(239,68,68,.18)}.rcrit:hover{box-shadow:0 12px 40px rgba(239,68,68,.15)}.rcrit::before{background:radial-gradient(ellipse at 50% 0%,rgba(239,68,68,.08),transparent 70%)}
.rdang{background:rgba(249,115,22,.06);border-color:rgba(249,115,22,.16)}.rdang:hover{box-shadow:0 12px 40px rgba(249,115,22,.12)}.rdang::before{background:radial-gradient(ellipse at 50% 0%,rgba(249,115,22,.08),transparent 70%)}
.rwarn{background:rgba(234,179,8,.06);border-color:rgba(234,179,8,.16)}.rwarn:hover{box-shadow:0 12px 40px rgba(234,179,8,.1)}.rwarn::before{background:radial-gradient(ellipse at 50% 0%,rgba(234,179,8,.08),transparent 70%)}
.rcaut{background:rgba(79,142,247,.06);border-color:rgba(79,142,247,.16)}.rcaut:hover{box-shadow:0 12px 40px rgba(79,142,247,.12)}.rcaut::before{background:radial-gradient(ellipse at 50% 0%,rgba(79,142,247,.08),transparent 70%)}
.rsafe{background:rgba(34,197,94,.06);border-color:rgba(34,197,94,.16)}.rsafe:hover{box-shadow:0 12px 40px rgba(34,197,94,.12)}.rsafe::before{background:radial-gradient(ellipse at 50% 0%,rgba(34,197,94,.08),transparent 70%)}
.rn{font-size:.68rem;font-weight:800;text-transform:uppercase;letter-spacing:.15em;margin-bottom:.5rem}
.rcrit .rn{color:#ef4444}.rdang .rn{color:#f97316}.rwarn .rn{color:#eab308}.rcaut .rn{color:#60a5fa}.rsafe .rn{color:#22c55e}
.rhf{font-size:1.1rem;font-weight:700;color:var(--t1);margin-bottom:.35rem}
.rdsc{font-size:.77rem;color:var(--t2);line-height:1.55}
.ent-row{display:flex;flex-wrap:wrap;gap:9px;margin-top:2rem}
.ebdg{font-size:.77rem;color:var(--t2);border:1px solid var(--bdr2);background:rgba(255,255,255,.02);
  padding:6px 14px;border-radius:7px;font-family:'Courier New',monospace;transition:all .2s;cursor:default}
.ebdg:hover{border-color:rgba(79,142,247,.45);color:var(--blue2);background:rgba(79,142,247,.07);transform:translateY(-1px)}
.gauge-sec{background:linear-gradient(180deg,var(--bg2),var(--bg));border-top:1px solid var(--bdr);border-bottom:1px solid var(--bdr);padding:7rem 2rem;position:relative;z-index:5}
.gauge-in{max-width:1140px;margin:0 auto;display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:center}
.g-leg-row{display:flex;gap:1.5rem;flex-wrap:wrap;margin-top:1.5rem}
.g-leg{display:flex;align-items:center;gap:8px;font-size:.81rem;color:var(--t2)}
.g-dot{width:9px;height:9px;border-radius:50%;display:inline-block}
.mbar{display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:1px;background:var(--bdr);
  border:1px solid var(--bdr);border-radius:16px;overflow:hidden;margin-bottom:4rem}
.mc{background:var(--bg2);padding:2rem;transition:background .2s;cursor:default;position:relative;overflow:hidden}
.mc::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(79,142,247,.3),transparent);opacity:0;transition:opacity .3s}
.mc:hover{background:var(--bg3)}.mc:hover::before{opacity:1}
.mv{font-size:2.5rem;font-weight:800;letter-spacing:-.04em;display:block;line-height:1;
  background:linear-gradient(135deg,var(--t1),var(--blue2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.ml{font-size:.78rem;color:var(--t2);margin-top:7px;font-weight:500}
.ms{font-size:.71rem;color:var(--t3);margin-top:3px}
.cw{background:var(--bg2);border:1px solid var(--bdr);border-radius:16px;overflow:hidden;transition:border-color .3s,box-shadow .3s}
.cw:hover{border-color:rgba(79,142,247,.25);box-shadow:0 0 50px rgba(79,142,247,.07)}
.cb-bar{display:flex;align-items:center;justify-content:space-between;padding:.9rem 1.5rem;border-bottom:1px solid var(--bdr)}
.dots{display:flex;gap:6px}.dot{width:12px;height:12px;border-radius:50%}
.dr{background:#ff5f57}.dy{background:#febc2e}.dg{background:#28c840}
.cl-tag{font-size:.72rem;color:var(--t3);font-family:'Courier New',monospace}
.cb-body{padding:2rem;overflow-x:auto}
pre{font-family:'Courier New',monospace;font-size:.82rem;line-height:1.9;color:var(--t2)}
.kw{color:#c792ea}.fn{color:#82aaff}.str{color:#c3e88d}.nm{color:#f78c6c}.cm{color:#4a6272}.op{color:#89ddff}
.cta-ban{position:relative;overflow:hidden;z-index:5;padding:8rem 2rem;text-align:center;
  background:linear-gradient(135deg,rgba(79,142,247,.08),rgba(124,58,237,.06) 50%,rgba(56,189,248,.04));
  border-top:1px solid rgba(79,142,247,.15);border-bottom:1px solid rgba(79,142,247,.15)}
.cta-ban::before{content:'';position:absolute;top:-250px;left:50%;transform:translateX(-50%);
  width:700px;height:500px;background:radial-gradient(ellipse,rgba(79,142,247,.14),transparent 65%);pointer-events:none}
.cta-inner{position:relative;z-index:1}
.cta-row{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
footer{border-top:1px solid var(--bdr);max-width:1140px;margin:0 auto;padding:3.5rem 2rem 2rem;position:relative;z-index:5}
.ft{display:grid;grid-template-columns:1.7fr 1fr 1fr 1fr;gap:3rem;margin-bottom:3rem;padding-bottom:3rem;border-bottom:1px solid var(--bdr)}
.fbrand{display:flex;flex-direction:column;gap:1rem}
.fdesc{font-size:.82rem;color:var(--t3);line-height:1.65;max-width:220px}
.fcol h4{font-size:.71rem;font-weight:700;color:var(--t1);text-transform:uppercase;letter-spacing:.13em;margin-bottom:1.1rem}
.fcol ul{list-style:none;display:flex;flex-direction:column;gap:9px}
.fcol li a{font-size:.81rem;color:var(--t3);text-decoration:none;transition:color .15s}
.fcol li a:hover{color:var(--t2)}
.fb{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem}
.fcopy{font-size:.77rem;color:var(--t3)}
.flinks{display:flex;gap:1.5rem}
.flinks a{font-size:.77rem;color:var(--t3);text-decoration:none;transition:color .15s}
.flinks a:hover{color:var(--t2)}
hr.div{border:none;border-top:1px solid var(--bdr);position:relative;z-index:5}
@media(max-width:900px){.sticky-wrap{grid-template-columns:1fr;gap:2rem}.sticky-left{position:relative;top:0}.feat-box{aspect-ratio:2/1}.gauge-in{grid-template-columns:1fr;gap:2rem}.ft{grid-template-columns:1fr 1fr;gap:2rem}.nav-links{display:none}}
@media(max-width:600px){.ft{grid-template-columns:1fr}.stats-row{flex-direction:column}.stat{border-right:none;border-bottom:1px solid var(--bdr)}.stat:last-child{border-bottom:none}h1.hero-h{font-size:2.4rem}}
</style>
</head>
<body>
<canvas id="aurora"></canvas>
<div class="ann">
  <span data-i18n="ann_t">New: Cascade Risk Alert simulates liquidation impact across 280,000+ positions.</span>
  <a href="https://web-production-387cf.up.railway.app" target="_blank" data-i18n="ann_l">View Live Dashboard →</a>
</div>
<button class="lang-btn" onclick="toggleLang()">
  <span id="lf">🇬🇧</span><span id="ll">Español</span>
</button>
<nav id="navbar">
  <a href="#" class="nav-logo"><div class="logo-mark">DR</div>DeFi Risk Monitor</a>
  <ul class="nav-links">
    <li><a href="#subgraphs" data-i18n="n_sg">Subgraphs</a></li>
    <li><a href="#features" data-i18n="n_ft">Features</a></li>
    <li><a href="#risk" data-i18n="n_rk">Risk Levels</a></li>
    <li><a href="#query" data-i18n="n_qr">Query API</a></li>
  </ul>
  <div class="nav-right">
    <a href="https://thegraph.com/explorer" target="_blank" class="btn-ghost" data-i18n="n_tg">The Graph</a>
    <a href="https://web-production-387cf.up.railway.app" target="_blank" class="btn-cta" data-i18n="n_db">Live Dashboard</a>
  </div>
</nav>
<div class="hero">
  <div class="hero-grid"></div>
  <div class="orb orb1"></div><div class="orb orb2"></div><div class="orb orb3"></div>
  <div class="hero-inner">
    <div class="hero-badge rv d1"><span class="bdot"></span><span data-i18n="h_bg">Live · Monitoring 280,000+ Active Positions</span></div>
    <h1 class="hero-h rv d2"><span data-i18n="h_t1">Real-Time Liquidation Risk</span><br><span data-i18n="h_t2">Monitor for </span><span class="grad">Aave &amp; Compound</span></h1>
    <p class="hero-sub rv d3" data-i18n="h_sb">Track every borrowing position across Ethereum, Arbitrum, Base, Optimism and Polygon. 5 risk levels, global DeFi Risk Index, and instant cascade simulation alerts.</p>
    <div class="hero-ctas rv d4">
      <a href="#subgraphs" class="btn-hp" data-i18n="h_c1">Explore Subgraphs</a>
      <a href="https://web-production-387cf.up.railway.app" target="_blank" class="btn-hs" data-i18n="h_c2">Live Dashboard →</a>
    </div>
    <div class="stats-row rv d5">
      <div class="stat"><span class="snum">280K+</span><span class="slbl" data-i18n="s1">Active Positions</span></div>
      <div class="stat"><span class="snum">5</span><span class="slbl" data-i18n="s2">Chains</span></div>
      <div class="stat"><span class="snum">220K+</span><span class="slbl" data-i18n="s3">Queries / 30d</span></div>
      <div class="stat"><span class="snum">71K</span><span class="slbl" data-i18n="s4">GRT Signal</span></div>
    </div>
  </div>
  <div class="hero-fade"></div>
</div>
<div class="mqs">
  <div class="mq-lbl" data-i18n="dep">Deployed on</div>
  <div class="mwrap"><div class="mtrack">
    <div class="mchip"><span class="mdot" style="background:#627eea"></span>Ethereum</div>
    <div class="mchip"><span class="mdot" style="background:#12aaff"></span>Arbitrum</div>
    <div class="mchip"><span class="mdot" style="background:#0052ff"></span>Base</div>
    <div class="mchip"><span class="mdot" style="background:#8247e5"></span>Polygon</div>
    <div class="mchip"><span class="mdot" style="background:#ff0420"></span>Optimism</div>
    <div class="mchip"><span class="mdot" style="background:#6748ff"></span>The Graph Protocol</div>
    <div class="mchip"><span class="mdot" style="background:#b6509e"></span>Aave V3</div>
    <div class="mchip"><span class="mdot" style="background:#00d395"></span>Compound V3</div>
    <div class="mchip"><span class="mdot" style="background:#f5a623"></span>GRT Token</div>
    <div class="mchip"><span class="mdot" style="background:#24a1de"></span>Telegram Bot</div>
    <div class="mchip"><span class="mdot" style="background:#5865f2"></span>Discord Alerts</div>
    <div class="mchip"><span class="mdot" style="background:#0fa963"></span>Railway</div>
    <div class="mchip"><span class="mdot" style="background:#627eea"></span>Ethereum</div>
    <div class="mchip"><span class="mdot" style="background:#12aaff"></span>Arbitrum</div>
    <div class="mchip"><span class="mdot" style="background:#0052ff"></span>Base</div>
    <div class="mchip"><span class="mdot" style="background:#8247e5"></span>Polygon</div>
    <div class="mchip"><span class="mdot" style="background:#ff0420"></span>Optimism</div>
    <div class="mchip"><span class="mdot" style="background:#6748ff"></span>The Graph Protocol</div>
    <div class="mchip"><span class="mdot" style="background:#b6509e"></span>Aave V3</div>
    <div class="mchip"><span class="mdot" style="background:#00d395"></span>Compound V3</div>
    <div class="mchip"><span class="mdot" style="background:#f5a623"></span>GRT Token</div>
    <div class="mchip"><span class="mdot" style="background:#24a1de"></span>Telegram Bot</div>
    <div class="mchip"><span class="mdot" style="background:#5865f2"></span>Discord Alerts</div>
    <div class="mchip"><span class="mdot" style="background:#0fa963"></span>Railway</div>
  </div></div>
</div>
<section class="sec" id="subgraphs">
  <div class="sin">
    <div class="sh-block sh-row">
      <div>
        <div class="sec-lbl rv" data-i18n="sg_l">The Graph Protocol</div>
        <h2 class="sh rv d1" data-i18n="sg_h">Deployed Subgraphs</h2>
        <p class="ssub rv d2" data-i18n="sg_s">6 production subgraphs on The Graph Network. Click any card to open it in the explorer.</p>
      </div>
      <div class="rv d2" style="display:flex;gap:9px;align-items:flex-end;flex-wrap:wrap">
        <button onclick="fetchAll()" id="ref-btn" style="cursor:pointer;font-size:.8rem;color:var(--blue2);border:1px solid rgba(79,142,247,.3);padding:8px 16px;border-radius:8px;background:rgba(79,142,247,.06);display:inline-flex;align-items:center;gap:6px;transition:all .2s;font-family:inherit" data-i18n="sg_rf">↻ Refresh</button>
        <a href="https://thegraph.com/explorer/profile/0x967c1f6fb8b5ecbabfe442120487ec2ba220a189?view=Subgraphs&chain=arbitrum-one" target="_blank" class="btn-ghost" data-i18n="sg_va">View all →</a>
      </div>
    </div>
    <div id="last-upd" class="last-upd rv"></div>
    <div class="sg-grid" style="margin-top:1.5rem">
      <a href="https://thegraph.com/explorer/subgraphs/Hmqe4B5PJ9AJ5T6bxiMg8bHfRASRHiSKJj6yqCHfpMBT?view=About&chain=arbitrum-one" target="_blank" class="sg-card ceth rv d1" id="c-eth">
        <div class="sg-top"><span class="cpill peth">Ethereum</span><span class="live-p" data-i18n="live">Live</span></div>
        <div><div class="sg-name">aave-liquidation-risk</div><div class="sg-proto">Aave V3 · Lending · DeFi</div></div>
        <hr class="sg-hr">
        <div class="sg-stats" id="s-eth"><div class="sg-row"><span class="sg-k" data-i18n="q30">Queries 30d</span><span class="sg-v"><span class="spin"></span></span></div><div class="sg-row"><span class="sg-k" data-i18n="sig">Signal</span><span class="sg-v"><span class="spin"></span></span></div></div>
      </a>
      <a href="https://thegraph.com/explorer/subgraphs/GCgNt6jsf8KWJbHBWWbwPM9MQrRiWb48kZ8VGbCNAXmH?view=About&chain=arbitrum-one" target="_blank" class="sg-card carb rv d2" id="c-arb">
        <div class="sg-top"><span class="cpill parb">Arbitrum</span><span class="live-p" data-i18n="live">Live</span></div>
        <div><div class="sg-name">aave-liquidation-risk-arbitrum</div><div class="sg-proto">Aave V3 · Lending · DeFi</div></div>
        <hr class="sg-hr">
        <div class="sg-stats" id="s-arb"><div class="sg-row"><span class="sg-k" data-i18n="q30">Queries 30d</span><span class="sg-v"><span class="spin"></span></span></div><div class="sg-row"><span class="sg-k" data-i18n="sig">Signal</span><span class="sg-v"><span class="spin"></span></span></div></div>
      </a>
      <a href="https://thegraph.com/explorer/subgraphs/Bf9yBDX9XrpNXLkfktdaSYBbfswdxcFkXzdMmBvL83SF?view=About&chain=arbitrum-one" target="_blank" class="sg-card cbas rv d3" id="c-bas">
        <div class="sg-top"><span class="cpill pbas">Base</span><span class="live-p" data-i18n="live">Live</span></div>
        <div><div class="sg-name">aave-liquidation-risk-base</div><div class="sg-proto">Aave V3 · Lending · DeFi</div></div>
        <hr class="sg-hr">
        <div class="sg-stats" id="s-bas"><div class="sg-row"><span class="sg-k" data-i18n="q30">Queries 30d</span><span class="sg-v"><span class="spin"></span></span></div><div class="sg-row"><span class="sg-k" data-i18n="sig">Signal</span><span class="sg-v"><span class="spin"></span></span></div></div>
      </a>
      <a href="https://thegraph.com/explorer/subgraphs/FBVyahKnFFc1b6E7CpRHK59whHta3AkLCAgqfpReXAvK?view=About&chain=arbitrum-one" target="_blank" class="sg-card cpol rv d4" id="c-pol">
        <div class="sg-top"><span class="cpill ppol">Polygon</span><span class="live-p" data-i18n="live">Live</span></div>
        <div><div class="sg-name">aave-liquidation-risk-polygon</div><div class="sg-proto">Aave V3 · Lending · DeFi</div></div>
        <hr class="sg-hr">
        <div class="sg-stats" id="s-pol"><div class="sg-row"><span class="sg-k" data-i18n="q30">Queries 30d</span><span class="sg-v"><span class="spin"></span></span></div><div class="sg-row"><span class="sg-k" data-i18n="sig">Signal</span><span class="sg-v"><span class="spin"></span></span></div></div>
      </a>
      <a href="https://thegraph.com/explorer/subgraphs/9hdBacnHPDmiMCNjdFUcPFgGcPPnYWrofsKvqjoEvcKu?view=About&chain=arbitrum-one" target="_blank" class="sg-card copt rv d5" id="c-opt">
        <div class="sg-top"><span class="cpill popt">Optimism</span><span class="live-p" data-i18n="live">Live</span></div>
        <div><div class="sg-name">aave-liquidation-risk-optimism</div><div class="sg-proto">Aave V3 · Lending · DeFi</div></div>
        <hr class="sg-hr">
        <div class="sg-stats" id="s-opt"><div class="sg-row"><span class="sg-k" data-i18n="q30">Queries 30d</span><span class="sg-v"><span class="spin"></span></span></div><div class="sg-row"><span class="sg-k" data-i18n="sig">Signal</span><span class="sg-v"><span class="spin"></span></span></div></div>
      </a>
      <a href="https://thegraph.com/explorer/subgraphs/FBVyahKnFFc1b6E7CpRHK59whHta3AkLCAgqfpReXAvK?view=About&chain=arbitrum-one" target="_blank" class="sg-card ccmp rv d6" id="c-cmp">
        <div class="sg-top"><span class="cpill pcmp">Compound V3</span><span class="live-p" data-i18n="live">Live</span></div>
        <div><div class="sg-name">compound-v3-liquidation-risk</div><div class="sg-proto">Compound V3 · Lending · DeFi</div></div>
        <hr class="sg-hr">
        <div class="sg-stats" id="s-cmp"><div class="sg-row"><span class="sg-k" data-i18n="ent">Entity Types</span><span class="sg-v">5</span></div><div class="sg-row"><span class="sg-k" data-i18n="st">Status</span><span class="sg-v" data-i18n="live">Live</span></div></div>
      </a>
    </div>
  </div>
</section>
<hr class="div">
<section class="sec sec-alt" id="features">
  <div class="sin">
    <div class="sh-block">
      <div class="sec-lbl rv" data-i18n="f_l">Ecosystem</div>
      <h2 class="sh rv d1" data-i18n="f_h">Built Around the Subgraphs.</h2>
      <p class="ssub rv d2" data-i18n="f_s">A full monitoring stack delivering risk intelligence across multiple channels, powered entirely by on-chain data.</p>
    </div>
    <div class="sticky-wrap">
      <div class="sticky-left rvl">
        <div class="feat-box" id="feat-box">
          <div class="corn c-tl"></div><div class="corn c-tr"></div>
          <div class="corn c-bl"></div><div class="corn c-br"></div>
          <div class="feat-em" id="feat-em">⚡</div>
          <div class="feat-glow" id="feat-glow"></div>
        </div>
      </div>
      <div id="feat-list">
        <div class="sp rv" data-em="⚡" data-gl="rgba(79,142,247,.15)">
          <div class="sp-num">01</div><div class="sp-title" data-i18n="f1t">Cascade Risk Alert</div>
          <p class="sp-desc" data-i18n="f1d">Simulates market impact before it happens. Models liquidation cascades to detect systemic DeFi risk before prices move.</p>
          <div class="sp-tags"><span class="sp-tag">Simulation</span><span class="sp-tag">Market Impact</span><span class="sp-tag">Real-time</span></div>
        </div>
        <div class="sp rv" data-em="📊" data-gl="rgba(34,197,94,.1)">
          <div class="sp-num">02</div><div class="sp-title" data-i18n="f2t">Web Dashboard</div>
          <p class="sp-desc" data-i18n="f2d">Live dashboard showing real-time position health, risk distribution, and the global DeFi Risk Index (0–100), updated on every block.</p>
          <div class="sp-tags"><span class="sp-tag">Real-time</span><span class="sp-tag">Multi-chain</span><span class="sp-tag">Risk Index</span></div>
        </div>
        <div class="sp rv" data-em="🤖" data-gl="rgba(36,161,222,.1)">
          <div class="sp-num">03</div><div class="sp-title" data-i18n="f3t">Telegram Bot</div>
          <p class="sp-desc" data-i18n="f3d">Instant push notifications for CRITICAL and DANGER positions. Alerted the moment a position enters liquidation territory.</p>
          <div class="sp-tags"><span class="sp-tag">Push Alerts</span><span class="sp-tag">Telegram</span><span class="sp-tag">CRITICAL · DANGER</span></div>
        </div>
        <div class="sp rv" data-em="💬" data-gl="rgba(88,101,242,.1)">
          <div class="sp-num">04</div><div class="sp-title" data-i18n="f4t">Discord Community Alerts</div>
          <p class="sp-desc" data-i18n="f4d">Protocol-wide risk announcements and daily summaries broadcast automatically to your Discord community.</p>
          <div class="sp-tags"><span class="sp-tag">Community</span><span class="sp-tag">Discord</span><span class="sp-tag">Daily Reports</span></div>
        </div>
        <div class="sp rv" data-em="📋" data-gl="rgba(234,179,8,.09)">
          <div class="sp-num">05</div><div class="sp-title" data-i18n="f5t">Google Sheets Reports</div>
          <p class="sp-desc" data-i18n="f5d">Weekly automated exports to Google Sheets. Full position lists, risk breakdowns, and historical liquidation trends.</p>
          <div class="sp-tags"><span class="sp-tag">Weekly</span><span class="sp-tag">Spreadsheet</span><span class="sp-tag">Historical</span></div>
        </div>
        <div class="sp rv" data-em="🔗" data-gl="rgba(168,85,247,.1)">
          <div class="sp-num">06</div><div class="sp-title" data-i18n="f6t">GraphQL API</div>
          <p class="sp-desc" data-i18n="f6d">Query any position, snapshot or alert through The Graph decentralized API. Fully composable and open.</p>
          <div class="sp-tags"><span class="sp-tag">GraphQL</span><span class="sp-tag">Decentralized</span><span class="sp-tag">Composable</span></div>
        </div>
      </div>
    </div>
  </div>
</section>
<section class="sec" id="risk">
  <div class="sin">
    <div class="sh-block">
      <div class="sec-lbl rv" data-i18n="r_l">Risk Classification</div>
      <h2 class="sh rv d1" data-i18n="r_h">5-Level Risk System</h2>
      <p class="ssub rv d2" data-i18n="r_s">Every position scored in real-time based on health factor proximity to the liquidation threshold.</p>
    </div>
    <div class="rg">
      <div class="rc rcrit rv d1"><div class="rn">Critical</div><div class="rhf">HF &lt; 1.05</div><div class="rdsc" data-i18n="rc_d">Liquidation imminent. Cascade alert active.</div></div>
      <div class="rc rdang rv d2"><div class="rn">Danger</div><div class="rhf">HF 1.05–1.10</div><div class="rdsc" data-i18n="rd_d">High probability. May trigger within hours.</div></div>
      <div class="rc rwarn rv d3"><div class="rn">Warning</div><div class="rhf">HF 1.10–1.20</div><div class="rdsc" data-i18n="rw_d">Significant moves could trigger liquidation.</div></div>
      <div class="rc rcaut rv d4"><div class="rn">Caution</div><div class="rhf">HF 1.20–1.50</div><div class="rdsc" data-i18n="rca_d">Moderate risk in volatile conditions.</div></div>
      <div class="rc rsafe rv d5"><div class="rn">Safe</div><div class="rhf">HF &gt; 1.50</div><div class="rdsc" data-i18n="rs_d">Well-collateralized, comfortable buffer.</div></div>
    </div>
    <div class="sec-lbl rv" style="margin-bottom:.8rem" data-i18n="e_l">Entity Types</div>
    <div class="ent-row">
      <span class="ebdg rv d1">Position</span><span class="ebdg rv d2">LiquidationCall</span>
      <span class="ebdg rv d3">HealthFactorSnapshot</span><span class="ebdg rv d4">RiskAlert</span><span class="ebdg rv d5">ProtocolStats</span>
    </div>
  </div>
</section>
<div class="gauge-sec">
  <div class="gauge-in">
    <div class="rvl">
      <div class="sec-lbl" data-i18n="g_l">Global Risk Index</div>
      <h2 class="sh" style="margin-bottom:1rem" data-i18n="g_h">DeFi Risk Index 0–100</h2>
      <p style="font-size:.92rem;color:var(--t2);line-height:1.75;max-width:440px" data-i18n="g_d">Composite score aggregating liquidation exposure across all monitored protocols and chains. Updated every block. Powers the Cascade Risk Alert engine.</p>
      <div class="g-leg-row">
        <div class="g-leg"><span class="g-dot" style="background:#ef4444"></span><span data-i18n="g_hi">0–30 High Risk</span></div>
        <div class="g-leg"><span class="g-dot" style="background:#eab308"></span><span data-i18n="g_md">30–70 Moderate</span></div>
        <div class="g-leg"><span class="g-dot" style="background:#22c55e"></span><span data-i18n="g_lo">70–100 Low Risk</span></div>
      </div>
    </div>
    <div class="rvr" style="display:flex;align-items:center;justify-content:center">
      <svg width="320" height="210" viewBox="0 0 320 210">
        <defs><linearGradient id="gg" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" stop-color="#ef4444"/><stop offset="30%" stop-color="#f97316"/>
          <stop offset="55%" stop-color="#eab308"/><stop offset="75%" stop-color="#60a5fa"/>
          <stop offset="100%" stop-color="#22c55e"/>
        </linearGradient></defs>
        <path d="M 25 175 A 135 135 0 0 1 295 175" fill="none" stroke="rgba(255,255,255,.05)" stroke-width="20" stroke-linecap="round"/>
        <path d="M 25 175 A 135 135 0 0 1 295 175" fill="none" stroke="url(#gg)" stroke-width="20" stroke-linecap="round" opacity=".9"/>
        <line x1="160" y1="175" x2="73" y2="89" stroke="rgba(255,255,255,.9)" stroke-width="3.5" stroke-linecap="round"/>
        <circle cx="160" cy="175" r="10" fill="rgba(79,142,247,.3)" stroke="rgba(79,142,247,.6)" stroke-width="1.5"/>
        <circle cx="160" cy="175" r="5" fill="white"/>
        <text x="160" y="148" text-anchor="middle" fill="white" font-family="Inter,sans-serif" font-size="38" font-weight="800" opacity=".95">35</text>
        <text x="160" y="164" text-anchor="middle" fill="#8b9db5" font-family="Inter,sans-serif" font-size="10" letter-spacing="3">RISK INDEX</text>
        <text x="17" y="190" fill="#ef4444" font-family="Inter,sans-serif" font-size="11" font-weight="700">0</text>
        <text x="287" y="190" fill="#22c55e" font-family="Inter,sans-serif" font-size="11" font-weight="700">100</text>
      </svg>
    </div>
  </div>
</div>
<section class="sec">
  <div class="sin">
    <div class="sh-block">
      <div class="sec-lbl rv" data-i18n="m_l">By the Numbers</div>
      <h2 class="sh rv d1" data-i18n="m_h">Infrastructure at Scale.</h2>
    </div>
    <div class="mbar">
      <div class="mc rv d1"><span class="mv">280K+</span><div class="ml" data-i18n="m1l">Active Positions Tracked</div><div class="ms" data-i18n="m1s">Aave V3 + Compound V3</div></div>
      <div class="mc rv d2"><span class="mv">220K+</span><div class="ml" data-i18n="m2l">Queries / 30 days</div><div class="ms" data-i18n="m2s">Across all 5 subgraphs</div></div>
      <div class="mc rv d3"><span class="mv">71K</span><div class="ml" data-i18n="m3l">GRT Signal Total</div><div class="ms" data-i18n="m3s">Curation across all subgraphs</div></div>
      <div class="mc rv d4"><span class="mv">5</span><div class="ml" data-i18n="m4l">Risk Levels</div><div class="ms" data-i18n="m4s">Critical → Safe</div></div>
    </div>
  </div>
</section>
<section class="sec" id="query" style="padding-top:0">
  <div class="sin">
    <div class="sh-block">
      <div class="sec-lbl rv" data-i18n="q_l">GraphQL API</div>
      <h2 class="sh rv d1" data-i18n="q_h">Start Querying in Seconds.</h2>
      <p class="ssub rv d2" data-i18n="q_s">Fetch at-risk positions directly via The Graph Network.</p>
    </div>
    <div class="cw rv">
      <div class="cb-bar"><div class="dots"><div class="dot dr"></div><div class="dot dy"></div><div class="dot dg"></div></div><span class="cl-tag">aave-liquidation-risk · GraphQL</span></div>
      <div class="cb-body"><pre><span class="cm"># Get CRITICAL positions ordered by health factor</span>
<span class="kw">query</span> <span class="fn">CriticalPositions</span> {
  <span class="fn">positions</span>(
    <span class="kw">where</span><span class="op">:</span> { riskLevel<span class="op">:</span> <span class="str">"CRITICAL"</span> }
    <span class="kw">orderBy</span><span class="op">:</span> healthFactor
    <span class="kw">orderDirection</span><span class="op">:</span> asc
    <span class="kw">first</span><span class="op">:</span> <span class="nm">20</span>
  ) {
    id
    user
    healthFactor
    totalCollateralUSD
    totalDebtUSD
    riskLevel
    lastUpdatedBlock
  }
}</pre></div>
    </div>
  </div>
</section>
<div class="cta-ban">
  <div class="cta-inner">
    <div class="sec-lbl rv" style="text-align:center;margin-bottom:.75rem">DeFi Risk Monitor</div>
    <h2 class="sh rv d1" style="text-align:center;max-width:600px;margin:0 auto .8rem" data-i18n="ct_h">Stay Ahead of Liquidations.</h2>
    <p class="rv d2" style="color:var(--t2);max-width:460px;margin:0 auto 2.5rem;font-size:.97rem" data-i18n="ct_d">Track 280,000+ positions in real-time. Get alerted before the market moves.</p>
    <div class="cta-row rv d3">
      <a href="https://web-production-387cf.up.railway.app" target="_blank" class="btn-hp" data-i18n="ct_b1">Open Dashboard</a>
      <a href="https://thegraph.com/explorer/profile/0x967c1f6fb8b5ecbabfe442120487ec2ba220a189?view=Subgraphs&chain=arbitrum-one" target="_blank" class="btn-hs" data-i18n="ct_b2">View Subgraphs →</a>
    </div>
  </div>
</div>
<footer>
  <div class="ft">
    <div class="fbrand">
      <a href="#" class="nav-logo" style="text-decoration:none"><div class="logo-mark">DR</div>DeFi Risk Monitor</a>
      <p class="fdesc" data-i18n="ft_d">Real-time liquidation risk for Aave V3 and Compound V3 across 5 EVM chains. Powered by The Graph.</p>
    </div>
    <div class="fcol"><h4 data-i18n="ft_sg">Subgraphs</h4><ul>
      <li><a href="https://thegraph.com/explorer/subgraphs/Hmqe4B5PJ9AJ5T6bxiMg8bHfRASRHiSKJj6yqCHfpMBT?view=About&chain=arbitrum-one" target="_blank">Ethereum</a></li>
      <li><a href="https://thegraph.com/explorer/subgraphs/GCgNt6jsf8KWJbHBWWbwPM9MQrRiWb48kZ8VGbCNAXmH?view=About&chain=arbitrum-one" target="_blank">Arbitrum</a></li>
      <li><a href="https://thegraph.com/explorer/subgraphs/Bf9yBDX9XrpNXLkfktdaSYBbfswdxcFkXzdMmBvL83SF?view=About&chain=arbitrum-one" target="_blank">Base</a></li>
      <li><a href="https://thegraph.com/explorer/subgraphs/FBVyahKnFFc1b6E7CpRHK59whHta3AkLCAgqfpReXAvK?view=About&chain=arbitrum-one" target="_blank">Polygon</a></li>
      <li><a href="https://thegraph.com/explorer/subgraphs/9hdBacnHPDmiMCNjdFUcPFgGcPPnYWrofsKvqjoEvcKu?view=About&chain=arbitrum-one" target="_blank">Optimism</a></li>
    </ul></div>
    <div class="fcol"><h4 data-i18n="ft_pr">Product</h4><ul>
      <li><a href="https://web-production-387cf.up.railway.app" target="_blank" data-i18n="ft_db">Dashboard</a></li>
      <li><a href="#" data-i18n="ft_tg">Telegram Bot</a></li>
      <li><a href="#" data-i18n="ft_dc">Discord Alerts</a></li>
      <li><a href="#" data-i18n="ft_gs">Google Sheets</a></li>
    </ul></div>
    <div class="fcol"><h4 data-i18n="ft_rs">Resources</h4><ul>
      <li><a href="#query" data-i18n="ft_ap">GraphQL API</a></li>
      <li><a href="https://thegraph.com/explorer" target="_blank">The Graph</a></li>
      <li><a href="https://forum.thegraph.com/t/just-launched-defi-risk-monitor-real-time-liquidation-risk-for-aaveaave-v3-compoundfinance-v3-across-5-chains/6879" target="_blank" data-i18n="ft_fo">Forum Post</a></li>
    </ul></div>
  </div>
  <div class="fb">
    <span class="fcopy" data-i18n="ft_cp">© 2026 DeFi Risk Monitor. All rights reserved.</span>
    <div class="flinks">
      <a href="https://thegraph.com/explorer/profile/0x967c1f6fb8b5ecbabfe442120487ec2ba220a189?view=Subgraphs&chain=arbitrum-one" target="_blank">The Graph</a>
      <a href="https://web-production-387cf.up.railway.app" target="_blank" data-i18n="ft_db">Dashboard</a>
    </div>
  </div>
</footer>
<script>
/* AURORA */
(function(){
  var cv=document.getElementById('aurora'),cx=cv.getContext('2d'),W,H;
  function rsz(){W=cv.width=window.innerWidth;H=cv.height=window.innerHeight;}
  rsz();window.addEventListener('resize',rsz);
  var blobs=[
    {x:.5,y:.15,r:.5,hue:220,sp:.0004,ph:0},
    {x:.15,y:.5,r:.4,hue:270,sp:.0003,ph:1.5},
    {x:.85,y:.4,r:.45,hue:195,sp:.00035,ph:3},
    {x:.6,y:.8,r:.4,hue:240,sp:.00025,ph:4.5}
  ];
  function draw(){
    cx.clearRect(0,0,W,H);
    var now=Date.now();
    blobs.forEach(function(b){
      var px=(b.x+Math.sin(now*b.sp+b.ph)*.12)*W;
      var py=(b.y+Math.cos(now*b.sp+b.ph*.7)*.1)*H;
      var rad=b.r*Math.min(W,H)*.65;
      var al=.07+Math.sin(now*b.sp*.5+b.ph)*.02;
      var g=cx.createRadialGradient(px,py,0,px,py,rad);
      g.addColorStop(0,'hsla('+b.hue+',80%,60%,'+al+')');
      g.addColorStop(.6,'hsla('+b.hue+',70%,50%,'+(al*.3)+')');
      g.addColorStop(1,'hsla('+b.hue+',60%,40%,0)');
      cx.fillStyle=g;
      cx.beginPath();
      cx.ellipse(px,py,rad*(1+Math.sin(now*b.sp*.8)*.1),rad*(1+Math.cos(now*b.sp*.6)*.1),now*b.sp*.2,0,Math.PI*2);
      cx.fill();
    });
    requestAnimationFrame(draw);
  }
  draw();
})();
 
/* SCROLL REVEAL */
var ro=new IntersectionObserver(function(entries){
  entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('on');});
},{threshold:.1,rootMargin:'0px 0px -40px 0px'});
document.querySelectorAll('.rv,.rvl,.rvr').forEach(function(el){ro.observe(el);});
 
/* NAV */
window.addEventListener('scroll',function(){
  document.getElementById('navbar').classList.toggle('scrolled',window.scrollY>30);
});
 
/* FEATURE STICKY SWAP */
var spEls=document.querySelectorAll('.sp');
var featEm=document.getElementById('feat-em');
var featGl=document.getElementById('feat-glow');
var spObs=new IntersectionObserver(function(entries){
  entries.forEach(function(e){
    if(e.isIntersecting&&e.intersectionRatio>.4){
      var em=e.target.dataset.em,gl=e.target.dataset.gl;
      spEls.forEach(function(s){s.classList.remove('active-sp');});
      e.target.classList.add('active-sp');
      if(em&&featEm.textContent!==em){
        featEm.style.opacity='0';featEm.style.transform='scale(.75) translateY(10px)';
        setTimeout(function(){featEm.textContent=em;featEm.style.opacity='1';featEm.style.transform='scale(1) translateY(0)';},220);
      }
      if(gl){featGl.style.background='radial-gradient(ellipse at 50% 50%,'+gl+',transparent 65%)';featGl.style.opacity='1';}
    }
  });
},{threshold:.4,rootMargin:'-5% 0px -5% 0px'});
spEls.forEach(function(s){spObs.observe(s);});
 
/* SUBGRAPH DATA */
var KNOWN={
  eth:{q:'25.5K',s:'10.2K GRT'},
  arb:{q:'42.5K',s:'35.7K GRT'},
  bas:{q:'49.3K',s:'15.2K GRT'},
  pol:{q:'79.4K',s:'9.9K GRT'},
  opt:{q:'24.2K',s:'0 GRT'}
};
var SUBS={
  eth:'Hmqe4B5PJ9AJ5T6bxiMg8bHfRASRHiSKJj6yqCHfpMBT',
  arb:'GCgNt6jsf8KWJbHBWWbwPM9MQrRiWb48kZ8VGbCNAXmH',
  bas:'Bf9yBDX9XrpNXLkfktdaSYBbfswdxcFkXzdMmBvL83SF',
  pol:'FBVyahKnFFc1b6E7CpRHK59whHta3AkLCAgqfpReXAvK',
  opt:'9hdBacnHPDmiMCNjdFUcPFgGcPPnYWrofsKvqjoEvcKu'
};
 
var lang='en';
 
function fmtGRT(raw){
  if(!raw)return'0 GRT';
  var n=parseFloat(raw)/1e18;
  if(n>=1000)return(n/1000).toFixed(1)+'K GRT';
  return n.toFixed(0)+' GRT';
}
function fmtQ(raw){
  if(!raw)return'0';
  var n=parseInt(raw);
  if(n>=1000)return(n/1000).toFixed(1)+'K';
  return''+n;
}
 
function setRow(id,q,s,cached){
  var el=document.getElementById('s-'+id);
  if(!el)return;
  var tag=cached?' <span style="font-size:.6rem;color:var(--t3)">(cached)</span>':'';
  var t=I18N[lang];
  el.innerHTML='<div class="sg-row"><span class="sg-k">'+t.q30+'</span><span class="sg-v">'+q+tag+'</span></div>'
    +'<div class="sg-row"><span class="sg-k">'+t.sig+'</span><span class="sg-v">'+s+'</span></div>';
}
function setSpinners(){
  var t=I18N[lang];
  ['eth','arb','bas','pol','opt'].forEach(function(id){
    var el=document.getElementById('s-'+id);
    if(el)el.innerHTML='<div class="sg-row"><span class="sg-k">'+t.q30+'</span><span class="sg-v"><span class="spin"></span></span></div>'
      +'<div class="sg-row"><span class="sg-k">'+t.sig+'</span><span class="sg-v"><span class="spin"></span></span></div>';
  });
}
 
async function tryFetch(id){
  var q='{"query":"{subgraph(id:\"'+SUBS[id]+'\"){signalledTokens queryFeesAmount}}"}';
  var url='https://api.thegraph.com/subgraphs/name/graphprotocol/graph-network-arbitrum';
  try{
    var r=await fetch(url,{method:'POST',headers:{'Content-Type':'application/json'},body:q,signal:AbortSignal.timeout(6000)});
    if(!r.ok)return null;
    var j=await r.json();
    var d=j&&j.data&&j.data.subgraph;
    if(d)return{q:fmtQ(d.queryFeesAmount),s:fmtGRT(d.signalledTokens),live:true};
  }catch(e){}
  return null;
}
 
async function fetchAll(){
  var btn=document.getElementById('ref-btn');
  if(btn){btn.style.opacity='.5';btn.style.pointerEvents='none';}
  setSpinners();
  var ids=['eth','arb','bas','pol','opt'];
  await Promise.all(ids.map(async function(id){
    var d=await tryFetch(id);
    if(d&&d.live){setRow(id,d.q,d.s,false);}
    else{setRow(id,KNOWN[id].q,KNOWN[id].s,true);}
  }));
  var now=new Date();
  var ts=now.toLocaleTimeString(lang==='es'?'es-ES':'en-US',{hour:'2-digit',minute:'2-digit',second:'2-digit'});
  var upd=document.getElementById('last-upd');
  if(upd)upd.textContent=(I18N[lang].upd||'Updated at')+' '+ts;
  if(btn){btn.style.opacity='1';btn.style.pointerEvents='auto';}
}
fetchAll();
setInterval(fetchAll,60000);
 
/* I18N */
var I18N={
en:{
  ann_t:'New: Cascade Risk Alert simulates liquidation impact across 280,000+ positions.',ann_l:'View Live Dashboard →',
  n_sg:'Subgraphs',n_ft:'Features',n_rk:'Risk Levels',n_qr:'Query API',n_tg:'The Graph',n_db:'Live Dashboard',
  h_bg:'Live · Monitoring 280,000+ Active Positions',h_t1:'Real-Time Liquidation Risk',h_t2:'Monitor for ',
  h_sb:'Track every borrowing position across Ethereum, Arbitrum, Base, Optimism and Polygon. 5 risk levels, global DeFi Risk Index, and instant cascade alerts.',
  h_c1:'Explore Subgraphs',h_c2:'Live Dashboard →',
  s1:'Active Positions',s2:'Chains',s3:'Queries / 30d',s4:'GRT Signal',dep:'Deployed on',
  sg_l:'The Graph Protocol',sg_h:'Deployed Subgraphs',sg_s:'6 production subgraphs on The Graph Network. Click any card to open in the explorer.',
  sg_rf:'↻ Refresh',sg_va:'View all →',q30:'Queries 30d',sig:'Signal',ent:'Entity Types',st:'Status',live:'Live',upd:'Updated at',
  f_l:'Ecosystem',f_h:'Built Around the Subgraphs.',f_s:'A full monitoring stack delivering risk intelligence across multiple channels, powered entirely by on-chain data.',
  f1t:'Cascade Risk Alert',f1d:'Simulates market impact before it happens. Models liquidation cascades to detect systemic DeFi risk before prices move.',
  f2t:'Web Dashboard',f2d:'Live dashboard showing real-time position health, risk distribution, and the global DeFi Risk Index (0–100), updated on every block.',
  f3t:'Telegram Bot',f3d:'Instant push notifications for CRITICAL and DANGER positions. Alerted the moment a position enters liquidation territory.',
  f4t:'Discord Community Alerts',f4d:'Protocol-wide risk announcements and daily summaries broadcast automatically to your Discord community.',
  f5t:'Google Sheets Reports',f5d:'Weekly automated exports to Google Sheets. Full position lists, risk breakdowns, and historical trends.',
  f6t:'GraphQL API',f6d:'Query any position, snapshot or alert through The Graph decentralized API. Fully composable and open.',
  r_l:'Risk Classification',r_h:'5-Level Risk System',r_s:'Every position scored in real-time based on health factor proximity to the liquidation threshold.',
  rc_d:'Liquidation imminent. Cascade alert active.',rd_d:'High probability. May trigger within hours.',rw_d:'Significant moves could trigger liquidation.',rca_d:'Moderate risk in volatile conditions.',rs_d:'Well-collateralized, comfortable buffer.',
  e_l:'Entity Types',
  g_l:'Global Risk Index',g_h:'DeFi Risk Index 0–100',g_d:'Composite score aggregating liquidation exposure across all monitored protocols and chains. Updated every block.',
  g_hi:'0–30 High Risk',g_md:'30–70 Moderate',g_lo:'70–100 Low Risk',
  m_l:'By the Numbers',m_h:'Infrastructure at Scale.',m1l:'Active Positions Tracked',m1s:'Aave V3 + Compound V3',m2l:'Queries / 30 days',m2s:'Across all 5 subgraphs',m3l:'GRT Signal Total',m3s:'Curation across all subgraphs',m4l:'Risk Levels',m4s:'Critical → Safe',
  q_l:'GraphQL API',q_h:'Start Querying in Seconds.',q_s:'Fetch at-risk positions directly via The Graph Network.',
  ct_h:'Stay Ahead of Liquidations.',ct_d:'Track 280,000+ positions in real-time. Get alerted before the market moves.',ct_b1:'Open Dashboard',ct_b2:'View Subgraphs →',
  ft_d:'Real-time liquidation risk for Aave V3 and Compound V3 across 5 EVM chains.',ft_sg:'Subgraphs',ft_pr:'Product',ft_rs:'Resources',ft_db:'Dashboard',ft_tg:'Telegram Bot',ft_dc:'Discord Alerts',ft_gs:'Google Sheets',ft_ap:'GraphQL API',ft_fo:'Forum Post',ft_cp:'© 2026 DeFi Risk Monitor. All rights reserved.'
},
es:{
  ann_t:'Nuevo: Cascade Risk Alert simula el impacto en más de 280.000 posiciones.',ann_l:'Ver Dashboard →',
  n_sg:'Subgraphs',n_ft:'Funciones',n_rk:'Niveles de Riesgo',n_qr:'API Query',n_tg:'The Graph',n_db:'Dashboard en Vivo',
  h_bg:'En Vivo · Monitoreando más de 280.000 posiciones activas',h_t1:'Monitor de Riesgo de',h_t2:'Liquidación en Tiempo Real para ',
  h_sb:'Monitorea cada posición de préstamo en Ethereum, Arbitrum, Base, Optimism y Polygon. 5 niveles de riesgo, Índice DeFi global y alertas de cascada instantáneas.',
  h_c1:'Explorar Subgraphs',h_c2:'Dashboard en Vivo →',
  s1:'Posiciones Activas',s2:'Cadenas',s3:'Consultas / 30d',s4:'Señal GRT',dep:'Desplegado en',
  sg_l:'The Graph Protocol',sg_h:'Subgraphs Desplegados',sg_s:'6 subgraphs en producción en The Graph Network. Haz clic para abrir en el explorador.',
  sg_rf:'↻ Actualizar',sg_va:'Ver todos →',q30:'Consultas 30d',sig:'Señal',ent:'Tipos de Entidad',st:'Estado',live:'En Vivo',upd:'Actualizado a las',
  f_l:'Ecosistema',f_h:'Construido Sobre los Subgraphs.',f_s:'Un stack de monitoreo completo que entrega inteligencia de riesgo a través de múltiples canales, alimentado por datos on-chain.',
  f1t:'Alerta de Riesgo en Cascada',f1d:'Simula el impacto de mercado antes de que ocurra. Detecta riesgo sistémico DeFi antes de que los precios se muevan.',
  f2t:'Dashboard Web',f2d:'Dashboard en vivo con salud de posiciones en tiempo real y el Índice de Riesgo DeFi global (0–100), actualizado en cada bloque.',
  f3t:'Bot de Telegram',f3d:'Notificaciones instantáneas para posiciones CRITICAL y DANGER. Alerta en el momento en que una posición entra en zona de liquidación.',
  f4t:'Alertas Discord',f4d:'Anuncios de riesgo y resúmenes diarios transmitidos automáticamente a tu comunidad de Discord.',
  f5t:'Informes Google Sheets',f5d:'Exportaciones automáticas semanales. Listas de posiciones, análisis por protocolo y tendencias históricas.',
  f6t:'API GraphQL',f6d:'Consulta cualquier posición, snapshot o alerta a través de la API descentralizada de The Graph.',
  r_l:'Clasificación de Riesgo',r_h:'Sistema de 5 Niveles de Riesgo',r_s:'Cada posición puntuada en tiempo real según la proximidad del factor de salud al umbral de liquidación.',
  rc_d:'Liquidación inminente. Alerta activa.',rd_d:'Alta probabilidad. Puede activarse en horas.',rw_d:'Movimientos significativos podrían causar liquidación.',rca_d:'Riesgo moderado en condiciones volátiles.',rs_d:'Bien colateralizada, margen cómodo.',
  e_l:'Tipos de Entidad',
  g_l:'Índice de Riesgo Global',g_h:'Índice de Riesgo DeFi 0–100',g_d:'Puntuación compuesta que agrega la exposición de liquidación en todos los protocolos y cadenas monitoreados.',
  g_hi:'0–30 Riesgo Alto',g_md:'30–70 Moderado',g_lo:'70–100 Riesgo Bajo',
  m_l:'En Números',m_h:'Infraestructura a Escala.',m1l:'Posiciones Rastreadas',m1s:'Aave V3 + Compound V3',m2l:'Consultas / 30 días',m2s:'En los 5 subgraphs',m3l:'Señal GRT Total',m3s:'Curación total',m4l:'Niveles de Riesgo',m4s:'Crítico → Seguro',
  q_l:'API GraphQL',q_h:'Empieza a Consultar en Segundos.',q_s:'Obtén posiciones en riesgo directamente a través de The Graph Network.',
  ct_h:'Adelántate a las Liquidaciones.',ct_d:'Rastrea más de 280.000 posiciones en tiempo real. Recibe alertas antes de que el mercado se mueva.',ct_b1:'Abrir Dashboard',ct_b2:'Ver Subgraphs →',
  ft_d:'Monitor de riesgo de liquidación en tiempo real para Aave V3 y Compound V3 en 5 cadenas EVM.',ft_sg:'Subgraphs',ft_pr:'Producto',ft_rs:'Recursos',ft_db:'Dashboard',ft_tg:'Bot Telegram',ft_dc:'Alertas Discord',ft_gs:'Google Sheets',ft_ap:'API GraphQL',ft_fo:'Post del Foro',ft_cp:'© 2026 DeFi Risk Monitor. Todos los derechos reservados.'
}
};
 
function applyLang(l){
  lang=l;
  var t=I18N[l];
  document.querySelectorAll('[data-i18n]').forEach(function(el){
    var k=el.dataset.i18n;
    if(t[k]!==undefined)el.textContent=t[k];
  });
  document.getElementById('lf').textContent=l==='en'?'🇬🇧':'🇪🇸';
  document.getElementById('ll').textContent=l==='en'?'Español':'English';
  document.documentElement.lang=l;
}
function toggleLang(){applyLang(lang==='en'?'es':'en');}
applyLang('en');
</script>
</body>
</html>
