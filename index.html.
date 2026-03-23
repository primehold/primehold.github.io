<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PrimeHold — Rentals & Asset Finance</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --ink: #111008; --cream: #F5F0E8; --gold: #C9A84C; --gold-light: #E8D5A3;
    --rust: #B85C38; --card-bg: #FDFAF4; --border: #DDD5C0; --text-muted: #7A6E5A;
  }
  html { scroll-behavior: smooth; }
  body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--ink); overflow-x: hidden; }

  /* CONTACT BAR */
  .contact-bar { background: var(--ink); color: rgba(245,240,232,0.65); display: flex; justify-content: space-between; align-items: center; padding: 0.5rem 5%; font-size: 0.79rem; flex-wrap: wrap; gap: 0.5rem; }
  .contact-bar-left { display: flex; align-items: center; gap: 0.4rem; }
  .contact-bar-right { display: flex; gap: 1.6rem; flex-wrap: wrap; }
  .contact-bar a { color: rgba(245,240,232,0.65); text-decoration: none; display: flex; align-items: center; gap: 0.35rem; transition: color 0.2s; }
  .contact-bar a:hover { color: var(--gold); }
  @media(max-width:640px){ .contact-bar { justify-content: center; } .contact-bar-left { display: none; } }

  /* NAV */
  nav { position: sticky; top: 0; z-index: 100; display: flex; align-items: center; justify-content: space-between; padding: 1.1rem 5%; background: rgba(245,240,232,0.96); backdrop-filter: blur(14px); border-bottom: 1px solid var(--border); }
  .nav-logo { font-family: 'Playfair Display', serif; font-size: 1.55rem; font-weight: 900; color: var(--ink); letter-spacing: -0.5px; text-decoration: none; }
  .nav-logo span { color: var(--gold); }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a { text-decoration: none; color: var(--ink); font-size: 0.88rem; font-weight: 500; transition: color 0.2s; }
  .nav-links a:hover { color: var(--gold); }
  .nav-cta { background: var(--ink) !important; color: var(--cream) !important; padding: 0.5rem 1.3rem; border-radius: 4px; }
  .nav-cta:hover { background: var(--gold) !important; color: var(--ink) !important; }
  .nav-ham { display: none; background: none; border: none; font-size: 1.4rem; cursor: pointer; }
  @media(max-width:680px){ .nav-links { display: none; flex-direction: column; position: absolute; top: 100%; left: 0; right: 0; background: var(--cream); border-bottom: 1px solid var(--border); padding: 1rem 5%; z-index: 99; } .nav-links.open { display: flex; } .nav-ham { display: block; } }

  /* HERO */
  .hero { min-height: 90vh; display: flex; flex-direction: column; justify-content: center; padding: 6rem 5% 5rem; position: relative; overflow: hidden; }
  .hero-bg { position: absolute; inset: 0; background: radial-gradient(ellipse 60% 80% at 80% 50%, rgba(201,168,76,0.13) 0%, transparent 70%), radial-gradient(ellipse 40% 40% at 15% 80%, rgba(74,94,78,0.09) 0%, transparent 60%); }
  .hero-tag { display: inline-block; margin-bottom: 1.4rem; font-size: 0.74rem; font-weight: 700; letter-spacing: 0.16em; text-transform: uppercase; color: var(--gold); border: 1px solid var(--gold-light); padding: 0.3rem 0.85rem; border-radius: 20px; width: fit-content; }
  .hero h1 { font-family: 'Playfair Display', serif; font-size: clamp(2.8rem, 6.5vw, 6rem); font-weight: 900; line-height: 1.06; max-width: 14ch; position: relative; z-index: 1; }
  .hero h1 em { font-style: italic; color: var(--gold); }
  .hero-sub { margin-top: 1.6rem; max-width: 50ch; font-size: 1.03rem; color: var(--text-muted); line-height: 1.75; position: relative; z-index: 1; }
  .hero-actions { margin-top: 2.2rem; display: flex; gap: 1rem; flex-wrap: wrap; position: relative; z-index: 1; }
  .btn-primary { background: var(--ink); color: var(--cream); padding: 0.85rem 1.9rem; border: none; border-radius: 5px; font-family: 'DM Sans', sans-serif; font-size: 0.92rem; font-weight: 600; cursor: pointer; transition: all 0.2s; text-decoration: none; display: inline-block; }
  .btn-primary:hover { background: var(--gold); color: var(--ink); transform: translateY(-2px); }
  .btn-outline { background: transparent; color: var(--ink); padding: 0.85rem 1.9rem; border: 1.5px solid var(--border); border-radius: 5px; font-family: 'DM Sans', sans-serif; font-size: 0.92rem; font-weight: 500; cursor: pointer; transition: all 0.2s; text-decoration: none; display: inline-block; }
  .btn-outline:hover { border-color: var(--ink); transform: translateY(-2px); }
  .hero-stats { margin-top: 3.5rem; display: flex; gap: 3rem; flex-wrap: wrap; position: relative; z-index: 1; padding-top: 2rem; border-top: 1px solid var(--border); }
  .stat-item h3 { font-family: 'Playfair Display', serif; font-size: 2.1rem; font-weight: 700; }
  .stat-item p { font-size: 0.82rem; color: var(--text-muted); margin-top: 0.2rem; }

  /* SECTIONS */
  section { padding: 5.5rem 5%; }
  .section-label { font-size: 0.72rem; font-weight: 700; letter-spacing: 0.16em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.7rem; }
  .section-title { font-family: 'Playfair Display', serif; font-size: clamp(1.9rem, 4vw, 3rem); font-weight: 700; line-height: 1.2; }
  .section-sub { color: var(--text-muted); margin-top: 0.8rem; font-size: 0.96rem; line-height: 1.75; max-width: 55ch; }

  /* LISTINGS */
  #listings { background: var(--card-bg); }
  .filter-bar { display: flex; gap: 0.8rem; flex-wrap: wrap; margin: 2rem 0 1.5rem; padding: 1.1rem 1.4rem; background: white; border: 1px solid var(--border); border-radius: 10px; }
  .filter-bar select, .filter-bar input { padding: 0.56rem 0.9rem; border: 1px solid var(--border); border-radius: 6px; font-family: 'DM Sans', sans-serif; font-size: 0.87rem; color: var(--ink); background: white; outline: none; flex: 1; min-width: 130px; }
  .filter-bar select:focus, .filter-bar input:focus { border-color: var(--gold); }
  .units-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(295px, 1fr)); gap: 1.5rem; }
  .unit-card { background: white; border: 1px solid var(--border); border-radius: 12px; overflow: hidden; transition: all 0.25s; animation: fadeUp 0.4s ease both; }
  .unit-card:hover { transform: translateY(-5px); box-shadow: 0 14px 35px rgba(0,0,0,0.09); }
  @keyframes fadeUp { from { opacity:0; transform:translateY(18px); } to { opacity:1; transform:translateY(0); } }
  .unit-img { height: 210px; position: relative; overflow: hidden; background: linear-gradient(135deg, rgba(201,168,76,0.12), rgba(74,94,78,0.1)); display: flex; align-items: center; justify-content: center; cursor: pointer; }
  .unit-img img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.35s; }
  .unit-img:hover img { transform: scale(1.04); }
  .unit-emoji { font-size: 3.5rem; }
  .unit-status-badge { position: absolute; top: 0.75rem; right: 0.75rem; z-index: 2; }
  .photo-pill { position: absolute; bottom: 0.6rem; right: 0.75rem; background: rgba(0,0,0,0.55); color: white; font-size: 0.7rem; font-weight: 700; padding: 0.18rem 0.52rem; border-radius: 20px; z-index: 2; }
  .unit-body { padding: 1.3rem; }
  .unit-type-tag { font-size: 0.67rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.33rem; }
  .unit-name { font-family: 'Playfair Display', serif; font-size: 1.13rem; font-weight: 700; margin-bottom: 0.28rem; }
  .unit-loc { font-size: 0.82rem; color: var(--text-muted); margin-bottom: 0.85rem; }
  .unit-feats { display: flex; gap: 0.9rem; font-size: 0.79rem; color: var(--text-muted); margin-bottom: 0.9rem; flex-wrap: wrap; }
  .unit-desc { font-size: 0.81rem; color: var(--text-muted); line-height: 1.55; margin-bottom: 0.9rem; }
  .unit-price-row { display: flex; align-items: center; justify-content: space-between; padding-top: 0.9rem; border-top: 1px solid var(--border); }
  .price-amt { font-family: 'Playfair Display', serif; font-size: 1.42rem; font-weight: 700; }
  .price-per { font-size: 0.77rem; color: var(--text-muted); margin-left: 0.12rem; }
  .enq-btn { background: var(--ink); color: var(--cream); padding: 0.5rem 1.1rem; border: none; border-radius: 6px; font-family: 'DM Sans', sans-serif; font-size: 0.81rem; font-weight: 600; cursor: pointer; transition: all 0.2s; }
  .enq-btn:hover { background: var(--gold); color: var(--ink); }
  .enq-btn:disabled { background: #ccc; color: #888; cursor: not-allowed; }
  .no-units { text-align: center; padding: 3rem; color: var(--text-muted); grid-column: 1/-1; }

  /* BADGES */
  .badge { display: inline-block; padding: 0.17rem 0.58rem; border-radius: 20px; font-size: 0.67rem; font-weight: 700; text-transform: uppercase; }
  .badge-available { background: rgba(74,94,78,0.16); color: #3a7a3e; }
  .badge-pending { background: rgba(201,168,76,0.18); color: #9a7520; }
  .badge-rented { background: rgba(184,92,56,0.16); color: #b85c38; }

  /* PAWN */
  #pawn { background: var(--cream); }
  .pawn-layout { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; margin-top: 3rem; align-items: start; }
  @media(max-width:768px){ .pawn-layout { grid-template-columns: 1fr; gap: 2rem; } }
  .pawn-features { display: flex; flex-direction: column; gap: 1.15rem; }
  .pawn-feature { display: flex; gap: 1.1rem; padding: 1.3rem; background: white; border: 1px solid var(--border); border-radius: 10px; transition: all 0.2s; }
  .pawn-feature:hover { border-color: var(--gold); transform: translateX(4px); }
  .pawn-icon { width: 46px; height: 46px; flex-shrink: 0; background: linear-gradient(135deg, var(--gold), var(--gold-light)); border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 1.3rem; }
  .pawn-feature h4 { font-size: 0.94rem; font-weight: 600; margin-bottom: 0.22rem; }
  .pawn-feature p { font-size: 0.83rem; color: var(--text-muted); line-height: 1.55; }

  /* LIGHT FORM */
  .light-form { background: white; border: 1px solid var(--border); border-radius: 12px; padding: 2rem; }
  .light-form h3 { font-family: 'Playfair Display', serif; font-size: 1.3rem; margin-bottom: 1.3rem; }
  .lf-g { margin-bottom: 1.05rem; }
  .lf-g label { display: block; font-size: 0.73rem; font-weight: 700; letter-spacing: 0.05em; text-transform: uppercase; color: var(--text-muted); margin-bottom: 0.4rem; }
  .lf-g input, .lf-g select, .lf-g textarea { width: 100%; padding: 0.68rem 0.9rem; background: var(--cream); border: 1px solid var(--border); border-radius: 6px; color: var(--ink); font-family: 'DM Sans', sans-serif; font-size: 0.9rem; outline: none; transition: border-color 0.2s; }
  .lf-g input:focus, .lf-g select:focus, .lf-g textarea:focus { border-color: var(--gold); }
  .lf-g textarea { resize: vertical; min-height: 82px; }
  .lf-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  @media(max-width:480px){ .lf-row { grid-template-columns: 1fr; } }
  .btn-dark { background: var(--ink); color: var(--cream); padding: 0.82rem 2rem; border: none; border-radius: 6px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; font-weight: 700; cursor: pointer; transition: all 0.2s; width: 100%; margin-top: 0.4rem; }
  .btn-dark:hover { background: var(--gold); color: var(--ink); }

  /* CONTACT SECTION */
  #contact { background: var(--card-bg); }
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.8rem; margin-top: 3rem; }
  @media(max-width:768px){ .contact-grid { grid-template-columns: 1fr; } }
  .contact-card { background: white; border: 1px solid var(--border); border-radius: 12px; padding: 1.8rem; display: flex; flex-direction: column; gap: 0.6rem; transition: all 0.2s; }
  .contact-card:hover { border-color: var(--gold); transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,0,0,0.07); }
  .contact-icon { width: 48px; height: 48px; background: linear-gradient(135deg, var(--gold), var(--gold-light)); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 1.35rem; margin-bottom: 0.3rem; }
  .contact-card h4 { font-family: 'Playfair Display', serif; font-size: 1.05rem; font-weight: 700; }
  .contact-card a, .contact-card p { font-size: 0.88rem; color: var(--text-muted); text-decoration: none; line-height: 1.65; transition: color 0.2s; }
  .contact-card a:hover { color: var(--gold); }

  /* ADMIN */
  #admin { background: var(--ink); color: var(--cream); }
  #admin .section-label { color: var(--gold); }
  #admin .section-title { color: var(--cream); }
  #admin .section-sub { color: rgba(245,240,232,0.5); }
  .tab-toggle { display: flex; margin-top: 2.5rem; border: 1px solid rgba(255,255,255,0.13); border-radius: 8px; overflow: hidden; width: fit-content; }
  .tab-btn { padding: 0.58rem 1.35rem; background: none; border: none; font-family: 'DM Sans', sans-serif; font-size: 0.84rem; font-weight: 600; color: rgba(245,240,232,0.4); cursor: pointer; transition: all 0.2s; }
  .tab-btn.active { background: var(--gold); color: var(--ink); }
  .tab-panel { display: none; margin-top: 1.8rem; }
  .tab-panel.active { display: block; }
  .admin-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
  @media(max-width:820px){ .admin-grid { grid-template-columns: 1fr; } }
  .admin-card { background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1); border-radius: 12px; padding: 2rem; }
  .admin-card h3 { font-family: 'Playfair Display', serif; font-size: 1.2rem; margin-bottom: 1.3rem; color: var(--gold); }
  .af-g { margin-bottom: 1.05rem; }
  .af-g label { display: block; font-size: 0.72rem; font-weight: 700; letter-spacing: 0.05em; text-transform: uppercase; color: rgba(245,240,232,0.45); margin-bottom: 0.4rem; }
  .af-g input, .af-g select, .af-g textarea { width: 100%; padding: 0.68rem 0.9rem; background: rgba(255,255,255,0.07); border: 1px solid rgba(255,255,255,0.13); border-radius: 6px; color: var(--cream); font-family: 'DM Sans', sans-serif; font-size: 0.9rem; outline: none; transition: border-color 0.2s; }
  .af-g input:focus, .af-g select:focus, .af-g textarea:focus { border-color: var(--gold); }
  .af-g select option { background: #1a1a0e; }
  .af-g textarea { resize: vertical; min-height: 78px; }
  .af-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  @media(max-width:480px){ .af-row { grid-template-columns: 1fr; } }

  /* Photo upload */
  .photo-upload-wrap { border: 2px dashed rgba(201,168,76,0.32); border-radius: 8px; padding: 1.2rem; text-align: center; position: relative; cursor: pointer; transition: all 0.2s; }
  .photo-upload-wrap:hover { border-color: var(--gold); background: rgba(201,168,76,0.04); }
  .photo-upload-wrap input[type="file"] { position: absolute; inset: 0; opacity: 0; width: 100%; height: 100%; cursor: pointer; }
  .upload-icon { font-size: 1.8rem; margin-bottom: 0.3rem; }
  .upload-hint { font-size: 0.78rem; color: rgba(245,240,232,0.38); }
  .upload-hint strong { color: var(--gold); }
  .photo-previews-admin { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.75rem; }
  .prev-wrap { position: relative; }
  .prev-thumb { width: 60px; height: 60px; object-fit: cover; border-radius: 6px; border: 2px solid rgba(201,168,76,0.35); display: block; }
  .prev-rm { position: absolute; top: -5px; right: -5px; width: 17px; height: 17px; border-radius: 50%; background: var(--rust); border: none; color: white; font-size: 0.6rem; cursor: pointer; display: flex; align-items: center; justify-content: center; font-weight: 800; }

  .btn-gold { background: var(--gold); color: var(--ink); padding: 0.8rem 2rem; border: none; border-radius: 6px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; font-weight: 700; cursor: pointer; transition: all 0.2s; width: 100%; margin-top: 0.55rem; }
  .btn-gold:hover { background: var(--gold-light); }

  /* Admin table */
  .tbl { width: 100%; border-collapse: collapse; font-size: 0.84rem; margin-top: 0.5rem; }
  .tbl th { text-align: left; padding: 0.52rem 0.72rem; color: rgba(245,240,232,0.38); font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.06em; border-bottom: 1px solid rgba(255,255,255,0.09); font-weight: 600; }
  .tbl td { padding: 0.68rem 0.72rem; border-bottom: 1px solid rgba(255,255,255,0.06); color: var(--cream); vertical-align: middle; }
  .tbl tr:hover td { background: rgba(255,255,255,0.03); }
  .tbl-thumb { width: 40px; height: 40px; object-fit: cover; border-radius: 5px; vertical-align: middle; }
  .tbl-ph { width: 40px; height: 40px; background: rgba(255,255,255,0.07); border-radius: 5px; display: inline-flex; align-items: center; justify-content: center; font-size: 1.15rem; vertical-align: middle; }
  .del-btn { background: none; border: none; color: rgba(245,240,232,0.22); cursor: pointer; font-size: 0.95rem; padding: 0.2rem 0.4rem; transition: color 0.2s; }
  .del-btn:hover { color: var(--rust); }
  .empty-row { text-align: center; padding: 1.8rem; color: rgba(245,240,232,0.22); font-size: 0.86rem; }

  /* Enquiry cards */
  .enq-card { border: 1px solid rgba(255,255,255,0.09); border-radius: 8px; padding: 1rem 1.15rem; margin-bottom: 0.7rem; }
  .enq-head { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 0.35rem; margin-bottom: 0.38rem; }
  .enq-name { font-weight: 700; color: var(--cream); }
  .enq-unit { color: var(--gold); font-size: 0.78rem; margin-left: 0.55rem; }
  .enq-date { color: rgba(245,240,232,0.3); font-size: 0.74rem; }
  .enq-contact { color: rgba(245,240,232,0.5); font-size: 0.81rem; margin-top: 0.28rem; }
  .enq-msg { color: rgba(245,240,232,0.42); font-size: 0.81rem; margin-top: 0.4rem; font-style: italic; }

  /* MODAL */
  .modal-overlay { display: none; position: fixed; inset: 0; z-index: 200; background: rgba(17,16,8,0.72); backdrop-filter: blur(6px); align-items: center; justify-content: center; padding: 1rem; }
  .modal-overlay.open { display: flex; }
  .modal { background: white; border-radius: 14px; padding: 2.1rem; width: min(500px, 100%); max-height: 90vh; overflow-y: auto; animation: mIn 0.22s ease; }
  @keyframes mIn { from { opacity:0; transform:scale(0.95) translateY(8px); } to { opacity:1; transform:scale(1) translateY(0); } }
  .modal-head { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 1.3rem; }
  .modal-head h2 { font-family: 'Playfair Display', serif; font-size: 1.45rem; }
  .modal-close { background: none; border: none; font-size: 1.35rem; cursor: pointer; color: var(--text-muted); line-height: 1; }
  .modal-unit-box { background: var(--cream); border-radius: 8px; padding: 0.85rem 1.05rem; margin-bottom: 1.3rem; }
  .modal-unit-box h3 { font-family: 'Playfair Display', serif; font-size: 1.02rem; }
  .modal-unit-box p { font-size: 0.81rem; color: var(--text-muted); margin-top: 0.18rem; }

  /* LIGHTBOX */
  .lightbox { display: none; position: fixed; inset: 0; z-index: 300; background: rgba(0,0,0,0.92); align-items: center; justify-content: center; }
  .lightbox.open { display: flex; }
  .lightbox img { max-width: 90vw; max-height: 84vh; object-fit: contain; border-radius: 6px; }
  .lb-close { position: absolute; top: 1.2rem; right: 1.5rem; background: none; border: none; color: rgba(255,255,255,0.7); font-size: 2rem; cursor: pointer; }
  .lb-prev, .lb-next { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(255,255,255,0.12); border: none; color: white; font-size: 1.5rem; padding: 0.75rem 1rem; cursor: pointer; border-radius: 6px; transition: background 0.2s; }
  .lb-prev:hover, .lb-next:hover { background: rgba(255,255,255,0.25); }
  .lb-prev { left: 1rem; } .lb-next { right: 1rem; }
  .lb-counter { position: absolute; bottom: 1.2rem; color: rgba(255,255,255,0.5); font-size: 0.82rem; }

  /* TOAST */
  .toast { position: fixed; bottom: 2rem; right: 2rem; z-index: 400; background: var(--ink); color: var(--cream); padding: 0.88rem 1.35rem; border-radius: 8px; font-size: 0.86rem; font-weight: 500; transform: translateY(130%); transition: transform 0.3s; border-left: 4px solid var(--gold); max-width: 310px; }
  .toast.show { transform: translateY(0); }

  /* FOOTER */
  footer { background: var(--ink); color: rgba(245,240,232,0.42); padding: 3rem 5%; }
  .footer-inner { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 3rem; }
  @media(max-width:640px){ .footer-inner { grid-template-columns: 1fr; gap: 2rem; } }
  .footer-logo { font-family: 'Playfair Display', serif; font-size: 1.45rem; font-weight: 900; color: var(--cream); margin-bottom: 0.55rem; }
  .footer-logo span { color: var(--gold); }
  .footer-tagline { font-size: 0.83rem; line-height: 1.65; max-width: 32ch; }
  .footer-col h5 { color: var(--cream); font-size: 0.76rem; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; margin-bottom: 0.95rem; }
  .footer-col a, .footer-col p { display: block; color: rgba(245,240,232,0.42); text-decoration: none; font-size: 0.83rem; margin-bottom: 0.52rem; transition: color 0.2s; line-height: 1.55; }
  .footer-col a:hover { color: var(--gold); }
  .footer-bottom { margin-top: 2.5rem; padding-top: 1.4rem; border-top: 1px solid rgba(255,255,255,0.08); text-align: center; font-size: 0.76rem; }
</style>
</head>
<body>

<!-- CONTACT BAR -->
<div class="contact-bar">
  <span class="contact-bar-left">📍 257 Rifle Range Road, Haddon, Johannesburg South</span>
  <div class="contact-bar-right">
    <a href="tel:+27747039943">📞 +27 74 703 9943</a>
    <a href="mailto:aidan4558@gmail.com">✉️ aidan4558@gmail.com</a>
  </div>
</div>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#home">Prime<span>Hold</span></a>
  <button class="nav-ham" onclick="document.getElementById('navLinks').classList.toggle('open')">☰</button>
  <ul class="nav-links" id="navLinks">
    <li><a href="#listings">Available Units</a></li>
    <li><a href="#pawn">Pawn Services</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#admin" class="nav-cta">Admin</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <span class="hero-tag">Property Rentals &amp; Asset Finance · Johannesburg</span>
  <h1>Find Your Next <em>Home.</em> Unlock Your Assets.</h1>
  <p class="hero-sub">Premium rental units across Johannesburg — and a fast, fair pawn service for vehicles &amp; valuables when you need cash quickly.</p>
  <div class="hero-actions">
    <a href="#listings" class="btn-primary">Browse Available Units</a>
    <a href="#pawn" class="btn-outline">Pawn Your Assets</a>
  </div>
  <div class="hero-stats">
    <div class="stat-item"><h3 id="heroStat">0</h3><p>Available Units</p></div>
    <div class="stat-item"><h3>24h</h3><p>Pawn Turnaround</p></div>
    <div class="stat-item"><h3>100%</h3><p>Secure &amp; Trusted</p></div>
  </div>
</section>

<!-- LISTINGS -->
<section id="listings">
  <div class="section-label">Available Now</div>
  <h2 class="section-title">Rental Units</h2>
  <p class="section-sub">Browse our current portfolio. Filter by type, location, or budget and enquire directly.</p>
  <div class="filter-bar">
    <select id="fType" onchange="renderPublic()"><option value="">All Types</option><option>Apartment</option><option>House</option><option>Studio</option><option>Townhouse</option><option>Commercial</option></select>
    <input type="number" id="fMax" placeholder="Max Rent (R)" oninput="renderPublic()">
    <select id="fBeds" onchange="renderPublic()"><option value="">Any Beds</option><option value="1">1+ Bed</option><option value="2">2+ Beds</option><option value="3">3+ Beds</option><option value="4">4+ Beds</option></select>
    <select id="fStat" onchange="renderPublic()"><option value="Available">Available Only</option><option value="">All Statuses</option><option value="Pending">Pending</option></select>
  </div>
  <div class="units-grid" id="publicGrid"></div>
</section>

<!-- PAWN -->
<section id="pawn">
  <div class="section-label">Fast Cash</div>
  <h2 class="section-title">Pawn Your Vehicle<br>&amp; Valuables</h2>
  <p class="section-sub">Need quick cash? Bring us your car, jewellery, electronics, or other valuables and get a fair offer in minutes.</p>
  <div class="pawn-layout">
    <div class="pawn-features">
      <div class="pawn-feature"><div class="pawn-icon">🚗</div><div><h4>Vehicles</h4><p>Cars, bakkies, motorbikes &amp; more. Get cash while we hold your vehicle safely.</p></div></div>
      <div class="pawn-feature"><div class="pawn-icon">💎</div><div><h4>Jewellery &amp; Watches</h4><p>Gold, diamonds, luxury timepieces — professionally assessed at market value.</p></div></div>
      <div class="pawn-feature"><div class="pawn-icon">📱</div><div><h4>Electronics</h4><p>Phones, laptops, cameras. Quick assessment, same-day payout.</p></div></div>
      <div class="pawn-feature"><div class="pawn-icon">🏆</div><div><h4>Other Valuables</h4><p>Artwork, collectibles, tools — if it has value, we'll make an offer.</p></div></div>
      <div class="pawn-feature"><div class="pawn-icon">🔒</div><div><h4>Safe &amp; Secure Storage</h4><p>Your assets are fully insured and stored in our secure facility while on loan.</p></div></div>
    </div>
    <div class="light-form">
      <h3>Request a Pawn Quote</h3>
      <div class="lf-g"><label>Your Name</label><input type="text" id="pawnName" placeholder="Full name"></div>
      <div class="lf-row">
        <div class="lf-g"><label>Phone</label><input type="tel" id="pawnPhone" placeholder="+27 ..."></div>
        <div class="lf-g"><label>Email</label><input type="email" id="pawnEmail" placeholder="you@email.com"></div>
      </div>
      <div class="lf-g"><label>Item Category</label>
        <select id="pawnCat"><option value="">Select category</option><option>Vehicle</option><option>Jewellery / Watch</option><option>Electronics</option><option>Artwork / Collectibles</option><option>Tools / Equipment</option><option>Other</option></select>
      </div>
      <div class="lf-g"><label>Item Description</label><textarea id="pawnDesc" placeholder="Make, model, year, condition…"></textarea></div>
      <div class="lf-row">
        <div class="lf-g"><label>Est. Value (R)</label><input type="number" id="pawnVal" placeholder="e.g. 50000"></div>
        <div class="lf-g"><label>Cash Needed (R)</label><input type="number" id="pawnAmt" placeholder="e.g. 20000"></div>
      </div>
      <button class="btn-dark" onclick="submitPawn()">Submit Quote Request</button>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-label">Get In Touch</div>
  <h2 class="section-title">Contact Us</h2>
  <p class="section-sub">We're here to help — whether you're looking for a rental or need quick cash for your valuables.</p>
  <div class="contact-grid">
    <div class="contact-card">
      <div class="contact-icon">📍</div>
      <h4>Office Address</h4>
      <p>257 Rifle Range Road<br>Haddon, Johannesburg South</p>
    </div>
    <div class="contact-card">
      <div class="contact-icon">📞</div>
      <h4>Phone</h4>
      <a href="tel:+27747039943">+27 74 703 9943</a>
      <p style="font-size:0.76rem;margin-top:0.1rem">Mon–Fri 8am–5pm · Sat 9am–1pm</p>
    </div>
    <div class="contact-card">
      <div class="contact-icon">✉️</div>
      <h4>Email</h4>
      <a href="mailto:aidan4558@gmail.com">aidan4558@gmail.com</a>
      <p style="font-size:0.76rem;margin-top:0.1rem">We respond within 24 hours</p>
    </div>
  </div>
</section>

<!-- ADMIN -->
<section id="admin">
  <div class="section-label">Management Portal</div>
  <h2 class="section-title">Admin Panel</h2>
  <p class="section-sub">Add rental listings with photos and review all enquiries and pawn requests.</p>
  <div class="tab-toggle">
    <button class="tab-btn active" onclick="switchTab('tListings',this)">🏠 Listings</button>
    <button class="tab-btn" onclick="switchTab('tEnquiries',this)">📩 Enquiries</button>
    <button class="tab-btn" onclick="switchTab('tPawns',this)">💰 Pawn Requests</button>
  </div>

  <div id="tListings" class="tab-panel active">
    <div class="admin-grid">
      <div class="admin-card">
        <h3>➕ Add New Unit</h3>
        <div class="af-g"><label>Unit Name / Title</label><input type="text" id="uName" placeholder="e.g. Bright 2-Bed in Haddon"></div>
        <div class="af-row">
          <div class="af-g"><label>Type</label><select id="uType"><option>Apartment</option><option>House</option><option>Studio</option><option>Townhouse</option><option>Commercial</option></select></div>
          <div class="af-g"><label>Status</label><select id="uStatus"><option>Available</option><option>Pending</option><option>Rented</option></select></div>
        </div>
        <div class="af-g"><label>Location / Address</label><input type="text" id="uLoc" placeholder="e.g. Haddon, Johannesburg South"></div>
        <div class="af-row">
          <div class="af-g"><label>Bedrooms</label><input type="number" id="uBeds" placeholder="2" min="0"></div>
          <div class="af-g"><label>Bathrooms</label><input type="number" id="uBaths" placeholder="1" min="0"></div>
        </div>
        <div class="af-row">
          <div class="af-g"><label>Size (m²)</label><input type="number" id="uSize" placeholder="65"></div>
          <div class="af-g"><label>Monthly Rent (R)</label><input type="number" id="uRent" placeholder="8500"></div>
        </div>
        <div class="af-g"><label>Description</label><textarea id="uDesc" placeholder="Key features, amenities, parking…"></textarea></div>
        <div class="af-g">
          <label>Photos (up to 8)</label>
          <div class="photo-upload-wrap">
            <input type="file" id="photoInput" accept="image/*" multiple onchange="handlePhotos(event)">
            <div class="upload-icon">📸</div>
            <p class="upload-hint">Click to upload · <strong>JPG, PNG, WEBP</strong> · Max 8 photos</p>
          </div>
          <div class="photo-previews-admin" id="photoPreviews"></div>
        </div>
        <button class="btn-gold" onclick="addUnit()">Add Unit to Listings</button>
      </div>
      <div class="admin-card">
        <h3>📋 Current Listings</h3>
        <div style="overflow-x:auto">
          <table class="tbl">
            <thead><tr><th>Photo</th><th>Unit</th><th>Rent</th><th>Status</th><th></th></tr></thead>
            <tbody id="adminTbody"><tr><td colspan="5" class="empty-row">No units yet — add one!</td></tr></tbody>
          </table>
        </div>
      </div>
    </div>
  </div>

  <div id="tEnquiries" class="tab-panel">
    <div class="admin-card" style="max-width:860px">
      <h3>📩 Rental Enquiries</h3>
      <div id="enqList"><div class="empty-row">No enquiries yet.</div></div>
    </div>
  </div>

  <div id="tPawns" class="tab-panel">
    <div class="admin-card" style="max-width:860px">
      <h3>💰 Pawn Quote Requests</h3>
      <div id="pawnList"><div class="empty-row">No pawn requests yet.</div></div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-logo">Prime<span>Hold</span></div>
      <p class="footer-tagline">Property Rentals &amp; Asset Finance in Johannesburg South. Trusted, transparent, and always here to help.</p>
    </div>
    <div class="footer-col">
      <h5>Quick Links</h5>
      <a href="#listings">Available Units</a>
      <a href="#pawn">Pawn Services</a>
      <a href="#contact">Contact</a>
      <a href="#admin">Admin Panel</a>
    </div>
    <div class="footer-col">
      <h5>Contact</h5>
      <a href="tel:+27747039943">+27 74 703 9943</a>
      <a href="mailto:aidan4558@gmail.com">aidan4558@gmail.com</a>
      <p>257 Rifle Range Road<br>Haddon, JHB South</p>
    </div>
  </div>
  <div class="footer-bottom">© 2025 PrimeHold · All rights reserved</div>
</footer>

<!-- ENQUIRY MODAL -->
<div class="modal-overlay" id="enquiryModal">
  <div class="modal">
    <div class="modal-head">
      <h2>Enquire About Unit</h2>
      <button class="modal-close" onclick="closeModal()">✕</button>
    </div>
    <div class="modal-unit-box" id="modalInfo"></div>
    <div class="lf-g"><label>Your Name</label><input type="text" id="eqName" placeholder="Full name"></div>
    <div class="lf-row">
      <div class="lf-g"><label>Phone</label><input type="tel" id="eqPhone" placeholder="+27 ..."></div>
      <div class="lf-g"><label>Email</label><input type="email" id="eqEmail" placeholder="you@email.com"></div>
    </div>
    <div class="lf-g"><label>Message</label><textarea id="eqMsg" placeholder="Move-in date, questions…"></textarea></div>
    <button class="btn-dark" onclick="submitEnquiry()">Send Enquiry</button>
  </div>
</div>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox">
  <button class="lb-close" onclick="closeLb()">✕</button>
  <button class="lb-prev" onclick="lbNav(-1)">&#8249;</button>
  <img id="lbImg" src="" alt="Property photo">
  <button class="lb-next" onclick="lbNav(1)">&#8250;</button>
  <span class="lb-counter" id="lbCnt"></span>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
// STATE
let units     = JSON.parse(localStorage.getItem('ph_units') || '[]');
let enquiries = JSON.parse(localStorage.getItem('ph_enq')   || '[]');
let pawnReqs  = JSON.parse(localStorage.getItem('ph_pawn')  || '[]');
let pendingPh = [];
let curUnit   = null;
let lbPh = [], lbIdx = 0;
const EM = { Apartment:'🏢', House:'🏡', Studio:'🛋️', Townhouse:'🏘️', Commercial:'🏬' };

function save() {
  localStorage.setItem('ph_units', JSON.stringify(units));
  localStorage.setItem('ph_enq',   JSON.stringify(enquiries));
  localStorage.setItem('ph_pawn',  JSON.stringify(pawnReqs));
}

function toast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg; t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 3500);
}

