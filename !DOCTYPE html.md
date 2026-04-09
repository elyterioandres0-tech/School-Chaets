# <!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8"/>  
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>  
<title>Delta Vault — Watch Free</title>  
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>  
<style>  
/* ── RESET & ROOT ── */  
*{margin:0;padding:0;box-sizing:border-box}  
:root{  
  --bg:#0a0a0f;  
  --bg2:#111118;  
  --bg3:#18181f;  
  --bg4:#1e1e28;  
  --bg5:#252530;  
  --border:rgba(255,255,255,0.06);  
  --border2:rgba(255,255,255,0.11);  
  --w:#f0f0f8;  
  --g:rgba(220,220,240,0.5);  
  --g2:rgba(220,220,240,0.28);  
  --g3:rgba(220,220,240,0.12);  
  --accent:#e50914;  
  --accent2:#ff4d57;  
  --gold:#f5c518;  
  --r:6px;  
  --nav-h:64px;  
}  
html{scroll-behavior:smooth}  
body{font-family:'Inter',sans-serif;background:var(--bg);color:var(--w);overflow-x:hidden;min-height:100vh}  
body.locked{overflow:hidden}  
::selection{background:rgba(229,9,20,0.35)}  
::-webkit-scrollbar{width:3px;height:3px}  
::-webkit-scrollbar-track{background:transparent}  
::-webkit-scrollbar-thumb{background:var(--bg5);border-radius:3px}  
img{display:block}  
  
/* ── GRAIN OVERLAY ── */  
body::before{  
  content:'';position:fixed;inset:0;pointer-events:none;z-index:9999;  
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='[http://www.w3.org/2000/svg'%3E%3Cfilter id='g'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23g)](http://www.w3.org/2000/svg'%253E%253Cfilter%20id='g'%253E%253CfeTurbulence%20type='fractalNoise'%20baseFrequency='0.75'%20numOctaves='4'%20stitchTiles='stitch'/%253E%253C/filter%253E%253Crect%20width='100%2525'%20height='100%2525'%20filter='url(%2523g))' opacity='0.045'/%3E%3C/svg%3E");  
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='[http://www.w3.org/2000/svg'%3E%3Cfilter id='g'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23g)](http://www.w3.org/2000/svg'%253E%253Cfilter%20id='g'%253E%253CfeTurbulence%20type='fractalNoise'%20baseFrequency='0.75'%20numOctaves='4'%20stitchTiles='stitch'/%253E%253C/filter%253E%253Crect%20width='100%2525'%20height='100%2525'%20filter='url(%2523g))' opacity='0.045'/%3E%3C/svg%3E");  
  opacity:.55;  
}  
  
/* ── NAV ── */  
#nav{  
  position:fixed;top:0;left:0;right:0;z-index:500;height:var(--nav-h);  
  display:flex;align-items:center;padding:0 3rem;gap:2rem;  
  transition:background .3s,box-shadow .3s;  
}  
#nav.solid{background:rgba(10,10,15,0.97);box-shadow:0 1px 0 var(--border);}  
#nav::after{  
  content:'';position:absolute;inset:0;pointer-events:none;  
  background:linear-gradient(to bottom,rgba(10,10,15,0.9) 0%,transparent 100%);  
  z-index:-1;  
}  
#nav.solid::after{display:none}  
.nav-logo{  
  font-family:'Bebas Neue',sans-serif;font-size:1.9rem;letter-spacing:0.06em;  
  color:var(--accent);cursor:pointer;flex-shrink:0;line-height:1;  
  text-shadow:0 0 30px rgba(229,9,20,0.5);  
}  
.nav-links{display:flex;gap:0.2rem}  
.nl{  
  font-size:0.8rem;font-weight:500;color:var(--g);padding:0.38rem 0.75rem;  
  border-radius:var(--r);cursor:pointer;background:none;border:none;  
  font-family:'Inter',sans-serif;transition:all .15s;letter-spacing:0.01em;  
}  
.nl:hover{color:var(--w)}  
.nl.active{color:var(--w);font-weight:600}  
.nav-r{margin-left:auto;display:flex;align-items:center;gap:0.5rem}  
.ni{  
  background:none;border:none;color:var(--g);width:36px;height:36px;  
  border-radius:var(--r);display:flex;align-items:center;justify-content:center;  
  cursor:pointer;transition:all .15s;  
}  
.ni:hover{color:var(--w);background:var(--bg3)}  
.ni.on{color:var(--accent2);background:rgba(229,9,20,.12)}  
.sw{overflow:hidden;max-width:0;transition:max-width .3s}  
.sw.open{max-width:260px}  
#srch{  
  background:var(--bg3);border:1px solid var(--border2);border-radius:var(--r);  
  color:var(--w);font-family:'Inter',sans-serif;font-size:.8rem;  
  padding:.4rem .9rem;width:260px;outline:none;  
}  
#srch:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(229,9,20,.15)}  
#srch::placeholder{color:var(--g2)}  
.profile-btn{  
  width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,#e50914,#ff6b35);  
  border:2px solid rgba(229,9,20,.4);cursor:pointer;display:flex;align-items:center;  
  justify-content:center;font-size:.75rem;font-weight:700;color:#fff;flex-shrink:0;  
}  
  
