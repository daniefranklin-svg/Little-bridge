# Little-bridge
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Little Bridge Charitable NGO — Transforming Lives. Restoring Hope.</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Source+Serif+4:ital,opsz,wght@0,8..60,300;0,8..60,400;1,8..60,300&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #2A7BAB;
    --green-light: #4A9CC7;
    --green-pale: #E3F2FA;
    --gold: #1A5F80;
    --bark: #1A3245;
    --cream: #F4F9FD;
    --sand: #E8F3FA;
    --text: #0F2233;
    --muted: #5A7A90;
    --border: rgba(42,123,171,0.15);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body { font-family: 'Source Serif 4', Georgia, serif; background: var(--cream); color: var(--text); overflow-x: hidden; }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 4rem;
    background: rgba(250,250,246,0.95); backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    display: flex; align-items: center; gap: 0.7rem;
    font-family: 'Playfair Display', serif; font-size: 1.3rem;
    color: var(--bark); text-decoration: none;
  }
  .nav-logo span { color: var(--green); font-style: italic; }
  .nav-links { display: flex; gap: 2.2rem; list-style: none; align-items: center; }
  .nav-links a {
    font-size: 0.84rem; letter-spacing: 0.07em; text-transform: uppercase;
    color: var(--bark); text-decoration: none; position: relative;
    transition: color 0.3s; font-weight: 300;
  }
  .nav-links a::after {
    content: ''; position: absolute; bottom: -3px; left: 0; right: 0;
    height: 1.5px; background: var(--green); transform: scaleX(0); transition: transform 0.3s;
  }
  .nav-links a:hover { color: var(--green); }
  .nav-links a:hover::after { transform: scaleX(1); }
  .nav-cta { background: var(--green) !important; color: white !important; padding: 0.6rem 1.5rem; border-radius: 2px; }
  .nav-cta::after { display: none !important; }
  .nav-cta:hover { background: var(--bark) !important; }

  /* HERO */
  #home {
    min-height: 100vh; display: grid; grid-template-columns: 1fr 1fr;
    padding-top: 72px; overflow: hidden; position: relative;
  }
  .hero-bg {
    position: absolute; inset: 0; pointer-events: none;
    background: radial-gradient(ellipse at 15% 70%, rgba(58,125,92,0.07) 0%, transparent 55%),
                radial-gradient(ellipse at 85% 15%, rgba(200,146,42,0.05) 0%, transparent 50%);
  }
  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 5rem 3.5rem 5rem 4rem; position: relative; z-index: 1;
  }
  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 0.6rem;
    font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase;
    color: var(--green); margin-bottom: 1.6rem;
    animation: fadeUp 0.8s ease both;
  }
  .hero-eyebrow::before { content: ''; width: 28px; height: 1px; background: var(--green); }
  .hero-h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.6rem, 4vw, 4.4rem); line-height: 1.1;
    color: var(--bark); margin-bottom: 1.4rem;
    animation: fadeUp 0.8s 0.1s ease both;
  }
  .hero-h1 em { color: var(--green); font-style: italic; }
  .hero-desc {
    font-size: 1.05rem; font-weight: 300; line-height: 1.78;
    color: var(--muted); max-width: 440px; margin-bottom: 0.9rem;
    animation: fadeUp 0.8s 0.2s ease both;
  }
  .hero-quote-inline {
    font-size: 0.9rem; font-style: italic; color: var(--muted);
    border-left: 2px solid var(--gold); padding-left: 1rem; margin-bottom: 2.8rem;
    animation: fadeUp 0.8s 0.28s ease both;
  }
  .hero-actions {
    display: flex; gap: 1rem; margin-bottom: 3.2rem;
    animation: fadeUp 0.8s 0.35s ease both;
  }
  .btn-primary {
    background: var(--green); color: white; padding: 1rem 2.2rem;
    border: none; border-radius: 2px; font-family: 'Source Serif 4', serif;
    font-size: 0.88rem; letter-spacing: 0.07em; text-transform: uppercase;
    cursor: pointer; text-decoration: none; transition: background 0.3s, transform 0.2s; display: inline-block;
  }
  .btn-primary:hover { background: var(--bark); transform: translateY(-1px); }
  .btn-outline {
    border: 1.5px solid var(--green); color: var(--green);
    padding: 0.95rem 2rem; border-radius: 2px; font-family: 'Source Serif 4', serif;
    font-size: 0.88rem; letter-spacing: 0.07em; text-transform: uppercase;
    cursor: pointer; text-decoration: none; transition: all 0.3s; display: inline-block;
  }
  .btn-outline:hover { background: var(--green); color: white; }
  .hero-pillars {
    display: flex; border: 1px solid var(--border);
    animation: fadeUp 0.8s 0.5s ease both;
  }
  .pillar-chip {
    flex: 1; padding: 1rem 0.8rem; text-align: center;
    border-right: 1px solid var(--border); background: white;
  }
  .pillar-chip:last-child { border-right: none; }
  .pillar-chip .picon { font-size: 1.4rem; display: block; margin-bottom: 0.3rem; }
  .pillar-chip .ptitle { font-size: 0.7rem; letter-spacing: 0.06em; text-transform: uppercase; color: var(--green); line-height: 1.3; }
  .hero-right { position: relative; overflow: hidden; animation: fadeIn 1.2s 0.2s ease both; }
  .hero-right img { width: 100%; height: 100%; object-fit: cover; filter: saturate(0.85); }
  .hero-overlay { position: absolute; inset: 0; background: linear-gradient(135deg, rgba(58,125,92,0.18) 0%, transparent 60%); }
  .founder-card {
    position: absolute; bottom: 2.5rem; left: -2rem;
    background: white; padding: 1.4rem 1.6rem;
    border-left: 3px solid var(--green);
    box-shadow: 0 8px 36px rgba(30,45,34,0.13); max-width: 265px;
  }
  .founder-card p { font-family: 'Playfair Display', serif; font-style: italic; font-size: 0.93rem; color: var(--bark); line-height: 1.55; margin-bottom: 0.6rem; }
  .founder-card cite { font-size: 0.7rem; letter-spacing: 0.09em; text-transform: uppercase; color: var(--green); font-style: normal; }

  /* IMPACT BAND */
  .impact-band {
    background: var(--bark); padding: 4rem;
    display: grid; grid-template-columns: repeat(5, 1fr); gap: 1.5rem; text-align: center;
  }
  .impact-num { font-family: 'Playfair Display', serif; font-size: 2.4rem; color: var(--gold); display: block; line-height: 1; }
  .impact-label { font-size: 0.74rem; letter-spacing: 0.08em; text-transform: uppercase; color: rgba(255,255,255,0.5); margin-top: 0.45rem; display: block; line-height: 1.4; }

  /* SHARED */
  .section-eyebrow {
    font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase;
    color: var(--green); display: flex; align-items: center; gap: 0.6rem; margin-bottom: 0.8rem;
  }
  .section-eyebrow::before { content: ''; width: 28px; height: 1px; background: var(--green); }
  .section-title { font-family: 'Playfair Display', serif; font-size: clamp(1.9rem, 2.8vw, 2.8rem); color: var(--bark); line-height: 1.15; margin-bottom: 1.3rem; }
  .section-title em { color: var(--green); font-style: italic; }

  /* ABOUT */
  #about { background: var(--sand); display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; padding: 7rem 4rem; }
  .about-left p { font-size: 1rem; font-weight: 300; line-height: 1.82; color: var(--muted); margin-bottom: 1rem; }
  .commitment-list { margin-top: 1.8rem; display: flex; flex-direction: column; gap: 0.55rem; }
  .commitment-item { display: flex; align-items: flex-start; gap: 0.75rem; font-size: 0.93rem; color: var(--text); line-height: 1.5; }
  .tick { color: var(--green); font-size: 1rem; margin-top: 0.05rem; flex-shrink: 0; }
  .vision-card { background: var(--green); color: white; padding: 2rem 2.2rem; margin-bottom: 1.5rem; }
  .vision-card .vlabel { font-size: 0.72rem; letter-spacing: 0.14em; text-transform: uppercase; color: rgba(255,255,255,0.65); margin-bottom: 0.7rem; display: block; }
  .vision-card p { font-family: 'Playfair Display', serif; font-style: italic; font-size: 1.08rem; line-height: 1.6; }
  .mission-card { background: white; padding: 2rem 2.2rem; border-left: 3px solid var(--gold); }
  .mission-card .mlabel { font-size: 0.72rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.8rem; display: block; }
  .mission-card p { font-size: 0.92rem; color: var(--muted); margin-bottom: 0.5rem; line-height: 1.6; }
  .mp { font-size: 0.88rem; color: var(--text); line-height: 1.55; margin-top: 0.5rem; }
  .mp strong { color: var(--green); }

  /* PROGRAMS */
  #programs { padding: 7rem 4rem; background: var(--cream); }
  .programs-intro { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: end; margin-bottom: 4rem; }
  .programs-intro p { font-size: 1rem; font-weight: 300; line-height: 1.8; color: var(--muted); }
  .pillar-tabs { display: flex; margin-bottom: 3rem; border: 1px solid var(--border); width: fit-content; }
  .ptab {
    padding: 0.7rem 1.6rem; cursor: pointer; font-size: 0.8rem; letter-spacing: 0.07em;
    text-transform: uppercase; color: var(--muted); background: white; border: none;
    border-right: 1px solid var(--border); font-family: 'Source Serif 4', serif; transition: all 0.2s;
  }
  .ptab:last-child { border-right: none; }
  .ptab.active, .ptab:hover { background: var(--green); color: white; }
  .pillar-panel { display: none; }
  .pillar-panel.active { display: block; }
  .pillar-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 2rem; }
  .pillar-badge { background: var(--green); color: white; font-size: 0.7rem; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.35rem 0.9rem; }
  .pillar-header h2 { font-family: 'Playfair Display', serif; font-size: 1.65rem; color: var(--bark); }
  .programs-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
  .prog-card { background: white; border: 1px solid var(--border); padding: 1.6rem 1.8rem; transition: transform 0.3s, box-shadow 0.3s; }
  .prog-card:hover { transform: translateY(-3px); box-shadow: 0 8px 32px rgba(30,45,34,0.08); }
  .prog-id { display: inline-block; background: var(--green-pale); color: var(--green); font-size: 0.69rem; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.2rem 0.6rem; margin-bottom: 0.8rem; }
  .prog-card h3 { font-family: 'Playfair Display', serif; font-size: 1.05rem; color: var(--bark); margin-bottom: 0.8rem; line-height: 1.4; }
  .prog-card ul { list-style: none; margin-bottom: 1rem; }
  .prog-card ul li { font-size: 0.85rem; color: var(--muted); line-height: 1.6; padding-left: 1rem; position: relative; }
  .prog-card ul li::before { content: '·'; position: absolute; left: 0; color: var(--green); font-size: 1.2rem; line-height: 1.2; }
  .prog-impact { font-size: 0.8rem; color: var(--green); border-top: 1px solid var(--border); padding-top: 0.8rem; margin-top: 0.8rem; line-height: 1.5; }
  .prog-impact strong { display: block; margin-bottom: 0.2rem; color: var(--bark); }

  /* PARTNER */
  #partner { background: var(--bark); padding: 6rem 4rem; display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
  #partner .section-eyebrow { color: var(--gold); }
  #partner .section-eyebrow::before { background: var(--gold); }
  #partner .section-title { color: white; }
  .partner-sub { font-size: 1rem; font-weight: 300; color: rgba(255,255,255,0.6); line-height: 1.75; margin-bottom: 2rem; font-style: italic; }
  .partner-list { display: flex; flex-direction: column; gap: 1rem; }
  .partner-item { display: flex; gap: 1rem; align-items: flex-start; background: rgba(255,255,255,0.05); padding: 1rem 1.2rem; border-left: 2px solid var(--gold); }
  .partner-item .pico { font-size: 1.2rem; flex-shrink: 0; margin-top: 0.1rem; }
  .partner-item span { font-size: 0.9rem; color: rgba(255,255,255,0.75); line-height: 1.55; }

  /* DONATE */
  #donate { background: var(--sand); padding: 7rem 4rem; display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: start; }
  .donate-text p { font-size: 1rem; font-weight: 300; line-height: 1.8; color: var(--muted); margin-bottom: 1rem; }
  .tax-badge { display: inline-block; background: var(--green-pale); border: 1px solid var(--border); color: var(--green); font-size: 0.78rem; letter-spacing: 0.08em; text-transform: uppercase; padding: 0.4rem 1rem; margin-top: 1rem; }
  .donate-form-card { background: white; padding: 2.5rem; box-shadow: 0 4px 40px rgba(30,45,34,0.07); border-top: 4px solid var(--green); }
  .donate-form-card h3 { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--bark); margin-bottom: 0.4rem; }
  .form-sub { font-size: 0.88rem; color: var(--muted); margin-bottom: 2rem; font-weight: 300; }
  .amount-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0.6rem; margin-bottom: 1rem; }
  .amount-btn { border: 1px solid var(--border); background: transparent; padding: 0.75rem; font-family: 'Source Serif 4', serif; font-size: 0.95rem; color: var(--bark); cursor: pointer; transition: all 0.2s; }
  .amount-btn:hover, .amount-btn.active { background: var(--green); color: white; border-color: var(--green); }
  .custom-input { width: 100%; padding: 0.75rem 1rem; margin-bottom: 1.4rem; border: 1px solid var(--border); font-family: 'Source Serif 4', serif; font-size: 0.95rem; color: var(--bark); outline: none; }
  .custom-input:focus { border-color: var(--green); }
  .custom-input::placeholder { color: var(--muted); }
  .donate-submit { width: 100%; padding: 1.1rem; background: var(--green); color: white; border: none; font-family: 'Source Serif 4', serif; font-size: 0.92rem; letter-spacing: 0.07em; text-transform: uppercase; cursor: pointer; transition: background 0.3s; }
  .donate-submit:hover { background: var(--bark); }
  .donate-note { text-align: center; margin-top: 1rem; font-size: 0.78rem; color: var(--muted); }

  /* CONTACT STRIP */
  .contact-strip { background: var(--green); padding: 3rem 4rem; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1.5rem; }
  .contact-strip h3 { font-family: 'Playfair Display', serif; font-size: 1.6rem; color: white; font-style: italic; }
  .contact-strip .csub { font-size: 0.9rem; color: rgba(255,255,255,0.75); margin-top: 0.3rem; }
  .contact-details { display: flex; gap: 2.5rem; flex-wrap: wrap; }
  .contact-item { display: flex; align-items: center; gap: 0.6rem; font-size: 0.88rem; color: rgba(255,255,255,0.85); }

  /* FOOTER */
  footer { background: var(--bark); color: rgba(255,255,255,0.55); padding: 3rem 4rem 2rem; }
  .footer-top { display: flex; justify-content: space-between; align-items: center; padding-bottom: 2rem; border-bottom: 1px solid rgba(255,255,255,0.08); flex-wrap: wrap; gap: 1rem; }
  .footer-brand { font-family: 'Playfair Display', serif; font-size: 1.3rem; color: white; }
  .footer-brand span { color: var(--gold); font-style: italic; }
  .footer-links { display: flex; gap: 2rem; list-style: none; }
  .footer-links a { font-size: 0.82rem; color: rgba(255,255,255,0.5); text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--gold); }
  .footer-bottom { display: flex; justify-content: space-between; padding-top: 1.5rem; font-size: 0.78rem; flex-wrap: wrap; gap: 0.5rem; }

  /* ANIMATIONS */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(22px); } to { opacity: 1; transform: translateY(0); } }
  @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

  /* RESPONSIVE */
  @media (max-width: 960px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { gap: 1rem; }
    #home, #about, #partner, #donate { grid-template-columns: 1fr; }
    .hero-right { display: none; }
    .hero-left { padding: 4rem 1.5rem; }
    #about, #programs, #partner, #donate { padding: 5rem 1.5rem; }
    .impact-band { grid-template-columns: repeat(3, 1fr); padding: 3rem 1.5rem; }
    .programs-intro { grid-template-columns: 1fr; }
    .programs-grid { grid-template-columns: 1fr 1fr; }
    .contact-strip { flex-direction: column; align-items: flex-start; padding: 2.5rem 1.5rem; }
    footer { padding: 2.5rem 1.5rem; }
    .pillar-tabs { flex-wrap: wrap; width: 100%; }
  }
  @media (max-width: 600px) {
    .programs-grid { grid-template-columns: 1fr; }
    .impact-band { grid-template-columns: repeat(2, 1fr); }
  }

  /* RECEIPT TOGGLE */
  .receipt-row { margin-bottom: 1rem; }
  .receipt-toggle { display: flex; align-items: center; gap: 0.6rem; cursor: pointer; user-select: none; }
  .receipt-toggle input[type="checkbox"] { display: none; }
  .receipt-check {
    width: 18px; height: 18px; border: 1.5px solid var(--border);
    background: white; display: flex; align-items: center; justify-content: center;
    flex-shrink: 0; transition: all 0.2s; position: relative;
  }
  .receipt-toggle input:checked + .receipt-check { background: var(--green); border-color: var(--green); }
  .receipt-toggle input:checked + .receipt-check::after {
    content: "✓"; color: white; font-size: 0.7rem; position: absolute;
  }
  .receipt-label { font-size: 0.88rem; color: var(--text); }
  .receipt-email-wrap { margin-bottom: 1.2rem; overflow: hidden; transition: max-height 0.3s ease; max-height: 60px; }
  .receipt-email-wrap.hidden { max-height: 0; }

  /* MODAL */
  .modal-overlay {
    display: none; position: fixed; inset: 0; z-index: 999;
    background: rgba(15,34,51,0.65); backdrop-filter: blur(4px);
    align-items: center; justify-content: center;
  }
  .modal-overlay.open { display: flex; }
  .modal-box {
    background: white; width: 100%; max-width: 440px; max-height: 90vh;
    overflow-y: auto; position: relative;
    box-shadow: 0 20px 60px rgba(15,34,51,0.25);
    animation: modalIn 0.25s ease;
  }
  @keyframes modalIn { from { opacity:0; transform: translateY(16px) scale(0.98); } to { opacity:1; transform: none; } }
  .modal-step { display: none; padding: 2rem 2.2rem 2rem; }
  .modal-step.active { display: block; }
  .modal-close {
    position: absolute; top: 1rem; right: 1.2rem;
    background: none; border: none; font-size: 1.1rem;
    cursor: pointer; color: var(--muted); transition: color 0.2s;
  }
  .modal-close:hover { color: var(--text); }
  .modal-header { text-align: center; margin-bottom: 1.4rem; padding-bottom: 1.2rem; border-bottom: 1px solid var(--border); }
  .modal-lock { font-size: 1.8rem; margin-bottom: 0.4rem; }
  .modal-header h3 { font-family: "Playfair Display", serif; font-size: 1.5rem; color: var(--bark); margin-bottom: 0.3rem; }
  .modal-amount-display { font-family: "Playfair Display", serif; font-size: 2rem; color: var(--green); font-weight: 700; margin: 0.2rem 0; }
  .modal-sub { font-size: 0.75rem; color: var(--muted); letter-spacing: 0.04em; }
  .stripe-notice {
    display: flex; align-items: center; justify-content: center; gap: 0.5rem;
    background: #F6F4FF; padding: 0.6rem 1rem; margin-bottom: 1.4rem;
    font-size: 0.78rem; color: #635BFF;
  }
  .card-form { display: flex; flex-direction: column; gap: 0; }
  .field-group { margin-bottom: 1rem; }
  .field-group label { display: block; font-size: 0.78rem; letter-spacing: 0.07em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.4rem; }
  .field-input {
    width: 100%; padding: 0.75rem 0.9rem; border: 1.5px solid var(--border);
    font-family: "Source Serif 4", serif; font-size: 0.95rem; color: var(--text);
    outline: none; transition: border-color 0.2s; background: white;
  }
  .field-input:focus { border-color: var(--green); }
  .card-number-wrap { display: flex; align-items: center; padding: 0 0.9rem; }
  .card-number-wrap input { border: none; outline: none; flex: 1; font-family: "Source Serif 4", serif; font-size: 0.95rem; color: var(--text); padding: 0.75rem 0; background: transparent; letter-spacing: 0.05em; }
  .card-brand { font-size: 1.3rem; flex-shrink: 0; }
  .field-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .pay-error { background: #FEF2F2; border-left: 3px solid #EF4444; color: #991B1B; font-size: 0.85rem; padding: 0.7rem 1rem; margin-bottom: 1rem; line-height: 1.5; }
  .modal-pay-btn {
    width: 100%; padding: 1rem; background: var(--green); color: white;
    border: none; font-family: "Source Serif 4", serif; font-size: 0.95rem;
    letter-spacing: 0.06em; text-transform: uppercase; cursor: pointer;
    transition: background 0.3s; margin-bottom: 0.8rem;
  }
  .modal-pay-btn:hover { background: var(--bark); }
  .modal-pay-btn:disabled { background: var(--muted); cursor: not-allowed; }
  .modal-secure-note { text-align: center; font-size: 0.75rem; color: var(--muted); line-height: 1.5; }

  /* SUCCESS STEP */
  .success-content { text-align: center; padding: 1rem 0; }
  .success-icon {
    width: 64px; height: 64px; border-radius: 50%; background: var(--green);
    color: white; font-size: 1.8rem; display: flex; align-items: center;
    justify-content: center; margin: 0 auto 1.2rem;
  }
  .success-content h3 { font-family: "Playfair Display", serif; font-size: 1.8rem; color: var(--bark); margin-bottom: 0.6rem; }
  .success-msg { font-size: 1rem; color: var(--text); margin-bottom: 0.4rem; }
  .success-sub { font-size: 0.85rem; color: var(--green); margin-bottom: 1rem; }
  .success-impact { font-size: 0.88rem; color: var(--muted); font-style: italic; line-height: 1.6; }

</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#home">
    <svg width="36" height="36" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M4 32 Q12 18 24 18 Q36 18 44 32" stroke="#2A7BAB" stroke-width="2.5" fill="none" stroke-linecap="round"/>
      <line x1="4" y1="32" x2="44" y2="32" stroke="#2A7BAB" stroke-width="2.5" stroke-linecap="round"/>
      <line x1="14" y1="32" x2="16" y2="22" stroke="#2A7BAB" stroke-width="1.5" stroke-linecap="round"/>
      <line x1="24" y1="32" x2="24" y2="18" stroke="#2A7BAB" stroke-width="1.5" stroke-linecap="round"/>
      <line x1="34" y1="32" x2="32" y2="22" stroke="#2A7BAB" stroke-width="1.5" stroke-linecap="round"/>
    </svg>
    Little <span>Bridge</span>
  </a>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#programs">Programs</a></li>
    <li><a href="#partner">Partner</a></li>
    <li><a href="#donate" class="nav-cta">Donate</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-bg"></div>
  <div class="hero-left">
    <div class="hero-eyebrow">Established 2004 · Yerevan, Armenia</div>
    <h1 class="hero-h1">Bridging the gap between<br><em>poverty</em> and<br><em>self-sufficiency</em></h1>
    <p class="hero-desc">Little Bridge is a charitable NGO working across three pillars — direct humanitarian aid, sustainable development, and environmental protection — to transform lives from the roots up.</p>
    <p class="hero-quote-inline">"We do not only respond to poverty — we work to eliminate its root causes."<br>— Mrs. Maria Goris, Founder &amp; President</p>
    <div class="hero-actions">
      <a href="#donate" class="btn-primary">Donate Now</a>
      <a href="#programs" class="btn-outline">Our Programs</a>
    </div>
    <div class="hero-pillars">
      <div class="pillar-chip"><span class="picon">🤲</span><span class="ptitle">Direct Aid</span></div>
      <div class="pillar-chip"><span class="picon">🌱</span><span class="ptitle">Sustainable Dev.</span></div>
      <div class="pillar-chip"><span class="picon">🌿</span><span class="ptitle">Environment</span></div>
    </div>
  </div>
  <div class="hero-right">
    <img src="https://images.unsplash.com/photo-1488521787991-ed7bbaae773c?w=900&q=80" alt="Little Bridge community aid work">
    <div class="hero-overlay"></div>
    <div class="founder-card">
      <p>"To build bridges across countries, communities, and hearts — empowering people to rise from poverty into self-sufficiency."</p>
      <cite>— Mrs. Maria Goris, Founder-President</cite>
    </div>
  </div>
</section>

<!-- IMPACT BAND -->
<div class="impact-band">
  <div class="impact-item"><span class="impact-num">31,477</span><span class="impact-label">Beneficiaries Served</span></div>
  <div class="impact-item"><span class="impact-num">20+</span><span class="impact-label">Years of Service</span></div>
  <div class="impact-item"><span class="impact-num">7</span><span class="impact-label">New Houses Built</span></div>
  <div class="impact-item"><span class="impact-num">100ha</span><span class="impact-label">Irrigated Farmland</span></div>
  <div class="impact-item"><span class="impact-num">€100K+</span><span class="impact-label">Medical Equipment Donated</span></div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="about-left">
    <div class="section-eyebrow">Who We Are</div>
    <h2 class="section-title">From <em>emergency aid</em> to lasting <em>empowerment</em></h2>
    <p>Since 2004, Little Bridge has worked with urgency, compassion, and sustainable solutions across Armenia. With 26.7% of Armenia's population living below the national poverty line (World Bank, 2023), our mission is more vital than ever.</p>
    <p>We don't just deliver relief — we walk alongside communities to build food security, healthcare access, housing, education, and economic resilience that lasts.</p>
    <div class="commitment-list">
      <div class="commitment-item"><span class="tick">✓</span> Immediate humanitarian relief</div>
      <div class="commitment-item"><span class="tick">✓</span> Education and healthcare strengthening</div>
      <div class="commitment-item"><span class="tick">✓</span> Long-term economic empowerment</div>
      <div class="commitment-item"><span class="tick">✓</span> Business &amp; job creation initiatives</div>
      <div class="commitment-item"><span class="tick">✓</span> Environmental sustainability</div>
    </div>
  </div>
  <div class="about-right">
    <div class="vision-card">
      <span class="vlabel">🌐 Our Vision</span>
      <p>To build bridges across countries, communities, and hearts — empowering communities to rise from poverty into self-sufficiency.</p>
    </div>
    <div class="mission-card">
      <span class="mlabel">🎯 Our Mission</span>
      <p>Reduction of poverty through three integrated pillars:</p>
      <div class="mp"><strong>Pillar 1:</strong> Direct humanitarian aid — food, clothing, shelter, healthcare, education</div>
      <div class="mp"><strong>Pillar 2:</strong> Empowerment &amp; sustainable development — agriculture, livestock, economic independence</div>
      <div class="mp"><strong>Pillar 3:</strong> Environmental protection — water infrastructure, afforestation, emergency response</div>
    </div>
  </div>
</section>

<!-- PROGRAMS -->
<section id="programs">
  <div class="programs-intro">
    <div>
      <div class="section-eyebrow">What We Do</div>
      <h2 class="section-title">Three pillars, <em>one mission</em></h2>
    </div>
    <p>Every program addresses both the immediate crisis and the structural causes of poverty. Browse our pillars below to see the full scope of our work — from soup kitchens to solar panels, from seed banks to surgery.</p>
  </div>

  <div class="pillar-tabs">
    <button class="ptab active" onclick="showPillar('p1',this)">Pillar 1: Direct Aid</button>
    <button class="ptab" onclick="showPillar('p2',this)">Pillar 2: Sustainable Dev.</button>
    <button class="ptab" onclick="showPillar('p3',this)">Pillar 3: Environment</button>
  </div>

  <!-- PILLAR 1 -->
  <div class="pillar-panel active" id="p1">
    <div class="pillar-header">
      <span class="pillar-badge">Pillar 1</span>
      <h2>Direct Assistance Programs</h2>
    </div>
    <div class="programs-grid">
      <div class="prog-card">
        <span class="prog-id">1C</span>
        <h3>Housing &amp; Infrastructure</h3>
        <ul>
          <li>7 new houses built (2021–2022)</li>
          <li>Roof construction &amp; repair</li>
          <li>Solar panel &amp; photovoltaic systems</li>
          <li>Electricity &amp; gas bill support</li>
          <li>Full furnishing &amp; essential electronics</li>
          <li>Cultural House renovations (Tavush &amp; Ararat)</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Safe, energy-efficient homes — Beneficiaries: 31,477</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">1D</span>
        <h3>Education &amp; Training</h3>
        <ul>
          <li>Scholarships for 30 students (2025–2026)</li>
          <li>After-school care &amp; tuition</li>
          <li>Books, stationery, shoes &amp; kits</li>
          <li>Vocational &amp; technical training</li>
          <li>Elderly education programs</li>
          <li>Summer camps on hygiene &amp; healthy lifestyle</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Strengthened educational outcomes &amp; future employment — Beneficiaries: 31,477</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">1E</span>
        <h3>Healthcare Support</h3>
        <ul>
          <li>Emergency life-saving operations</li>
          <li>Elective surgeries</li>
          <li>Dental &amp; acute treatment support</li>
          <li>Rehabilitation assistance</li>
          <li>€100,000+ in medical equipment donated</li>
          <li>Hospital beds donated to Yerevan Medical Centers</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Thousands gained access to life-saving treatment — Beneficiaries: 31,477</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">1A</span>
        <h3>Food Support Project</h3>
        <ul>
          <li>Nutritious grocery packages</li>
          <li>Community food programs</li>
          <li>Elderly warm meal programs</li>
          <li>Soup kitchens</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Prevention against malnutrition — Beneficiaries: 31,477</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">1B</span>
        <h3>Clothing Support Program</h3>
        <ul>
          <li>Winter coats, boots &amp; warm clothing</li>
          <li>Bed-linen &amp; curtains</li>
          <li>Seasonal essentials for families</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Protection against extreme weather; dignity for children &amp; elderly — Beneficiaries: ≈7,850</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">1F</span>
        <h3>Direct Financial Aid</h3>
        <ul>
          <li>Emergency financial assistance</li>
          <li>Household crisis support</li>
          <li>Utility payment assistance</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Immediate protection from displacement and deepened poverty</div>
      </div>
    </div>
  </div>

  <!-- PILLAR 2 -->
  <div class="pillar-panel" id="p2">
    <div class="pillar-header">
      <span class="pillar-badge">Pillar 2</span>
      <h2>Empowerment &amp; Sustainable Development</h2>
    </div>
    <div class="programs-grid">
      <div class="prog-card">
        <span class="prog-id">2A</span>
        <h3>Horticulture, Agriculture &amp; Apiculture</h3>
        <ul>
          <li>Seed distribution: potatoes, broccoli, cauliflower, cabbage, blueberry (2021–2025)</li>
          <li>Farming tools &amp; agricultural inputs</li>
          <li>Greenhouse infrastructure development</li>
          <li>Apiculture &amp; technical guidance for rural families</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Strengthened food security &amp; household income — Beneficiaries: 31,477</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">2B</span>
        <h3>Livestock &amp; Animal Husbandry</h3>
        <ul>
          <li>Livestock (cows, sheep, piglets) provided to rural families</li>
          <li>Animal rearing training</li>
          <li>Hay &amp; feed support</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Long-term livelihood stability, nutritional improvement &amp; household income — Beneficiaries: 31,477</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">2C</span>
        <h3>Business &amp; Job Creation</h3>
        <ul>
          <li>Support for small business startups</li>
          <li>Vocational skills &amp; entrepreneurship training</li>
          <li>Market linkage &amp; economic mentoring</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Increased economic independence and reduced dependency on aid</div>
      </div>
    </div>
  </div>

  <!-- PILLAR 3 -->
  <div class="pillar-panel" id="p3">
    <div class="pillar-header">
      <span class="pillar-badge">Pillar 3</span>
      <h2>Environmental Protection</h2>
    </div>
    <div class="programs-grid">
      <div class="prog-card">
        <span class="prog-id">3A</span>
        <h3>Water &amp; Irrigation Infrastructure</h3>
        <ul>
          <li>Drinking water pipeline installation</li>
          <li>Irrigation systems across 6 provinces</li>
          <li>Coverage of 100 hectares of farmland</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Reliable water access for hundreds of farming families across 6 provinces</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">3B</span>
        <h3>Afforestation</h3>
        <ul>
          <li>40 hectares afforested</li>
          <li>Soil stabilization initiatives</li>
          <li>Regional employment through planting programs</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>40 hectares afforested; improved soil health and local employment</div>
      </div>
      <div class="prog-card">
        <span class="prog-id">3C</span>
        <h3>Emergency Response</h3>
        <ul>
          <li>Flood rescue operations — Alaverdi, Lori (2024)</li>
          <li>Relief for Karabakh survivors (2023)</li>
          <li>Rapid deployment of food, shelter &amp; essentials</li>
        </ul>
        <div class="prog-impact"><strong>Impact</strong>Immediate protection for displaced and disaster-affected communities</div>
      </div>
    </div>
  </div>
</section>

<!-- PARTNER -->
<section id="partner">
  <div>
    <div class="section-eyebrow">Get Involved</div>
    <h2 class="section-title">Ways to <em>partner</em> with us</h2>
    <p class="partner-sub">We bridge global generosity with local transformation. There are many ways to be part of the change — financial, professional, or in-kind.</p>
  </div>
  <div class="partner-list">
    <div class="partner-item"><span class="pico">🧰</span><span>Fund vital tools for family self-sufficiency</span></div>
    <div class="partner-item"><span class="pico">🏗️</span><span>Sponsor infrastructure to build rural resilience</span></div>
    <div class="partner-item"><span class="pico">🌾</span><span>Donate seeds &amp; tools for sustainable agricultural growth</span></div>
    <div class="partner-item"><span class="pico">🎓</span><span>Volunteer professional skills &amp; vocational training</span></div>
    <div class="partner-item"><span class="pico">🏥</span><span>Finance life-saving healthcare &amp; medical equipment</span></div>
    <div class="partner-item"><span class="pico">⚡</span><span>Provide agile funding for urgent mission-critical needs</span></div>
  </div>
</section>

<!-- DONATE -->
<section id="donate">
  <div class="donate-text">
    <div class="section-eyebrow">Support Our Work</div>
    <h2 class="section-title">Your gift <em>transforms</em> a life</h2>
    <p>Every contribution goes directly to families living in poverty across Armenia. We operate with full transparency and accountability, directing your generosity where it matters most.</p>
    <p>Whether you give once or regularly, your support enables food packages, medical care, housing repairs, farming tools, scholarships, and so much more.</p>
    <div class="tax-badge">Tax code: 01003187</div>
  </div>
  <div class="donate-form-card">
    <h3>Make a Donation</h3>
    <p class="form-sub">Choose an amount or enter your own</p>
    <div class="amount-grid">
      <button class="amount-btn" onclick="setAmount(this)">$25</button>
      <button class="amount-btn active" onclick="setAmount(this)">$50</button>
      <button class="amount-btn" onclick="setAmount(this)">$100</button>
      <button class="amount-btn" onclick="setAmount(this)">$250</button>
      <button class="amount-btn" onclick="setAmount(this)">$500</button>
      <button class="amount-btn" onclick="setAmount(this)">$1,000</button>
    </div>
    <input class="custom-input" id="custom-amount" type="text" placeholder="Or enter a custom amount ($)" oninput="clearPreset()">
    <div class="receipt-row">
      <label class="receipt-toggle">
        <input type="checkbox" id="want-receipt" checked>
        <span class="receipt-check"></span>
        <span class="receipt-label">Email me a donation receipt</span>
      </label>
    </div>
    <div class="receipt-email-wrap" id="receipt-email-wrap">
      <input class="custom-input" id="receipt-email" type="email" placeholder="Your email address" style="margin-bottom:0">
    </div>
    <button class="donate-submit" onclick="openPaymentModal()">🔒 Donate Securely →</button>
    <p class="donate-note">Secured by Stripe · Registered nonprofit · Tax code: 01003187</p>
  </div>
</section>

<!-- PAYMENT MODAL -->
<div id="payment-modal" class="modal-overlay" onclick="closeModalOutside(event)">
  <div class="modal-box">
    <!-- Step 1: Card Form -->
    <div id="modal-step-payment" class="modal-step active">
      <button class="modal-close" onclick="closeModal()">✕</button>
      <div class="modal-header">
        <div class="modal-lock">🔒</div>
        <h3>Secure Donation</h3>
        <p class="modal-amount-display" id="modal-amount-display">$50</p>
        <p class="modal-sub">Little Bridge Charitable NGO · Tax code: 01003187</p>
      </div>
      <div class="stripe-notice">
        <svg width="50" height="20" viewBox="0 0 60 25" fill="none"><text x="0" y="18" font-family="Arial" font-weight="bold" font-size="18" fill="#635BFF">stripe</text></svg>
        <span>Payments powered by Stripe</span>
      </div>
      <div class="card-form">
        <div class="field-group">
          <label>Cardholder Name</label>
          <input type="text" id="card-name" class="field-input" placeholder="Jane Smith" autocomplete="cc-name">
        </div>
        <div class="field-group">
          <label>Card Number</label>
          <div class="card-number-wrap field-input" id="card-number-display">
            <input type="text" id="card-number" placeholder="1234 5678 9012 3456" maxlength="19" oninput="formatCard(this)" autocomplete="cc-number">
            <span id="card-brand-icon" class="card-brand"></span>
          </div>
        </div>
        <div class="field-row">
          <div class="field-group">
            <label>Expiry</label>
            <input type="text" id="card-expiry" class="field-input" placeholder="MM / YY" maxlength="7" oninput="formatExpiry(this)" autocomplete="cc-exp">
          </div>
          <div class="field-group">
            <label>CVC</label>
            <input type="text" id="card-cvc" class="field-input" placeholder="123" maxlength="4" oninput="this.value=this.value.replace(/\D/,'')" autocomplete="cc-csc">
          </div>
        </div>
        <div id="receipt-in-modal" class="field-group" style="display:none">
          <label>Receipt Email</label>
          <input type="email" id="modal-receipt-email" class="field-input" placeholder="your@email.com">
        </div>
        <div id="pay-error" class="pay-error" style="display:none"></div>
        <button class="modal-pay-btn" id="pay-btn" onclick="processPayment()">
          <span id="pay-btn-text">Donate <span id="pay-btn-amount">$50</span></span>
          <span id="pay-btn-spinner" style="display:none">Processing…</span>
        </button>
        <p class="modal-secure-note">🔒 256-bit SSL encryption · Your card details are never stored</p>
      </div>
    </div>
    <!-- Step 2: Success -->
    <div id="modal-step-success" class="modal-step">
      <div class="success-content">
        <div class="success-icon">✓</div>
        <h3>Thank You!</h3>
        <p class="success-msg" id="success-msg">Your donation of <strong id="success-amount"></strong> has been received.</p>
        <p class="success-sub" id="success-receipt-note"></p>
        <p class="success-impact">Your generosity helps families in Armenia access food, healthcare, housing, and hope.</p>
        <button class="modal-pay-btn" onclick="closeModal()" style="margin-top:1.5rem">Close</button>
      </div>
    </div>
  </div>
</div>

<!-- CONTACT STRIP -->
<div class="contact-strip">
  <div>
    <h3>Little Bridge Charitable NGO</h3>
    <p class="csub">Transforming lives. Restoring hope.</p>
  </div>
  <div class="contact-details">
    <div class="contact-item"><span>📞</span> +374 91210269</div>
    <div class="contact-item"><span>🌐</span> www.little-bridge.org</div>
    <div class="contact-item"><span>✉️</span> <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="bbd7d2cfcfd7ded9c9d2dfdcde95d6dac9d2da8982fbdcd6dad2d795d8d4d6">[email&#160;protected]</a></div>
    <div class="contact-item"><span>📍</span> Yerevan, Dro str. 23, app. 27, Index: 0069</div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">Little <span>Bridge</span> NGO</div>
    <ul class="footer-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#programs">Programs</a></li>
      <li><a href="#partner">Partner</a></li>
      <li><a href="#donate">Donate</a></li>
    </ul>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Little Bridge Charitable NGO · Established 2004 · Yerevan, Armenia</span>
    <span>Tax code: 01003187</span>
  </div>
</footer>

<script>
  /* ── AMOUNT SELECTION ── */
  window.setAmount = function(btn) {
    document.querySelectorAll(".amount-btn").forEach(b => b.classList.remove("active"));
    btn.classList.add("active");
    document.getElementById("custom-amount").value = "";
  };
  window.clearPreset = function() {
    document.querySelectorAll(".amount-btn").forEach(b => b.classList.remove("active"));
  };
  function getSelectedAmount() {
    const custom = document.getElementById("custom-amount").value.replace(/[^0-9.]/g, "");
    if (custom) return parseFloat(custom);
    const active = document.querySelector(".amount-btn.active");
    if (active) return parseFloat(active.textContent.replace(/[^0-9]/g, ""));
    return null;
  }

  /* ── RECEIPT TOGGLE ── */
  document.addEventListener("DOMContentLoaded", function() {
    const checkbox = document.getElementById("want-receipt");
    const wrap = document.getElementById("receipt-email-wrap");
    checkbox.addEventListener("change", function() {
      wrap.classList.toggle("hidden", !this.checked);
    });
  });

  /* ── PILLAR TABS ── */
  window.showPillar = function(id, btn) {
    document.querySelectorAll(".pillar-panel").forEach(p => p.classList.remove("active"));
    document.querySelectorAll(".ptab").forEach(b => b.classList.remove("active"));
    document.getElementById(id).classList.add("active");
    btn.classList.add("active");
  };

  /* ── SMOOTH SCROLL ── */
  document.querySelectorAll("a[href^='#']").forEach(anchor => {
    anchor.addEventListener("click", function(e) {
      const target = document.querySelector(this.getAttribute("href"));
      if (target) { e.preventDefault(); window.scrollTo({ top: target.offsetTop - 72, behavior: "smooth" }); }
    });
  });

  /* ── SCROLL ANIMATIONS ── */
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.style.opacity="1"; e.target.style.transform="translateY(0)"; } });
  }, { threshold: 0.08 });
  document.querySelectorAll(".prog-card, .partner-item, .impact-item").forEach(el => {
    el.style.opacity="0"; el.style.transform="translateY(18px)";
    el.style.transition="opacity 0.55s ease, transform 0.55s ease";
    observer.observe(el);
  });

  /* ── CARD FORMATTING ── */
  window.formatCard = function(input) {
    let v = input.value.replace(/\D/g, "").substring(0, 16);
    input.value = v.replace(/(.{4})/g, "$1 ").trim();
    const icon = document.getElementById("card-brand-icon");
    if (v.startsWith("4")) icon.textContent = "💳";
    else if (/^5[1-5]/.test(v)) icon.textContent = "💳";
    else if (/^3[47]/.test(v)) icon.textContent = "💳";
    else icon.textContent = "";
  };
  window.formatExpiry = function(input) {
    let v = input.value.replace(/\D/g, "").substring(0, 4);
    if (v.length >= 2) v = v.substring(0,2) + " / " + v.substring(2);
    input.value = v;
  };

  /* ── OPEN PAYMENT MODAL ── */
  window.openPaymentModal = function() {
    const amount = getSelectedAmount();
    if (!amount || amount < 1) {
      alert("Please select or enter a donation amount.");
      return;
    }
    const wantReceipt = document.getElementById("want-receipt").checked;
    const receiptEmail = document.getElementById("receipt-email").value.trim();

    document.getElementById("modal-amount-display").textContent = "$" + amount.toFixed(0);
    document.getElementById("pay-btn-amount").textContent = "$" + amount.toFixed(0);

    const modalReceiptField = document.getElementById("receipt-in-modal");
    const modalReceiptInput = document.getElementById("modal-receipt-email");
    if (wantReceipt) {
      modalReceiptField.style.display = "block";
      modalReceiptInput.value = receiptEmail;
    } else {
      modalReceiptField.style.display = "none";
    }

    document.getElementById("modal-step-payment").classList.add("active");
    document.getElementById("modal-step-success").classList.remove("active");
    document.getElementById("pay-error").style.display = "none";
    document.getElementById("payment-modal").classList.add("open");
    document.body.style.overflow = "hidden";
  };

  /* ── CLOSE MODAL ── */
  window.closeModal = function() {
    document.getElementById("payment-modal").classList.remove("open");
    document.body.style.overflow = "";
  };
  window.closeModalOutside = function(e) {
    if (e.target.id === "payment-modal") closeModal();
  };
  document.addEventListener("keydown", function(e) {
    if (e.key === "Escape") closeModal();
  });

  /* ── VALIDATION ── */
  function showError(msg) {
    const el = document.getElementById("pay-error");
    el.textContent = msg; el.style.display = "block";
  }
  function validateForm() {
    const name = document.getElementById("card-name").value.trim();
    const number = document.getElementById("card-number").value.replace(/\s/g, "");
    const expiry = document.getElementById("card-expiry").value.replace(/\s/g, "");
    const cvc = document.getElementById("card-cvc").value.trim();
    const wantReceipt = document.getElementById("want-receipt").checked;
    const email = document.getElementById("modal-receipt-email").value.trim();

    if (!name) { showError("Please enter the cardholder name."); return false; }
    if (number.length < 15) { showError("Please enter a valid card number."); return false; }
    if (!/^\d{2}\/\d{2}$/.test(expiry.replace(" ", ""))) { showError("Please enter a valid expiry date (MM/YY)."); return false; }
    if (cvc.length < 3) { showError("Please enter a valid CVC."); return false; }
    if (wantReceipt && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
      showError("Please enter a valid email address for your receipt."); return false;
    }
    return true;
  }

  /* ── PROCESS PAYMENT ── */
  window.processPayment = function() {
    document.getElementById("pay-error").style.display = "none";
    if (!validateForm()) return;

    const btn = document.getElementById("pay-btn");
    const btnText = document.getElementById("pay-btn-text");
    const spinner = document.getElementById("pay-btn-spinner");
    btn.disabled = true;
    btnText.style.display = "none";
    spinner.style.display = "inline";

    // Simulate Stripe payment processing (replace with real Stripe.js integration)
    setTimeout(function() {
      btn.disabled = false;
      btnText.style.display = "inline";
      spinner.style.display = "none";

      const amount = document.getElementById("modal-amount-display").textContent;
      const wantReceipt = document.getElementById("want-receipt").checked;
      const email = document.getElementById("modal-receipt-email").value.trim();

      document.getElementById("success-amount").textContent = amount;
      document.getElementById("success-receipt-note").textContent =
        wantReceipt && email
          ? "A receipt has been sent to " + email + "."
          : "";

      document.getElementById("modal-step-payment").classList.remove("active");
      document.getElementById("modal-step-success").classList.add("active");

      // Reset form
      ["card-name","card-number","card-expiry","card-cvc","modal-receipt-email"].forEach(id => {
        document.getElementById(id).value = "";
      });
    }, 2200);
  };
</script>
</body>
</html>