function switchTab(id, btn) {
  document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  btn.classList.add('active');
}

// PHOTOS
function handlePhotos(e) {
  const files = Array.from(e.target.files);
  const left = 8 - pendingPh.length;
  files.slice(0, left).forEach(f => {
    const r = new FileReader();
    r.onload = ev => { pendingPh.push(ev.target.result); renderPreviews(); };
    r.readAsDataURL(f);
  });
  if (files.length > left) toast('⚠️ Max 8 photos per unit');
  e.target.value = '';
}

function renderPreviews() {
  document.getElementById('photoPreviews').innerHTML = pendingPh.map((s, i) => `
    <div class="prev-wrap">
      <img class="prev-thumb" src="${s}" alt="">
      <button class="prev-rm" onclick="rmPhoto(${i})">✕</button>
    </div>`).join('');
}

function rmPhoto(i) { pendingPh.splice(i, 1); renderPreviews(); }

// ADD UNIT
function addUnit() {
  const name   = document.getElementById('uName').value.trim();
  const type   = document.getElementById('uType').value;
  const status = document.getElementById('uStatus').value;
  const loc    = document.getElementById('uLoc').value.trim();
  const beds   = document.getElementById('uBeds').value;
  const baths  = document.getElementById('uBaths').value;
  const size   = document.getElementById('uSize').value;
  const rent   = document.getElementById('uRent').value;
  const desc   = document.getElementById('uDesc').value.trim();
  if (!name || !loc || !rent) { toast('⚠️ Name, Location and Rent are required'); return; }
  units.push({ id: Date.now(), name, type, status, loc, beds, baths, size, rent: Number(rent), desc, photos: [...pendingPh] });
  pendingPh = []; renderPreviews(); save(); renderAll();
  toast('✅ Unit added successfully!');
  ['uName','uLoc','uBeds','uBaths','uSize','uRent','uDesc'].forEach(id => document.getElementById(id).value = '');
}