/* ── HERO ── */  
#hero{  
  position:relative;height:100vh;min-height:600px;max-height:900px;  
  display:flex;align-items:flex-end;padding:0 3rem 7rem;overflow:hidden;  
}  
#heroBg{  
  position:absolute;inset:0;background-size:cover;background-position:center top;  
  transition:opacity .7s ease;  
}  
#heroBg::after{  
  content:'';position:absolute;inset:0;  
  background:  
    linear-gradient(to right,rgba(10,10,15,0.95) 0%,rgba(10,10,15,0.6) 45%,transparent 75%),  
    linear-gradient(to top,rgba(10,10,15,1) 0%,rgba(10,10,15,0.4) 30%,transparent 60%);  
}  
.hero-content{position:relative;z-index:1;max-width:600px}  
.hero-tags{display:flex;gap:.5rem;margin-bottom:1rem;flex-wrap:wrap}  
.htag{  
  font-size:.65rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;  
  padding:.22rem .65rem;border-radius:3px;  
}  
.htag.type{background:var(--accent);color:#fff}  
.htag.genre{background:rgba(255,255,255,.08);color:var(--g);border:1px solid var(--border2)}  
.htag.year{background:rgba(255,255,255,.05);color:var(--g2);border:1px solid var(--border)}  
.hero-title{  
  font-family:'Bebas Neue',sans-serif;font-size:clamp(3rem,7vw,5.5rem);  
  letter-spacing:.03em;line-height:.95;margin-bottom:.9rem;  
  text-shadow:0 4px 30px rgba(0,0,0,.8);  
}  
.hero-meta{  
  display:flex;align-items:center;gap:.8rem;font-size:.82rem;  
  color:var(--g);margin-bottom:1rem;flex-wrap:wrap;  
}  
.hero-rating{color:var(--gold);font-weight:700;display:flex;align-items:center;gap:.25rem}  
.hero-dot{width:3px;height:3px;border-radius:50%;background:var(--g2)}  
.hero-desc{  
  font-size:.88rem;color:var(--g);line-height:1.7;margin-bottom:2rem;  
  max-width:500px;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden;  
}  
.hero-btns{display:flex;gap:.75rem;flex-wrap:wrap}  
.hbtn{  
  display:inline-flex;align-items:center;gap:.5rem;  
  font-family:'Inter',sans-serif;font-size:.88rem;font-weight:600;  
  padding:.72rem 1.8rem;border-radius:var(--r);border:none;cursor:pointer;transition:all .2s;  
}  
.hbtn.play{background:var(--w);color:#0a0a0f;}  
.hbtn.play:hover{background:#d8d8e8;transform:scale(1.03)}  
.hbtn.info{background:rgba(255,255,255,.15);color:var(--w);border:1px solid rgba(255,255,255,.2);backdrop-filter:blur(8px)}  
.hbtn.info:hover{background:rgba(255,255,255,.22);transform:scale(1.02)}  
.hbtn.add{background:none;color:var(--w);border:1px solid rgba(255,255,255,.3)}  
.hbtn.add:hover{background:rgba(255,255,255,.08)}  
.hero-indicators{  
  position:absolute;bottom:3rem;right:3rem;display:flex;gap:.4rem;z-index:1;  
}  
.hi{width:28px;height:3px;border-radius:2px;background:rgba(255,255,255,.25);cursor:pointer;transition:all .2s}  
.hi.active{background:var(--accent);width:36px}  
  
/* ── ROWS ── */  
#main{padding:0 0 6rem;background:linear-gradient(to bottom,transparent 0%,var(--bg) 6rem)}  
.row-wrap{margin-bottom:2.5rem;padding:0 3rem}  
.row-hdr{  
  display:flex;align-items:center;justify-content:space-between;  
  margin-bottom:.9rem;  
}  
.row-title{  
  font-size:1.05rem;font-weight:700;letter-spacing:-.01em;  
  display:flex;align-items:center;gap:.5rem;  
}  
.row-title-accent{color:var(--accent);font-family:'Bebas Neue',sans-serif;font-size:1.1rem;letter-spacing:.05em}  
.row-see-all{  
  font-size:.74rem;font-weight:600;color:var(--g2);cursor:pointer;  
  display:flex;align-items:center;gap:.3rem;transition:color .15s;  
}  
.row-see-all:hover{color:var(--accent)}  
.row-scroll{  
  display:flex;gap:.6rem;overflow-x:auto;padding-bottom:.5rem;  
  scroll-snap-type:x mandatory;scrollbar-width:none;  
  -webkit-overflow-scrolling:touch;  
}  
.row-scroll::-webkit-scrollbar{display:none}  
  
/* ── CARD ── */  
.card{  
  flex-shrink:0;width:160px;border-radius:var(--r);overflow:hidden;  
  cursor:pointer;position:relative;background:var(--bg3);  
  scroll-snap-align:start;transition:transform .25s cubic-bezier(.34,1.4,.64,1),box-shadow .25s;  
  border:1px solid var(--border);  
}  
.card:hover{transform:scale(1.08);z-index:10;box-shadow:0 20px 50px rgba(0,0,0,.9)}  
.card-wide{width:220px}  
.card-poster{  
  position:relative;padding-top:150%;background:var(--bg4);overflow:hidden;  
}  
.card-poster img{  
  position:absolute;inset:0;width:100%;height:100%;object-fit:cover;  
  transition:transform .3s,filter .3s;  
}  
.card:hover .card-poster img{transform:scale(1.06);filter:brightness(1.1)}  
.card-poster-fade{  
  position:absolute;bottom:0;left:0;right:0;height:60%;  
  background:linear-gradient(to top,rgba(10,10,15,.95),transparent);  
}  
.card-rating{  
  position:absolute;top:7px;left:7px;background:rgba(0,0,0,.75);  
  backdrop-filter:blur(4px);border-radius:3px;padding:2px 6px;  
  font-size:.6rem;font-weight:700;color:var(--gold);  
  display:flex;align-items:center;gap:3px;border:1px solid rgba(245,197,24,.2);  
}  
.card-type{  
  position:absolute;top:7px;right:7px;background:var(--accent);  
  color:#fff;font-size:.52rem;font-weight:800;letter-spacing:.1em;  
  padding:2px 5px;border-radius:2px;  
}  
.card-wl{  
  position:absolute;bottom:7px;right:7px;background:rgba(0,0,0,.7);  
  border:1px solid var(--border2);border-radius:50%;width:26px;height:26px;  
  display:flex;align-items:center;justify-content:center;  
  cursor:pointer;color:var(--g);font-size:.75rem;transition:all .15s;  
  opacity:0;  
}  
.card:hover .card-wl{opacity:1}  
.card-wl:hover,.card-wl.on{color:var(--accent2);border-color:rgba(229,9,20,.4)}  
.card-wl.on{opacity:1}  
.card-info{padding:.55rem .6rem .65rem}  
.card-title{  
  font-size:.78rem;font-weight:600;white-space:nowrap;overflow:hidden;  
  text-overflow:ellipsis;margin-bottom:.2rem;  
}  
.card-sub{font-size:.65rem;color:var(--g2);display:flex;align-items:center;gap:.3rem}  
  
/* HOVER CARD */  
.hov-card{  
  position:absolute;z-index:200;width:300px;background:var(--bg2);  
  border-radius:10px;border:1px solid var(--border2);  
  box-shadow:0 30px 80px rgba(0,0,0,.95);overflow:hidden;  
  pointer-events:none;opacity:0;transform:scale(.92) translateY(8px);  
  transition:opacity .2s,transform .2s;  
}  
.hov-card.vis{opacity:1;transform:scale(1) translateY(0);pointer-events:all}  
.hc-art{position:relative;height:160px;overflow:hidden}  
.hc-art img{width:100%;height:100%;object-fit:cover}  
.hc-art-fade{position:absolute;inset:0;background:linear-gradient(to top,var(--bg2),transparent 50%)}  
.hc-play{  
  position:absolute;inset:0;display:flex;align-items:center;justify-content:center;  
}  
.hc-play-btn{  
  width:46px;height:46px;border-radius:50%;background:rgba(229,9,20,.9);  
  border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;  
  color:#fff;transition:transform .15s,background .15s;  
}  
.hc-play-btn:hover{background:var(--accent2);transform:scale(1.1)}  
.hc-body{padding:.9rem 1rem 1rem}  
.hc-title{font-size:.92rem;font-weight:700;margin-bottom:.4rem}  
.hc-meta{display:flex;align-items:center;gap:.5rem;font-size:.72rem;color:var(--g);margin-bottom:.6rem;flex-wrap:wrap}  
.hc-rating{color:var(--gold);font-weight:700}  
.hc-dot{width:2px;height:2px;border-radius:50%;background:var(--g2)}  
.hc-desc{font-size:.74rem;color:var(--g);line-height:1.6;margin-bottom:.8rem;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden}  
.hc-tags{display:flex;gap:.3rem;flex-wrap:wrap;margin-bottom:.8rem}  
.hc-tag{font-size:.6rem;background:var(--bg4);border:1px solid var(--border);color:var(--g2);padding:.15rem .5rem;border-radius:3px}  
.hc-btns{display:flex;gap:.4rem}  
.hc-btn{  
  flex:1;display:flex;align-items:center;justify-content:center;gap:.35rem;  
  font-family:'Inter',sans-serif;font-size:.73rem;font-weight:600;  
  padding:.48rem;border-radius:var(--r);cursor:pointer;transition:all .15s;border:none;  
}  
.hc-btn.p{background:var(--accent);color:#fff}  
.hc-btn.p:hover{background:var(--accent2)}  
.hc-btn.w{background:var(--bg4);color:var(--w);border:1px solid var(--border2)}  
.hc-btn.w:hover{background:var(--bg5)}  
.hc-btn.w.on{border-color:rgba(229,9,20,.4);color:var(--accent2)}  
  
/* ── MOVIE MODAL ── */  
.overlay{  
  display:none;position:fixed;inset:0;z-index:800;  
  background:rgba(5,5,10,.92);backdrop-filter:blur(12px);  
  align-items:center;justify-content:center;padding:1.5rem;  
}  
.overlay.open{display:flex;animation:fIn .2s ease}  
@keyframes fIn{from{opacity:0}to{opacity:1}}  
#movieModal{  
  background:var(--bg2);border-radius:12px;width:100%;max-width:860px;  
  border:1px solid var(--border2);max-height:92vh;overflow-y:auto;  
  animation:mUp .28s cubic-bezier(.34,1.1,.64,1);  
}  
@keyframes mUp{from{opacity:0;transform:scale(.93) translateY(20px)}to{opacity:1;transform:none}}  
.mm-hero{position:relative;height:380px;overflow:hidden;background:var(--bg3)}  
#mmBg{  
  position:absolute;inset:0;background-size:cover;background-position:center 20%;  
  filter:brightness(.6);transition:all .5s;  
}  
.mm-fade{position:absolute;inset:0;background:linear-gradient(to top,var(--bg2) 0%,rgba(17,17,24,.5) 40%,transparent 75%)}  
.mm-close{  
  position:absolute;top:1rem;right:1rem;background:rgba(10,10,15,.85);  
  border:1px solid var(--border2);color:var(--g);width:34px;height:34px;  
  border-radius:50%;cursor:pointer;font-size:.8rem;display:flex;  
  align-items:center;justify-content:center;transition:all .15s;z-index:2;  
}  
.mm-close:hover{background:var(--bg4);color:var(--w)}  
.mm-hero-play{  
  position:absolute;inset:0;display:flex;align-items:center;justify-content:center;z-index:1;  
}  
.mm-play-ring{  
  width:68px;height:68px;border-radius:50%;background:rgba(229,9,20,.85);  
  border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;  
  color:#fff;transition:all .2s;  
}  
.mm-play-ring:hover{background:var(--accent2);transform:scale(1.08);box-shadow:0 0 0 8px rgba(229,9,20,.2)}  
.mm-body{padding:1.8rem 2.2rem 2.2rem}  
.mm-top{display:grid;grid-template-columns:1fr auto;gap:1.5rem;margin-bottom:1.5rem}  
.mm-title{  
  font-family:'Bebas Neue',sans-serif;font-size:2.4rem;letter-spacing:.03em;  
  line-height:1;margin-bottom:.7rem;  
}  
.mm-meta{display:flex;align-items:center;gap:.7rem;font-size:.8rem;color:var(--g);flex-wrap:wrap;margin-bottom:.8rem}  
.mm-rating-big{  
  display:flex;align-items:center;gap:.3rem;color:var(--gold);font-weight:700;font-size:.85rem;  
}  
.mm-genres{display:flex;gap:.35rem;flex-wrap:wrap;margin-bottom:1rem}  
.mm-genre{  
  font-size:.65rem;font-weight:600;letter-spacing:.06em;text-transform:uppercase;  
  padding:.2rem .6rem;background:var(--bg4);border:1px solid var(--border2);  
  border-radius:3px;color:var(--g);  
}  
.mm-desc{font-size:.86rem;color:var(--g);line-height:1.75;margin-bottom:1.5rem}  
.mm-actions{display:flex;gap:.6rem;flex-wrap:wrap;margin-bottom:2rem}  
.mm-btn{  
  display:inline-flex;align-items:center;gap:.45rem;  
  font-family:'Inter',sans-serif;font-size:.82rem;font-weight:600;  
  padding:.62rem 1.4rem;border-radius:var(--r);cursor:pointer;border:none;transition:all .18s;  
}  
.mm-btn.play{background:var(--accent);color:#fff}  
.mm-btn.play:hover{background:var(--accent2);transform:translateY(-1px);box-shadow:0 6px 20px rgba(229,9,20,.4)}  
.mm-btn.wl{background:var(--bg4);color:var(--w);border:1px solid var(--border2)}  
.mm-btn.wl:hover{background:var(--bg5)}  
.mm-btn.wl.on{border-color:rgba(229,9,20,.4);color:var(--accent2)}  
.mm-poster{width:130px;flex-shrink:0}  
.mm-poster img{width:100%;border-radius:var(--r);border:1px solid var(--border)}  
.mm-cast-title{font-size:.72rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--g2);margin-bottom:.7rem}  
.mm-cast{display:flex;gap:.6rem;overflow-x:auto;scrollbar-width:none}  
.mm-cast::-webkit-scrollbar{display:none}  
.cast-item{flex-shrink:0;text-align:center;width:68px}  
.cast-img{width:52px;height:52px;border-radius:50%;object-fit:cover;margin:0 auto .35rem;background:var(--bg4);border:2px solid var(--border)}  
.cast-name{font-size:.6rem;font-weight:600;line-height:1.3;color:var(--g)}  
.mm-trailer{  
  border-top:1px solid var(--border);padding-top:1.5rem;margin-top:0.5rem;  
}  
.mm-trailer-title{font-size:.72rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--g2);margin-bottom:.7rem}  
#trailerFrame{  
  width:100%;aspect-ratio:16/9;border-radius:var(--r);border:1px solid var(--border);  
  background:#000;  
}  
  
