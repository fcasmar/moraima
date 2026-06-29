<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Hostal Moraima · Capileira — Alpujarra Granadina</title>
<meta name="description" content="Hostal Moraima, hostal rural con restaurante en Capileira (Alpujarra Granadina). 6 habitaciones dobles, cocina alpujarreña y punto de partida al Mulhacén y Veleta. Reserva directa." />

<!-- Flatpickr (calendario) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css" />
<script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
<script src="https://cdn.jsdelivr.net/npm/flatpickr/dist/l10n/es.js"></script>

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;600;700&family=Mulish:wght@300;400;500;600;700&display=swap" rel="stylesheet" />

<style>
  :root{
    --cream:#f7f2ea;
    --sand:#efe5d6;
    --paper:#fffdf8;
    --clay:#b05c34;
    --clay-dark:#8f4424;
    --espresso:#2e2620;
    --olive:#6f7a4f;
    --gold:#c4a05a;
    --text:#3d342c;
    --muted:#837567;
    --line:rgba(46,38,32,.12);
    --shadow:0 18px 50px -22px rgba(46,38,32,.45);
    --shadow-sm:0 8px 24px -14px rgba(46,38,32,.4);
    --radius:18px;
  }

  *{margin:0;padding:0;box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    font-family:'Mulish',system-ui,sans-serif;
    color:var(--text);
    background:var(--cream);
    line-height:1.7;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
  h1,h2,h3,h4{font-family:'Playfair Display',Georgia,serif;font-weight:600;line-height:1.15;color:var(--espresso)}
  a{color:inherit;text-decoration:none}
  img{max-width:100%;display:block}
  section{position:relative}

  .wrap{width:min(1180px,92vw);margin:0 auto}
  .eyebrow{
    text-transform:uppercase;letter-spacing:.28em;font-size:.72rem;font-weight:700;
    color:var(--clay);display:inline-flex;align-items:center;gap:.6rem;margin-bottom:1rem;
  }
  .eyebrow::before{content:"";width:34px;height:1px;background:var(--clay);display:inline-block}
  .eyebrow.center::after{content:"";width:34px;height:1px;background:var(--clay);display:inline-block}

  .btn{
    display:inline-flex;align-items:center;gap:.6rem;cursor:pointer;border:none;
    font-family:'Mulish',sans-serif;font-weight:700;font-size:.95rem;letter-spacing:.02em;
    padding:.95rem 1.7rem;border-radius:50px;transition:.25s ease;white-space:nowrap;
  }
  .btn-primary{background:var(--clay);color:#fff}
  .btn-primary:hover{background:var(--clay-dark);transform:translateY(-2px);box-shadow:0 14px 28px -12px rgba(176,92,52,.7)}
  .btn-ghost{background:transparent;color:#fff;border:1.5px solid rgba(255,255,255,.7)}
  .btn-ghost:hover{background:rgba(255,255,255,.12);border-color:#fff}
  .btn-dark{background:var(--espresso);color:#fff}
  .btn-dark:hover{background:#1d1813;transform:translateY(-2px)}
  .btn-block{width:100%;justify-content:center}

  /* ===== NAV ===== */
  header.nav{
    position:fixed;top:0;left:0;right:0;z-index:60;
    transition:.35s ease;padding:1.3rem 0;
  }
  header.nav.scrolled{background:rgba(247,242,234,.96);backdrop-filter:blur(10px);box-shadow:0 6px 30px -18px rgba(46,38,32,.5);padding:.7rem 0}
  .nav-inner{display:flex;align-items:center;justify-content:space-between;gap:1.5rem}
  .brand{display:flex;flex-direction:column;line-height:1.05}
  .brand .name{font-family:'Playfair Display',serif;font-weight:700;font-size:1.45rem;color:#fff;letter-spacing:.01em;transition:.35s}
  .brand .sub{font-size:.62rem;letter-spacing:.32em;text-transform:uppercase;color:rgba(255,255,255,.78);font-weight:600;transition:.35s}
  header.nav.scrolled .brand .name,header.nav.scrolled .brand .sub{color:var(--espresso)}
  header.nav.scrolled .brand .sub{color:var(--clay)}
  .nav-links{display:flex;align-items:center;gap:2rem;list-style:none}
  .nav-links a{color:rgba(255,255,255,.92);font-weight:600;font-size:.9rem;position:relative;padding:.3rem 0;transition:.3s}
  .nav-links a::after{content:"";position:absolute;left:0;bottom:-2px;width:0;height:2px;background:var(--gold);transition:.3s}
  .nav-links a:hover::after{width:100%}
  header.nav.scrolled .nav-links a{color:var(--text)}
  .nav-cta{display:flex;align-items:center;gap:1rem}
  .burger{display:none;background:none;border:none;cursor:pointer;width:42px;height:42px;flex-direction:column;justify-content:center;gap:5px;align-items:center}
  .burger span{width:24px;height:2px;background:#fff;transition:.3s;border-radius:2px}
  header.nav.scrolled .burger span{background:var(--espresso)}
  .burger.open span:nth-child(1){transform:translateY(7px) rotate(45deg)}
  .burger.open span:nth-child(2){opacity:0}
  .burger.open span:nth-child(3){transform:translateY(-7px) rotate(-45deg)}

  .mobile-menu{
    position:fixed;inset:0;z-index:55;background:var(--espresso);
    display:flex;flex-direction:column;justify-content:center;align-items:center;gap:1.8rem;
    transform:translateY(-100%);transition:.45s cubic-bezier(.7,0,.2,1);visibility:hidden;
  }
  .mobile-menu.open{transform:translateY(0);visibility:visible}
  .mobile-menu a{color:#fff;font-family:'Playfair Display',serif;font-size:1.8rem}
  .mobile-menu a:hover{color:var(--gold)}

  /* ===== HERO ===== */
  .hero{
    min-height:100vh;display:flex;align-items:center;color:#fff;position:relative;overflow:hidden;
    background:
      linear-gradient(180deg,rgba(46,38,32,.5) 0%,rgba(46,38,32,.35) 40%,rgba(46,38,32,.75) 100%),
      url('https://images.unsplash.com/photo-1469474968028-56623f02e42e?auto=format&fit=crop&w=2000&q=80') center/cover no-repeat,
      linear-gradient(135deg,#3a4a3a,#6f7a4f);
    background-attachment:fixed;
  }
  .hero::after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,transparent 60%,var(--cream) 101%)}
  .hero-content{position:relative;z-index:2;max-width:760px;padding:8rem 0 4rem}
  .hero .eyebrow{color:var(--gold)}
  .hero .eyebrow::before{background:var(--gold)}
  .hero h1{color:#fff;font-size:clamp(2.6rem,6vw,4.6rem);font-weight:700;letter-spacing:-.01em;margin-bottom:1.2rem;text-shadow:0 4px 30px rgba(0,0,0,.3)}
  .hero p.lead{font-size:clamp(1.05rem,1.6vw,1.25rem);color:rgba(255,255,255,.92);max-width:580px;margin-bottom:2.2rem;font-weight:300}
  .hero-actions{display:flex;gap:1rem;flex-wrap:wrap}
  .hero-badges{display:flex;gap:2rem;flex-wrap:wrap;margin-top:3rem;color:rgba(255,255,255,.9)}
  .hero-badges .b{display:flex;flex-direction:column}
  .hero-badges .b strong{font-family:'Playfair Display',serif;font-size:1.8rem;color:#fff;line-height:1}
  .hero-badges .b span{font-size:.78rem;letter-spacing:.12em;text-transform:uppercase;color:rgba(255,255,255,.7)}

  .scroll-cue{position:absolute;left:50%;bottom:2rem;transform:translateX(-50%);z-index:3;color:#fff;writing-mode:vertical-lr;font-size:.72rem;letter-spacing:.3em;text-transform:uppercase;opacity:.8}
  .scroll-cue::after{content:"";display:block;width:1px;height:40px;background:#fff;margin:.6rem auto 0;animation:cue 1.8s infinite}
  @keyframes cue{0%{transform:scaleY(0);transform-origin:top}50%{transform:scaleY(1);transform-origin:top}51%{transform-origin:bottom}100%{transform:scaleY(0);transform-origin:bottom}}

  /* ===== SECTION SHELL ===== */
  .section{padding:6.5rem 0}
  .section-head{max-width:640px;margin-bottom:3.5rem}
  .section-head.center{margin-left:auto;margin-right:auto;text-align:center}
  .section-head.center .eyebrow{justify-content:center}
  .section-head h2{font-size:clamp(2rem,4vw,3rem);margin-bottom:1rem}
  .section-head p{color:var(--muted);font-size:1.05rem}

  /* ===== INTRO ===== */
  .intro{background:var(--cream)}
  .intro-grid{display:grid;grid-template-columns:1.05fr .95fr;gap:4rem;align-items:center}
  .intro-media{position:relative;border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);aspect-ratio:4/5}
  .intro-media img{width:100%;height:100%;object-fit:cover}
  .intro-media .tag{
    position:absolute;left:1.5rem;bottom:1.5rem;background:var(--paper);padding:1.1rem 1.5rem;border-radius:14px;box-shadow:var(--shadow-sm);
    display:flex;align-items:center;gap:.9rem;max-width:78%;
  }
  .intro-media .tag .ic{width:42px;height:42px;flex:none;background:var(--clay);color:#fff;border-radius:50%;display:grid;place-items:center}
  .intro-media .tag b{display:block;font-family:'Playfair Display',serif;font-size:1.05rem;color:var(--espresso)}
  .intro-media .tag span{font-size:.82rem;color:var(--muted)}
  .intro-text p{margin-bottom:1.2rem;color:var(--text)}
  .intro-features{display:grid;grid-template-columns:repeat(2,1fr);gap:1.2rem;margin-top:2rem}
  .feat{display:flex;gap:.9rem;align-items:flex-start}
  .feat .ic{width:44px;height:44px;flex:none;background:var(--sand);border-radius:12px;display:grid;place-items:center;color:var(--clay)}
  .feat b{display:block;color:var(--espresso);font-size:.98rem}
  .feat span{font-size:.85rem;color:var(--muted)}

  /* ===== ROOMS ===== */
  .rooms{background:var(--paper)}
  .rooms-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.8rem}
  .room-card{
    background:#fff;border:1px solid var(--line);border-radius:var(--radius);overflow:hidden;
    transition:.35s;display:flex;flex-direction:column;
  }
  .room-card:hover{transform:translateY(-6px);box-shadow:var(--shadow);border-color:transparent}
  .room-card .ph{height:210px;position:relative;background-size:cover;background-position:center}
  .room-card .ph::after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,transparent 50%,rgba(46,38,32,.45))}
  .room-card .ph .price{position:absolute;right:1rem;top:1rem;background:rgba(255,253,248,.95);color:var(--clay);font-weight:700;padding:.45rem .9rem;border-radius:50px;font-size:.85rem;z-index:2}
  .room-body{padding:1.6rem;flex:1;display:flex;flex-direction:column}
  .room-body h3{font-size:1.4rem;margin-bottom:.4rem}
  .room-body .desc{color:var(--muted);font-size:.92rem;margin-bottom:1.1rem}
  .room-amen{display:flex;flex-wrap:wrap;gap:.5rem .9rem;margin-top:auto;padding-top:1rem;border-top:1px dashed var(--line)}
  .room-amen span{font-size:.8rem;color:var(--text);display:inline-flex;align-items:center;gap:.35rem}
  .room-amen svg{width:15px;height:15px;color:var(--olive)}

  /* ===== RESTAURANT ===== */
  .rest{position:relative;color:#fff;overflow:hidden}
  .rest-bg{
    position:absolute;inset:0;z-index:0;
    background:
      linear-gradient(120deg,rgba(46,38,32,.92),rgba(46,38,32,.7)),
      url('https://images.unsplash.com/photo-1414235077428-338989a2e8c0?auto=format&fit=crop&w=2000&q=80') center/cover fixed no-repeat;
  }
  .rest .wrap{position:relative;z-index:1}
  .rest .section-head h2,.rest .section-head p{color:#fff}
  .rest .section-head p{color:rgba(255,255,255,.8)}
  .rest .eyebrow{color:var(--gold)}
  .rest .eyebrow::before{background:var(--gold)}
  .menu-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.4rem;margin-top:1rem}
  .menu-card{background:rgba(255,253,248,.06);border:1px solid rgba(255,255,255,.16);border-radius:var(--radius);padding:1.8rem 1.5rem;backdrop-filter:blur(4px);transition:.3s}
  .menu-card:hover{background:rgba(255,253,248,.12);transform:translateY(-4px)}
  .menu-card .ic{width:50px;height:50px;border-radius:14px;background:rgba(196,160,90,.2);color:var(--gold);display:grid;place-items:center;margin-bottom:1.1rem}
  .menu-card h4{color:#fff;font-size:1.25rem;margin-bottom:.4rem}
  .menu-card p{font-size:.88rem;color:rgba(255,255,255,.75)}
  .menu-card .time{margin-top:.9rem;font-size:.78rem;color:var(--gold);font-weight:700;letter-spacing:.05em}

  /* ===== NATURE / SURROUNDINGS ===== */
  .nature{background:var(--cream)}
  .nature-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.8rem}
  .nature-card{border-radius:var(--radius);overflow:hidden;position:relative;min-height:380px;background-size:cover;background-position:center;display:flex;align-items:flex-end}
  .nature-card::before{content:"";position:absolute;inset:0;background:linear-gradient(180deg,rgba(46,38,32,0) 30%,rgba(46,38,32,.85))}
  .nature-card .nbody{position:relative;z-index:2;padding:1.8rem;color:#fff}
  .nature-card .nbody h3{color:#fff;font-size:1.5rem;margin-bottom:.4rem}
  .nature-card .nbody p{color:rgba(255,255,255,.85);font-size:.9rem}
  .nature-card .alt{position:absolute;top:1.2rem;left:1.2rem;z-index:2;background:rgba(255,253,248,.95);color:var(--clay);font-weight:700;padding:.4rem .85rem;border-radius:50px;font-size:.78rem}

  /* ===== MAP ===== */
  .map{background:var(--paper)}
  .map-grid{display:grid;grid-template-columns:1fr 1fr;gap:3rem;align-items:stretch}
  .map-info{display:flex;flex-direction:column;justify-content:center}
  .map-info ul{list-style:none;margin:1.8rem 0}
  .map-info li{display:flex;gap:1rem;align-items:flex-start;padding:1rem 0;border-bottom:1px solid var(--line)}
  .map-info li .ic{width:42px;height:42px;flex:none;background:var(--sand);border-radius:12px;display:grid;place-items:center;color:var(--clay)}
  .map-info li b{display:block;color:var(--espresso)}
  .map-info li span{font-size:.9rem;color:var(--muted)}
  .map-frame{border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);min-height:420px;border:6px solid #fff}
  .map-frame iframe{width:100%;height:100%;min-height:420px;border:0;display:block}

  /* ===== BOOK ===== */
  .book{background:linear-gradient(160deg,var(--sand),var(--cream))}
  .book-card{background:var(--paper);border-radius:24px;box-shadow:var(--shadow);overflow:hidden;display:grid;grid-template-columns:1.1fr 1fr}
  .book-hero{
    background:
      linear-gradient(160deg,rgba(176,92,52,.85),rgba(143,68,36,.85)),
      url('https://images.unsplash.com/photo-1505691938895-1758d7feb511?auto=format&fit=crop&w=1200&q=80') center/cover;
    color:#fff;padding:3rem 2.6rem;display:flex;flex-direction:column;justify-content:space-between;min-height:420px;
  }
  .book-hero h3{color:#fff;font-size:2rem;margin-bottom:.6rem}
  .book-hero p{color:rgba(255,255,255,.9);font-size:.95rem;margin-bottom:1.6rem}
  .book-hero .rate{background:rgba(255,255,255,.14);border:1px solid rgba(255,255,255,.25);border-radius:14px;padding:1rem 1.2rem;backdrop-filter:blur(4px)}
  .book-hero .rate b{font-family:'Playfair Display',serif;font-size:1.8rem;display:block;line-height:1}
  .book-hero .rate span{font-size:.78rem;letter-spacing:.05em;color:rgba(255,255,255,.85)}
  .book-form{padding:3rem 2.6rem}
  .field{margin-bottom:1.3rem}
  .field label{display:block;font-size:.78rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--muted);margin-bottom:.5rem}
  .field input,.field select{
    width:100%;font-family:inherit;font-size:1rem;color:var(--text);
    background:#fff;border:1.5px solid var(--line);border-radius:12px;padding:.85rem 1rem;transition:.2s;
  }
  .field input:focus,.field select:focus{outline:none;border-color:var(--clay);box-shadow:0 0 0 4px rgba(176,92,52,.12)}
  .field-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem}
  .flatpickr-input[readonly]{background:#fff;cursor:pointer}
  .summary{
    background:var(--sand);border-radius:14px;padding:1.2rem 1.3rem;margin:1.2rem 0;
    display:flex;flex-direction:column;gap:.5rem;
  }
  .summary .row{display:flex;justify-content:space-between;font-size:.92rem;color:var(--text)}
  .summary .row span{color:var(--muted)}
  .summary .total{margin-top:.5rem;padding-top:.8rem;border-top:1px dashed var(--line);display:flex;justify-content:space-between;align-items:baseline}
  .summary .total b{font-family:'Playfair Display',serif;font-size:1.8rem;color:var(--clay)}
  .summary .total small{font-size:.72rem;color:var(--muted)}
  .form-note{font-size:.78rem;color:var(--muted);margin-top:.8rem;text-align:center}

  /* ===== CONTACT / FOOTER ===== */
  footer{background:var(--espresso);color:rgba(255,255,255,.75);padding:4.5rem 0 2rem}
  .foot-grid{display:grid;grid-template-columns:1.4fr 1fr 1fr;gap:3rem;margin-bottom:3rem}
  footer .brand .name{color:#fff}
  footer .brand .sub{color:var(--gold)}
  footer h5{color:#fff;font-family:'Mulish',sans-serif;font-size:.82rem;letter-spacing:.18em;text-transform:uppercase;margin-bottom:1.2rem}
  footer ul{list-style:none}
  footer li{margin-bottom:.6rem;font-size:.92rem}
  footer a:hover{color:var(--gold)}
  .foot-about p{margin-top:1.2rem;font-size:.92rem;max-width:34ch}
  .foot-bottom{border-top:1px solid rgba(255,255,255,.12);padding-top:1.8rem;display:flex;justify-content:space-between;gap:1rem;flex-wrap:wrap;font-size:.82rem;color:rgba(255,255,255,.55)}
  .soc{display:flex;gap:.7rem;margin-top:1.2rem}
  .soc a{width:40px;height:40px;border-radius:50%;background:rgba(255,255,255,.08);display:grid;place-items:center;color:#fff;transition:.25s}
  .soc a:hover{background:var(--clay);transform:translateY(-3px)}

  /* ===== WHATSAPP FLOAT ===== */
  .wa{
    position:fixed;right:1.2rem;bottom:1.2rem;z-index:70;width:58px;height:58px;border-radius:50%;
    background:#25d366;display:grid;place-items:center;box-shadow:0 12px 30px -8px rgba(37,211,102,.6);
    transition:.25s;
  }
  .wa:hover{transform:scale(1.08)}
  .wa svg{width:30px;height:30px;fill:#fff}

  /* ===== REVEAL ===== */
  .reveal{opacity:0;transform:translateY(28px);transition:.7s cubic-bezier(.2,.7,.2,1)}
  .reveal.in{opacity:1;transform:none}

  /* ===== RESPONSIVE ===== */
  @media(max-width:980px){
    .intro-grid,.map-grid,.book-card{grid-template-columns:1fr}
    .rooms-grid,.nature-grid,.menu-grid{grid-template-columns:repeat(2,1fr)}
    .foot-grid{grid-template-columns:1fr 1fr}
    .foot-about{grid-column:1/-1}
    .book-hero{min-height:auto}
    .hero{background-attachment:scroll}
    .rest-bg{background-attachment:scroll}
  }
  @media(max-width:680px){
    .nav-links{display:none}
    .nav-cta .btn-primary{display:none}
    .burger{display:flex}
    .section{padding:4.5rem 0}
    .rooms-grid,.nature-grid,.menu-grid{grid-template-columns:1fr}
    .foot-grid{grid-template-columns:1fr}
    .field-row{grid-template-columns:1fr}
    .hero-content{padding:7rem 0 3rem}
    .hero-badges{gap:1.4rem}
    .hero-badges .b strong{font-size:1.4rem}
    .intro-features{grid-template-columns:1fr}
    .book-form,.book-hero{padding:2.2rem 1.5rem}
    .menu-grid{gap:1rem}
  }
</style>
</head>
<body>

<!-- ===== NAV ===== -->
<header class="nav" id="nav">
  <div class="wrap nav-inner">
    <a href="#inicio" class="brand">
      <span class="name">Hostal Moraima</span>
      <span class="sub">Capileira · Alpujarra</span>
    </a>
    <nav>
      <ul class="nav-links">
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#habitaciones">Habitaciones</a></li>
        <li><a href="#restaurante">Restaurante</a></li>
        <li><a href="#entorno">Entorno</a></li>
        <li><a href="#ubicacion">Ubicación</a></li>
        <li><a href="#contacto">Contacto</a></li>
      </ul>
    </nav>
    <div class="nav-cta">
      <a href="#reservar" class="btn btn-primary">Reservar</a>
      <button class="burger" id="burger" aria-label="Menú"><span></span><span></span><span></span></button>
    </div>
  </div>
</header>

<!-- ===== MOBILE MENU ===== -->
<div class="mobile-menu" id="mobileMenu">
  <a href="#inicio">Inicio</a>
  <a href="#habitaciones">Habitaciones</a>
  <a href="#restaurante">Restaurante</a>
  <a href="#entorno">Entorno</a>
  <a href="#ubicacion">Ubicación</a>
  <a href="#reservar">Reservar</a>
  <a href="#contacto">Contacto</a>
</div>

<!-- ===== HERO ===== -->
<section class="hero" id="inicio">
  <div class="wrap">
    <div class="hero-content">
      <span class="eyebrow">Alpujarra Granadina · 1.436 m</span>
      <h1>Rincones de montaña<br/>con alma alpujarreña</h1>
      <p class="lead">Hostal rural con restaurante en el corazón de Capileira. Seis habitaciones con encanto, cocina casera y la puerta de salida al Mulhacén y al Veleta.</p>
      <div class="hero-actions">
        <a href="#reservar" class="btn btn-primary">Reservar estancia</a>
        <a href="#habitaciones" class="btn btn-ghost">Ver habitaciones</a>
      </div>
      <div class="hero-badges">
        <div class="b"><strong>6</strong><span>Habit. dobles</span></div>
        <div class="b"><strong>1.436 m</strong><span>Altitud</span></div>
        <div class="b"><strong>7:00</strong><span>Desayunos</span></div>
        <div class="b"><strong>★</strong><span>Trato familiar</span></div>
      </div>
    </div>
  </div>
  <div class="scroll-cue">Descubre</div>
</section>

<!-- ===== INTRO ===== -->
<section class="section intro" id="nosotros">
  <div class="wrap intro-grid">
    <div class="intro-media reveal">
      <img src="https://images.unsplash.com/photo-1518733057094-95b53143d2a7?auto=format&fit=crop&w=1000&q=80" alt="Calle típica de la Alpujarra" loading="lazy" />
      <div class="tag">
        <div class="ic">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 21s-7-5.2-7-11a7 7 0 0 1 14 0c0 5.8-7 11-7 11z"/><circle cx="12" cy="10" r="2.5"/></svg>
        </div>
        <div><b>C/ Barranco de Poqueira, 4</b><span>Capileira, Granada</span></div>
      </div>
    </div>
    <div class="intro-text reveal">
      <span class="eyebrow">Bienvenidos a Moraima</span>
      <h2>Un hogar en lo alto de la Alpujarra</h2>
      <p>A 1.436 metros de altitud, en uno de los pueblos más bellos de España, Hostal Moraima es punto de encuentro de senderistas, montañeros y viajeros que buscan autenticidad. Un edificio tradicional reformado con materials de la zona, calefacción en cada rincón y el aroma del guiso alpujarreño saliendo del restaurante.</p>
      <p>Más que alojamiento, ofrecemos una experiencia: madrugar con un café antes de subir al Mulhacén, descansar junto a la chimenea o compartir tapas con un vino de la Contraviesa al regreso de la ruta.</p>
      <div class="intro-features">
        <div class="feat">
          <div class="ic"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 21h18M5 21V8l7-5 7 5v13M9 21v-6h6v6"/></svg></div>
          <div><b>Edificio tradicional</b><span>Arquitectura alpujarreña</span></div>
        </div>
        <div class="feat">
          <div class="ic"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v6M12 16v6M2 12h6M16 12h6M5 5l4 4M15 15l4 4M19 5l-4 4M9 15l-4 4"/></svg></div>
          <div><b>Plena sierra</b><span>A pie de rutas y senderos</span></div>
        </div>
        <div class="feat">
          <div class="ic"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2a7 7 0 0 0-4 12.7V17h8v-2.3A7 7 0 0 0 12 2zM9 21h6M10 17v4M14 17v4"/></svg></div>
          <div><b>Cocina casera</b><span>Restaurante en el mismo edificio</span></div>
        </div>
        <div class="feat">
          <div class="ic"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20.8 4.6a5.5 5.5 0 0 0-7.8 0L12 5.6l-1-1a5.5 5.5 0 0 0-7.8 7.8l1 1L12 21l7.8-7.6 1-1a5.5 5.5 0 0 0 0-7.8z"/></svg></div>
          <div><b>Trato cercano</b><span>Gestión familiar</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== ROOMS ===== -->
<section class="section rooms" id="habitaciones">
  <div class="wrap">
    <div class="section-head center reveal">
      <span class="eyebrow center">Hospédate</span>
      <h2>Seis habitaciones dobles con encanto</h2>
      <p>Cada habitación está pensada para el descanso del montañero: baño privado, calefacción para las noches frías de sierra y televisión para los ratos de relax.</p>
    </div>
    <div class="rooms-grid">
      <article class="room-card reveal">
        <div class="ph" style="background-image:url('https://images.unsplash.com/photo-1611892440504-42a792e24d32?auto=format&fit=crop&w=800&q=80')">
          <span class="price">desde 50€/noche</span>
        </div>
        <div class="room-body">
          <h3>Habitación Doble</h3>
          <p class="desc">Cama de matrimonio, ventanas al barranco y la calma de la sierra para un sueño reparador.</p>
          <div class="room-amen">
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2 12h20M2 12v6h20M6 12V8a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v4"/></svg> Cama matrimonio</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 18v-6a4 4 0 0 1 4-4h10a4 4 0 0 1 4 4v6M3 18h18"/></svg> Baño privado</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v8M5 8a7 7 0 1 0 14 0"/></svg> Calefacción</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="M8 21h8"/></svg> TV</span>
          </div>
        </div>
      </article>
      <article class="room-card reveal">
        <div class="ph" style="background-image:url('https://images.unsplash.com/photo-1631049307264-da0ec9d70304?auto=format&fit=crop&w=800&q=80')">
          <span class="price">desde 55€/noche</span>
        </div>
        <div class="room-body">
          <h3>Doble con vistas</h3>
          <p class="desc">Con balcón o ventanal orientado al Barranco del Poqueira y a las cumbres nevadas.</p>
          <div class="room-amen">
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2 12h20M2 12v6h20M6 12V8a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v4"/></svg> 2 camas</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 18v-6a4 4 0 0 1 4-4h10a4 4 0 0 1 4 4v6"/></svg> Baño privado</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v8M5 8a7 7 0 1 0 14 0"/></svg> Calefacción</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="3"/><path d="M2 12s3-7 10-7 10 7 10 7-3 7-10 7-10-7-10-7z"/></svg> Vistas</span>
          </div>
        </div>
      </article>
      <article class="room-card reveal">
        <div class="ph" style="background-image:url('https://images.unsplash.com/photo-1566665797739-1674de7a421a?auto=format&fit=crop&w=800&q=80')">
          <span class="price">desde 60€/noche</span>
        </div>
        <div class="room-body">
          <h3>Doble Superior</h3>
          <p class="desc">Más espacio, zona de estar y detalles en madera y textil alpujarreño. Ideal para estancias largas.</p>
          <div class="room-amen">
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2 12h20M2 12v6h20M6 12V8a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v4"/></svg> Cama matrimonio</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 18v-6a4 4 0 0 1 4-4h10a4 4 0 0 1 4 4v6"/></svg> Baño privado</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v8M5 8a7 7 0 1 0 14 0"/></svg> Calefacción</span>
            <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 11l9-8 9 8M5 10v10h14V10"/></svg> Zona estar</span>
          </div>
        </div>
      </article>
    </div>
    <p style="text-align:center;margin-top:2.2rem;color:var(--muted);font-size:.92rem">Todas las habitaciones incluyen baño completo, toallas, ropa de cama, calefacción y TV. Consulta tarifas para estancias largas y grupos.</p>
  </div>
</section>

<!-- ===== RESTAURANT ===== -->
<section class="section rest" id="restaurante">
  <div class="rest-bg"></div>
  <div class="wrap">
    <div class="section-head center reveal">
      <span class="eyebrow center">La mesa de Moraima</span>
      <h2>Restaurante de cocina alpujarreña</h2>
      <p>En el mismo edificio. Desayunos para madrugar en ruta, platos de cuchara, tapas de la tierra y vinos de la Contraviesa para cerrar el día.</p>
    </div>
    <div class="menu-grid">
      <div class="menu-card reveal">
        <div class="ic"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 3v7a3 3 0 0 0 6 0V3M7 3v18M16 3c-1.5 0-3 1.5-3 4s1.5 4 3 4v10"/></svg></div>
        <h4>Desayunos</h4>
        <p>Repostería casera, tostada con aceite de la Alpujarra, café y zumo natural para emprender la ruta con energía.</p>
        <div class="time">DESDE LAS 7:00</div>
      </div>
      <div class="menu-card reveal">
        <div class="ic"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 2v8a3 3 0 0 0 6 0V2M9 13v9M16 2c-1 4-1 7 1 9v11"/></svg></div>
        <h4>Bocadillos para llevar</h4>
        <p>Preparamos tu comida de pista: pan de pueblo, jamón, queso y embutidos para el día de montaña.</p>
        <div class="time">PÍDELO LA NOCHE ANTERIOR</div>
      </div>
      <div class="menu-card reveal">
        <div class="ic"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 11h18M5 11a7 7 0 0 1 14 0M3 11v3a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-3M7 19a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2"/></svg></div>
        <h4>Tapas alpujarreñas</h4>
        <p>Plato alpujarreño, migas, choto al ajillo, embutidos de la sierra y guisos de cuchara caseros.</p>
        <div class="time">COCINA TRADICIONAL</div>
      </div>
      <div class="menu-card reveal">
        <div class="ic"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M8 2h8l-1 7a3 3 0 0 1-6 0L8 2zM9 9l-2 13h10L15 9M10 14h4"/></svg></div>
        <h4>Vinos de la Contraviesa</h4>
        <p>Tintos y blancos de las bodegas de la comarca, tierra de viticultura de altura con carácter único.</p>
        <div class="time">CARTA DE LA TIERRA</div>
      </div>
    </div>
  </div>
</section>

<!-- ===== NATURE ===== -->
<section class="section nature" id="entorno">
  <div class="wrap">
    <div class="section-head center reveal">
      <span class="eyebrow center">A pie de cumbre</span>
      <h2>La sierra como jardín</h2>
      <p>Desde la puerta del hostal parten algunas de las rutas más bellas del sur de Europa, entre pueblos blancos, barrancos y los techos de la península.</p>
    </div>
    <div class="nature-grid">
      <div class="nature-card reveal" style="background-image:url('https://images.unsplash.com/photo-1486870591958-9b9d0d1dda99?auto=format&fit=crop&w=900&q=80')">
        <span class="alt">3.479 m</span>
        <div class="nbody">
          <h3>Mulhacén</h3>
          <p>El techo de la península ibérica. Ascensión clásica desde Capileira para montañeros.</p>
        </div>
      </div>
      <div class="nature-card reveal" style="background-image:url('https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=900&q=80')">
        <span class="alt">3.396 m</span>
        <div class="nbody">
          <h3>Veleta</h3>
          <p>Cumbre accesible con vistas al Mediterráneo en los días despejados.</p>
        </div>
      </div>
      <div class="nature-card reveal" style="background-image:url('https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=900&q=80')">
        <span class="alt">Senderos</span>
        <div class="nbody">
          <h3>Rutas y barrancos</h3>
          <p>El Barranco del Poqueira, GR-7, pistas forestales y la red de senderos del Parque Natural.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== MAP ===== -->
<section class="section map" id="ubicacion">
  <div class="wrap map-grid">
    <div class="map-info reveal">
      <span class="eyebrow">Cómo llegar</span>
      <h2>En el centro de Capileira</h2>
      <p>A pie de calle, junto al Barranco del Poqueira. Capileira es uno de los tres pueblos del barranco y está declarado Conjunto Histórico.</p>
      <ul>
        <li>
          <div class="ic"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 21s-7-5.2-7-11a7 7 0 0 1 14 0c0 5.8-7 11-7 11z"/><circle cx="12" cy="10" r="2.5"/></svg></div>
          <div><b>C/ Barranco de Poqueira, 4</b><span>18413 Capileira (Granada)</span></div>
        </li>
        <li>
          <div class="ic"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 12-9 12s-9-5-9-12a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg></div>
          <div><b>A 1.436 m de altitud</b><span>Parque Natural de Sierra Nevada</span></div>
        </li>
        <li>
          <div class="ic"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="9"/><path d="M12 7v5l3 2"/></svg></div>
          <div><b>A 1h 30min de Granada</b><span>Por la A-44 y la carretera de la Alpujarra</span></div>
        </li>
      </ul>
      <a href="https://www.google.com/maps/dir/?api=1&destination=Calle+Barranco+de+Poqueira+4+18413+Capileira+Granada" target="_blank" rel="noopener" class="btn btn-dark">Cómo llegar en Google Maps →</a>
    </div>
    <div class="map-frame reveal">
      <iframe title="Mapa Hostal Moraima Capileira" src="https://www.google.com/maps?q=Hostal%20Moraima%2C%20Calle%20Barranco%20de%20Poqueira%204%2C%2018413%20Capileira%2C%20Granada&output=embed" loading="lazy" referrerpolicy="no-referrer-when-downgrade" allowfullscreen></iframe>
    </div>
  </div>
</section>

<!-- ===== BOOKING ===== -->
<section class="section book" id="reservar">
  <div class="wrap">
    <div class="section-head center reveal">
      <span class="eyebrow center">Reserva directa</span>
      <h2>Solicita tu reserva</h2>
      <p>Sin intermediarios: trámites directos con el hostal y mejor precio garantizado. Indica tus fechas y te responderemos por email.</p>
    </div>

    <div class="book-card reveal">
      <div class="book-hero">
        <div>
          <h3>Tu escapada a la sierra</h3>
          <p>Selecciona las fechas de tu estancia y calcula al instante el precio estimado. Confirmamos disponibilidad en menos de 24h.</p>
        </div>
        <div class="rate">
          <b>50€</b>
          <span>PRECIO ESTIMADO / NOCHE · HABITACIÓN DOBLE</span>
        </div>
      </div>

      <form class="book-form" id="bookingForm" novalidate>
        <div class="field">
          <label for="bk-name">Nombre y apellidos</label>
          <input type="text" id="bk-name" placeholder="Tu nombre completo" required />
        </div>
        <div class="field-row">
          <div class="field">
            <label for="bk-in">Entrada (check-in)</label>
            <input type="text" id="bk-in" placeholder="Selecciona fecha" readonly required />
          </div>
          <div class="field">
            <label for="bk-out">Salida (check-out)</label>
            <input type="text" id="bk-out" placeholder="Selecciona fecha" readonly required />
          </div>
        </div>
        <div class="field-row">
          <div class="field">
            <label for="bk-guests">Personas</label>
            <select id="bk-guests">
              <option value="1">1 persona</option>
              <option value="2" selected>2 personas</option>
              <option value="3">3 personas</option>
              <option value="4">4 personas</option>
              <option value="5">5 personas</option>
              <option value="6">6 personas</option>
              <option value="8">8 personas</option>
              <option value="10">10 personas</option>
              <option value="12">12 personas (grupo)</option>
            </select>
          </div>
          <div class="field">
            <label for="bk-room">Tipo de habitación</label>
            <select id="bk-room">
              <option value="Doble estándar">Doble estándar</option>
              <option value="Doble con vistas">Doble con vistas</option>
              <option value="Doble superior">Doble superior</option>
              <option value="Indiferente">Indiferente</option>
            </select>
          </div>
        </div>

        <div class="summary" id="summary">
          <div class="row"><span>Noches</span><strong id="s-nights">—</strong></div>
          <div class="row"><span>Habitaciones</span><strong id="s-rooms">—</strong></div>
          <div class="row"><span>Personas</span><strong id="s-guests">—</strong></div>
          <div class="total"><span>Precio estimado <small>(IVA incl.)</small></span><b id="s-total">— €</b></div>
        </div>

        <div class="field">
          <label for="bk-email">Tu email</label>
          <input type="email" id="bk-email" placeholder="tucorreo@email.com" required />
        </div>
        <div class="field">
          <label for="bk-note">Comentarios (opcional)</label>
          <input type="text" id="bk-note" placeholder="Hora de llegada, alergias, bocadillos para llevar…" />
        </div>

        <button type="submit" class="btn btn-primary btn-block">Enviar solicitud de reserva</button>
        <p class="form-note">Se abrirá tu correo con la solicitud lista para enviar a <strong>carmencapileira@hotmail.com</strong>. El precio es orientativo; la confirmación final la realiza el hostal.</p>
      </form>
    </div>
  </div>
</section>

<!-- ===== FOOTER ===== -->
<footer id="contacto">
  <div class="wrap">
    <div class="foot-grid">
      <div class="foot-about">
        <a href="#inicio" class="brand">
          <span class="name" style="font-family:'Playfair Display',serif;font-weight:700;font-size:1.5rem;display:block;margin-bottom:.2rem">Hostal Moraima</span>
          <span class="sub" style="font-size:.62rem;letter-spacing:.32em;text-transform:uppercase;font-weight:600">Capileira · Alpujarra</span>
        </a>
        <p>Hostal rural con restaurante en Capileira, a los pies del Mulhacén. Alojamiento acogedor, cocina alpujarreña y la montaña como patio.</p>
        <div class="soc">
          <a href="https://wa.me/34652619845" target="_blank" rel="noopener" aria-label="WhatsApp" title="WhatsApp">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0a12 12 0 0 0-10.3 18l-1.4 5 5.1-1.3A12 12 0 1 0 12 0zm0 2a10 10 0 0 1 8.3 15.5l.9 3.3-3.4-.9A10 10 0 1 1 12 2zm-4 5c-.3 0-.8.1-1.2.6-.4.5-1.6 1.6-1.6 3.8s1.6 4.4 1.9 4.7c.2.3 3.2 5 7.8 6.8 3.8 1.5 4.6 1.2 5.4 1.1.8-.1 2.5-1 2.8-2 .4-1 .4-1.9.3-2-.1-.2-.4-.3-.8-.5l-2.8-1.4c-.4-.2-.7-.2-1 .2l-1.3 1.7c-.3.3-.5.4-.9.2-.5-.2-2-.7-3.8-2.3-1.4-1.2-2.3-2.8-2.6-3.2-.3-.5 0-.7.2-1l.7-.8c.2-.3.3-.5.5-.8 0-.3 0-.6-.1-.8l-1.2-2.9c-.3-.8-.6-.7-.8-.7z"/></svg>
          </a>
          <a href="mailto:carmencapileira@hotmail.com" aria-label="Email" title="Email">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="m3 7 9 6 9-6"/></svg>
          </a>
          <a href="tel:+34958763180" aria-label="Teléfono" title="Teléfono">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.9v3a2 2 0 0 1-2.2 2 19.8 19.8 0 0 1-8.6-3 19.5 19.5 0 0 1-6-6 19.8 19.8 0 0 1-3-8.7A2 2 0 0 1 4.1 2h3a2 2 0 0 1 2 1.7c.1 1 .4 1.9.7 2.8a2 2 0 0 1-.5 2.1L8.1 9.9a16 16 0 0 0 6 6l1.3-1.3a2 2 0 0 1 2.1-.4c.9.3 1.8.6 2.8.7a2 2 0 0 1 1.7 2z"/></svg>
          </a>
        </div>
      </div>
      <div>
        <h5>Contacto</h5>
        <ul>
          <li><a href="tel:+34958763180"> ☎ 958 76 31 80</a></li>
          <li><a href="tel:+34652619845"> ☎ 652 61 98 45</a></li>
          <li><a href="mailto:carmencapileira@hotmail.com"> ✉ carmencapileira@hotmail.com</a></li>
        </ul>
      </div>
      <div>
        <h5>Visítanos</h5>
        <ul>
          <li>C/ Barranco de Poqueira, 4</li>
          <li>18413 Capileira (Granada)</li>
          <li>Andalucía · España</li>
          <li style="margin-top:.8rem"><a href="#reservar" style="color:var(--gold);font-weight:700">→ Solicitar reserva</a></li>
        </ul>
      </div>
    </div>
    <div class="foot-bottom">
      <span>© <span id="year"></span> Hostal Moraima · Capileira, Alpujarra Granadina</span>
      <span>Hecho con cariño desde la sierra</span>
    </div>
  </div>
</footer>

<!-- ===== WHATSAPP FLOAT ===== -->
<a class="wa" href="https://wa.me/34652619845" target="_blank" rel="noopener" aria-label="Escríbenos por WhatsApp">
  <svg viewBox="0 0 24 24"><path d="M12 0a12 12 0 0 0-10.3 18l-1.4 5 5.1-1.3A12 12 0 1 0 12 0zm0 2a10 10 0 0 1 8.3 15.5l.9 3.3-3.4-.9A10 10 0 1 1 12 2zm-4 5c-.3 0-.8.1-1.2.6-.4.5-1.6 1.6-1.6 3.8s1.6 4.4 1.9 4.7c.2.3 3.2 5 7.8 6.8 3.8 1.5 4.6 1.2 5.4 1.1.8-.1 2.5-1 2.8-2 .4-1 .4-1.9.3-2-.1-.2-.4-.3-.8-.5l-2.8-1.4c-.4-.2-.7-.2-1 .2l-1.3 1.7c-.3.3-.5.4-.9.2-.5-.2-2-.7-3.8-2.3-1.4-1.2-2.3-2.8-2.6-3.2-.3-.5 0-.7.2-1l.7-.8c.2-.3.3-.5.5-.8 0-.3 0-.6-.1-.8l-1.2-2.9c-.3-.8-.6-.7-.8-.7z"/></svg>
</a>

<script>
/* ===== AÑO ===== */
document.getElementById('year').textContent = new Date().getFullYear();

/* ===== NAV SCROLL ===== */
const nav = document.getElementById('nav');
window.addEventListener('scroll', () => {
  if(window.scrollY > 60) nav.classList.add('scrolled');
  else nav.classList.remove('scrolled');
});

/* ===== MOBILE MENU ===== */
const burger = document.getElementById('burger');
const mmenu = document.getElementById('mobileMenu');
burger.addEventListener('click', () => {
  burger.classList.toggle('open');
  mmenu.classList.toggle('open');
  document.body.style.overflow = mmenu.classList.contains('open') ? 'hidden' : '';
});
mmenu.querySelectorAll('a').forEach(a => a.addEventListener('click', () => {
  burger.classList.remove('open');
  mmenu.classList.remove('open');
  document.body.style.overflow = '';
}));

/* ===== REVEAL ON SCROLL ===== */
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); } });
}, { threshold: 0.12 });
document.querySelectorAll('.reveal').forEach(el => io.observe(el));

/* ===== FLATPICKR CALENDARIO ===== */
const PRECIO_POR_NOCHE = 50; // € por habitación doble y noche (precio estimado)

const inicio = flatpickr("#bk-in", {
  locale: "es",
  minDate: "today",
  dateFormat: "d/m/Y",
  disableMobile: true,
  onChange: function(selected){
    if(selected.length){
      const min = new Date(selected[0]);
      min.setDate(min.getDate()+1);
      checkout.set('minDate', min);
      recalcular();
    }
  }
});
const checkout = flatpickr("#bk-out", {
  locale: "es",
  minDate: new Date().fp_incr(1),
  dateFormat: "d/m/Y",
  disableMobile: true,
  onChange: recalcular
});

/* ===== CÁLCULO DE PRECIO ===== */
const sNights = document.getElementById('s-nights');
const sRooms  = document.getElementById('s-rooms');
const sGuests = document.getElementById('s-guests');
const sTotal  = document.getElementById('s-total');

function parseFp(str){
  // d/m/Y -> Date
  const p = str.split('/');
  return new Date(p[2], p[1]-1, p[0]);
}

function recalcular(){
  const inV  = document.getElementById('bk-in').value;
  const outV = document.getElementById('bk-out').value;
  const guests = parseInt(document.getElementById('bk-guests').value, 10) || 1;

  if(!inV || !outV){
    sNights.textContent = '—';
    sRooms.textContent  = '—';
    sGuests.textContent = guests;
    sTotal.textContent  = '— €';
    return;
  }
  const nights = Math.round((parseFp(outV) - parseFp(inV)) / 86400000);
  const rooms  = Math.ceil(guests / 2);
  const total  = Math.max(nights,0) * rooms * PRECIO_POR_NOCHE;

  sNights.textContent = nights > 0 ? nights : '—';
  sRooms.textContent  = rooms;
  sGuests.textContent = guests;
  sTotal.textContent  = nights > 0 ? total.toLocaleString('es-ES') + ' €' : '— €';
}
document.getElementById('bk-guests').addEventListener('change', recalcular);

/* ===== ENVÍO DE RESERVA POR MAILTO ===== */
document.getElementById('bookingForm').addEventListener('submit', function(e){
  e.preventDefault();
  recalcular();

  const nombre  = document.getElementById('bk-name').value.trim();
  const email   = document.getElementById('bk-email').value.trim();
  const inV     = document.getElementById('bk-in').value;
  const outV    = document.getElementById('bk-out').value;
  const guests  = document.getElementById('bk-guests').value;
  const room    = document.getElementById('bk-room').value;
  const note    = document.getElementById('bk-note').value.trim();

  if(!nombre){ alert('Por favor, indica tu nombre.'); return; }
  if(!email){ alert('Por favor, indica tu email de contacto.'); return; }
  if(!inV || !outV){ alert('Por favor, selecciona las fechas de entrada y salida.'); return; }

  const nights = Math.round((parseFp(outV) - parseFp(inV)) / 86400000);
  if(nights < 1){ alert('La fecha de salida debe ser posterior a la de entrada.'); return; }
  const rooms = Math.ceil(parseInt(guests,10)/2);
  const total = nights * rooms * PRECIO_POR_NOCHE;

  const subject = `Solicitud de reserva - Hostal Moraima (${inV} → ${outV})`;
  const body =
`Hola,

Me gustaría solicitar una reserva en el Hostal Moraima.

 · Nombre: ${nombre}
 · Email: ${email}
 · Entrada (check-in): ${inV}
 · Salida (check-out): ${outV}
 · Noches: ${nights}
 · Personas: ${guests}
 · Habitaciones estimadas: ${rooms}
 · Tipo de habitación: ${room}
 · Precio estimado: ${total.toLocaleString('es-ES')} € (orientativo)
${note ? ' · Comentarios: ' + note + '\n' : ''}
Quedo a la espera de su confirmación. Muchas gracias.

${nombre}`;

  const mailto = 'mailto:carmencapileira@hotmail.com'
    + '?subject=' + encodeURIComponent(subject)
    + '&body=' + encodeURIComponent(body);

  window.location.href = mailto;
});
</script>
</body>
</html>