function deleteUnit(id) {
  if (!confirm('Remove this unit?')) return;
  units = units.filter(u => u.id !== id);
  save(); renderAll(); toast('🗑️ Unit removed.');
}

function badge(s) {
  const c = s==='Available'?'badge-available':s==='Pending'?'badge-pending':'badge-rented';
  return `<span class="badge ${c}">${s}</span>`;
}

// RENDER ADMIN
function renderAdmin() {
  const tb = document.getElementById('adminTbody');
  if (!units.length) { tb.innerHTML = '<tr><td colspan="5" class="empty-row">No units yet — add one!</td></tr>'; return; }
  tb.innerHTML = units.map(u => `
    <tr>
      <td>${u.photos&&u.photos.length?`<img class="tbl-thumb" src="${u.photos[0]}" alt="">`: `<span class="tbl-ph">${EM[u.type]||'🏠'}</span>`}</td>
      <td><strong>${u.name}</strong><br><span style="color:rgba(245,240,232,0.3);font-size:0.74rem">${u.loc}</span></td>
      <td style="font-weight:700">R ${u.rent.toLocaleString()}</td>
      <td>${badge(u.status)}</td>
      <td><button class="del-btn" onclick="deleteUnit(${u.id})">🗑️</button></td>
    </tr>`).join('');
}