/* ── PLAYER ── */  
#playerWrap{  
  display:none;position:fixed;inset:0;background:#000;z-index:1000;flex-direction:column;  
}  
#playerWrap.open{display:flex}  
#pHeader{  
  display:flex;justify-content:space-between;align-items:center;  
  background:rgba(10,10,15,.98);border-bottom:1px solid var(--border);  
  padding:.7rem 1.5rem;flex-shrink:0;  
}  
.ph-l{display:flex;align-items:center;gap:.7rem}  
.ph-badge{background:var(--accent);color:#fff;font-size:.55rem;font-weight:800;letter-spacing:.12em;padding:.15rem .45rem;border-radius:2px}  
#pTitle{font-size:.88rem;font-weight:700}  
#pSub{font-size:.68rem;color:var(--g);margin-top:1px}  
.ph-r{display:flex;gap:.4rem}  
.pbtn{  
  background:var(--bg3);border:1px solid var(--border);color:var(--g);  
  padding:.32rem .9rem;border-radius:var(--r);cursor:pointer;  
  font-family:'Inter',sans-serif;font-size:.74rem;font-weight:600;transition:all .15s;  
}  
.pbtn:hover{background:var(--bg4);color:var(--w)}  
#playerInner{flex:1;display:flex;align-items:center;justify-content:center;background:#000}  
#playerInner iframe{width:100%;height:100%;border:none}  
.player-msg{color:var(--g);text-align:center;font-size:.9rem;padding:3rem}  
  
/* ── WATCHLIST PAGE ── */  
#wlPage{display:none;padding:0 3rem 5rem}  
#wlPage .page-title{  
  font-family:'Bebas Neue',sans-serif;font-size:2.2rem;letter-spacing:.04em;  
  padding:1.5rem 0 1.2rem;color:var(--w);  
}  
  
