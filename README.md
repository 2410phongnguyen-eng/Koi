
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
  <meta name="theme-color" content="#17110f">
  <meta name="description" content="Nishiki Hub — không gian lưu giữ những dự án website do KoiFish phát triển.">
  <title>KOIFISH — Nishiki Hub</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght,SOFT,WONK@9..144,400,20,1;9..144,500,20,1;9..144,600,20,1;9..144,700,20,1&family=Manrope:wght@400;500;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">

  <style>
    /* =========================================================
       KOIFISH / NISHIKI HUB
       Giao diện full-viewport, ưu tiên màn hình ngang.
       Chỉ vùng nội dung dài mới có thanh cuộn riêng.
    ========================================================= */
    :root {
      color-scheme: light;
      --cream: #f3e8d7;
      --cream-deep: #e8d8bb;
      --paper: #fbf7ef;
      --ink: #17110f;
      --ink-soft: #50413a;
      --red: #b61f34;
      --red-deep: #871629;
      --gold: #c99a53;
      --line: rgba(23, 17, 15, .13);
      --panel: rgba(251, 247, 239, .88);
      --shadow: 0 16px 42px rgba(54, 31, 23, .10);
      --topbar-height: 72px;
      --footer-height: 25px;
      --page-pad: clamp(10px, 1.3vw, 20px);
      --display: "Fraunces", Georgia, serif;
      --body: "Manrope", Arial, sans-serif;
      --mono: "Space Mono", monospace;
    }

    *, *::before, *::after { box-sizing: border-box; }
    html, body {
      width: 100%;
      height: 100%;
      margin: 0 !important;
      padding: 0 !important;
      overflow: hidden !important;
      overscroll-behavior: none;
    }
    body {
      color: var(--ink);
      font-family: var(--body);
      background:
        radial-gradient(ellipse at 0% 0%, rgba(182, 31, 52, .105), transparent 34%),
        radial-gradient(ellipse at 100% 100%, rgba(201, 154, 83, .17), transparent 30%),
        var(--cream);
      -webkit-font-smoothing: antialiased;
      text-rendering: optimizeLegibility;
    }
    button, input, textarea { font: inherit; }
    button { -webkit-tap-highlight-color: transparent; }
    button:focus-visible, a:focus-visible, input:focus-visible, textarea:focus-visible {
      outline: 2px solid var(--red);
      outline-offset: 3px;
    }

    .app-shell {
      position: fixed;
      inset: 0;
      isolation: isolate;
      display: grid;
      grid-template-rows: var(--topbar-height) minmax(0, 1fr) var(--footer-height);
      width: 100vw;
      height: 100vh;
      height: 100dvh;
      overflow: hidden;
    }
    .app-shell::before {
      content: "";
      position: absolute;
      inset: 0;
      z-index: -1;
      pointer-events: none;
      opacity: .19;
      background-image: radial-gradient(circle, rgba(135, 22, 41, .36) .7px, transparent .9px);
      background-size: 19px 19px;
      mask-image: linear-gradient(135deg, #000, transparent 67%);
    }

    /* Thanh điều hướng */
    .topbar {
      z-index: 20;
      min-width: 0;
      display: grid;
      grid-template-columns: auto minmax(0, 1fr);
      align-items: center;
      gap: clamp(10px, 2vw, 28px);
      padding: 0 clamp(12px, 2vw, 28px);
      color: var(--paper);
      background: rgba(23, 17, 15, .97);
      border-bottom: 3px solid var(--red);
      box-shadow: 0 8px 26px rgba(23, 17, 15, .12);
    }
    .brand {
      min-width: 0;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 0;
      border: 0;
      color: inherit;
      background: transparent;
      cursor: pointer;
      text-align: left;
    }
    .seal {
      flex: 0 0 auto;
      display: grid;
      place-items: center;
      width: 42px;
      aspect-ratio: 1;
      border: 1px solid rgba(251, 247, 239, .78);
      border-radius: 50%;
      background: linear-gradient(145deg, #d52b45, var(--red-deep));
      box-shadow: 0 0 0 3px rgba(182, 31, 52, .18), 0 5px 16px rgba(182, 31, 52, .22);
      font-family: var(--display);
      font-size: 21px;
      font-weight: 700;
    }
    .brand-copy { display: grid; gap: 1px; }
    .brand-name {
      font-family: var(--display);
      font-size: clamp(17px, 1.7vw, 22px);
      font-weight: 600;
      letter-spacing: .025em;
      line-height: 1;
      white-space: nowrap;
    }
    .brand-name span { color: #ed5266; font-style: italic; }
    .brand-caption {
      color: rgba(251, 247, 239, .52);
      font: 8px/1.3 var(--mono);
      letter-spacing: .16em;
      text-transform: uppercase;
    }
    .mainnav {
      min-width: 0;
      display: flex;
      justify-content: flex-end;
      align-items: center;
      gap: 5px;
    }
    .nav-link {
      padding: 10px clamp(9px, 1.3vw, 17px);
      border: 1px solid transparent;
      border-radius: 999px;
      color: rgba(251, 247, 239, .66);
      background: transparent;
      font: 10px/1.2 var(--mono);
      letter-spacing: .045em;
      text-transform: uppercase;
      white-space: nowrap;
      cursor: pointer;
      transition: color .18s ease, background .18s ease, border-color .18s ease;
    }
    .nav-link:hover { color: var(--paper); background: rgba(255, 255, 255, .06); }
    .nav-link.active {
      color: var(--paper);
      background: rgba(182, 31, 52, .20);
      border-color: rgba(237, 82, 102, .35);
    }

    /* Khung ứng dụng: các màn hình không làm trang dài ra */
    main { position: relative; min-width: 0; min-height: 0; overflow: hidden; }
    .view {
      position: absolute;
      inset: 0;
      display: none;
      min-width: 0;
      min-height: 0;
      overflow: hidden;
      padding: var(--page-pad);
    }
    .view.active { display: flex; animation: view-in .24s ease both; }
    @keyframes view-in {
      from { opacity: .55; }
      to { opacity: 1; }
    }
    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      color: var(--red-deep);
      font: 9px/1.4 var(--mono);
      letter-spacing: .17em;
      text-transform: uppercase;
    }
    .eyebrow::before { content: ""; width: 20px; height: 1px; background: currentColor; }
    .section-title {
      margin: 4px 0 0;
      font: 600 clamp(29px, 3.2vw, 46px)/.98 var(--display);
      letter-spacing: -.035em;
    }
    .muted { color: var(--ink-soft); }

    /* Nút dùng chung */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      min-height: 39px;
      padding: 10px 15px;
      border: 1px solid var(--ink);
      border-radius: 999px;
      color: var(--paper);
      background: var(--ink);
      box-shadow: 0 6px 15px rgba(23, 17, 15, .09);
      font: 9px/1.1 var(--mono);
      letter-spacing: .055em;
      text-transform: uppercase;
      text-decoration: none;
      white-space: nowrap;
      cursor: pointer;
      transition: transform .16s ease, background .16s ease, border-color .16s ease;
    }
    .btn:hover { transform: translateY(-1px); background: var(--red); border-color: var(--red); }
    .btn.ghost { color: var(--ink); background: transparent; box-shadow: none; }
    .btn.ghost:hover { color: var(--paper); background: var(--red-deep); border-color: var(--red-deep); }
    .btn.soft { color: var(--ink); background: rgba(255, 255, 255, .42); border-color: var(--line); box-shadow: none; }
    .btn.soft:hover { background: var(--paper); }
    .btn.danger { color: var(--red-deep); background: transparent; border-color: rgba(135, 22, 41, .48); box-shadow: none; }
    .btn.danger:hover { color: var(--paper); background: var(--red-deep); border-color: var(--red-deep); }
    .btn.small { min-height: 32px; padding: 8px 11px; font-size: 8px; }

    /* Trang chủ */
    .home-view { padding: 0; }
    .home-layout {
      display: grid;
      grid-template-columns: minmax(0, 1.04fr) minmax(0, .96fr);
      gap: clamp(12px, 1.6vw, 24px);
      width: 100%;
      height: 100%;
      min-width: 0;
      min-height: 0;
      padding: clamp(12px, 1.55vw, 24px);
    }
    .hero-copy {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: center;
      min-width: 0;
      min-height: 0;
      padding: clamp(4px, 1.3vw, 22px) clamp(2px, 1vw, 16px);
    }
    .hero-title {
      margin: clamp(9px, 1.5vh, 17px) 0 0;
      font: 600 clamp(47px, 7.4vw, 104px)/.78 var(--display);
      letter-spacing: -.065em;
    }
    .hero-title span { display: block; }
    .hero-title em {
      display: block;
      margin-top: .13em;
      color: var(--red);
      font-weight: 400;
      font-style: italic;
      letter-spacing: -.055em;
    }
    .hero-sub {
      max-width: 600px;
      margin: clamp(12px, 2.3vh, 24px) 0 0;
      color: var(--ink-soft);
      font-size: clamp(11px, .95vw, 14px);
      line-height: 1.75;
    }
    .hero-actions { display: flex; flex-wrap: wrap; gap: 9px; margin-top: clamp(13px, 2.2vh, 24px); }
    .stats {
      display: flex;
      flex-wrap: wrap;
      align-items: stretch;
      gap: clamp(17px, 3vw, 42px);
      width: 100%;
      margin-top: clamp(18px, 3.4vh, 36px);
      padding-top: clamp(12px, 1.7vh, 18px);
      border-top: 1px solid var(--line);
    }
    .stat { min-width: 0; }
    .stat-num { color: var(--red); font: 600 clamp(29px, 3.7vw, 48px)/.9 var(--display); letter-spacing: -.035em; }
    .stat-label {
      max-width: 185px;
      margin-top: 7px;
      color: var(--ink-soft);
      font: 8px/1.55 var(--mono);
      letter-spacing: .07em;
      text-transform: uppercase;
    }
    .hero-note {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-top: clamp(14px, 2.4vh, 26px);
      color: rgba(80, 65, 58, .78);
      font: 8px/1.5 var(--mono);
      letter-spacing: .05em;
    }
    .live-dot { width: 6px; height: 6px; flex: 0 0 auto; border-radius: 50%; background: var(--red); box-shadow: 0 0 0 4px rgba(182, 31, 52, .10); }

    .pond-wrap {
      position: relative;
      isolation: isolate;
      min-width: 0;
      min-height: 0;
      overflow: hidden;
      border: 1px solid rgba(23, 17, 15, .14);
      border-radius: clamp(18px, 2.5vw, 34px);
      background:
        radial-gradient(ellipse at 28% 22%, rgba(255, 255, 255, .82), transparent 26%),
        radial-gradient(ellipse at 78% 77%, rgba(182, 31, 52, .10), transparent 29%),
        linear-gradient(150deg, #fbf7ef, #e7d2b3);
      box-shadow: var(--shadow);
    }
    .pond-wrap::before, .pond-wrap::after {
      content: "";
      position: absolute;
      z-index: -1;
      width: 65%;
      aspect-ratio: 1;
      border: 1px solid rgba(182, 31, 52, .12);
      border-radius: 50%;
      pointer-events: none;
    }
    .pond-wrap::before { left: -21%; top: 10%; box-shadow: 0 0 0 19px rgba(182,31,52,.025), 0 0 0 38px rgba(182,31,52,.02); }
    .pond-wrap::after { right: -30%; bottom: -22%; box-shadow: 0 0 0 20px rgba(201,154,83,.07), 0 0 0 40px rgba(201,154,83,.045); }
    .pond-grid {
      position: absolute;
      inset: 0;
      z-index: -1;
      opacity: .36;
      background: linear-gradient(rgba(23,17,15,.035) 1px, transparent 1px), linear-gradient(90deg, rgba(23,17,15,.035) 1px, transparent 1px);
      background-size: 36px 36px;
      mask-image: linear-gradient(135deg, transparent, #000 45%, transparent);
    }
    .hero-koi { position: absolute; inset: 0; z-index: 2; pointer-events: none; }
    #koiCanvas { display: block; width: 100%; height: 100%; }
    .pond-meta {
      position: absolute;
      z-index: 3;
      left: clamp(13px, 1.7vw, 24px);
      right: clamp(13px, 1.7vw, 24px);
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      color: rgba(23, 17, 15, .62);
      font: 8px/1.3 var(--mono);
      letter-spacing: .12em;
      text-transform: uppercase;
      pointer-events: none;
    }
    .pond-meta.top { top: clamp(13px, 1.7vw, 24px); }
    .pond-meta.bottom { bottom: clamp(13px, 1.7vw, 24px); align-items: flex-end; }
    .pond-index { color: var(--red-deep); }
    .pond-caption { display: grid; gap: 5px; }
    .pond-caption strong { color: var(--ink); font: 500 clamp(19px, 2.1vw, 30px)/1 var(--display); letter-spacing: -.025em; text-transform: none; }
    .pond-caption span { font-size: 7px; }
    .pond-stamp {
      display: grid;
      place-items: center;
      width: clamp(37px, 4vw, 53px);
      aspect-ratio: 1;
      border: 1px solid rgba(135, 22, 41, .48);
      border-radius: 50%;
      color: var(--red-deep);
      font: 700 clamp(14px, 1.4vw, 19px)/1 var(--display);
      transform: rotate(-12deg);
    }
    .ripple {
      position: absolute;
      left: 50%;
      top: 52%;
      width: 44px;
      aspect-ratio: 1;
      border: 1px solid rgba(182, 31, 52, .38);
      border-radius: 50%;
      transform: translate(-50%, -50%) scale(.2);
      animation: ripple 4s ease-out infinite;
      pointer-events: none;
    }
    .ripple:nth-child(2) { left: 38%; top: 42%; animation-delay: 1.3s; }
    .ripple:nth-child(3) { left: 65%; top: 63%; animation-delay: 2.6s; }
    @keyframes ripple {
      0% { opacity: .58; transform: translate(-50%, -50%) scale(.3); }
      100% { opacity: 0; transform: translate(-50%, -50%) scale(5); }
    }

    /* Các màn hình danh sách */
    .view-layout { display: flex; flex-direction: column; gap: clamp(10px, 1.4vh, 16px); width: 100%; height: 100%; min-height: 0; }
    .view-heading {
      flex: 0 0 auto;
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 16px;
      min-width: 0;
      padding: 2px 2px 12px;
      border-bottom: 1px solid var(--line);
    }
    .heading-side { display: flex; align-items: center; justify-content: flex-end; gap: 12px; min-width: 0; }
    .heading-note { color: rgba(80,65,58,.72); font: 8px/1.5 var(--mono); letter-spacing: .07em; text-align: right; }
    .content-fill { flex: 1 1 auto; min-height: 0; overflow: hidden; }
    .site-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(min(240px, 100%), 1fr));
      grid-auto-rows: minmax(160px, 1fr);
      align-content: start;
      gap: clamp(9px, 1.2vw, 16px);
      width: 100%;
      height: 100%;
      min-height: 0;
      overflow: auto;
      padding: 2px 3px 5px 2px;
      scrollbar-width: thin;
      scrollbar-color: rgba(135, 22, 41, .35) transparent;
    }
    .site-card {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 10px;
      min-width: 0;
      min-height: 0;
      overflow: hidden;
      padding: clamp(13px, 1.45vw, 21px);
      border: 1px solid var(--line);
      border-left: 3px solid var(--red);
      border-radius: 19px;
      background: var(--panel);
      box-shadow: 0 8px 25px rgba(54,31,23,.055);
      backdrop-filter: blur(8px);
      transition: transform .18s ease, box-shadow .18s ease, border-color .18s ease;
    }
    .site-card:hover { transform: translateY(-2px); border-color: rgba(182,31,52,.35); box-shadow: var(--shadow); }
    .site-card-top { display: flex; align-items: center; justify-content: space-between; gap: 8px; width: 100%; }
    .site-number, .site-category { color: var(--red-deep); font: 8px/1.4 var(--mono); letter-spacing: .11em; text-transform: uppercase; }
    .site-category { color: rgba(80,65,58,.64); text-align: right; }
    .site-card h3 { margin: 0; font: 500 clamp(20px, 1.8vw, 27px)/1.05 var(--display); letter-spacing: -.025em; overflow-wrap: anywhere; }
    .site-card p { display: -webkit-box; -webkit-box-orient: vertical; -webkit-line-clamp: 4; overflow: hidden; margin: 0; color: var(--ink-soft); font-size: 11px; line-height: 1.65; }
    .visit {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      margin-top: auto;
      padding-bottom: 3px;
      border-bottom: 1px solid var(--red);
      color: var(--ink);
      font: 8px/1.35 var(--mono);
      letter-spacing: .055em;
      text-decoration: none;
      text-transform: uppercase;
    }
    .visit:hover { color: var(--red); }
    .empty-note {
      display: grid;
      place-items: center;
      min-height: 130px;
      padding: 24px;
      border: 1px dashed rgba(23,17,15,.22);
      border-radius: 18px;
      color: var(--ink-soft);
      font: 10px/1.7 var(--mono);
      text-align: center;
    }
    .search-box {
      width: clamp(145px, 19vw, 250px);
      min-width: 0;
      padding: 10px 13px;
      border: 1px solid var(--line);
      border-radius: 999px;
      color: var(--ink);
      background: rgba(251, 247, 239, .75);
      font-size: 11px;
    }

    /* Quản lý */
    .lock-stage { flex: 1 1 auto; display: grid; place-items: center; min-height: 0; overflow: auto; padding: 8px; }
    .lock-card {
      width: min(100%, 430px);
      padding: clamp(19px, 2.5vw, 32px);
      border: 1px solid var(--line);
      border-radius: 25px;
      background: var(--panel);
      box-shadow: var(--shadow);
      text-align: center;
    }
    .lock-icon { width: 36px; height: 36px; margin: 0 auto 12px; color: var(--red); }
    .lock-card h3 { margin: 0; font: 500 clamp(22px, 2.2vw, 29px)/1.1 var(--display); }
    .lock-card p { margin: 8px auto 17px; max-width: 320px; color: var(--ink-soft); font-size: 11px; line-height: 1.6; }
    .lock-form { display: flex; gap: 8px; }
    .lock-form input { flex: 1 1 auto; min-width: 0; }
    .lock-error { display: none; margin-top: 11px; color: var(--red-deep); font: 9px/1.5 var(--mono); }
    .lock-error.show { display: block; animation: shake .25s ease; }
    @keyframes shake { 25% { transform: translateX(-4px); } 75% { transform: translateX(4px); } }
    .manage-panel { display: none; flex: 1 1 auto; min-width: 0; min-height: 0; overflow: hidden; }
    .manage-panel.show { display: grid; grid-template-columns: minmax(245px, .72fr) minmax(0, 1.28fr); gap: clamp(10px, 1.3vw, 18px); }
    .form-card, .manage-list-wrap {
      min-width: 0;
      min-height: 0;
      overflow: auto;
      padding: clamp(13px, 1.5vw, 21px);
      border: 1px solid var(--line);
      border-radius: 20px;
      background: var(--panel);
      box-shadow: 0 8px 25px rgba(54,31,23,.055);
      scrollbar-width: thin;
      scrollbar-color: rgba(135, 22, 41, .35) transparent;
    }
    .form-card h3 { margin: 0 0 5px; font: 500 clamp(20px, 1.8vw, 26px)/1.1 var(--display); }
    .form-intro { margin: 0 0 17px; color: var(--ink-soft); font-size: 10px; line-height: 1.55; }
    .form-grid { display: grid; grid-template-columns: minmax(0,1fr); gap: 11px; }
    label { display: block; margin: 0 0 5px; color: var(--ink-soft); font: 8px/1.4 var(--mono); letter-spacing: .08em; text-transform: uppercase; }
    input[type="text"], input[type="url"], input[type="password"], textarea {
      display: block;
      width: 100%;
      min-width: 0;
      padding: 10px 11px;
      border: 1px solid rgba(23,17,15,.14);
      border-radius: 11px;
      color: var(--ink);
      background: rgba(243,232,215,.62);
      font-size: 11px;
      line-height: 1.4;
    }
    textarea { min-height: 68px; resize: vertical; }
    input::placeholder, textarea::placeholder { color: rgba(80,65,58,.52); }
    .form-actions { display: flex; flex-wrap: wrap; justify-content: flex-end; gap: 7px; margin-top: 13px; }
    .form-divider { height: 1px; margin: 17px 0 12px; background: var(--line); }
    .manage-list-wrap { display: flex; flex-direction: column; gap: 10px; }
    .manage-list-heading { position: sticky; top: -1px; z-index: 2; display: flex; align-items: center; justify-content: space-between; gap: 10px; margin: -2px -2px 2px; padding: 2px 2px 10px; background: var(--paper); border-bottom: 1px solid var(--line); }
    .manage-list-heading h3 { margin: 0; font: 500 21px/1.1 var(--display); }
    .manage-list-heading span { color: var(--ink-soft); font: 8px/1.4 var(--mono); }
    .manage-item { flex: 0 0 auto; padding: 13px; border: 1px solid var(--line); border-radius: 15px; background: rgba(243,232,215,.36); }
    .manage-item .form-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 9px; }
    .manage-item .full { grid-column: 1 / -1; }
    .manage-item textarea { min-height: 50px; }
    .item-actions { display: flex; justify-content: flex-end; flex-wrap: wrap; gap: 7px; margin-top: 9px; }
    .save-msg { display: none; margin-top: 7px; color: var(--red-deep); font: 8px/1.4 var(--mono); }
    .save-msg.show { display: block; }
    .is-hidden { display: none !important; }

    /* Liên hệ */
    .contact-view .view-layout { gap: clamp(12px, 2vh, 24px); }
    .contact-grid {
      flex: 1 1 auto;
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      align-content: center;
      gap: clamp(9px, 1.5vw, 20px);
      min-width: 0;
      min-height: 0;
    }
    .contact-card {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: center;
      gap: 10px;
      min-width: 0;
      min-height: clamp(135px, 25vh, 220px);
      padding: clamp(14px, 2vw, 28px);
      border: 1px solid var(--line);
      border-radius: 22px;
      color: var(--ink);
      background: var(--panel);
      box-shadow: 0 8px 25px rgba(54,31,23,.055);
      text-decoration: none;
      transition: transform .18s ease, border-color .18s ease, box-shadow .18s ease;
    }
    .contact-card:hover { transform: translateY(-3px); border-color: rgba(182,31,52,.4); box-shadow: var(--shadow); }
    .contact-icon { width: 27px; height: 27px; color: var(--red); }
    .clabel { color: var(--ink-soft); font: 8px/1.4 var(--mono); letter-spacing: .12em; text-transform: uppercase; }
    .cvalue { max-width: 100%; overflow-wrap: anywhere; font: 500 clamp(16px, 1.8vw, 25px)/1.1 var(--display); }
    .contact-arrow { margin-top: 4px; color: var(--red-deep); font: 8px/1.4 var(--mono); text-transform: uppercase; }
    .maker-note { flex: 0 0 auto; display: flex; justify-content: space-between; gap: 10px; padding: 11px 2px 0; border-top: 1px solid var(--line); color: var(--ink-soft); font: 8px/1.5 var(--mono); }
    .maker-note b { color: var(--red-deep); }

    .app-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      min-width: 0;
      padding: 0 clamp(12px, 2vw, 28px);
      border-top: 1px solid rgba(23,17,15,.10);
      color: rgba(80,65,58,.82);
      background: rgba(243,232,215,.62);
      font: 8px/1 var(--mono);
      letter-spacing: .045em;
      white-space: nowrap;
    }
    .footer-right { color: rgba(80,65,58,.57); }

    /* Điện thoại: yêu cầu trải nghiệm ngang */
    .rotate-prompt { display: none; }
    @media (max-width: 800px) and (orientation: landscape) {
      :root { --topbar-height: 49px; --footer-height: 19px; --page-pad: 8px; }
      .topbar { gap: 8px; padding-inline: 10px; border-bottom-width: 2px; }
      .seal { width: 31px; font-size: 16px; }
      .brand { gap: 7px; }
      .brand-name { font-size: 16px; }
      .brand-caption { display: none; }
      .nav-link { padding: 7px clamp(6px, 1.2vw, 11px); font-size: 8px; letter-spacing: 0; }
      .home-layout { gap: 10px; padding: 9px; }
      .hero-copy { padding: 4px 6px; }
      .hero-title { margin-top: 7px; font-size: clamp(36px, 7.1vw, 60px); }
      .hero-sub { margin-top: 9px; font-size: 10px; line-height: 1.45; }
      .hero-actions { gap: 6px; margin-top: 10px; }
      .btn { min-height: 31px; padding: 8px 10px; font-size: 8px; }
      .stats { gap: 19px; margin-top: 12px; padding-top: 9px; }
      .stat-num { font-size: 28px; }
      .stat-label { max-width: 130px; margin-top: 4px; font-size: 7px; line-height: 1.35; }
      .hero-note { margin-top: 9px; font-size: 7px; }
      .pond-wrap { border-radius: 17px; }
      .pond-meta { left: 12px; right: 12px; font-size: 7px; }
      .pond-meta.top { top: 10px; }
      .pond-meta.bottom { bottom: 10px; }
      .pond-caption strong { font-size: 19px; }
      .pond-stamp { width: 34px; font-size: 13px; }
      .view { padding: 8px; }
      .view-layout { gap: 8px; }
      .view-heading { padding: 0 1px 8px; }
      .section-title { font-size: 28px; }
      .eyebrow { font-size: 7px; }
      .heading-note { font-size: 7px; }
      .search-box { width: 150px; padding: 8px 10px; font-size: 10px; }
      .site-grid { grid-template-columns: repeat(auto-fit, minmax(min(190px, 100%), 1fr)); grid-auto-rows: minmax(136px, 1fr); gap: 8px; }
      .site-card { gap: 7px; padding: 11px; border-radius: 14px; }
      .site-card h3 { font-size: 19px; }
      .site-card p { font-size: 9px; line-height: 1.45; -webkit-line-clamp: 3; }
      .site-number, .site-category, .visit { font-size: 7px; }
      .manage-panel.show { grid-template-columns: minmax(205px, .7fr) minmax(0, 1.3fr); gap: 8px; }
      .form-card, .manage-list-wrap { padding: 10px; border-radius: 14px; }
      .form-card h3 { font-size: 19px; }
      .form-intro { margin-bottom: 9px; font-size: 9px; }
      .form-grid { gap: 7px; }
      label { font-size: 7px; }
      input[type="text"], input[type="url"], input[type="password"], textarea { padding: 7px 8px; font-size: 10px; }
      textarea { min-height: 45px; }
      .form-actions { margin-top: 8px; }
      .form-divider { margin: 10px 0 8px; }
      .manage-list-heading { padding-bottom: 7px; }
      .manage-list-heading h3 { font-size: 18px; }
      .manage-item { padding: 9px; }
      .manage-item .form-grid { gap: 6px; }
      .manage-item textarea { min-height: 38px; }
      .item-actions { margin-top: 6px; }
      .contact-grid { gap: 8px; }
      .contact-card { min-height: 125px; gap: 8px; padding: 13px; border-radius: 15px; }
      .contact-icon { width: 22px; height: 22px; }
      .cvalue { font-size: clamp(14px, 2.2vw, 19px); }
      .maker-note { padding-top: 7px; font-size: 7px; }
      .app-footer { padding-inline: 10px; font-size: 7px; }
    }
    @media (max-height: 430px) and (orientation: landscape) {
      .hero-title { font-size: clamp(34px, 6.3vw, 54px); }
      .hero-sub { max-width: 460px; font-size: 9px; }
      .stats { margin-top: 9px; }
      .hero-note { margin-top: 7px; }
      .section-title { font-size: 25px; }
      .contact-card { min-height: 110px; }
    }
    @media (max-width: 800px) and (orientation: portrait) {
      .rotate-prompt {
        position: fixed;
        inset: 0;
        z-index: 1000;
        display: grid;
        place-items: center;
        padding: 28px;
        color: var(--paper);
        background: rgba(23,17,15,.97);
        text-align: center;
      }
      .rotate-card { width: min(100%, 340px); }
      .rotate-symbol { display: inline-block; margin-bottom: 17px; color: #ed5266; font-size: 44px; animation: tilt 1.8s ease-in-out infinite; }
      .rotate-card h2 { margin: 0; font: 500 29px/1.1 var(--display); }
      .rotate-card p { color: rgba(251,247,239,.72); font-size: 12px; line-height: 1.7; }
      .rotate-card small { color: rgba(251,247,239,.42); font: 8px/1.5 var(--mono); letter-spacing: .1em; text-transform: uppercase; }
      @keyframes tilt { 0%,100% { transform: rotate(0); } 50% { transform: rotate(-90deg); } }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { scroll-behavior: auto !important; animation-duration: .01ms !important; animation-iteration-count: 1 !important; transition-duration: .01ms !important; }
    }
  </style>
</head>
<body>
  <div class="app-shell" id="app">
    <header class="topbar">
      <button class="brand" type="button" data-view="home" aria-label="Về trang chủ Nishiki Hub">
        <span class="seal" aria-hidden="true">鯉</span>
        <span class="brand-copy">
          <span class="brand-name">KOI<span>FISH</span></span>
          <span class="brand-caption">Personal web archive</span>
        </span>
      </button>

      <nav class="mainnav" aria-label="Điều hướng chính">
        <button class="nav-link active" type="button" data-view="home" aria-current="page">Trang chủ</button>
        <button class="nav-link" type="button" data-view="websites">Website</button>
        <button class="nav-link" type="button" data-view="manage">Quản lý</button>
        <button class="nav-link" type="button" data-view="contact">Liên hệ</button>
      </nav>
    </header>

    <main id="appMain">
      <!-- TRANG CHỦ -->
      <section id="view-home" class="view home-view active" aria-label="Trang chủ">
        <div class="home-layout">
          <div class="hero-copy">
            <span class="eyebrow">Nishiki Hub / Digital archive</span>
            <h1 class="hero-title"><span>NISHIKI</span><em>HUB.</em></h1>
            <p class="hero-sub">Nơi lưu giữ những không gian số do KoiFish tạo nên. Mỗi website là một thử nghiệm, một ý tưởng và một hành trình sáng tạo đang tiếp tục mở rộng.</p>
            <div class="hero-actions">
              <button class="btn" type="button" data-view="websites">Khám phá website <span aria-hidden="true">↗</span></button>
              <button class="btn ghost" type="button" data-view="manage">Mở khu quản lý</button>
            </div>
            <div class="stats" aria-label="Thống kê Nishiki Hub">
              <div class="stat">
                <div class="stat-num" id="stat-count">04</div>
                <div class="stat-label">Website được lưu giữ</div>
              </div>
              <div class="stat">
                <div class="stat-num">01</div>
                <div class="stat-label">Người phát triển · KoiFish</div>
              </div>
            </div>
            <div class="hero-note"><span class="live-dot" aria-hidden="true"></span> Một góc nhỏ dành cho những ý tưởng không ngừng chuyển động.</div>
          </div>

          <div class="pond-wrap" aria-label="Minh họa hai chú cá koi bơi trong hồ">
            <div class="pond-grid" aria-hidden="true"></div>
            <div class="ripple" aria-hidden="true"></div>
            <div class="ripple" aria-hidden="true"></div>
            <div class="ripple" aria-hidden="true"></div>
            <div class="hero-koi" aria-hidden="true"><canvas id="koiCanvas"></canvas></div>
            <div class="pond-meta top"><span>KOI POND / 001</span><span class="pond-index">水 · 鯉</span></div>
            <div class="pond-meta bottom">
              <div class="pond-caption"><strong>Flow with ideas.</strong><span>A SMALL UNIVERSE BY KOIFISH</span></div>
              <span class="pond-stamp" aria-hidden="true">鯉</span>
            </div>
          </div>
        </div>
      </section>

      <!-- DANH SÁCH WEBSITE -->
      <section id="view-websites" class="view" aria-label="Danh sách website">
        <div class="view-layout">
          <header class="view-heading">
            <div>
              <span class="eyebrow">Bộ sưu tập / 01</span>
              <h2 class="section-title">Website</h2>
            </div>
            <div class="heading-side">
              <span class="heading-note">ARCHIVE<br>KOIFISH PROJECTS</span>
              <input class="search-box" type="search" id="site-search" placeholder="Tìm website…" aria-label="Tìm website">
            </div>
          </header>
          <div class="content-fill">
            <div class="site-grid" id="site-grid" aria-live="polite"></div>
          </div>
        </div>
      </section>

      <!-- QUẢN LÝ -->
      <section id="view-manage" class="view" aria-label="Quản lý website">
        <div class="view-layout">
          <header class="view-heading">
            <div>
              <span class="eyebrow">Không gian riêng / 02</span>
              <h2 class="section-title">Quản lý Hub</h2>
            </div>
            <span class="heading-note">ADD · EDIT · ORGANIZE</span>
          </header>

          <div class="lock-stage" id="lock-stage">
            <div class="lock-card" id="lock-card">
              <svg class="lock-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                <rect x="4" y="10" width="16" height="10" rx="2"></rect>
                <path d="M7.5 10V7a4.5 4.5 0 0 1 9 0v3"></path>
                <path d="M12 14v2"></path>
              </svg>
              <h3>Khu vực đang khóa</h3>
              <p>Nhập mật khẩu để mở các công cụ thêm, chỉnh sửa và xóa website.</p>
              <form class="lock-form" id="unlock-form">
                <input type="password" id="pw-input" placeholder="Mật khẩu truy cập" autocomplete="current-password" aria-label="Mật khẩu truy cập" required>
                <button class="btn" type="submit" id="unlock-btn">Mở khóa ↗</button>
              </form>
              <div class="lock-error" id="lock-error" role="alert">Mật khẩu chưa chính xác. Vui lòng thử lại.</div>
            </div>
          </div>

          <div class="manage-panel" id="manage-panel">
            <form class="form-card" id="add-form">
              <h3>Thêm website</h3>
              <p class="form-intro">Tạo một thẻ mới trong bộ sưu tập Nishiki Hub.</p>
              <div class="form-grid">
                <div>
                  <label for="new-title">Tên website</label>
                  <input type="text" id="new-title" placeholder="Ví dụ: KOI STUDIO" maxlength="90" required>
                </div>
                <div>
                  <label for="new-url">Đường dẫn website</label>
                  <input type="url" id="new-url" placeholder="https://example.com" required>
                </div>
                <div>
                  <label for="new-desc">Mô tả ngắn</label>
                  <textarea id="new-desc" rows="3" maxlength="500" placeholder="Giới thiệu về dự án…"></textarea>
                </div>
              </div>
              <div class="form-actions">
                <button class="btn soft" type="reset">Xóa ô nhập</button>
                <button class="btn" type="submit">Thêm website +</button>
              </div>
              <div class="form-divider"></div>
              <button class="btn danger small" id="delete-all-btn" type="button">Xóa toàn bộ website</button>
              <p class="form-intro" style="margin:9px 0 0">Thao tác xóa toàn bộ sẽ yêu cầu xác nhận.</p>
            </form>

            <div class="manage-list-wrap">
              <div class="manage-list-heading">
                <h3>Danh sách hiện có</h3>
                <span id="manage-count">04 WEBSITE</span>
              </div>
              <div id="manage-list"></div>
            </div>
          </div>
        </div>
      </section>

      <!-- LIÊN HỆ -->
      <section id="view-contact" class="view contact-view" aria-label="Thông tin liên hệ">
        <div class="view-layout">
          <header class="view-heading">
            <div>
              <span class="eyebrow">Kết nối / 03</span>
              <h2 class="section-title">Liên hệ</h2>
            </div>
            <span class="heading-note">SAY HELLO TO KOIFISH</span>
          </header>

          <div class="contact-grid">
            <a class="contact-card" href="https://www.tiktok.com/@_oki__ne_" target="_blank" rel="noopener noreferrer">
              <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M16.6 5.82c-.9-.78-1.47-1.9-1.6-3.14h-3.14v13.3c0 1.53-1.24 2.77-2.77 2.77a2.77 2.77 0 0 1 0-5.54c.25 0 .5.03.73.09V9.9a6.1 6.1 0 0 0-.73-.04A6.13 6.13 0 0 0 3 16.06 6.13 6.13 0 0 0 9.09 22a6.13 6.13 0 0 0 6.13-6.13V9.01a9.1 9.1 0 0 0 5.28 1.7V7.6a5.6 5.6 0 0 1-3.9-1.78Z"/></svg>
              <span class="clabel">TikTok</span>
              <span class="cvalue">@_oki__ne_</span>
              <span class="contact-arrow">Mở hồ sơ ↗</span>
            </a>
            <a class="contact-card" href="https://www.facebook.com/share/1Uj8VCKwVm/" target="_blank" rel="noopener noreferrer">
              <svg class="contact-icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M13.5 21v-7.6h2.6l.4-3H13.5V8.4c0-.87.24-1.46 1.5-1.46h1.6V4.24C16.3 4.17 15.3 4 14.2 4c-2.3 0-3.9 1.4-3.9 4v2.4H7.7v3h2.6V21h3.2Z"/></svg>
              <span class="clabel">Facebook</span>
              <span class="cvalue">KoiFish</span>
              <span class="contact-arrow">Mở trang ↗</span>
            </a>
            <a class="contact-card" href="tel:0367634821">
              <svg class="contact-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M4 5c0-.6.4-1 1-1h3l2 5-2 1.5a11 11 0 0 0 5.5 5.5L15 14l5 2v3c0 .6-.4 1-1 1C10.5 20 4 13.5 4 5Z"/></svg>
              <span class="clabel">Điện thoại</span>
              <span class="cvalue">0367 634 821</span>
              <span class="contact-arrow">Gọi điện ↗</span>
            </a>
          </div>

          <div class="maker-note"><span>Được thiết kế và phát triển bởi <b>KoiFish</b>.</span><span>NISHIKI HUB · EST. 2026</span></div>
        </div>
      </section>
    </main>

    <footer class="app-footer">
      <span>© <span id="year"></span> KOIFISH — NISHIKI HUB</span>
      <span class="footer-right">DESIGNED TO FLOW · BUILT WITH CURIOSITY</span>
    </footer>
  </div>

  <div class="rotate-prompt" role="status" aria-live="polite">
    <div class="rotate-card">
      <div class="rotate-symbol" aria-hidden="true">▱</div>
      <h2>Hãy xoay ngang thiết bị</h2>
      <p>Nishiki Hub được thiết kế theo bố cục màn hình ngang để nội dung hiển thị trọn vẹn, không cần cuộn cả trang.</p>
      <small>Rotate your device to continue</small>
    </div>
  </div>

  <script>
    (() => {
      'use strict';

      const PASSWORD = '24102011';
      const STORAGE_KEY = 'koifish_nishiki_websites_v3';

      const DEFAULT_WEBSITES = [
        {
          id: 'koi-dictionary',
          title: 'KOI DICTIONARY',
          url: 'https://2410phongnguyen-eng.github.io/KOIDICTIONARY/',
          desc: 'Tra cứu từ vựng Anh, Trung, Nhật và Việt; luyện nghe, nói và mở rộng vốn từ theo cách trực quan.'
        },
        {
          id: 'koi-laboratory',
          title: 'KOI LABORATORY',
          url: 'https://2410phongnguyen-eng.github.io/KOILABORATORY/',
          desc: 'Không gian thực hành hóa học, khám phá chất mới và tìm hiểu các phương trình phản ứng vô cơ, hữu cơ.'
        },
        {
          id: 'koi-music',
          title: 'KOI MUSIC',
          url: 'https://2410phongnguyen-eng.github.io/KOIMUSIC/',
          desc: 'Không gian âm nhạc cá nhân để nghe nhạc, sáng tác, tạo danh sách phát và chia sẻ với bạn bè.'
        },
        {
          id: 'koi-horoscope',
          title: 'KOI HOROSCOPE',
          url: 'https://2410phongnguyen-eng.github.io/KOIHOROSCOPE/',
          desc: 'Khám phá Kinh Dịch và trải nghiệm nội dung luận giải tử vi theo phong cách riêng.'
        }
      ];

      const $ = (selector, root = document) => root.querySelector(selector);
      const $$ = (selector, root = document) => [...root.querySelectorAll(selector)];
      let unlocked = false;
      let websites = loadWebsites();

      function loadWebsites() {
        try {
          const saved = localStorage.getItem(STORAGE_KEY);
          if (saved !== null) {
            const parsed = JSON.parse(saved);
            if (Array.isArray(parsed)) return parsed.filter(item => item && typeof item === 'object');
          }
        } catch (error) {
          console.warn('Không thể đọc dữ liệu website đã lưu:', error);
        }
        return DEFAULT_WEBSITES.map(item => ({ ...item }));
      }

      function saveWebsites() {
        try {
          localStorage.setItem(STORAGE_KEY, JSON.stringify(websites));
          return true;
        } catch (error) {
          console.error('Không thể lưu dữ liệu website:', error);
          alert('Trình duyệt không cho phép lưu dữ liệu. Hãy kiểm tra cài đặt lưu trữ của trình duyệt.');
          return false;
        }
      }

      function escapeHtml(value) {
        return String(value ?? '')
          .replace(/&/g, '&amp;')
          .replace(/</g, '&lt;')
          .replace(/>/g, '&gt;')
          .replace(/"/g, '&quot;')
          .replace(/'/g, '&#39;');
      }

      function validateHttpUrl(value) {
        try {
          const parsed = new URL(String(value).trim());
          return parsed.protocol === 'http:' || parsed.protocol === 'https:' ? parsed.href : null;
        } catch {
          return null;
        }
      }

      function makeId() {
        return `site-${Date.now()}-${Math.random().toString(36).slice(2, 7)}`;
      }

      function updateStats() {
        $('#stat-count').textContent = String(websites.length).padStart(2, '0');
        $('#manage-count').textContent = `${String(websites.length).padStart(2, '0')} WEBSITE`;
      }

      function renderSiteGrid() {
        const grid = $('#site-grid');
        const search = ($('#site-search').value || '').trim().toLocaleLowerCase('vi');
        const filtered = websites.filter(site => {
          const searchable = `${site.title || ''} ${site.desc || ''} ${site.url || ''}`.toLocaleLowerCase('vi');
          return searchable.includes(search);
        });

        if (filtered.length === 0) {
          grid.innerHTML = `<div class="empty-note">${websites.length === 0 ? 'Hub chưa có website nào. Hãy mở mục Quản lý để thêm dự án đầu tiên.' : 'Không tìm thấy website phù hợp với từ khóa này.'}</div>`;
          return;
        }

        grid.innerHTML = filtered.map(site => {
          const originalIndex = websites.findIndex(item => String(item.id) === String(site.id));
          const safeUrl = validateHttpUrl(site.url);
          return `
            <article class="site-card">
              <div class="site-card-top">
                <span class="site-number">#${String(originalIndex + 1).padStart(2, '0')}</span>
                <span class="site-category">KOIFISH / PROJECT</span>
              </div>
              <h3>${escapeHtml(site.title || 'Không tên')}</h3>
              <p>${escapeHtml(site.desc || 'Chưa có mô tả cho website này.')}</p>
              ${safeUrl ? `<a class="visit" href="${escapeHtml(safeUrl)}" target="_blank" rel="noopener noreferrer">Truy cập website <span aria-hidden="true">↗</span></a>` : '<span class="visit" aria-disabled="true">Đường dẫn không hợp lệ</span>'}
            </article>`;
        }).join('');
      }

      function renderManageList() {
        const list = $('#manage-list');
        if (websites.length === 0) {
          list.innerHTML = '<div class="empty-note">Chưa có website nào trong Hub.</div>';
          updateStats();
          return;
        }

        list.innerHTML = websites.map((site, index) => `
          <article class="manage-item" data-id="${escapeHtml(site.id)}">
            <div class="form-grid">
              <div>
                <label for="edit-title-${index}">Tên website</label>
                <input class="f-title" id="edit-title-${index}" type="text" maxlength="90" value="${escapeHtml(site.title || '')}" required>
              </div>
              <div>
                <label for="edit-url-${index}">Đường dẫn (URL)</label>
                <input class="f-url" id="edit-url-${index}" type="url" value="${escapeHtml(site.url || '')}" required>
              </div>
              <div class="full">
                <label for="edit-desc-${index}">Mô tả</label>
                <textarea class="f-desc" id="edit-desc-${index}" rows="2" maxlength="500">${escapeHtml(site.desc || '')}</textarea>
              </div>
            </div>
            <div class="item-actions">
              <button class="btn danger small act-delete" type="button">Xóa</button>
              <button class="btn small act-save" type="button">Lưu thay đổi</button>
            </div>
            <div class="save-msg" role="status">Đã lưu thay đổi.</div>
          </article>`).join('');
        updateStats();
      }

      function refreshWebsiteViews() {
        renderSiteGrid();
        if (unlocked) renderManageList();
        updateStats();
      }

      function switchView(viewName) {
        const target = $(`#view-${viewName}`);
        if (!target) return;

        $$('.view').forEach(view => view.classList.toggle('active', view === target));
        $$('.nav-link').forEach(button => {
          const isActive = button.dataset.view === viewName;
          button.classList.toggle('active', isActive);
          if (isActive) button.setAttribute('aria-current', 'page');
          else button.removeAttribute('aria-current');
        });

        if (viewName === 'websites') renderSiteGrid();
        if (viewName === 'home') updateStats();
        if (viewName === 'manage' && unlocked) renderManageList();
        if (viewName === 'home') requestAnimationFrame(resizeKoiCanvas);
      }

      $$('[data-view]').forEach(button => {
        button.addEventListener('click', () => switchView(button.dataset.view));
      });

      // Mở khóa khu vực quản lý. Lưu ý: đây là khóa giao diện phía trình duyệt,
      // không thay thế cơ chế xác thực phía máy chủ cho dữ liệu nhạy cảm.
      $('#unlock-form').addEventListener('submit', event => {
        event.preventDefault();
        const input = $('#pw-input');
        if (input.value === PASSWORD) {
          unlocked = true;
          $('#lock-stage').classList.add('is-hidden');
          $('#manage-panel').classList.add('show');
          $('#lock-error').classList.remove('show');
          renderManageList();
        } else {
          const error = $('#lock-error');
          error.classList.remove('show');
          void error.offsetWidth;
          error.classList.add('show');
          input.select();
        }
      });

      // Thêm website mới.
      $('#add-form').addEventListener('submit', event => {
        event.preventDefault();
        const title = $('#new-title').value.trim();
        const rawUrl = $('#new-url').value.trim();
        const desc = $('#new-desc').value.trim();
        const url = validateHttpUrl(rawUrl);

        if (!title) {
          alert('Vui lòng nhập tên website.');
          $('#new-title').focus();
          return;
        }
        if (!url) {
          alert('Vui lòng nhập một đường dẫn hợp lệ bắt đầu bằng http:// hoặc https://.');
          $('#new-url').focus();
          return;
        }

        websites.push({ id: makeId(), title, url, desc: desc || 'Chưa có mô tả.' });
        if (!saveWebsites()) return;
        $('#add-form').reset();
        refreshWebsiteViews();
      });

      // Lưu chỉnh sửa và xóa từng website bằng event delegation.
      $('#manage-list').addEventListener('click', event => {
        const saveButton = event.target.closest('.act-save');
        const deleteButton = event.target.closest('.act-delete');
        const item = event.target.closest('.manage-item');
        if (!item) return;

        if (saveButton) {
          const title = $('.f-title', item).value.trim();
          const rawUrl = $('.f-url', item).value.trim();
          const desc = $('.f-desc', item).value.trim();
          const url = validateHttpUrl(rawUrl);
          if (!title) {
            alert('Tên website không được để trống.');
            $('.f-title', item).focus();
            return;
          }
          if (!url) {
            alert('Đường dẫn không hợp lệ. Hãy dùng http:// hoặc https://.');
            $('.f-url', item).focus();
            return;
          }

          const current = websites.find(site => String(site.id) === String(item.dataset.id));
          if (!current) return;
          current.title = title;
          current.url = url;
          current.desc = desc || 'Chưa có mô tả.';
          if (!saveWebsites()) return;
          renderSiteGrid();
          updateStats();
          const message = $('.save-msg', item);
          message.classList.add('show');
          saveButton.textContent = 'Đã lưu ✓';
          return;
        }

        if (deleteButton) {
          const current = websites.find(site => String(site.id) === String(item.dataset.id));
          if (!current || !confirm(`Xóa website “${current.title}” khỏi Hub?`)) return;
          websites = websites.filter(site => String(site.id) !== String(item.dataset.id));
          if (!saveWebsites()) return;
          refreshWebsiteViews();
        }
      });

      $('#delete-all-btn').addEventListener('click', () => {
        if (!websites.length) {
          alert('Danh sách hiện không có website nào để xóa.');
          return;
        }
        if (!confirm('Bạn có chắc muốn xóa toàn bộ website khỏi Nishiki Hub? Thao tác này không thể tự hoàn tác.')) return;
        websites = [];
        if (!saveWebsites()) return;
        refreshWebsiteViews();
      });

      $('#site-search').addEventListener('input', renderSiteGrid);
      $('#year').textContent = new Date().getFullYear();
      updateStats();
      renderSiteGrid();

      /* Hoạt ảnh cá koi canvas */
      const canvas = $('#koiCanvas');
      const context = canvas ? canvas.getContext('2d') : null;
      const pond = canvas ? canvas.closest('.pond-wrap') : null;
      let canvasWidth = 0;
      let canvasHeight = 0;
      let pixelRatio = Math.min(window.devicePixelRatio || 1, 2);
      let koiList = [];
      let animationFrame = 0;
      let previousTime = 0;
      let resizeObserver = null;

      function resizeKoiCanvas() {
        if (!canvas || !context || !pond) return;
        const rect = pond.getBoundingClientRect();
        if (rect.width <= 0 || rect.height <= 0) return;
        canvasWidth = rect.width;
        canvasHeight = rect.height;
        pixelRatio = Math.min(window.devicePixelRatio || 1, 2);
        canvas.width = Math.round(canvasWidth * pixelRatio);
        canvas.height = Math.round(canvasHeight * pixelRatio);
        context.setTransform(pixelRatio, 0, 0, pixelRatio, 0, 0);
        if (!koiList.length) createKoi();
        koiList.forEach(koi => {
          koi.x = Math.min(canvasWidth - 40, Math.max(40, koi.x));
          koi.y = Math.min(canvasHeight - 40, Math.max(40, koi.y));
        });
      }

      function createOneKoi(options) {
        return {
          x: options.x,
          y: options.y,
          angle: options.angle,
          vx: 0,
          vy: 0,
          tailPhase: Math.random() * 8,
          targetX: options.x,
          targetY: options.y,
          retarget: 0,
          scale: options.scale,
          palette: options.palette,
          speed: options.speed
        };
      }

      function createKoi() {
        koiList = [
          createOneKoi({ x: canvasWidth * .36, y: canvasHeight * .39, angle: .15, scale: 1.12, speed: 45, palette: 'red' }),
          createOneKoi({ x: canvasWidth * .63, y: canvasHeight * .62, angle: 3.0, scale: .82, speed: 36, palette: 'gold' })
        ];
      }

      function chooseTarget(koi) {
        const padX = Math.min(75 * koi.scale, canvasWidth * .22);
        const padY = Math.min(65 * koi.scale, canvasHeight * .2);
        koi.targetX = padX + Math.random() * Math.max(1, canvasWidth - padX * 2);
        koi.targetY = padY + Math.random() * Math.max(1, canvasHeight - padY * 2);
        koi.retarget = 2.7 + Math.random() * 3.6;
      }

      function updateKoi(koi, dt) {
        koi.retarget -= dt;
        if (koi.retarget <= 0 || Math.hypot(koi.targetX - koi.x, koi.targetY - koi.y) < 23) chooseTarget(koi);
        const dx = koi.targetX - koi.x;
        const dy = koi.targetY - koi.y;
        const distance = Math.hypot(dx, dy) || 1;
        const targetAngle = Math.atan2(dy, dx);
        let difference = targetAngle - koi.angle;
        while (difference > Math.PI) difference -= Math.PI * 2;
        while (difference < -Math.PI) difference += Math.PI * 2;
        koi.angle += difference * Math.min(1, dt * 2.1);
        const speed = Math.min(distance * 1.35, koi.speed);
        koi.vx += (Math.cos(koi.angle) * speed - koi.vx) * Math.min(1, dt * 2.2);
        koi.vy += (Math.sin(koi.angle) * speed - koi.vy) * Math.min(1, dt * 2.2);
        koi.x += koi.vx * dt;
        koi.y += koi.vy * dt;
        koi.tailPhase += dt * (3 + Math.hypot(koi.vx, koi.vy) * .03);
      }

      function drawKoi(koi) {
        const isGold = koi.palette === 'gold';
        const bodyLength = 48;
        const bodyWidth = 19;
        context.save();
        context.translate(koi.x, koi.y + Math.sin(koi.tailPhase * 1.2) * 1.5);
        context.rotate(koi.angle);
        context.scale(koi.scale, koi.scale);

        const glow = context.createRadialGradient(0, 0, 3, 0, 0, bodyLength * 1.5);
        glow.addColorStop(0, isGold ? 'rgba(201,154,83,.26)' : 'rgba(182,31,52,.22)');
        glow.addColorStop(1, 'rgba(251,247,239,0)');
        context.fillStyle = glow;
        context.beginPath();
        context.arc(0, 0, bodyLength * 1.5, 0, Math.PI * 2);
        context.fill();

        // Đuôi cá.
        context.save();
        context.translate(-bodyLength * .48, 0);
        context.rotate(Math.sin(koi.tailPhase * 5.5) * .32);
        context.fillStyle = isGold ? '#c99a53' : '#b61f34';
        context.beginPath();
        context.moveTo(0, 0);
        context.quadraticCurveTo(-bodyLength * .48, -bodyWidth * 1.05, -bodyLength * .95, 0);
        context.quadraticCurveTo(-bodyLength * .48, bodyWidth * 1.05, 0, 0);
        context.closePath();
        context.fill();
        context.restore();

        // Vây lưng.
        context.fillStyle = isGold ? 'rgba(201,154,83,.82)' : 'rgba(182,31,52,.82)';
        context.beginPath();
        context.moveTo(-10, -bodyWidth * .39);
        context.quadraticCurveTo(0, -bodyWidth * 1.12, 14, -bodyWidth * .43);
        context.quadraticCurveTo(4, -bodyWidth * .5, -10, -bodyWidth * .39);
        context.fill();

        // Thân cá.
        const bodyGradient = context.createLinearGradient(-bodyLength * .5, 0, bodyLength * .5, 0);
        bodyGradient.addColorStop(0, '#fffaf1');
        bodyGradient.addColorStop(.5, isGold ? '#f4e6cc' : '#fbf7ef');
        bodyGradient.addColorStop(1, isGold ? '#c99a53' : '#c52b40');
        context.fillStyle = bodyGradient;
        context.beginPath();
        context.ellipse(0, 0, bodyLength * .52, bodyWidth * .5, 0, 0, Math.PI * 2);
        context.fill();

        // Hoa văn trên lưng.
        context.fillStyle = isGold ? 'rgba(201,154,83,.67)' : 'rgba(138,21,37,.82)';
        context.beginPath();
        context.ellipse(7, -4, 8, 5.5, .35, 0, Math.PI * 2);
        context.fill();
        context.beginPath();
        context.ellipse(-9, 4, 5.5, 4.1, -.25, 0, Math.PI * 2);
        context.fill();

        // Vây ngực.
        context.fillStyle = 'rgba(251,247,239,.84)';
        context.beginPath();
        context.ellipse(5, bodyWidth * .48, 12, 4.5, .5, 0, Math.PI * 2);
        context.fill();

        // Đầu và mắt; không vẽ râu để giữ tạo hình tối giản.
        context.fillStyle = '#fffaf1';
        context.beginPath();
        context.ellipse(bodyLength * .42, 0, bodyWidth * .39, bodyWidth * .36, 0, 0, Math.PI * 2);
        context.fill();
        context.fillStyle = '#17110f';
        context.beginPath();
        context.arc(bodyLength * .51, -bodyWidth * .13, 2.4, 0, Math.PI * 2);
        context.fill();
        context.restore();
      }

      function animateKoi(time) {
        animationFrame = requestAnimationFrame(animateKoi);
        if (!context || !canvasWidth || !canvasHeight) return;
        if (document.hidden || !$('#view-home').classList.contains('active')) {
          previousTime = time;
          return;
        }
        const dt = previousTime ? Math.min(.04, (time - previousTime) / 1000) : .016;
        previousTime = time;
        context.clearRect(0, 0, canvasWidth, canvasHeight);
        koiList.forEach(koi => { updateKoi(koi, dt); drawKoi(koi); });
      }

      if (pond && canvas && context) {
        if ('ResizeObserver' in window) {
          resizeObserver = new ResizeObserver(resizeKoiCanvas);
          resizeObserver.observe(pond);
        } else {
          window.addEventListener('resize', resizeKoiCanvas, { passive: true });
        }
        resizeKoiCanvas();
        animationFrame = requestAnimationFrame(animateKoi);
      }

      document.addEventListener('visibilitychange', () => {
        if (!document.hidden) previousTime = 0;
      });
    })();
  </script>
</body>
</html>