// RENDER PUBLIC
function renderPublic() {
  const fT = document.getElementById('fType').value;
  const fM = parseFloat(document.getElementById('fMax').value)||Infinity;
  const fB = document.getElementById('fBeds').value;
  const fS = document.getElementById('fStat').value;
  let list = units.filter(u => {
    if (fT && u.type!==fT) return false;
    if (u.rent>fM) return false;
    if (fB && Number(u.beds)<Number(fB)) return false;
    if (fS && u.status!==fS) return false;
    return true;
  });
  const g = document.getElementById('publicGrid');
  if (!list.length) { g.innerHTML='<div class="no-units">😕 No units match your filters. Try adjusting!</div>'; }
  else {
    g.innerHTML = list.map((u,i)=>{
      const hasPh = u.photos&&u.photos.length>0;
      const imgH = hasPh
        ? `<img src="${u.photos[0]}" alt="${u.name}" style="width:100%;height:100%;object-fit:cover;display:block" onclick="openLb(${u.id},0,event)">`
        : `<span class="unit-emoji">${EM[u.type]||'🏠'}</span>`;
      const pill = hasPh&&u.photos.length>1 ? `<span class="photo-pill">📷 ${u.photos.length}</span>` : '';
      return `
        <div class="unit-card" style="animation-delay:${i*0.06}s">
          <div class="unit-img">${imgH}<div class="unit-status-badge">${badge(u.status)}</div>${pill}</div>
          <div class="unit-body">
            <div class="unit-type-tag">${u.type}</div>
            <div class="unit-name">${u.name}</div>
            <div class="unit-loc">📍 ${u.loc}</div>
            <div class="unit-feats">
              ${u.beds?`<span>🛏 ${u.beds} Bed${u.beds>1?'s':''}</span>`:''}
              ${u.baths?`<span>🚿 ${u.baths} Bath${u.baths>1?'s':''}</span>`:''}
              ${u.size?`<span>📐 ${u.size}m²</span>`:''}
            </div>
            ${u.desc?`<p class="unit-desc">${u.desc.slice(0,110)}${u.desc.length>110?'…':''}</p>`:''}
            <div class="unit-price-row">
              <div><span class="price-amt">R ${u.rent.toLocaleString()}</span><span class="price-per">/month</span></div>
              <button class="enq-btn" onclick="openModal(${u.id})" ${u.status==='Rented'?'disabled':''}>
                ${u.status==='Rented'?'Rented':'Enquire'}
              </button>
            </div>
          </div>
        </div>`;
    }).join('');
  }
  document.getElementById('heroStat').textContent = units.filter(u=>u.status==='Available').length;
}