/* ── GENRE PAGE ── */  
#genrePage{display:none;padding:0 3rem 5rem}  
#genrePage .page-title{  
  font-family:'Bebas Neue',sans-serif;font-size:2.2rem;letter-spacing:.04em;  
  padding:1.5rem 0 .5rem;  
}  
.genre-filter{display:flex;gap:.4rem;flex-wrap:wrap;margin-bottom:1.5rem}  
.gf{  
  font-size:.72rem;font-weight:600;padding:.35rem .9rem;border-radius:100px;  
  border:1px solid var(--border);color:var(--g);background:none;  
  cursor:pointer;font-family:'Inter',sans-serif;transition:all .15s;  
}  
.gf:hover{border-color:var(--accent);color:var(--w)}  
.gf.active{background:rgba(229,9,20,.15);border-color:rgba(229,9,20,.5);color:var(--accent2)}  
.pg-grid{  
  display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:.85rem;  
}  
  
/* ── SEARCH PAGE ── */  
#searchPage{display:none;padding:0 3rem 5rem}  
#searchPage .page-title{font-family:'Bebas Neue',sans-serif;font-size:2.2rem;letter-spacing:.04em;padding:1.5rem 0 1.2rem;}  
.srch-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:.85rem}  
  
/* ── LOADING ── */  
.skeleton{  
  background:linear-gradient(90deg,var(--bg3) 25%,var(--bg4) 50%,var(--bg3) 75%);  
  background-size:200% 100%;animation:shimmer 1.4s infinite;border-radius:var(--r);  
}  
@keyframes shimmer{0%{background-position:200% 0}100%{background-position:-200% 0}}  
  
/* ── TOAST ── */  
#toast{  
  position:fixed;bottom:1.5rem;left:50%;transform:translateX(-50%) translateY(70px);  
  background:var(--bg3);border:1px solid var(--border2);border-radius:var(--r);  
  padding:.7rem 1.2rem;display:flex;align-items:center;gap:.55rem;  
  box-shadow:0 12px 36px rgba(0,0,0,.8);z-index:9000;  
  transition:transform .28s ease;font-size:.78rem;font-weight:600;max-width:340px;  
}  
#toast.show{transform:translateX(-50%) translateY(0)}  
  
/* ── FOOTER ── */  
footer{  
  padding:2rem 3rem;border-top:1px solid var(--border);  
  display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem;  
}  
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:1.4rem;color:var(--accent);letter-spacing:.06em}  
.footer-txt{font-size:.7rem;color:var(--g2)}  
  
/* ── RESPONSIVE ── */  
@media(max-width:768px){  
  #nav{padding:0 1.2rem;gap:1rem}  
  #hero{padding:0 1.2rem 5rem}  
  .hero-title{font-size:2.8rem}  
  .row-wrap{padding:0 1.2rem}  
  #wlPage,#genrePage,#searchPage{padding:0 1.2rem 4rem}  
  .mm-body{padding:1.2rem 1.2rem 1.5rem}  
  .mm-top{grid-template-columns:1fr}  
  .mm-poster{display:none}  
}  
@media(max-width:480px){  
  .nav-links{display:none}  
  .card{width:130px}  
  .card-wide{width:180px}  
}  
</style>  
</head>  
<body>  
  
<!-- ═══ NAV ═══ -->  
<nav id="nav">  
  <div class="nav-logo" onclick="goHome()">Delta VAULT</div>  
  <div class="nav-links">  
    <button class="nl active" id="nlHome" onclick="goHome()">Home</button>  
    <button class="nl" id="nlMovies" onclick="goGenre('movie')">Movies</button>  
    <button class="nl" id="nlTV" onclick="goGenre('tv')">TV Shows</button>  
    <button class="nl" id="nlWL" onclick="goWatchlist()">My List</button>  
  </div>  
  <div class="nav-r">  
    <div class="sw" id="sw"><input id="srch" type="text" placeholder="Search movies & shows…"/></div>  
    <button class="ni" onclick="toggleSearch()" title="Search">  
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>  
    </button>  
    <div class="profile-btn">S</div>  
  </div>  
</nav>  
  
<!-- ═══ HERO ═══ -->  
<div id="hero">  
  <div id="heroBg"></div>  
  <div class="hero-content" id="heroContent">  
    <div class="hero-tags" id="heroTags"></div>  
    <div class="hero-title" id="heroTitle">Loading…</div>  
    <div class="hero-meta" id="heroMeta"></div>  
    <div class="hero-desc" id="heroDesc"></div>  
    <div class="hero-btns">  
      <button class="hbtn play" onclick="heroPlay()">  
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><polygon points="5,3 19,12 5,21"/></svg>Play Now  
      </button>  
      <button class="hbtn info" onclick="heroInfo()">  
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>More Info  
      </button>  
      <button class="hbtn add" id="heroWLBtn" onclick="heroWL()">+ My List</button>  
    </div>  
  </div>  
  <div class="hero-indicators" id="heroInds"></div>  
</div>  
  
<!-- ═══ MAIN (HOME) ═══ -->  
<div id="main">  
  <div id="rowsContainer"></div>  
</div>  
  
<!-- ═══ WATCHLIST PAGE ═══ -->  
<div id="wlPage">  
  <div class="page-title">My List</div>  
  <div class="pg-grid" id="wlGrid"></div>  
</div>  
  
<!-- ═══ GENRE PAGE ═══ -->  
<div id="genrePage">  
  <div class="page-title" id="genrePageTitle">Movies</div>  
  <div class="genre-filter" id="genreFilter"></div>  
  <div class="pg-grid" id="genreGrid"></div>  
</div>  
  
<!-- ═══ SEARCH PAGE ═══ -->  
<div id="searchPage">  
  <div class="page-title">Search Results</div>  
  <div class="srch-grid" id="srchGrid"></div>  
</div>  
  
