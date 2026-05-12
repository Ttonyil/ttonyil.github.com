

<html lang="it">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Room Center Sorrento Baby – B&B nel cuore di Sorrento</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --cream: #f5f0e8;
      --sand: #e8dfc8;
      --terracotta: #b5603a;
      --terracotta-light: #d07a52;
      --navy: #1a2a3a;
      --gold: #c9a96e;
      --gold-light: #e0c48a;
      --text: #2d2d2d;
      --text-light: #6b6b6b;
      --white: #ffffff;
    }
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { font-family: 'Jost', sans-serif; background: var(--cream); color: var(--text); overflow-x: hidden; }

    /* LANGUAGE SWITCHER */
    .lang-switcher {
      display: flex; gap: .4rem; align-items: center;
    }
    .lang-btn {
      background: transparent;
      border: 1px solid rgba(201,169,110,.35);
      color: var(--sand);
      font-family: 'Jost', sans-serif;
      font-size: .65rem;
      font-weight: 500;
      letter-spacing: .12em;
      text-transform: uppercase;
      padding: .28rem .6rem;
      border-radius: 2px;
      cursor: pointer;
      transition: background .2s, color .2s, border-color .2s;
    }
    .lang-btn:hover,
    .lang-btn.active { background: var(--gold); color: var(--navy); border-color: var(--gold); }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%; height: 70px;
      background: rgba(26,42,58,0.95); backdrop-filter: blur(8px);
      transition: background .3s;
    }
    nav.scrolled { background: var(--navy); box-shadow: 0 2px 20px rgba(0,0,0,.3); }
    .logo { font-family: 'Cormorant Garamond', serif; font-size: 1.35rem; font-weight: 600; letter-spacing: .05em; color: var(--gold); text-decoration: none; line-height: 1.2; }
    .logo span { display: block; font-size: .75rem; font-weight: 300; color: var(--sand); letter-spacing: .2em; text-transform: uppercase; }
    .nav-right { display: flex; align-items: center; gap: 2rem; }
    .nav-links { display: flex; gap: 1.2rem; list-style: none; align-items: center; }
    .nav-links a { font-size: .68rem; font-weight: 500; letter-spacing: .12em; text-transform: uppercase; color: var(--sand); text-decoration: none; transition: color .2s; }
    .nav-links a:hover { color: var(--gold); }
    .nav-links .book-btn { background: var(--terracotta); color: var(--white); padding: .5rem 1.2rem; border-radius: 2px; transition: background .2s; }
    .nav-links .book-btn:hover { background: var(--terracotta-light); color: var(--white); }
    .hamburger { display: none; cursor: pointer; flex-direction: column; gap: 5px; }
    .hamburger span { display: block; width: 24px; height: 2px; background: var(--gold); transition: .3s; }
    .mobile-menu { display: none; position: fixed; inset: 0; background: var(--navy); z-index: 99; flex-direction: column; align-items: center; justify-content: center; gap: 2.5rem; }
    .mobile-menu.open { display: flex; }
    .mobile-menu a { font-size: 1.2rem; font-weight: 500; letter-spacing: .1em; text-transform: uppercase; color: var(--sand); text-decoration: none; transition: color .2s; }
    .mobile-menu a:hover { color: var(--gold); }
    .mobile-menu .book-btn { background: var(--terracotta); color: var(--white) !important; padding: .8rem 2rem; border-radius: 2px; }
    .close-menu { position: absolute; top: 1.5rem; right: 2rem; cursor: pointer; color: var(--gold); font-size: 2rem; }
    .mobile-lang { display: flex; gap: .6rem; margin-top: 1rem; }

    /* HERO */
    #hero { position: relative; height: 100vh; min-height: 600px; display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; overflow: hidden; }
    .hero-bg {
      position: absolute; inset: 0;
      background: linear-gradient(to bottom, rgba(26,42,58,.55) 0%, rgba(26,42,58,.3) 50%, rgba(26,42,58,.7) 100%),
        url('https://images.unsplash.com/photo-1533104816931-20fa691ff6ca?w=1600&q=80') center/cover no-repeat;
      transform: scale(1.05);
      animation: heroZoom 14s ease-in-out infinite alternate;
    }
    @keyframes heroZoom { from { transform: scale(1.05); } to { transform: scale(1.12); } }
    .hero-content { position: relative; z-index: 1; padding: 0 1.5rem; }
    .hero-badge {
      display: inline-block; font-size: .65rem; font-weight: 500; letter-spacing: .3em; text-transform: uppercase;
      color: var(--gold); border: 1px solid var(--gold); padding: .4rem 1.2rem; margin-bottom: 1.5rem;
      animation: fadeUp .8s ease both;
      position: relative; overflow: hidden;
    }
    .hero-badge::after {
      content: ''; position: absolute; inset: 0;
      background: linear-gradient(90deg, transparent, rgba(201,169,110,.18), transparent);
      animation: shimmer 2.8s infinite;
    }
    @keyframes shimmer { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }
    .hero-title { font-family: 'Cormorant Garamond', serif; font-size: clamp(2.8rem, 7vw, 5.5rem); font-weight: 300; line-height: 1.05; color: var(--white); letter-spacing: .02em; margin-bottom: 1rem; animation: fadeUp .8s .15s ease both; }
    .hero-title em { font-style: italic; color: var(--gold-light); }
    .hero-sub { font-size: 1rem; font-weight: 300; letter-spacing: .15em; text-transform: uppercase; color: var(--sand); margin-bottom: 2.5rem; animation: fadeUp .8s .3s ease both; }
    .hero-btn { display: inline-block; background: var(--terracotta); color: var(--white); font-size: .8rem; font-weight: 500; letter-spacing: .2em; text-transform: uppercase; padding: 1rem 2.5rem; text-decoration: none; border-radius: 2px; transition: background .2s, transform .2s, box-shadow .2s; animation: fadeUp .8s .45s ease both; }
    .hero-btn:hover { background: var(--terracotta-light); transform: translateY(-3px); box-shadow: 0 12px 30px rgba(181,96,58,.4); }
    .scroll-hint { position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: .5rem; z-index: 1; animation: fadeUp .8s .7s ease both; }
    .scroll-hint span { font-size: .65rem; letter-spacing: .2em; text-transform: uppercase; color: var(--sand); }
    .scroll-line { width: 1px; height: 40px; background: linear-gradient(to bottom, var(--gold), transparent); animation: scrollPulse 2s infinite; }

    /* ABOUT */
    #about { padding: 7rem 5%; background: var(--white); position: relative; overflow: hidden; }
    #about::before { content: ''; position: absolute; top: -4rem; right: -4rem; width: 22rem; height: 22rem; border-radius: 50%; background: radial-gradient(circle, rgba(201,169,110,.08) 0%, transparent 70%); pointer-events: none; }
    .about-inner { max-width: 1100px; margin: auto; display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
    .about-img-wrap { position: relative; }
    .about-img-wrap img { width: 100%; aspect-ratio: 4/5; object-fit: cover; border-radius: 2px; transition: transform .6s ease; }
    .about-img-wrap:hover img { transform: scale(1.02); }
    .about-img-accent { position: absolute; bottom: -1.5rem; right: -1.5rem; width: 60%; aspect-ratio: 1; background: var(--sand); z-index: -1; border-radius: 2px; }
    .section-label { font-size: .65rem; font-weight: 500; letter-spacing: .3em; text-transform: uppercase; color: var(--terracotta); margin-bottom: 1rem; }
    .section-title { font-family: 'Cormorant Garamond', serif; font-size: clamp(2rem, 4vw, 3rem); font-weight: 300; line-height: 1.2; margin-bottom: 1.5rem; }
    .about-text { font-size: .95rem; font-weight: 300; line-height: 1.9; color: var(--text-light); margin-bottom: 1.2rem; }
    .info-list { list-style: none; margin-top: 1.5rem; display: flex; flex-direction: column; gap: .7rem; }
    .info-list li { font-size: .85rem; color: var(--text-light); display: flex; align-items: center; gap: .75rem; }
    .info-list li::before { content: '—'; color: var(--gold); font-weight: 300; }

    /* ROOMS — ora prima dei servizi */
    #rooms { padding: 7rem 5%; background: var(--cream); position: relative; overflow: hidden; }
    #rooms::before {
      content: 'CAMERE';
      position: absolute; top: 50%; left: -2rem;
      transform: translateY(-50%) rotate(-90deg);
      font-family: 'Cormorant Garamond', serif;
      font-size: 8rem; font-weight: 300;
      color: rgba(181,96,58,.05);
      white-space: nowrap;
      pointer-events: none;
      letter-spacing: .3em;
    }
    #rooms .section-label,
    #rooms .section-title { text-align: center; margin: 0 auto 1rem; display: block; }
    #rooms .section-title { margin-bottom: .5rem; }
    .rooms-subtitle { text-align: center; font-size: .9rem; font-weight: 300; color: var(--text-light); margin-bottom: 4rem; }
    .rooms-grid { max-width: 1200px; margin: auto; display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 2rem; }
    .room-card {
      background: var(--white); border-radius: 2px; overflow: hidden;
      box-shadow: 0 4px 30px rgba(0,0,0,.07);
      transition: box-shadow .4s, transform .4s;
      position: relative;
    }
    .room-card::after {
      content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--terracotta), var(--gold));
      transform: scaleX(0); transform-origin: left;
      transition: transform .4s ease;
    }
    .room-card:hover { box-shadow: 0 16px 56px rgba(0,0,0,.14); transform: translateY(-6px); }
    .room-card:hover::after { transform: scaleX(1); }
    .room-img-wrap { overflow: hidden; }
    .room-img { width: 100%; aspect-ratio: 4/3; object-fit: cover; display: block; transition: transform .6s ease; }
    .room-card:hover .room-img { transform: scale(1.06); }
    .room-body { padding: 1.5rem; }
    .room-tag { font-size: .65rem; font-weight: 600; letter-spacing: .25em; text-transform: uppercase; color: var(--terracotta); margin-bottom: .5rem; }
    .room-name { font-family: 'Cormorant Garamond', serif; font-size: 1.6rem; font-weight: 300; margin-bottom: .75rem; }
    .room-desc { font-size: .85rem; font-weight: 300; color: var(--text-light); line-height: 1.7; margin-bottom: 1.2rem; }
    .room-amenities { display: flex; flex-wrap: wrap; gap: .4rem; margin-bottom: 1.5rem; }
    .amenity-tag { font-size: .7rem; background: var(--sand); color: var(--text); padding: .25rem .7rem; border-radius: 20px; transition: background .2s; }
    .room-card:hover .amenity-tag { background: #dfd3b6; }
    .room-cta { display: inline-block; font-size: .75rem; font-weight: 500; letter-spacing: .15em; text-transform: uppercase; color: var(--terracotta); text-decoration: none; border-bottom: 1px solid var(--terracotta); padding-bottom: 2px; transition: color .2s, border-color .2s, letter-spacing .2s; }
    .room-cta:hover { color: var(--terracotta-light); border-color: var(--terracotta-light); letter-spacing: .22em; }

    /* SERVICES — ora dopo le camere */
    #services { padding: 7rem 5%; background: var(--navy); position: relative; overflow: hidden; }
    #services::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; bottom: 0;
      background: radial-gradient(ellipse at 70% 40%, rgba(201,169,110,.07) 0%, transparent 60%),
                  radial-gradient(ellipse at 20% 80%, rgba(181,96,58,.05) 0%, transparent 50%);
      pointer-events: none;
    }
    #services .section-label { color: var(--gold); display: block; text-align: center; }
    #services .section-title { color: var(--white); text-align: center; }
    .services-subtitle { text-align: center; font-size: .9rem; font-style: italic; color: var(--sand); margin-bottom: 4rem; font-family: 'Cormorant Garamond', serif; }
    .services-grid { max-width: 1000px; margin: auto; display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 2rem; }
    .service-card {
      display: flex; flex-direction: column; align-items: center; gap: 1rem;
      padding: 2rem 1.5rem; text-align: center;
      border: 1px solid rgba(201,169,110,.2); border-radius: 2px;
      transition: border-color .3s, transform .3s, background .3s, box-shadow .3s;
      cursor: default; position: relative; overflow: hidden;
    }
    .service-card::before {
      content: ''; position: absolute; inset: 0;
      background: linear-gradient(135deg, rgba(201,169,110,.05) 0%, transparent 60%);
      opacity: 0; transition: opacity .3s;
    }
    .service-card:hover { border-color: var(--gold); transform: translateY(-6px); background: rgba(201,169,110,.07); box-shadow: 0 12px 30px rgba(0,0,0,.3); }
    .service-card:hover::before { opacity: 1; }
    .service-icon { font-size: 2.2rem; transition: transform .3s; }
    .service-card:hover .service-icon { transform: scale(1.18) rotate(-6deg); }
    .service-card h3 { font-size: .85rem; font-weight: 500; letter-spacing: .1em; text-transform: uppercase; color: var(--sand); }

    /* CONTACT */
    #contact { padding: 7rem 5%; background: var(--white); }
    .contact-inner { max-width: 1100px; margin: auto; display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
    .contact-info h2 { margin-bottom: 2rem; }
    .contact-detail { display: flex; align-items: flex-start; gap: 1rem; margin-bottom: 1.5rem; transition: transform .2s; }
    .contact-detail:hover { transform: translateX(4px); }
    .contact-detail .icon { font-size: 1.3rem; margin-top: .1rem; }
    .contact-detail p { font-size: .9rem; font-weight: 300; line-height: 1.6; color: var(--text-light); }
    .contact-detail a { color: var(--terracotta); text-decoration: none; }
    .contact-detail a:hover { text-decoration: underline; }
    .or-divider { display: flex; align-items: center; gap: 1rem; margin: 2rem 0; color: var(--text-light); font-size: .8rem; letter-spacing: .1em; text-transform: uppercase; }
    .or-divider::before, .or-divider::after { content: ''; flex: 1; height: 1px; background: var(--sand); }
    .book-big-btn { display: block; text-align: center; background: var(--terracotta); color: var(--white); font-size: .8rem; font-weight: 500; letter-spacing: .2em; text-transform: uppercase; padding: 1rem; border-radius: 2px; text-decoration: none; transition: background .2s, transform .2s, box-shadow .2s; }
    .book-big-btn:hover { background: var(--terracotta-light); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(181,96,58,.35); }
    .contact-form { display: flex; flex-direction: column; gap: 1rem; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .form-group { display: flex; flex-direction: column; gap: .4rem; }
    .form-group label { font-size: .7rem; font-weight: 500; letter-spacing: .15em; text-transform: uppercase; color: var(--text-light); }
    .form-group input, .form-group textarea {
      border: 1px solid var(--sand); background: var(--cream); border-radius: 2px;
      padding: .8rem 1rem; font-family: 'Jost', sans-serif; font-size: .9rem; color: var(--text);
      outline: none; transition: border-color .2s, box-shadow .2s;
    }
    .form-group input:focus, .form-group textarea:focus { border-color: var(--gold); box-shadow: 0 0 0 3px rgba(201,169,110,.12); }
    .form-group textarea { min-height: 120px; resize: vertical; }
    .submit-btn { background: var(--navy); color: var(--white); border: none; cursor: pointer; padding: 1rem; font-family: 'Jost', sans-serif; font-size: .8rem; font-weight: 500; letter-spacing: .2em; text-transform: uppercase; border-radius: 2px; transition: background .2s, transform .2s; }
    .submit-btn:hover { background: #2a3f55; transform: translateY(-2px); }
    .form-msg { display: none; padding: .8rem 1rem; border-radius: 2px; font-size: .85rem; margin-top: .5rem; }
    .form-msg.success { background: #d4edda; color: #155724; display: block; }
    .form-msg.error { background: #f8d7da; color: #721c24; display: block; }

    /* MAP */
    #map-section { background: var(--sand); padding: 5rem 5% 0; }
    #map-section .section-label { text-align: center; margin-bottom: .5rem; }
    #map-section .section-title { text-align: center; margin-bottom: 3rem; }
    .map-frame { max-width: 1200px; margin: auto; }
    .map-frame iframe { width: 100%; height: 400px; border: none; display: block; }

    /* FOOTER */
    footer { background: var(--navy); padding: 4rem 5% 2rem; }
    .footer-inner { max-width: 1100px; margin: auto; display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 3rem; margin-bottom: 3rem; }
    .footer-brand .logo { font-size: 1.2rem; }
    .footer-brand p { font-size: .85rem; font-weight: 300; color: rgba(232,223,200,.6); line-height: 1.7; margin-top: 1rem; }
    .footer-col h4 { font-size: .7rem; font-weight: 500; letter-spacing: .2em; text-transform: uppercase; color: var(--gold); margin-bottom: 1rem; }
    .footer-col a, .footer-col p { display: block; font-size: .85rem; font-weight: 300; color: rgba(232,223,200,.7); text-decoration: none; margin-bottom: .5rem; transition: color .2s; }
    .footer-col a:hover { color: var(--gold); }
    .footer-bottom { border-top: 1px solid rgba(201,169,110,.2); padding-top: 1.5rem; text-align: center; font-size: .75rem; color: rgba(232,223,200,.4); }

    /* FLOAT */
    .float-book {
      position: fixed; bottom: 2rem; right: 2rem; z-index: 90;
      background: var(--terracotta); color: var(--white);
      font-size: .75rem; font-weight: 500; letter-spacing: .15em; text-transform: uppercase;
      padding: .9rem 1.5rem; border-radius: 2px; text-decoration: none;
      box-shadow: 0 4px 20px rgba(181,96,58,.4);
      transition: background .2s, transform .2s, box-shadow .2s;
    }
    .float-book:hover { background: var(--terracotta-light); transform: translateY(-3px); box-shadow: 0 10px 30px rgba(181,96,58,.5); }

    /* ANIMATIONS */
    @keyframes fadeUp { from { opacity:0; transform: translateY(24px); } to { opacity:1; transform: translateY(0); } }
    @keyframes scrollPulse { 0%,100% { opacity:.3; } 50% { opacity:1; } }
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity .7s ease, transform .7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    .reveal-left { opacity: 0; transform: translateX(-30px); transition: opacity .7s ease, transform .7s ease; }
    .reveal-left.visible { opacity: 1; transform: translateX(0); }
    .reveal-right { opacity: 0; transform: translateX(30px); transition: opacity .7s ease, transform .7s ease; }
    .reveal-right.visible { opacity: 1; transform: translateX(0); }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      .about-inner, .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
      .footer-inner { grid-template-columns: 1fr 1fr; }
      .about-img-accent { display: none; }
      .nav-right { gap: 1rem; }
    }
    @media (max-width: 640px) {
      .nav-links { display: none; }
      .hamburger { display: flex; }
      .footer-inner { grid-template-columns: 1fr; }
      .form-row { grid-template-columns: 1fr; }
      .lang-switcher { display: none; }
    }

    /* ===== MOBILE ENHANCEMENTS ===== */

    /* Prevent horizontal overflow on all screens */
    html, body { max-width: 100%; overflow-x: hidden; }

    /* Better touch targets */
    a, button { -webkit-tap-highlight-color: transparent; touch-action: manipulation; }
    .nav-links a, .mobile-menu a { min-height: 44px; display: inline-flex; align-items: center; }
    .lang-btn { min-height: 36px; min-width: 36px; }

    @media (max-width: 768px) {
      /* NAV */
      nav { padding: 0 4%; height: 60px; }
      .logo { font-size: 1.15rem; }
      .logo span { font-size: .65rem; }
      .hamburger { display: flex; }
      .nav-links { display: none; }
      .lang-switcher { display: none; }

      /* HERO */
      #hero { min-height: 100svh; }
      .hero-content { padding: 0 1.2rem; }
      .hero-badge { font-size: .6rem; padding: .35rem 1rem; margin-bottom: 1.2rem; }
      .hero-title { font-size: clamp(2.2rem, 10vw, 3.5rem); margin-bottom: .8rem; }
      .hero-sub { font-size: .85rem; letter-spacing: .1em; margin-bottom: 2rem; }
      .hero-btn { padding: .9rem 2rem; font-size: .75rem; }
      .scroll-hint { bottom: 1.5rem; }

      /* ABOUT */
      #about { padding: 5rem 5%; }
      .about-inner { gap: 2.5rem; }
      .about-img-wrap img { aspect-ratio: 3/2; }
      .section-title { font-size: clamp(1.7rem, 5vw, 2.5rem); }

      /* ROOMS */
      #rooms { padding: 5rem 4%; overflow: hidden; }
      #rooms::before { display: none; } /* hide decorative watermark - causes overflow */
      .rooms-grid { grid-template-columns: 1fr; gap: 1.5rem; }
      .room-body { padding: 1.2rem; }
      .room-name { font-size: 1.4rem; }
      .rooms-subtitle { margin-bottom: 2.5rem; font-size: .85rem; }

      /* SERVICES */
      #services { padding: 5rem 4%; }
      .services-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;
        max-width: 100%;
      }
      .service-card { padding: 1.5rem 1rem; gap: .75rem; }
      .service-icon { font-size: 1.8rem; }
      .service-card h3 { font-size: .8rem; }
      .services-subtitle { margin-bottom: 2.5rem; }

      /* CONTACT */
      #contact { padding: 5rem 4%; }
      .contact-inner { gap: 2.5rem; }
      .contact-detail { gap: .75rem; }
      .contact-detail p { font-size: .88rem; }
      .book-big-btn { padding: 1rem; font-size: .75rem; }
      .form-group input, .form-group textarea { padding: .9rem; font-size: 1rem; } /* prevent zoom on iOS */
      .submit-btn { padding: 1rem; font-size: .8rem; }

      /* MAP */
      #map-section { padding: 4rem 4% 0; }
      .map-frame iframe { height: 280px; }

      /* FOOTER */
      footer { padding: 3rem 4% 2rem; }
      .footer-inner { gap: 2rem; }
      .footer-brand p { font-size: .8rem; }
      .footer-bottom { font-size: .7rem; line-height: 1.6; }

      /* FLOAT BUTTON — reposition to avoid covering content */
      .float-book {
        bottom: 1rem; right: 1rem;
        padding: .8rem 1.2rem;
        font-size: .7rem;
      }

      /* MOBILE MENU improvements */
      .mobile-menu a { font-size: 1.1rem; }
      .mobile-menu { gap: 2rem; }
      .close-menu { top: 1rem; right: 1.5rem; font-size: 1.8rem; min-height: 44px; min-width: 44px; display: flex; align-items: center; justify-content: flex-end; }
      .mobile-lang { gap: .5rem; }
      .mobile-lang .lang-btn { padding: .4rem .8rem; font-size: .7rem; }
    }

    @media (max-width: 400px) {
      /* Very small screens */
      .hero-title { font-size: 2rem; }
      .hero-btn { padding: .8rem 1.6rem; width: 100%; max-width: 260px; display: block; margin: 0 auto; }
      .services-grid { grid-template-columns: repeat(2, 1fr); gap: .75rem; }
      .service-card { padding: 1.2rem .75rem; }
      .room-amenities { gap: .3rem; }
      .amenity-tag { font-size: .65rem; padding: .2rem .5rem; }
      .about-inner { gap: 2rem; }
      nav { padding: 0 3%; }
    }

    /* iOS safe area insets (notch / home indicator) */
    @supports (padding: max(0px)) {
      nav { padding-left: max(4%, env(safe-area-inset-left)); padding-right: max(4%, env(safe-area-inset-right)); }
      footer { padding-bottom: max(2rem, calc(1rem + env(safe-area-inset-bottom))); }
      .float-book { bottom: max(1rem, calc(.5rem + env(safe-area-inset-bottom))); right: max(1rem, env(safe-area-inset-right)); }
    }
  </style>
</head>
<body>

<!-- MOBILE MENU -->
<div class="mobile-menu" id="mobileMenu">
  <span class="close-menu" id="closeMenu">✕</span>
  <a href="#about">Chi Siamo</a>
  <a href="https://www.sorrentoroom.com/attrazioni/" target="_blank">Attrazioni</a>
  <a href="#rooms">Camere</a>
  <a href="#services">Servizi</a>
  <a href="https://www.sorrentoroom.com/dove-siamo/" target="_blank">Dove Siamo</a>
  <a href="https://www.sorrentoroom.com/recensioni/" target="_blank">Recensioni</a>
  <a href="https://www.sorrentoroom.com/privacy-policy/" target="_blank">Privacy Policy</a>
  <a href="https://babyroom.kross.travel/" class="book-btn" target="_blank">Book Now</a>
  <div class="mobile-lang">
    <button class="lang-btn active" onclick="setLang('it')">IT</button>
    <button class="lang-btn" onclick="setLang('en')">EN</button>
    <button class="lang-btn" onclick="setLang('de')">DE</button>
    <button class="lang-btn" onclick="setLang('fr')">FR</button>
  </div>
</div>

<!-- NAV -->
<nav id="navbar">
  <a href="#" class="logo">Room Center Sorrento<span>Baby — B&amp;B</span></a>
  <div class="nav-right">
    <ul class="nav-links">
      <li><a href="#about">Chi Siamo</a></li>
      <li><a href="https://www.sorrentoroom.com/attrazioni/" target="_blank">Attrazioni</a></li>
      <li><a href="#rooms">Camere</a></li>
      <li><a href="#services">Servizi</a></li>
      <li><a href="https://www.sorrentoroom.com/dove-siamo/" target="_blank">Dove Siamo</a></li>
      <li><a href="https://www.sorrentoroom.com/recensioni/" target="_blank">Recensioni</a></li>
      <li><a href="https://www.sorrentoroom.com/privacy-policy/" target="_blank">Privacy Policy</a></li>
      <li><a href="https://babyroom.kross.travel/" class="book-btn" target="_blank">Book Now</a></li>
    </ul>
    <div class="lang-switcher" id="langSwitcher">
      <button class="lang-btn active" onclick="setLang('it')">IT</button>
      <button class="lang-btn" onclick="setLang('en')">EN</button>
      <button class="lang-btn" onclick="setLang('de')">DE</button>
      <button class="lang-btn" onclick="setLang('fr')">FR</button>
    </div>
  </div>
  <div class="hamburger" id="hamburger"><span></span><span></span><span></span></div>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div class="hero-badge">✦ Sorrento, Campania ✦</div>
    <h1 class="hero-title">Room Center<br><em>Sorrento Baby</em></h1>
    <p class="hero-sub" data-i18n="hero.sub">Il tuo B&amp;B nel cuore di Sorrento</p>
    <a href="https://babyroom.kross.travel/" class="hero-btn" target="_blank" data-i18n="hero.btn">Prenota una Camera</a>
  </div>
  <div class="scroll-hint">
    <span data-i18n="hero.scroll">Scopri</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-inner">
    <div class="about-img-wrap reveal-left">
      <img src="https://www.sorrentoroom.com/wp-content/uploads/2025/05/530838972.jpg" alt="Room Center Sorrento Baby" loading="lazy"/>
      <div class="about-img-accent"></div>
    </div>
    <div class="reveal-right">
      <p class="section-label" data-i18n="about.label">La Nostra Storia</p>
      <h2 class="section-title" data-i18n="about.title">Una luxury guest house nel cuore di Sorrento</h2>
      <p class="about-text" data-i18n="about.p1">Sorrento Baby B&amp;B è una luxury guest house situata nel centro di Sorrento, a pochi passi dal mare e dalle maggiori attrazioni storico-artistiche. Un moderno ed elegante affittacamere in un edificio signorile con ascensore, situato a due passi dalla stazione e dai maggiori punti di interesse della città.</p>
      <p class="about-text" data-i18n="about.p2">La struttura dispone di quattro camere da letto, ognuna con bagno privato. Ogni camera è arredata in stile moderno e confortevole, luminosa grazie al balcone dove è possibile sorseggiare un aperitivo con vista sul cortile. Tutte le camere godono di aria condizionata indipendente, TV a schermo piatto, bollitore, mini frigo, macchina del caffè, cassaforte, asse e ferro da stiro.</p>
      <ul class="info-list">
        <li data-i18n="about.checkin">Check-in: dalle ore 14:00 alle 22:00</li>
        <li data-i18n="about.checkout">Check-out: entro le ore 10:30</li>
        <li data-i18n="about.luggage">Deposito bagagli gratuito su richiesta</li>
        <li data-i18n="about.concierge">Servizio concierge e assistenza H24</li>
        <li data-i18n="about.id">Documento di identità richiesto all'arrivo</li>
      </ul>
    </div>
  </div>
</section>

<!-- ROOMS — sezione camere ora PRIMA dei servizi -->
<section id="rooms">
  <p class="section-label reveal" data-i18n="rooms.label">Le Nostre Camere</p>
  <h2 class="section-title reveal" data-i18n="rooms.title">Dove il Comfort Incontra l'Eleganza</h2>
  <p class="rooms-subtitle reveal" data-i18n="rooms.sub">Prezzo speciale · Bagno privato incluso · WiFi gratis</p>
  <div class="rooms-grid">

    <article class="room-card reveal">
      <div class="room-img-wrap">
        <img class="room-img" src="https://www.sorrentoroom.com/wp-content/uploads/2025/06/WhatsApp-Image-2025-06-12-at-10.01.06-1024x768.jpeg" alt="Camera Sophia Loren" loading="lazy"/>
      </div>
      <div class="room-body">
        <p class="room-tag" data-i18n="rooms.r1.tag">Camera Matrimoniale · 2 persone</p>
        <h3 class="room-name">Sophia Loren</h3>
        <p class="room-desc" data-i18n="rooms.r1.desc">Superficie 20 mq — 1 letto matrimoniale — Balcone con vista giardino.</p>
        <div class="room-amenities">
          <span class="amenity-tag" data-i18n="am.ac">Aria condizionata</span>
          <span class="amenity-tag" data-i18n="am.bath">Bagno privato</span>
          <span class="amenity-tag" data-i18n="am.tv">TV schermo piatto</span>
          <span class="amenity-tag" data-i18n="am.minibar">Minibar</span>
          <span class="amenity-tag" data-i18n="am.wifi">WiFi gratis</span>
          <span class="amenity-tag" data-i18n="am.balcony">Balcone</span>
        </div>
        <a href="https://babyroom.kross.travel/" class="room-cta" target="_blank" data-i18n="rooms.cta">Dettagli e Prenotazione →</a>
      </div>
    </article>

    <article class="room-card reveal">
      <div class="room-img-wrap">
        <img class="room-img" src="https://www.sorrentoroom.com/wp-content/uploads/2025/06/WhatsApp-Image-2025-06-12-at-10.02.17-1024x768.jpeg" alt="Camera Torquato Tasso" loading="lazy"/>
      </div>
      <div class="room-body">
        <p class="room-tag" data-i18n="rooms.r2.tag">Camera Tripla · 3 persone</p>
        <h3 class="room-name">Torquato Tasso</h3>
        <p class="room-desc" data-i18n="rooms.r2.desc">Superficie 20 mq — 1 letto matrimoniale + 1 divano letto — Vista cortile interno.</p>
        <div class="room-amenities">
          <span class="amenity-tag" data-i18n="am.ac">Aria condizionata</span>
          <span class="amenity-tag" data-i18n="am.bath">Bagno privato</span>
          <span class="amenity-tag" data-i18n="am.tv">TV schermo piatto</span>
          <span class="amenity-tag" data-i18n="am.minibar">Minibar</span>
          <span class="amenity-tag" data-i18n="am.wifi">WiFi gratis</span>
          <span class="amenity-tag" data-i18n="am.sofa">Divano letto</span>
        </div>
        <a href="https://babyroom.kross.travel/" class="room-cta" target="_blank" data-i18n="rooms.cta">Dettagli e Prenotazione →</a>
      </div>
    </article>

    <article class="room-card reveal">
      <div class="room-img-wrap">
        <img class="room-img" src="https://www.sorrentoroom.com/wp-content/uploads/2025/06/WhatsApp-Image-2025-06-12-at-10.00.44-1-1024x768.jpeg" alt="Camera Ulysse" loading="lazy"/>
      </div>
      <div class="room-body">
        <p class="room-tag" data-i18n="rooms.r3.tag">Camera Matrimoniale · 2 persone</p>
        <h3 class="room-name">Ulysse</h3>
        <p class="room-desc" data-i18n="rooms.r3.desc">Superficie 20 mq — 1 letto matrimoniale — Balcone con vista giardino.</p>
        <div class="room-amenities">
          <span class="amenity-tag" data-i18n="am.ac">Aria condizionata</span>
          <span class="amenity-tag" data-i18n="am.bath">Bagno privato</span>
          <span class="amenity-tag" data-i18n="am.tv">TV schermo piatto</span>
          <span class="amenity-tag" data-i18n="am.minibar">Minibar</span>
          <span class="amenity-tag" data-i18n="am.wifi">WiFi gratis</span>
          <span class="amenity-tag" data-i18n="am.balcony">Balcone</span>
        </div>
        <a href="https://babyroom.kross.travel/" class="room-cta" target="_blank" data-i18n="rooms.cta">Dettagli e Prenotazione →</a>
      </div>
    </article>

    <article class="room-card reveal">
      <div class="room-img-wrap">
        <img class="room-img" src="https://www.sorrentoroom.com/wp-content/uploads/2025/06/WhatsApp-Image-2025-06-12-at-10.00.00-1-1024x768.jpeg" alt="Camera Lucio Dalla" loading="lazy"/>
      </div>
      <div class="room-body">
        <p class="room-tag" data-i18n="rooms.r4.tag">Camera Tripla · 3 persone</p>
        <h3 class="room-name">Lucio Dalla</h3>
        <p class="room-desc" data-i18n="rooms.r4.desc">Superficie 20 mq — 1 letto matrimoniale + 1 divano letto — Vista cortile interno.</p>
        <div class="room-amenities">
          <span class="amenity-tag" data-i18n="am.ac">Aria condizionata</span>
          <span class="amenity-tag" data-i18n="am.bath">Bagno privato</span>
          <span class="amenity-tag" data-i18n="am.tv">TV schermo piatto</span>
          <span class="amenity-tag" data-i18n="am.minibar">Minibar</span>
          <span class="amenity-tag" data-i18n="am.wifi">WiFi gratis</span>
          <span class="amenity-tag" data-i18n="am.sofa">Divano letto</span>
        </div>
        <a href="https://babyroom.kross.travel/" class="room-cta" target="_blank" data-i18n="rooms.cta">Dettagli e Prenotazione →</a>
      </div>
    </article>

  </div>
</section>

<!-- SERVICES — sezione servizi ora DOPO le camere -->
<section id="services">
  <div style="text-align:center; margin-bottom:.5rem;" class="reveal">
    <p class="section-label" data-i18n="services.label">I Nostri Servizi</p>
  </div>
  <h2 class="section-title reveal" style="color:var(--white);text-align:center;margin-bottom:.5rem;" data-i18n="services.title">Lasciati Stupire</h2>
  <p class="services-subtitle reveal" data-i18n="services.sub">Tutto il comfort che meriti</p>
  <div class="services-grid">
    <div class="service-card reveal"><div class="service-icon">🅿️</div><h3 data-i18n="srv.parking">Parcheggio Privato</h3></div>
    <div class="service-card reveal"><div class="service-icon">☕</div><h3 data-i18n="srv.coffee">Caffè in Camera</h3></div>
    <div class="service-card reveal"><div class="service-icon">🏖️</div><h3 data-i18n="srv.beach">Accesso Spiaggia</h3></div>
    <div class="service-card reveal"><div class="service-icon">🛎️</div><h3 data-i18n="srv.roomservice">Room Service</h3></div>
    <div class="service-card reveal"><div class="service-icon">🕐</div><h3 data-i18n="srv.reception">Reception 24×7</h3></div>
    <div class="service-card reveal"><div class="service-icon">✈️</div><h3 data-i18n="srv.shuttle">Navetta Aeroportuale</h3></div>
    <div class="service-card reveal"><div class="service-icon">💨</div><h3 data-i18n="srv.dryer">Phon in Camera</h3></div>
    <div class="service-card reveal"><div class="service-icon">📶</div><h3 data-i18n="srv.wifi">WiFi Gratuito</h3></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <div>
      <p class="section-label reveal" data-i18n="contact.label">Contattaci</p>
      <h2 class="section-title reveal" data-i18n="contact.title">Dubbi o Domande?<br>Siamo Qui per Te</h2>
      <div class="contact-detail reveal">
        <span class="icon">📍</span>
        <p>Corso Italia 261, 80067<br>Sorrento (NA), Italia</p>
      </div>
      <div class="contact-detail reveal">
        <span class="icon">📞</span>
        <p><a href="tel:+393394625714">+39 339 462 5714</a></p>
      </div>
      <div class="contact-detail reveal">
        <span class="icon">✉️</span>
        <p><a href="mailto:info@sorrentoroom.com">info@sorrentoroom.com</a></p>
      </div>
      <div class="contact-detail reveal">
        <span class="icon">📷</span>
        <p><a href="https://www.instagram.com/baby_sorrento_room" target="_blank" data-i18n="contact.instagram">Seguici su Instagram</a></p>
      </div>
      <div class="or-divider reveal" data-i18n="contact.or">oppure</div>
      <a href="https://babyroom.kross.travel/" class="book-big-btn reveal" target="_blank" data-i18n="contact.bookbtn">Prenota una Camera Ora</a>
    </div>
    <div class="reveal">
      <div class="contact-form">
        <div class="form-row">
          <div class="form-group">
            <label for="fname" data-i18n="form.fname">Nome</label>
            <input type="text" id="fname" data-i18n-placeholder="form.fname_ph" placeholder="Mario"/>
          </div>
          <div class="form-group">
            <label for="lname" data-i18n="form.lname">Cognome</label>
            <input type="text" id="lname" data-i18n-placeholder="form.lname_ph" placeholder="Rossi"/>
          </div>
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" placeholder="mario@esempio.it"/>
        </div>
        <div class="form-group">
          <label for="message" data-i18n="form.message">Messaggio</label>
          <textarea id="message" data-i18n-placeholder="form.message_ph" placeholder="Come possiamo aiutarti?"></textarea>
        </div>
        <button class="submit-btn" id="submitBtn" type="button" data-i18n="form.submit">Invia Messaggio</button>
        <div class="form-msg" id="formMsg"></div>
      </div>
    </div>
  </div>
</section>

<!-- MAP -->
<section id="map-section">
  <p class="section-label reveal" style="text-align:center;" data-i18n="map.label">Dove Siamo</p>
  <h2 class="section-title reveal" style="text-align:center;margin-bottom:3rem;" data-i18n="map.title">Trovaci a Sorrento</h2>
  <div class="map-frame reveal">
    <iframe src="https://maps.google.com/maps?q=Corso+Italia+261,+80067+Sorrento+NA,+Italia&output=embed&hl=it&z=16" allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="Mappa Room Center Sorrento Baby"></iframe>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand">
      <a href="#" class="logo">Room Center Sorrento<span>Baby — B&amp;B</span></a>
      <p data-i18n="footer.desc">Una luxury guest house nel cuore di Sorrento, a pochi passi dal mare e dalle maggiori attrazioni storico-artistiche della Penisola Sorrentina.</p>
    </div>
    <div class="footer-col">
      <h4 data-i18n="footer.nav">Navigazione</h4>
      <a href="#about">Chi Siamo</a>
      <a href="https://www.sorrentoroom.com/attrazioni/" target="_blank">Attrazioni</a>
      <a href="#rooms">Camere</a>
      <a href="#services">Servizi</a>
      <a href="https://www.sorrentoroom.com/dove-siamo/" target="_blank">Dove Siamo</a>
      <a href="https://www.sorrentoroom.com/recensioni/" target="_blank">Recensioni</a>
      <a href="https://www.sorrentoroom.com/privacy-policy/" target="_blank">Privacy Policy</a>
    </div>
    <div class="footer-col">
      <h4 data-i18n="footer.contacts">Contatti</h4>
      <p>Corso Italia 261</p>
      <p>80067 Sorrento (NA)</p>
      <a href="tel:+393394625714">+39 339 462 5714</a>
      <a href="mailto:info@sorrentoroom.com">info@sorrentoroom.com</a>
      <a href="https://www.instagram.com/baby_sorrento_room?igsh=MW02cXpsb3Bma2dnZg==" target="_blank">📷 Seguici su Instagram</a>
    </div>
  </div>
  <div class="footer-bottom" data-i18n="footer.copy">&copy; 2025 Room Center Sorrento Baby · Tutti i diritti riservati · Corso Italia 261, Sorrento (NA)</div>
</footer>

<a href="https://babyroom.kross.travel/" class="float-book" target="_blank" data-i18n="nav.book">📅 Prenota</a>

<script>
/* ===== TRANSLATIONS ===== */
const translations = {
  it: {
    'nav.about': 'Chi Siamo',
    'nav.rooms': 'Camere',
    'nav.services': 'Servizi',
    'nav.contact': 'Contatti',
    'nav.book': '📅 Prenota',
    'hero.sub': 'Il tuo B&B nel cuore di Sorrento',
    'hero.btn': 'Prenota una Camera',
    'hero.scroll': 'Scopri',
    'about.label': 'La Nostra Storia',
    'about.title': 'Una luxury guest house nel cuore di Sorrento',
    'about.p1': 'Sorrento Baby B&B è una luxury guest house situata nel centro di Sorrento, a pochi passi dal mare e dalle maggiori attrazioni storico-artistiche. Un moderno ed elegante affittacamere in un edificio signorile con ascensore, situato a due passi dalla stazione e dai maggiori punti di interesse della città.',
    'about.p2': 'La struttura dispone di quattro camere da letto, ognuna con bagno privato. Ogni camera è arredata in stile moderno e confortevole, luminosa grazie al balcone dove è possibile sorseggiare un aperitivo con vista sul cortile. Tutte le camere godono di aria condizionata indipendente, TV a schermo piatto, bollitore, mini frigo, macchina del caffè, cassaforte, asse e ferro da stiro.',
    'about.checkin': 'Check-in: dalle ore 14:00 alle 22:00',
    'about.checkout': 'Check-out: entro le ore 10:30',
    'about.luggage': 'Deposito bagagli gratuito su richiesta',
    'about.concierge': 'Servizio concierge e assistenza H24',
    'about.id': 'Documento di identità richiesto all\'arrivo',
    'rooms.label': 'Le Nostre Camere',
    'rooms.title': 'Dove il Comfort Incontra l\'Eleganza',
    'rooms.sub': 'Prezzo speciale · Bagno privato incluso · WiFi gratis',
    'rooms.cta': 'Dettagli e Prenotazione →',
    'rooms.r1.tag': 'Camera Matrimoniale · 2 persone',
    'rooms.r1.desc': 'Superficie 20 mq — 1 letto matrimoniale — Balcone con vista giardino.',
    'rooms.r2.tag': 'Camera Tripla · 3 persone',
    'rooms.r2.desc': 'Superficie 20 mq — 1 letto matrimoniale + 1 divano letto — Vista cortile interno.',
    'rooms.r3.tag': 'Camera Matrimoniale · 2 persone',
    'rooms.r3.desc': 'Superficie 20 mq — 1 letto matrimoniale — Balcone con vista giardino.',
    'rooms.r4.tag': 'Camera Tripla · 3 persone',
    'rooms.r4.desc': 'Superficie 20 mq — 1 letto matrimoniale + 1 divano letto — Vista cortile interno.',
    'am.ac': 'Aria condizionata', 'am.bath': 'Bagno privato', 'am.tv': 'TV schermo piatto',
    'am.minibar': 'Minibar', 'am.wifi': 'WiFi gratis', 'am.balcony': 'Balcone', 'am.sofa': 'Divano letto',
    'services.label': 'I Nostri Servizi',
    'services.title': 'Lasciati Stupire',
    'services.sub': 'Tutto il comfort che meriti',
    'srv.parking': 'Parcheggio Privato', 'srv.coffee': 'Caffè in Camera', 'srv.beach': 'Accesso Spiaggia',
    'srv.roomservice': 'Room Service', 'srv.reception': 'Reception 24×7', 'srv.shuttle': 'Navetta Aeroportuale',
    'srv.dryer': 'Phon in Camera', 'srv.wifi': 'WiFi Gratuito',
    'contact.label': 'Contattaci',
    'contact.title': 'Dubbi o Domande?<br>Siamo Qui per Te',
    'contact.instagram': 'Seguici su Instagram',
    'contact.or': 'oppure',
    'contact.bookbtn': 'Prenota una Camera Ora',
    'form.fname': 'Nome', 'form.fname_ph': 'Mario',
    'form.lname': 'Cognome', 'form.lname_ph': 'Rossi',
    'form.message': 'Messaggio', 'form.message_ph': 'Come possiamo aiutarti?',
    'form.submit': 'Invia Messaggio',
    'form.err_fields': 'Controlla che tutti i campi siano compilati correttamente.',
    'form.err_email': 'Inserisci un indirizzo email valido.',
    'form.success': 'Il messaggio è stato inviato correttamente!',
    'map.label': 'Dove Siamo',
    'map.title': 'Trovaci a Sorrento',
    'footer.desc': 'Una luxury guest house nel cuore di Sorrento, a pochi passi dal mare e dalle maggiori attrazioni della Penisola Sorrentina.',
    'footer.nav': 'Navigazione', 'footer.contacts': 'Contatti', 'footer.privacy': 'Privacy Policy',
    'footer.copy': '© 2025 Room Center Sorrento Baby · Tutti i diritti riservati · Corso Italia 261, Sorrento (NA)',
  },
  en: {
    'nav.about': 'About Us',
    'nav.rooms': 'Rooms',
    'nav.services': 'Services',
    'nav.contact': 'Contact',
    'nav.book': '📅 Book Now',
    'hero.sub': 'Your B&B in the heart of Sorrento',
    'hero.btn': 'Book a Room',
    'hero.scroll': 'Discover',
    'about.label': 'Our Story',
    'about.title': 'A luxury guest house in the heart of Sorrento',
    'about.p1': 'Sorrento Baby B&B is a luxury guest house located in the centre of Sorrento, a short walk from the sea and the main historic and artistic attractions. A modern and elegant B&B in a prestigious building with lift, just steps from the railway station and major points of interest.',
    'about.p2': 'The property has four bedrooms, each with an en-suite bathroom. Every room is furnished in a modern and comfortable style, bright thanks to a balcony overlooking the courtyard. All rooms feature independent air conditioning, flat-screen TV, kettle, mini fridge, coffee machine, safe, and ironing board.',
    'about.checkin': 'Check-in: from 2:00 PM to 10:00 PM',
    'about.checkout': 'Check-out: by 10:30 AM',
    'about.luggage': 'Free luggage storage on request',
    'about.concierge': 'Concierge service and 24/7 assistance',
    'about.id': 'ID document required upon arrival',
    'rooms.label': 'Our Rooms',
    'rooms.title': 'Where Comfort Meets Elegance',
    'rooms.sub': 'Special price · Private bathroom included · Free WiFi',
    'rooms.cta': 'Details & Booking →',
    'rooms.r1.tag': 'Double Room · 2 guests',
    'rooms.r1.desc': '20 sqm — 1 double bed — Balcony with garden view.',
    'rooms.r2.tag': 'Triple Room · 3 guests',
    'rooms.r2.desc': '20 sqm — 1 double bed + 1 sofa bed — Internal courtyard view.',
    'rooms.r3.tag': 'Double Room · 2 guests',
    'rooms.r3.desc': '20 sqm — 1 double bed — Balcony with garden view.',
    'rooms.r4.tag': 'Triple Room · 3 guests',
    'rooms.r4.desc': '20 sqm — 1 double bed + 1 sofa bed — Internal courtyard view.',
    'am.ac': 'Air conditioning', 'am.bath': 'Private bathroom', 'am.tv': 'Flat-screen TV',
    'am.minibar': 'Minibar', 'am.wifi': 'Free WiFi', 'am.balcony': 'Balcony', 'am.sofa': 'Sofa bed',
    'services.label': 'Our Services',
    'services.title': 'Be Amazed',
    'services.sub': 'All the comfort you deserve',
    'srv.parking': 'Private Parking', 'srv.coffee': 'In-Room Coffee', 'srv.beach': 'Beach Access',
    'srv.roomservice': 'Room Service', 'srv.reception': '24/7 Reception', 'srv.shuttle': 'Airport Shuttle',
    'srv.dryer': 'Hair Dryer', 'srv.wifi': 'Free WiFi',
    'contact.label': 'Contact Us',
    'contact.title': 'Questions or Doubts?<br>We\'re Here for You',
    'contact.instagram': 'Follow us on Instagram',
    'contact.or': 'or',
    'contact.bookbtn': 'Book a Room Now',
    'form.fname': 'First Name', 'form.fname_ph': 'John',
    'form.lname': 'Last Name', 'form.lname_ph': 'Smith',
    'form.message': 'Message', 'form.message_ph': 'How can we help you?',
    'form.submit': 'Send Message',
    'form.err_fields': 'Please fill in all fields correctly.',
    'form.err_email': 'Please enter a valid email address.',
    'form.success': 'Your message has been sent successfully!',
    'map.label': 'Find Us',
    'map.title': 'Find Us in Sorrento',
    'footer.desc': 'A luxury guest house in the heart of Sorrento, steps from the sea and the main attractions of the Sorrentine Peninsula.',
    'footer.nav': 'Navigation', 'footer.contacts': 'Contacts', 'footer.privacy': 'Privacy Policy',
    'footer.copy': '© 2025 Room Center Sorrento Baby · All rights reserved · Corso Italia 261, Sorrento (NA)',
  },
  de: {
    'nav.about': 'Über Uns',
    'nav.rooms': 'Zimmer',
    'nav.services': 'Leistungen',
    'nav.contact': 'Kontakt',
    'nav.book': '📅 Buchen',
    'hero.sub': 'Ihr B&B im Herzen von Sorrent',
    'hero.btn': 'Ein Zimmer buchen',
    'hero.scroll': 'Entdecken',
    'about.label': 'Unsere Geschichte',
    'about.title': 'Ein Luxus-Gästehaus im Herzen von Sorrent',
    'about.p1': 'Das Sorrento Baby B&B ist ein Luxus-Gästehaus im Zentrum von Sorrent, nur wenige Schritte vom Meer und den bedeutendsten historischen und künstlerischen Sehenswürdigkeiten entfernt. Ein modernes und elegantes Zimmerangebot in einem herrschaftlichen Gebäude mit Aufzug, in unmittelbarer Nähe des Bahnhofs.',
    'about.p2': 'Das Haus verfügt über vier Schlafzimmer, jedes mit eigenem Bad. Jedes Zimmer ist modern und komfortabel eingerichtet, hell dank des Balkons mit Blick auf den Innenhof. Alle Zimmer verfügen über eine eigene Klimaanlage, Flachbildschirm-TV, Wasserkocher, Mini-Kühlschrank, Kaffeemaschine, Safe sowie Bügeleisenstation.',
    'about.checkin': 'Check-in: von 14:00 bis 22:00 Uhr',
    'about.checkout': 'Check-out: bis 10:30 Uhr',
    'about.luggage': 'Kostenlose Gepäckaufbewahrung auf Anfrage',
    'about.concierge': 'Concierge-Service und 24/7-Assistance',
    'about.id': 'Lichtbildausweis bei der Ankunft erforderlich',
    'rooms.label': 'Unsere Zimmer',
    'rooms.title': 'Wo Komfort auf Eleganz trifft',
    'rooms.sub': 'Sonderpreis · Eigenes Bad inklusive · Kostenloses WLAN',
    'rooms.cta': 'Details & Buchung →',
    'rooms.r1.tag': 'Doppelzimmer · 2 Personen',
    'rooms.r1.desc': '20 m² — 1 Doppelbett — Balkon mit Gartenblick.',
    'rooms.r2.tag': 'Dreibettzimmer · 3 Personen',
    'rooms.r2.desc': '20 m² — 1 Doppelbett + 1 Schlafsofa — Blick auf den Innenhof.',
    'rooms.r3.tag': 'Doppelzimmer · 2 Personen',
    'rooms.r3.desc': '20 m² — 1 Doppelbett — Balkon mit Gartenblick.',
    'rooms.r4.tag': 'Dreibettzimmer · 3 Personen',
    'rooms.r4.desc': '20 m² — 1 Doppelbett + 1 Schlafsofa — Blick auf den Innenhof.',
    'am.ac': 'Klimaanlage', 'am.bath': 'Eigenes Bad', 'am.tv': 'Flachbildschirm',
    'am.minibar': 'Minibar', 'am.wifi': 'Kostenloses WLAN', 'am.balcony': 'Balkon', 'am.sofa': 'Schlafsofa',
    'services.label': 'Unsere Leistungen',
    'services.title': 'Lassen Sie sich begeistern',
    'services.sub': 'Aller Komfort, den Sie verdienen',
    'srv.parking': 'Privatparkplatz', 'srv.coffee': 'Kaffee im Zimmer', 'srv.beach': 'Strandzugang',
    'srv.roomservice': 'Zimmerservice', 'srv.reception': 'Rezeption 24×7', 'srv.shuttle': 'Flughafenshuttle',
    'srv.dryer': 'Haartrockner', 'srv.wifi': 'Kostenloses WLAN',
    'contact.label': 'Kontakt',
    'contact.title': 'Fragen?<br>Wir sind für Sie da',
    'contact.instagram': 'Folgen Sie uns auf Instagram',
    'contact.or': 'oder',
    'contact.bookbtn': 'Jetzt ein Zimmer buchen',
    'form.fname': 'Vorname', 'form.fname_ph': 'Hans',
    'form.lname': 'Nachname', 'form.lname_ph': 'Müller',
    'form.message': 'Nachricht', 'form.message_ph': 'Wie können wir Ihnen helfen?',
    'form.submit': 'Nachricht senden',
    'form.err_fields': 'Bitte füllen Sie alle Felder korrekt aus.',
    'form.err_email': 'Bitte geben Sie eine gültige E-Mail-Adresse ein.',
    'form.success': 'Ihre Nachricht wurde erfolgreich gesendet!',
    'map.label': 'So finden Sie uns',
    'map.title': 'Finden Sie uns in Sorrent',
    'footer.desc': 'Ein Luxus-Gästehaus im Herzen von Sorrent, wenige Schritte vom Meer und den wichtigsten Sehenswürdigkeiten der Sorrentinischen Halbinsel.',
    'footer.nav': 'Navigation', 'footer.contacts': 'Kontakt', 'footer.privacy': 'Datenschutz',
    'footer.copy': '© 2025 Room Center Sorrento Baby · Alle Rechte vorbehalten · Corso Italia 261, Sorrent (NA)',
  },
  fr: {
    'nav.about': 'À Propos',
    'nav.rooms': 'Chambres',
    'nav.services': 'Services',
    'nav.contact': 'Contact',
    'nav.book': '📅 Réserver',
    'hero.sub': 'Votre B&B au cœur de Sorrente',
    'hero.btn': 'Réserver une Chambre',
    'hero.scroll': 'Découvrir',
    'about.label': 'Notre Histoire',
    'about.title': 'Une maison d\'hôtes de luxe au cœur de Sorrente',
    'about.p1': 'Le Sorrento Baby B&B est une maison d\'hôtes de luxe située au centre de Sorrente, à quelques pas de la mer et des principales attractions historiques et artistiques. Un hébergement moderne et élégant dans un immeuble de prestige avec ascenseur, situé à deux pas de la gare et des principaux points d\'intérêt de la ville.',
    'about.p2': 'L\'établissement dispose de quatre chambres à coucher, chacune avec salle de bain privative. Chaque chambre est meublée dans un style moderne et confortable, lumineuse grâce au balcon donnant sur la cour intérieure. Toutes les chambres bénéficient d\'une climatisation indépendante, d\'une télévision à écran plat, d\'une bouilloire, d\'un mini-frigo, d\'une machine à café, d\'un coffre-fort et d\'une table à repasser.',
    'about.checkin': 'Check-in : de 14h00 à 22h00',
    'about.checkout': 'Check-out : avant 10h30',
    'about.luggage': 'Consigne à bagages gratuite sur demande',
    'about.concierge': 'Service de conciergerie et assistance 24h/24',
    'about.id': 'Pièce d\'identité requise à l\'arrivée',
    'rooms.label': 'Nos Chambres',
    'rooms.title': 'Où le Confort Rencontre l\'Élégance',
    'rooms.sub': 'Prix spécial · Salle de bain privée incluse · WiFi gratuit',
    'rooms.cta': 'Détails & Réservation →',
    'rooms.r1.tag': 'Chambre Double · 2 personnes',
    'rooms.r1.desc': '20 m² — 1 lit double — Balcon avec vue sur le jardin.',
    'rooms.r2.tag': 'Chambre Triple · 3 personnes',
    'rooms.r2.desc': '20 m² — 1 lit double + 1 canapé-lit — Vue sur la cour intérieure.',
    'rooms.r3.tag': 'Chambre Double · 2 personnes',
    'rooms.r3.desc': '20 m² — 1 lit double — Balcon avec vue sur le jardin.',
    'rooms.r4.tag': 'Chambre Triple · 3 personnes',
    'rooms.r4.desc': '20 m² — 1 lit double + 1 canapé-lit — Vue sur la cour intérieure.',
    'am.ac': 'Climatisation', 'am.bath': 'Salle de bain privée', 'am.tv': 'Télévision écran plat',
    'am.minibar': 'Minibar', 'am.wifi': 'WiFi gratuit', 'am.balcony': 'Balcon', 'am.sofa': 'Canapé-lit',
    'services.label': 'Nos Services',
    'services.title': 'Laissez-vous Surprendre',
    'services.sub': 'Tout le confort que vous méritez',
    'srv.parking': 'Parking Privé', 'srv.coffee': 'Café en Chambre', 'srv.beach': 'Accès Plage',
    'srv.roomservice': 'Room Service', 'srv.reception': 'Réception 24×7', 'srv.shuttle': 'Navette Aéroport',
    'srv.dryer': 'Sèche-cheveux', 'srv.wifi': 'WiFi Gratuit',
    'contact.label': 'Contactez-Nous',
    'contact.title': 'Des Questions?<br>Nous Sommes Là pour Vous',
    'contact.instagram': 'Suivez-nous sur Instagram',
    'contact.or': 'ou',
    'contact.bookbtn': 'Réserver une Chambre Maintenant',
    'form.fname': 'Prénom', 'form.fname_ph': 'Jean',
    'form.lname': 'Nom', 'form.lname_ph': 'Dupont',
    'form.message': 'Message', 'form.message_ph': 'Comment pouvons-nous vous aider?',
    'form.submit': 'Envoyer le Message',
    'form.err_fields': 'Veuillez remplir tous les champs correctement.',
    'form.err_email': 'Veuillez entrer une adresse e-mail valide.',
    'form.success': 'Votre message a été envoyé avec succès !',
    'map.label': 'Où Nous Trouver',
    'map.title': 'Retrouvez-nous à Sorrente',
    'footer.desc': 'Une maison d\'hôtes de luxe au cœur de Sorrente, à quelques pas de la mer et des principales attractions de la Péninsule Sorrentine.',
    'footer.nav': 'Navigation', 'footer.contacts': 'Contacts', 'footer.privacy': 'Politique de Confidentialité',
    'footer.copy': '© 2025 Room Center Sorrento Baby · Tous droits réservés · Corso Italia 261, Sorrente (NA)',
  }
};

let currentLang = 'it';

function setLang(lang) {
  currentLang = lang;
  const t = translations[lang];

  // Text nodes
  document.querySelectorAll('[data-i18n]').forEach(el => {
    const key = el.getAttribute('data-i18n');
    if (t[key] !== undefined) el.innerHTML = t[key];
  });

  // Placeholders
  document.querySelectorAll('[data-i18n-placeholder]').forEach(el => {
    const key = el.getAttribute('data-i18n-placeholder');
    if (t[key] !== undefined) el.placeholder = t[key];
  });

  // Update active button
  document.querySelectorAll('.lang-btn').forEach(btn => {
    btn.classList.toggle('active', btn.textContent === lang.toUpperCase());
  });

  document.documentElement.lang = lang;
}

/* ===== NAV SCROLL ===== */
const navbar = document.getElementById('navbar');
window.addEventListener('scroll', () => {
  navbar.classList.toggle('scrolled', window.scrollY > 60);
});

/* ===== HAMBURGER ===== */
document.getElementById('hamburger').addEventListener('click', () => {
  document.getElementById('mobileMenu').classList.add('open');
});
document.getElementById('closeMenu').addEventListener('click', () => {
  document.getElementById('mobileMenu').classList.remove('open');
});
document.querySelectorAll('.mobile-menu a').forEach(a => {
  a.addEventListener('click', () => {
    document.getElementById('mobileMenu').classList.remove('open');
  });
});

/* ===== SCROLL REVEAL ===== */
const revealEls = document.querySelectorAll('.reveal, .reveal-left, .reveal-right');
const obs = new IntersectionObserver((entries) => {
  entries.forEach((e, i) => {
    if (e.isIntersecting) {
      setTimeout(() => {
        e.target.classList.add('visible');
      }, (e.target.dataset.delay || 0) * 1);
      obs.unobserve(e.target);
    }
  });
}, { threshold: 0.1 });

// Stagger children inside grids
document.querySelectorAll('.rooms-grid .room-card, .services-grid .service-card').forEach((el, i) => {
  el.style.transitionDelay = (i * 80) + 'ms';
});

revealEls.forEach(el => obs.observe(el));

/* ===== CONTACT FORM ===== */
document.getElementById('submitBtn').addEventListener('click', () => {
  const t = translations[currentLang];
  const fname = document.getElementById('fname').value.trim();
  const lname = document.getElementById('lname').value.trim();
  const email = document.getElementById('email').value.trim();
  const message = document.getElementById('message').value.trim();
  const msg = document.getElementById('formMsg');
  msg.className = 'form-msg';
  if (!fname || !lname || !email || !message) {
    msg.className = 'form-msg error';
    msg.textContent = t['form.err_fields'];
    return;
  }
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
    msg.className = 'form-msg error';
    msg.textContent = t['form.err_email'];
    return;
  }
  msg.className = 'form-msg success';
  msg.textContent = t['form.success'];
  document.getElementById('fname').value = '';
  document.getElementById('lname').value = '';
  document.getElementById('email').value = '';
  document.getElementById('message').value = '';
});

// Init Italian as default
setLang('it');
</script>
</body>
</html>