// RENDER ENQUIRIES
function renderEnq() {
  const el = document.getElementById('enqList');
  if (!enquiries.length) { el.innerHTML='<div class="empty-row">No enquiries yet.</div>'; return; }
  el.innerHTML = enquiries.slice().reverse().map(e=>`
    <div class="enq-card">
      <div class="enq-head"><div><span class="enq-name">${e.name}</span><span class="enq-unit">→ ${e.unitName}</span></div><span class="enq-date">${e.date}</span></div>
      <div class="enq-contact">📞 ${e.phone} &nbsp; ✉️ ${e.email}</div>
      ${e.msg?`<div class="enq-msg">"${e.msg}"</div>`:''}
    </div>`).join('');
}

// RENDER PAWN LIST
function renderPawnList() {
  const el = document.getElementById('pawnList');
  if (!pawnReqs.length) { el.innerHTML='<div class="empty-row">No pawn requests yet.</div>'; return; }
  el.innerHTML = pawnReqs.slice().reverse().map(p=>`
    <div class="enq-card">
      <div class="enq-head">
        <div><span class="enq-name">${p.name}</span><span style="background:rgba(201,168,76,0.16);color:var(--gold);padding:.13rem .52rem;border-radius:10px;font-size:.71rem;margin-left:.55rem;font-weight:700">${p.cat}</span></div>
        <span class="enq-date">${p.date}</span>
      </div>
      <div class="enq-contact">📞 ${p.phone} &nbsp; ✉️ ${p.email}</div>
      <div style="color:rgba(245,240,232,0.55);font-size:.81rem;margin-top:.38rem">${p.desc}</div>
      <div style="display:flex;gap:2rem;margin-top:.45rem;font-size:.81rem">
        ${p.val?`<span style="color:var(--gold)">Est. Value: R ${Number(p.val).toLocaleString()}</span>`:''}
        ${p.amt?`<span style="color:#6db56d">Needs: R ${Number(p.amt).toLocaleString()}</span>`:''}
      </div>
    </div>`).join('');
}