<!-- ═══ HOVER CARD ═══ -->  
<div class="hov-card" id="hovCard">  
  <div class="hc-art">  
    <img id="hcImg" src="" alt=""/>  
    <div class="hc-art-fade"></div>  
    <div class="hc-play">  
      <button class="hc-play-btn" id="hcPlayBtn">  
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><polygon points="5,3 19,12 5,21"/></svg>  
      </button>  
    </div>  
  </div>  
  <div class="hc-body">  
    <div class="hc-title" id="hcTitle"></div>  
    <div class="hc-meta" id="hcMeta"></div>  
    <div class="hc-desc" id="hcDesc"></div>  
    <div class="hc-tags" id="hcTags"></div>  
    <div class="hc-btns">  
      <button class="hc-btn p" id="hcPlay">  
        <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><polygon points="5,3 19,12 5,21"/></svg>Play  
      </button>  
      <button class="hc-btn w" id="hcWL">+ My List</button>  
    </div>  
  </div>  
</div>  
  
<!-- ═══ MOVIE MODAL ═══ -->  
<div class="overlay" id="movieOv">  
  <div id="movieModal">  
    <div class="mm-hero">  
      <div id="mmBg"></div>  
      <div class="mm-fade"></div>  
      <button class="mm-close" onclick="closeModal()">✕</button>  
      <div class="mm-hero-play">  
        <button class="mm-play-ring" onclick="modalPlay()">  
          <svg width="26" height="26" viewBox="0 0 24 24" fill="currentColor"><polygon points="5,3 19,12 5,21"/></svg>  
        </button>  
      </div>  
    </div>  
    <div class="mm-body">  
      <div class="mm-top">  
        <div>  
          <div class="mm-title" id="mmTitle"></div>  
          <div class="mm-meta" id="mmMeta"></div>  
          <div class="mm-genres" id="mmGenres"></div>  
          <div class="mm-desc" id="mmDesc"></div>  
          <div class="mm-actions">  
            <button class="mm-btn play" onclick="modalPlay()">  
              <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><polygon points="5,3 19,12 5,21"/></svg>Play Now  
            </button>  
            <button class="mm-btn wl" id="mmWLBtn" onclick="modalWL()">  
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" id="mmWLIco"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>  
              <span id="mmWLTxt">Add to My List</span>  
            </button>  
          </div>  
        </div>  
        <div class="mm-poster"><img id="mmPoster" src="" alt=""/></div>  
      </div>  
      <div>  
        <div class="mm-cast-title">Cast</div>  
        <div class="mm-cast" id="mmCast"></div>  
      </div>  
      <div class="mm-trailer" id="mmTrailer" style="display:none">  
        <div class="mm-trailer-title">Trailer</div>  
        <iframe id="trailerFrame" allow="autoplay;encrypted-media" allowfullscreen></iframe>  
      </div>  
    </div>  
  </div>  
</div>  
  
<!-- ═══ PLAYER ═══ -->  
<div id="playerWrap">  
  <div id="pHeader">  
    <div class="ph-l">  
      <span class="ph-badge">PLAYING</span>  
      <div><div id="pTitle">—</div><div id="pSub"></div></div>  
    </div>  
    <div class="ph-r">  
      <button class="pbtn" onclick="closePlayer()">✕ Close</button>  
    </div>  
  </div>  
  <div id="playerInner"></div>  
</div>  
  
<div id="toast"><span id="toastIco">✓</span> <span id="toastMsg">Done</span></div>  
  
<footer>  
  <div class="footer-logo">Delta VAULT</div>  
  <div class="footer-txt">Powered by TMDB · Content from public sources · For demo purposes</div>  
</footer>  
  
<script>  
// ── CONFIG ──  
const TMDB_KEY = '8265bd1679663a7ea12ac168da84d2e8'; // public demo key  
const TMDB = 'https://api.tmdb.org/3';  
const IMG = 'https://image.tmdb.org/t/p/';  
  
// ── STATE ──  
let watchlist = [], heroItems = [], curHeroIdx = 0, heroTimer = null;  
let curModal = null, curPage = 'home', hovTimeout = null, hovItem = null;  
const genres = {  
  movie: { 28:'Action',12:'Adventure',16:'Animation',35:'Comedy',80:'Crime',99:'Documentary',18:'Drama',10751:'Family',14:'Fantasy',36:'History',27:'Horror',10402:'Music',9648:'Mystery',10749:'Romance',878:'Sci-Fi',53:'Thriller',10752:'War',37:'Western' },  
  tv:    { 10759:'Action & Adventure',16:'Animation',35:'Comedy',80:'Crime',99:'Documentary',18:'Drama',10751:'Family',10762:'Kids',9648:'Mystery',10763:'News',10764:'Reality',10765:'Sci-Fi & Fantasy',10766:'Soap',10767:'Talk',10768:'War & Politics',37:'Western' }  
};  
let genrePageType = 'movie', genreFilter = 0;  
  
// ── PERSIST ──  
function load(){try{watchlist=JSON.parse(localStorage.getItem('sv_wl')||'[]')}catch{watchlist=[]}}  
function save(){try{localStorage.setItem('sv_wl',JSON.stringify(watchlist))}catch{}}  
load();  
  
// ── TMDB FETCH ──  
async function tmdb(path,params={}){  
  const p=new URLSearchParams({api_key:TMDB_KEY,language:'en-US',...params});  
  const r=await fetch(`${TMDB}${path}?${p}`);  
  return r.json();  
}  
  
// ── IMAGE HELPERS ──  
const backdropUrl = (p,sz='w1280') => p ? `${IMG}${sz}${p}` : '';  
const posterUrl   = (p,sz='w342')  => p ? `${IMG}${sz}${p}` : '';  
const profileUrl  = (p,sz='w185')  => p ? `${IMG}${sz}${p}` : '';  
  
// ── STAR RATING ──  
const stars = v => '★'.repeat(Math.round(v/2)) + '☆'.repeat(5-Math.round(v/2));  
  
// ── HOME LOAD ──  
async function loadHome(){  
  document.getElementById('rowsContainer').innerHTML='';  
  const rows=[  
    {title:'🔥 Trending Now',  fn:()=>tmdb('/trending/all/week')},  
    {title:'🎬 Popular Movies', fn:()=>tmdb('/movie/popular')},  
    {title:'📺 Top Rated TV',   fn:()=>tmdb('/tv/top_rated')},  
    {title:'⭐ Top Rated Movies',fn:()=>tmdb('/movie/top_rated')},  
    {title:'🆕 New Releases',   fn:()=>tmdb('/movie/now_playing')},  
    {title:'🤩 Fan Favorites',  fn:()=>tmdb('/tv/popular')},  
    {title:'😂 Comedies',       fn:()=>tmdb('/discover/movie',{with_genres:'35',sort_by:'popularity.desc'})},  
    {title:'😱 Horror & Thrills',fn:()=>tmdb('/discover/movie',{with_genres:'27,53',sort_by:'popularity.desc'})},  
    {title:'🚀 Sci-Fi & Fantasy',fn:()=>tmdb('/discover/movie',{with_genres:'878,14',sort_by:'popularity.desc'})},  
    {title:'❤️ Romance',        fn:()=>tmdb('/discover/movie',{with_genres:'10749',sort_by:'popularity.desc'})},  
    {title:'🌍 International',  fn:()=>tmdb('/discover/movie',{with_original_language:'fr|es|ko|ja|de',sort_by:'vote_average.desc','vote_count.gte':500})},  
    {title:'📚 Documentaries',  fn:()=>tmdb('/discover/movie',{with_genres:'99',sort_by:'popularity.desc'})},  
  ];  
  // Build hero from trending  
  const trendData = await rows[0].fn();  
  setupHero(trendData.results.slice(0,6));  
  // Render all rows  
  rows.forEach((row,i)=>{  
    const wrap = document.createElement('div');  
    wrap.className = 'row-wrap';  
    wrap.innerHTML = `<div class="row-hdr"><div class="row-title">${row.title}</div><div class="row-see-all" onclick="goGenre('${i<=1||i===5?i<=1||i===3?'movie':'tv':'movie'}')">See all <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polyline points="9 18 15 12 9 6"/></svg></div></div><div class="row-scroll" id="row_${i}"><div style="display:flex;gap:.6rem">${[...Array(8)].map(()=>`<div class="skeleton" style="width:160px;height:240px;flex-shrink:0"></div>`).join('')}</div></div>`;  
    document.getElementById('rowsContainer').appendChild(wrap);  
    row.fn().then(data=>{  
      if(!data.results)return;  
      renderRow(`row_${i}`, data.results, i%3===0);  
    });  
  });  
}  
  