function renderAll() { renderAdmin(); renderPublic(); renderEnq(); renderPawnList(); }

// MODAL
function openModal(id) {
  curUnit = units.find(u=>u.id===id);
  if (!curUnit) return;
  document.getElementById('modalInfo').innerHTML=`<h3>${curUnit.name}</h3><p>${curUnit.type} · ${curUnit.loc} · R ${curUnit.rent.toLocaleString()}/mo</p>`;
  ['eqName','eqPhone','eqEmail','eqMsg'].forEach(i=>document.getElementById(i).value='');
  document.getElementById('enquiryModal').classList.add('open');
}
function closeModal() { document.getElementById('enquiryModal').classList.remove('open'); curUnit=null; }
document.getElementById('enquiryModal').addEventListener('click',e=>{ if(e.target===document.getElementById('enquiryModal')) closeModal(); });

function submitEnquiry() {
  const name=document.getElementById('eqName').value.trim();
  const phone=document.getElementById('eqPhone').value.trim();
  const email=document.getElementById('eqEmail').value.trim();
  const msg=document.getElementById('eqMsg').value.trim();
  if(!name||!phone||!email){toast('⚠️ Name, Phone & Email required');return;}
  enquiries.push({unitId:curUnit.id,unitName:curUnit.name,name,phone,email,msg,date:new Date().toLocaleDateString('en-ZA',{day:'numeric',month:'short',year:'numeric'})});
  save(); renderEnq(); closeModal();
  toast('✅ Enquiry sent! We\'ll be in touch soon.');
}