// ── HERO ──  
async function setupHero(items){  
  heroItems = items;  
  curHeroIdx = 0;  
  buildHeroIndicators();  
  await setHero(items[0]);  
  startHeroTimer();  
}  
function buildHeroIndicators(){  
  const el = document.getElementById('heroInds');  
  el.innerHTML = heroItems.map((_,i)=>`<div class="hi${i===0?' active':''}" onclick="jumpHero(${i})"></div>`).join('');  
}  
async function setHero(item){  
  if(!item)return;  
  const isTV = item.media_type==='tv'||item.first_air_date;  
  const title = item.title||item.name||'Unknown';  
  const year = (item.release_date||item.first_air_date||'').slice(0,4);  
  document.getElementById('heroBg').style.backgroundImage = backdropUrl(item.backdrop_path) ? `url(${backdropUrl(item.backdrop_path)})` : 'none';  
  document.getElementById('heroTitle').textContent = title;  
  document.getElementById('heroTags').innerHTML = `<span class="htag type">${isTV?'TV SHOW':'MOVIE'}</span>${year?`<span class="htag year">${year}</span>`:''}`;  
  document.getElementById('heroMeta').innerHTML = `<span class="hero-rating">★ ${item.vote_average?.toFixed(1)||'—'}</span><span class="hero-dot"></span><span>${item.vote_count?.toLocaleString()||0} votes</span>${item.original_language?`<span class="hero-dot"></span><span>${item.original_language.toUpperCase()}</span>`:''}`;  
  document.getElementById('heroDesc').textContent = item.overview||'';  
  // WL btn  
  const inWL = watchlist.some(w=>w.id===item.id);  
  const wlBtn = document.getElementById('heroWLBtn');  
  wlBtn.textContent = inWL ? '✓ In My List' : '+ My List';  
  wlBtn.style.borderColor = inWL ? 'rgba(229,9,20,.5)' : '';  
  wlBtn.style.color = inWL ? 'var(--accent2)' : '';  
  curModal = {item, type: isTV?'tv':'movie'};  
  // Update indicators  
  document.querySelectorAll('.hi').forEach((el,i)=>el.classList.toggle('active',i===curHeroIdx));  
}  
function startHeroTimer(){  
  clearInterval(heroTimer);  
  heroTimer = setInterval(()=>{  
    curHeroIdx = (curHeroIdx+1) % heroItems.length;  
    setHero(heroItems[curHeroIdx]);  
  }, 7000);  
}  
function jumpHero(i){curHeroIdx=i;setHero(heroItems[i]);startHeroTimer();}  
function heroPlay(){if(curModal)playItem(curModal.item,curModal.type)}  
function heroInfo(){if(curModal)openModal(curModal.item,curModal.type)}  
function heroWL(){if(curModal){toggleWL(curModal.item);setHero(heroItems[curHeroIdx]);}}  
  
// ── ROW RENDER ──  
function renderRow(id, items, wide=false){  
  const el = document.getElementById(id);  
  if(!el)return;  
  el.innerHTML = '';  
  items.slice(0,18).forEach(item=>{  
    el.appendChild(makeCard(item, wide));  
  });  
}  
function makeCard(item, wide=false){  
  const isTV = item.media_type==='tv'||item.first_air_date;  
  const type = isTV?'tv':'movie';  
  const title = item.title||item.name||'';  
  const year = (item.release_date||item.first_air_date||'').slice(0,4);  
  const rating = item.vote_average?.toFixed(1)||'—';  
  const poster = posterUrl(item.poster_path);  
  const inWL = watchlist.some(w=>w.id===item.id);  
  const card = document.createElement('div');  
  card.className = `card${wide?' card-wide':''}`;  
  card.setAttribute('data-id', item.id);  
  card.innerHTML = `  
    <div class="card-poster">  
      <img src="${poster||'data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 width=%22160%22 height=%22240%22%3E%3Crect fill=%22%2318181f%22 width=%22160%22 height=%22240%22/%3E%3Ctext fill=%22%23444%22 font-size=%2218%22 font-family=%22Arial%22 x=%2250%25%22 y=%2250%25%22 text-anchor=%22middle%22 dy=%22.35em%22%3E🎬%3C/text%3E%3C/svg%3E'}" alt="${title}" loading="lazy" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 width=%22160%22 height=%22240%22%3E%3Crect fill=%22%2318181f%22 width=%22160%22 height=%22240%22/%3E%3C/svg%3E'"/>  
      <div class="card-poster-fade"></div>  
      <div class="card-rating">★ ${rating}</div>  
      <div class="card-type">${isTV?'TV':'MOVIE'}</div>  
      <button class="card-wl ${inWL?'on':''}" onclick="event.stopPropagation();cardWL(event,${JSON.stringify(item).replace(/"/g,'&quot;')})">${inWL?'♥':'♡'}</button>  
    </div>  
    <div class="card-info">  
      <div class="card-title">${title}</div>  
      <div class="card-sub">${year?`<span>${year}</span><span class="card-meta-dot" style="width:2px;height:2px;border-radius:50%;background:var(--g3)"></span>`:''}${isTV?'<span>TV</span>':'<span>Movie</span>'}</div>  
    </div>`;  
  card.addEventListener('click', ()=>openModal(item, type));  
  card.addEventListener('mouseenter', e=>showHovCard(e,item,type,card));  
  card.addEventListener('mouseleave', ()=>scheduleHideHov());  
  return card;  
}  
  
// ── HOVER CARD ──  
let hovEl = null;  
function showHovCard(e, item, type, card){  
  clearTimeout(hovTimeout);  
  hovTimeout = setTimeout(()=>{  
    hovItem = {item,type};  
    const title = item.title||item.name||'';  
    const year = (item.release_date||item.first_air_date||'').slice(0,4);  
    const rating = item.vote_average?.toFixed(1)||'—';  
    const backdrop = backdropUrl(item.backdrop_path,'w500');  
    const poster = posterUrl(item.poster_path);  
    const inWL = watchlist.some(w=>w.id===item.id);  
    document.getElementById('hcImg').src = backdrop||poster||'';  
    document.getElementById('hcTitle').textContent = title;  
    document.getElementById('hcMeta').innerHTML = `<span class="hc-rating">★ ${rating}</span>${year?`<span class="hc-dot"></span><span>${year}</span>`:''}${type==='tv'?`<span class="hc-dot"></span><span>TV Series</span>`:''}`;  
    document.getElementById('hcDesc').textContent = item.overview||'';  
    document.getElementById('hcTags').innerHTML = '';  
    document.getElementById('hcPlay').onclick = ()=>{hideHovCard();playItem(item,type);};  
    document.getElementById('hcPlayBtn').onclick = ()=>{hideHovCard();playItem(item,type);};  
    const wlBtn = document.getElementById('hcWL');  
    wlBtn.textContent = inWL?'✓ In List':'+ My List';  
    wlBtn.classList.toggle('on',inWL);  
    wlBtn.onclick = ()=>{ toggleWL(item); const ni=watchlist.some(w=>w.id===item.id); wlBtn.textContent=ni?'✓ In List':'+ My List'; wlBtn.classList.toggle('on',ni); };  
    const hov = document.getElementById('hovCard');  
    const rect = card.getBoundingClientRect();  
    let left = rect.left + window.scrollX;  
    let top = rect.top + window.scrollY - 20;  
    if(left + 310 > window.innerWidth) left = window.innerWidth - 320;  
    if(left < 10) left = 10;  
    hov.style.left = left + 'px';  
    hov.style.top = top + 'px';  
    hov.style.position = 'absolute';  
    hov.classList.add('vis');  
    hovEl = card;  
  }, 400);  
}  
function scheduleHideHov(){  
  clearTimeout(hovTimeout);  
  hovTimeout = setTimeout(hideHovCard, 220);  
}  
function hideHovCard(){document.getElementById('hovCard').classList.remove('vis');hovEl=null;}  
document.getElementById('hovCard').addEventListener('mouseenter',()=>clearTimeout(hovTimeout));  
document.getElementById('hovCard').addEventListener('mouseleave',()=>scheduleHideHov());  
  
// ── MODAL ──  
async function openModal(item, type){  
  hideHovCard();  
  curModal = {item,type};  
  const title = item.title||item.name||'';  
  const year  = (item.release_date||item.first_air_date||'').slice(0,4);  
  document.getElementById('mmBg').style.backgroundImage = backdropUrl(item.backdrop_path) ? `url(${backdropUrl(item.backdrop_path,'w1280')})` : 'none';  
  document.getElementById('mmTitle').textContent = title;  
  document.getElementById('mmPoster').src = posterUrl(item.poster_path)||'';  
  const runtime = item.runtime ? `${item.runtime}m` : item.number_of_seasons ? `${item.number_of_seasons} season${item.number_of_seasons>1?'s':''}` : '';  
  document.getElementById('mmMeta').innerHTML = `<div class="mm-rating-big">★ ${item.vote_average?.toFixed(1)||'—'}</div>${year?`<span>·</span><span>${year}</span>`:''}${runtime?`<span>·</span><span>${runtime}</span>`:''}`;  
  document.getElementById('mmDesc').textContent = item.overview||'No description available.';  
  document.getElementById('mmGenres').innerHTML = (item.genres||item.genre_ids||[]).slice(0,5).map(g=>`<span class="mm-genre">${g.name||genres[type][g]||g}</span>`).join('');  
  updateMMWLBtn(item);  
  // Cast  
  document.getElementById('mmCast').innerHTML = '<div class="skeleton" style="width:52px;height:52px;border-radius:50%"></div>'.repeat(6);  
  document.getElementById('mmTrailer').style.display='none';  
  document.getElementById('trailerFrame').src='';  
  document.getElementById('movieOv').classList.add('open');  
  document.body.classList.add('locked');  
  // Fetch details  
  try{  
    const [details, credits, videos] = await Promise.all([  
      tmdb(`/${type}/${item.id}`),  
      tmdb(`/${type}/${item.id}/credits`),  
      tmdb(`/${type}/${item.id}/videos`)  
    ]);  
    // Update genres from details  
    if(details.genres){  
      document.getElementById('mmGenres').innerHTML = details.genres.slice(0,5).map(g=>`<span class="mm-genre">${g.name}</span>`).join('');  
    }  
    // Runtime / seasons  
    const rt = details.runtime ? `${details.runtime}m` : details.number_of_seasons ? `${details.number_of_seasons} season${details.number_of_seasons>1?'s':''}` : '';  
    document.getElementById('mmMeta').innerHTML = `<div class="mm-rating-big">★ ${details.vote_average?.toFixed(1)||'—'}</div>${year?`<span>·</span><span>${year}</span>`:''}${rt?`<span>·</span><span>${rt}</span>`:''}${details.status?`<span>·</span><span>${details.status}</span>`:''}`;  
    // Cast  
    const cast = credits.cast?.slice(0,12)||[];  
    document.getElementById('mmCast').innerHTML = cast.length ? cast.map(a=>`  
      <div class="cast-item">  
        <img class="cast-img" src="${profileUrl(a.profile_path)||'data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 width=%2252%22 height=%2252%22%3E%3Ccircle cx=%2226%22 cy=%2226%22 r=%2226%22 fill=%22%231e1e28%22/%3E%3C/svg%3E'}" alt="${a.name}" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 width=%2252%22 height=%2252%22%3E%3Ccircle cx=%2226%22 cy=%2226%22 r=%2226%22 fill=%22%231e1e28%22/%3E%3C/svg%3E'"/>  
        <div class="cast-name">${a.name}</div>  
      </div>`).join('') : '<span style="font-size:.78rem;color:var(--g2)">No cast info available</span>';  
    // Trailer  
    const trailer = videos.results?.find(v=>v.type==='Trailer'&&v.site==='YouTube') || videos.results?.[0];  
    if(trailer?.key){  
      document.getElementById('trailerFrame').src = `https://www.youtube.com/embed/${trailer.key}?autoplay=0&rel=0`;  
      document.getElementById('mmTrailer').style.display = 'block';  
    }  
  }catch(e){console.error('Detail fetch:',e);}  
}  
function closeModal(){  
  document.getElementById('movieOv').classList.remove('open');  
  document.body.classList.remove('locked');  
  document.getElementById('trailerFrame').src='';  
}  
document.getElementById('movieOv').addEventListener('click',e=>{if(e.target===document.getElementById('movieOv'))closeModal();});  
function modalPlay(){closeModal();if(curModal)playItem(curModal.item,curModal.type);}  
function updateMMWLBtn(item){  
  const inWL = watchlist.some(w=>w.id===item.id);  
  document.getElementById('mmWLBtn').classList.toggle('on',inWL);  
  document.getElementById('mmWLTxt').textContent = inWL?'In My List':'Add to My List';  
  document.getElementById('mmWLIco').innerHTML = inWL ?  
    '<polyline points="20 6 9 17 4 12" stroke="currentColor" stroke-width="2.5" fill="none"/>' :  
    '<line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/>';  
}  
function modalWL(){if(curModal){toggleWL(curModal.item);updateMMWLBtn(curModal.item);}}  
  