// PAWN SUBMIT
function submitPawn() {
  const name=document.getElementById('pawnName').value.trim();
  const phone=document.getElementById('pawnPhone').value.trim();
  const email=document.getElementById('pawnEmail').value.trim();
  const cat=document.getElementById('pawnCat').value;
  const desc=document.getElementById('pawnDesc').value.trim();
  const val=document.getElementById('pawnVal').value;
  const amt=document.getElementById('pawnAmt').value;
  if(!name||!phone||!email||!cat||!desc){toast('⚠️ Please fill in all required fields');return;}
  pawnReqs.push({name,phone,email,cat,desc,val,amt,date:new Date().toLocaleDateString('en-ZA',{day:'numeric',month:'short',year:'numeric'})});
  save(); renderPawnList();
  ['pawnName','pawnPhone','pawnEmail','pawnDesc','pawnVal','pawnAmt'].forEach(i=>document.getElementById(i).value='');
  document.getElementById('pawnCat').value='';
  toast('✅ Quote submitted! We\'ll contact you within 24 hours.');
}

// LIGHTBOX
function openLb(unitId, idx, e) {
  if(e) e.stopPropagation();
  const u=units.find(u=>u.id===unitId);
  if(!u||!u.photos||!u.photos.length) return;
  lbPh=u.photos; lbIdx=idx; showLb();
  document.getElementById('lightbox').classList.add('open');
}
function showLb() {
  document.getElementById('lbImg').src=lbPh[lbIdx];
  document.getElementById('lbCnt').textContent=`${lbIdx+1} / ${lbPh.length}`;
  document.querySelector('.lb-prev').style.display=lbPh.length>1?'':'none';
  document.querySelector('.lb-next').style.display=lbPh.length>1?'':'none';
}
function lbNav(d) { lbIdx=(lbIdx+d+lbPh.length)%lbPh.length; showLb(); }
function closeLb() { document.getElementById('lightbox').classList.remove('open'); }
document.getElementById('lightbox').addEventListener('click',e=>{ if(e.target===document.getElementById('lightbox')) closeLb(); });
document.addEventListener('keydown',e=>{
  if(!document.getElementById('lightbox').classList.contains('open')) return;
  if(e.key==='ArrowLeft') lbNav(-1);
  if(e.key==='ArrowRight') lbNav(1);
  if(e.key==='Escape') closeLb();
});

renderAll();
</script>
</body>
</html>