// ── PLAYER ──  
function playItem(item, type){  
  const id = item.id;  
  const title = item.title||item.name||'';  
  document.getElementById('pTitle').textContent = title;  
  document.getElementById('pSub').textContent = type==='tv'?'TV Series':'Movie';  
  document.getElementById('playerWrap').classList.add('open');  
  document.body.classList.add('locked');  
  // Use vidsrc embed — free public movie/tv embed service  
  const src = type==='tv'  
    ? `https://vidsrc.to/embed/tv/${id}`  
    : `https://vidsrc.to/embed/movie/${id}`;  
  document.getElementById('playerInner').innerHTML = `<iframe src="${src}" width="100%" height="100%" allowfullscreen allow="autoplay;fullscreen" frameborder="0" style="width:100%;height:100%;border:none"></iframe>`;  
}  
function closePlayer(){  
  document.getElementById('playerWrap').classList.remove('open');  
  document.body.classList.remove('locked');  
  document.getElementById('playerInner').innerHTML='';  
}  
  
// ── WATCHLIST ──  
function toggleWL(item){  
  const idx = watchlist.findIndex(w=>w.id===item.id);  
  if(idx>-1){watchlist.splice(idx,1);toast('Removed from My List','✓');}  
  else{watchlist.push(item);toast('Added to My List','♥');}  
  save();  
  refreshWLButtons(item);  
}  
function refreshWLButtons(item){  
  document.querySelectorAll(`.card[data-id="${item.id}"] .card-wl`).forEach(btn=>{  
    const inWL=watchlist.some(w=>w.id===item.id);  
    btn.classList.toggle('on',inWL);btn.innerHTML=inWL?'♥':'♡';  
  });  
}  
function cardWL(e,item){e.stopPropagation();toggleWL(item);}  
function heroWL(){if(curModal){toggleWL(curModal.item);setHero(heroItems[curHeroIdx]);}}  
function goWatchlist(){  
  setPage('wl');  
  const g = document.getElementById('wlGrid');  
  if(!watchlist.length){g.innerHTML='<div style="color:var(--g2);padding:2rem;font-size:.88rem;grid-column:1/-1">Your list is empty. Browse and add movies & shows!</div>';return;}  
  g.innerHTML='';  
  watchlist.forEach(item=>{  
    const type = item.media_type||(item.first_air_date?'tv':'movie');  
    g.appendChild(makeCard(item,type==='tv'));  
  });  
}  
  
// ── GENRE PAGE ──  
async function goGenre(type){  
  genrePageType = type;  
  genreFilter = 0;  
  setPage('genre');  
  document.getElementById('genrePageTitle').textContent = type==='tv' ? 'TV Shows' : 'Movies';  
  // Build filter pills  
  const gMap = genres[type];  
  document.getElementById('genreFilter').innerHTML = `<button class="gf active" onclick="filterGenre(0,this)">All</button>` +  
    Object.entries(gMap).map(([id,name])=>`<button class="gf" onclick="filterGenre(${id},this)">${name}</button>`).join('');  
  await loadGenreGrid(type, 0);  
}  
async function filterGenre(genreId, el){  
  genreFilter = genreId;  
  document.querySelectorAll('.gf').forEach(g=>g.classList.remove('active'));  
  el.classList.add('active');  
  await loadGenreGrid(genrePageType, genreId);  
}  
async function loadGenreGrid(type, genreId){  
  const grid = document.getElementById('genreGrid');  
  grid.innerHTML = [...Array(12)].map(()=>`<div class="skeleton" style="height:280px;border-radius:6px"></div>`).join('');  
  const params = {sort_by:'popularity.desc'};  
  if(genreId) params.with_genres = genreId;  
  const data = await tmdb(`/discover/${type}`, params);  
  grid.innerHTML='';  
  (data.results||[]).forEach(item=>grid.appendChild(makeCard(item)));  
}  
  
// ── SEARCH ──  
let _st=null;  
function toggleSearch(){  
  const sw = document.getElementById('sw');  
  sw.classList.toggle('open');  
  if(sw.classList.contains('open')){document.getElementById('srch').focus();}  
}  
document.getElementById('srch').addEventListener('input', e=>{  
  clearTimeout(_st);  
  const q = e.target.value.trim();  
  if(!q){setPage('home');return;}  
  _st = setTimeout(()=>doSearch(q), 350);  
});  
async function doSearch(q){  
  setPage('search');  
  const grid = document.getElementById('srchGrid');  
  grid.innerHTML = [...Array(10)].map(()=>`<div class="skeleton" style="height:260px;border-radius:6px"></div>`).join('');  
  const data = await tmdb('/search/multi',{query:q});  
  grid.innerHTML='';  
  const res = (data.results||[]).filter(r=>r.media_type!=='person'&&(r.poster_path||r.backdrop_path));  
  if(!res.length){grid.innerHTML='<div style="color:var(--g2);font-size:.88rem;padding:2rem;grid-column:1/-1">No results found.</div>';return;}  
  res.forEach(item=>grid.appendChild(makeCard(item)));  
}  
  
// ── PAGE ROUTING ──  
function setPage(p){  
  curPage = p;  
  document.getElementById('main').style.display       = p==='home'?'block':'none';  
  document.getElementById('hero').style.display       = p==='home'?'flex':'none';  
  document.getElementById('wlPage').style.display     = p==='wl'?'block':'none';  
  document.getElementById('genrePage').style.display  = p==='genre'?'block':'none';  
  document.getElementById('searchPage').style.display = p==='search'?'block':'none';  
  ['nlHome','nlMovies','nlTV','nlWL'].forEach((id,i)=>{  
    document.getElementById(id)?.classList.toggle('active',  
      (p==='home'&&i===0)||(p==='genre'&&genrePageType==='movie'&&i===1)||(p==='genre'&&genrePageType==='tv'&&i===2)||(p==='wl'&&i===3)  
    );  
  });  
  window.scrollTo(0,0);  
}  
function goHome(){setPage('home');}  
  
// ── NAV SCROLL ──  
window.addEventListener('scroll',()=>document.getElementById('nav').classList.toggle('solid',window.scrollY>60));  
  
// ── KEYBOARD ──  
document.addEventListener('keydown',e=>{  
  if(e.key==='Escape'){  
    if(document.getElementById('playerWrap').classList.contains('open'))closePlayer();  
    else if(document.getElementById('movieOv').classList.contains('open'))closeModal();  
  }  
});  
  
// ── TOAST ──  
let _tt=null;  
function toast(msg,ico='✓'){  
  document.getElementById('toastMsg').textContent=msg;  
  document.getElementById('toastIco').textContent=ico;  
  document.getElementById('toast').classList.add('show');  
  clearTimeout(_tt);_tt=setTimeout(()=>document.getElementById('toast').classList.remove('show'),2500);  
}  
  
// ── INIT ──  
loadHome();  
</script>  
</body>  
</html>  
