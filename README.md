
<html lang="vi">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>KOIFISH — Kho tàng website</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,500;0,9..144,600;0,9..144,700;1,9..144,400;1,9..144,500;1,9..144,600&family=Manrope:wght@400;500;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root{
    --cream: #F3E8D7;
    --cream-2: #E8D8BB;
    --paper: #FBF7EF;
    --ink: #15110D;
    --ink-soft: #302724;
    --koi-red: #B61F34;
    --koi-red-deep: #8A1525;
    --gold: #C99A53;
    --line: rgba(21,17,13,0.12);
    --shadow: 0 18px 40px rgba(21,17,13,0.10);
  }

  *{ box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{
    margin:0;
    background:
      radial-gradient(circle at top left, rgba(182,31,52,0.08), transparent 26%),
      radial-gradient(circle at bottom right, rgba(201,154,83,0.10), transparent 24%),
      var(--cream);
    color:var(--ink);
    font-family:'Manrope', sans-serif;
    overflow-x:hidden;
    position:relative;
  }

  body::before{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    background-image:
      radial-gradient(circle at 0 0, transparent 10px, rgba(232,216,187,0.55) 11px, transparent 12px);
    background-size:34px 34px;
    opacity:0.35;
    mix-blend-mode:multiply;
    z-index:0;
  }

  .eyebrow{
    display:inline-flex;
    align-items:center;
    gap:.7rem;
    font-family:'Space Mono', monospace;
    font-size:.72rem;
    letter-spacing:.22em;
    text-transform:uppercase;
    color:var(--koi-red-deep);
  }
  .eyebrow::before{
    content:"";
    width:22px;
    height:1px;
    background:var(--koi-red-deep);
  }

  .topbar{
    position:sticky;
    top:0;
    z-index:50;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:1rem;
    padding:.95rem 1.4rem;
    background:rgba(21,17,13,0.96);
    color:var(--paper);
    border-bottom:3px solid var(--koi-red);
    backdrop-filter: blur(10px);
  }

  .brand{
    display:flex;
    align-items:center;
    gap:.75rem;
    background:none;
    border:none;
    color:inherit;
    padding:0;
    cursor:pointer;
  }

  .seal{
    width:40px;
    height:40px;
    border-radius:50%;
    background:linear-gradient(145deg, #d42742, var(--koi-red-deep));
    display:grid;
    place-items:center;
    font-family:'Fraunces', serif;
    font-size:1.05rem;
    font-weight:700;
    box-shadow:
      0 0 0 2px rgba(251,247,239,.85) inset,
      0 8px 20px rgba(182,31,52,.35);
  }

  .brand-name{
    font-family:'Fraunces', serif;
    font-size:1.15rem;
    font-weight:600;
    letter-spacing:.02em;
  }
  .brand-name span{ color:var(--koi-red); font-style:italic; }

  .mainnav{
    display:flex;
    flex-wrap:wrap;
    gap:.35rem;
    justify-content:flex-end;
  }

  .nav-link{
    font-family:'Space Mono', monospace;
    font-size:.78rem;
    letter-spacing:.08em;
    text-transform:uppercase;
    color:var(--paper);
    opacity:.72;
    background:none;
    border:1px solid transparent;
    padding:.52rem .86rem;
    border-radius:999px;
    cursor:pointer;
    transition:.2s ease;
  }
  .nav-link:hover{ opacity:1; transform:translateY(-1px); }
  .nav-link.active{
    opacity:1;
    background:rgba(182,31,52,.18);
    border-color:rgba(182,31,52,.35);
  }

  main{ position:relative; z-index:1; }

  .view{ display:none; }
  .view.active{ display:block; animation:fadeIn .45s ease; }
  @keyframes fadeIn{
    from{ opacity:0; transform:translateY(10px); }
    to{ opacity:1; transform:translateY(0); }
  }

  .hero{
    position:relative;
    max-width:1180px;
    margin:0 auto;
    padding:5.2rem 1.4rem 4rem;
    overflow:hidden;
  }

  .hero-grid{
    display:grid;
    grid-template-columns:1.1fr .9fr;
    gap:2rem;
    align-items:center;
  }

  .hero-title{
    margin:.4rem 0 0;
    font-family:'Fraunces', serif;
    font-size:clamp(3rem, 9vw, 6.5rem);
    line-height:.92;
    font-weight:600;
    letter-spacing:-.03em;
  }
  .hero-title em{
    display:block;
    color:var(--koi-red);
    font-style:italic;
    font-weight:400;
  }

  .hero-sub{
    max-width:560px;
    margin:1.4rem 0 2rem;
    font-size:1.02rem;
    line-height:1.8;
    color:var(--ink-soft);
  }

  .hero-actions{
    display:flex;
    flex-wrap:wrap;
    gap:.9rem;
    margin-top:1.2rem;
  }

  .btn{
    display:inline-flex;
    align-items:center;
    justify-content:center;
    gap:.5rem;
    padding:.9rem 1.35rem;
    border-radius:999px;
    border:1px solid var(--ink);
    background:var(--ink);
    color:var(--paper);
    text-decoration:none;
    cursor:pointer;
    font-family:'Space Mono', monospace;
    font-size:.78rem;
    letter-spacing:.07em;
    text-transform:uppercase;
    transition:.18s ease;
    box-shadow:0 8px 18px rgba(21,17,13,.10);
  }
  .btn:hover{ transform:translateY(-2px); background:var(--koi-red); border-color:var(--koi-red); }
  .btn.ghost{
    background:transparent;
    color:var(--ink);
  }
  .btn.ghost:hover{ color:var(--paper); background:var(--koi-red-deep); border-color:var(--koi-red-deep); }

  .btn.soft{
    background:rgba(255,255,255,.40);
    color:var(--ink);
    border-color:rgba(21,17,13,.14);
  }
  .btn.soft:hover{ background:rgba(255,255,255,.65); }

  .stats{
    display:flex;
    flex-wrap:wrap;
    gap:2.6rem;
    margin-top:3rem;
    padding-top:2rem;
    border-top:1px solid var(--line);
  }
  .stat-num{
    font-family:'Fraunces', serif;
    font-size:3.2rem;
    line-height:1;
    font-weight:600;
    color:var(--koi-red);
  }
  .stat-label{
    margin-top:.45rem;
    max-width:200px;
    font-family:'Space Mono', monospace;
    font-size:.72rem;
    letter-spacing:.08em;
    text-transform:uppercase;
    color:var(--ink-soft);
  }

  .pond-wrap{
    position:relative;
    min-height:430px;
    border-radius:34px;
    background:
      radial-gradient(circle at 30% 25%, rgba(255,255,255,.35), transparent 22%),
      linear-gradient(160deg, rgba(251,247,239,.90), rgba(232,216,187,.92));
    border:1px solid rgba(21,17,13,.10);
    box-shadow:var(--shadow);
    overflow:hidden;
  }

  .pond{
    position:absolute;
    inset:0;
    background:
      radial-gradient(circle at 20% 30%, rgba(255,255,255,.30), transparent 18%),
      radial-gradient(circle at 70% 18%, rgba(182,31,52,.09), transparent 20%),
      radial-gradient(circle at 50% 55%, rgba(255,255,255,.16), transparent 24%),
      linear-gradient(180deg, rgba(251,247,239,.2), rgba(255,255,255,0));
  }

  .ripples{
    position:absolute;
    inset:0;
    filter:blur(.2px);
    opacity:.9;
  }
  .ripple{
    position:absolute;
    left:50%;
    top:56%;
    width:38px;
    height:38px;
    border-radius:50%;
    border:1.5px solid rgba(182,31,52,.55);
    transform:translate(-50%,-50%) scale(.2);
    animation:ripple 3.4s ease-out infinite;
  }
  .ripple:nth-child(2){ animation-delay:1.1s; left:42%; top:45%; }
  .ripple:nth-child(3){ animation-delay:2.1s; left:61%; top:62%; }
  @keyframes ripple{
    0%{ transform:translate(-50%,-50%) scale(.25); opacity:.55; }
    100%{ transform:translate(-50%,-50%) scale(5.4); opacity:0; }
  }
@keyframes float{

0%,100%{
transform:translateY(0px);
}

50%{
transform:translateY(-18px);
}

}
  .bubbles span{
    position:absolute;
    border-radius:50%;
    background:rgba(255,255,255,.45);
    box-shadow:0 0 0 1px rgba(182,31,52,.10) inset;
    animation:floatUp 7s linear infinite;
  }
  .bubbles span:nth-child(1){ width:11px;height:11px; left:18%; top:78%; animation-delay:0s; }
  .bubbles span:nth-child(2){ width:7px;height:7px; left:29%; top:84%; animation-delay:1.2s; }
  .bubbles span:nth-child(3){ width:13px;height:13px; left:67%; top:86%; animation-delay:2.1s; }
  .bubbles span:nth-child(4){ width:8px;height:8px; left:78%; top:70%; animation-delay:3s; }
  .bubbles span:nth-child(5){ width:10px;height:10px; left:58%; top:92%; animation-delay:4.3s; }
  @keyframes floatUp{
    0%{ transform:translateY(0) scale(.9); opacity:0; }
    10%{ opacity:.7; }
    100%{ transform:translateY(-180px) scale(1.2); opacity:0; }
  }

  .section-shell{
    max-width:1180px;
    margin:0 auto;
    padding:3.4rem 1.4rem 5rem;
  }

  .section-head{ margin-bottom:2rem; }
  .section-title{
    margin:.35rem 0 0;
    font-family:'Fraunces', serif;
    font-size:clamp(2.1rem, 5vw, 3rem);
    font-weight:600;
    line-height:1.05;
  }

  .about-block{
    max-width:1180px;
    margin:0 auto;
    padding:0 1.4rem 5rem;
    display:grid;
    grid-template-columns:.85fr 1.15fr;
    gap:2rem;
  }
  .about-block p{
    line-height:1.8;
    color:var(--ink-soft);
    margin:0 0 1rem;
  }

  .site-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill, minmax(280px, 1fr));
    gap:1.2rem;
  }

  .site-card,
  .form-card,
  .manage-item,
  .lock-card,
  .contact-card{
    background:rgba(251,247,239,.92);
    border:1px solid var(--line);
    box-shadow:var(--shadow);
    backdrop-filter: blur(6px);
  }

  .site-card{
    border-left:4px solid var(--koi-red);
    border-radius:24px;
    padding:1.4rem;
    display:flex;
    flex-direction:column;
    gap:.8rem;
  }
  .site-card .tag{
    font-family:'Space Mono', monospace;
    font-size:.68rem;
    letter-spacing:.1em;
    text-transform:uppercase;
    color:var(--gold);
  }
  .site-card h3{
    margin:0;
    font-family:'Fraunces', serif;
    font-size:1.35rem;
    font-style:italic;
    font-weight:500;
  }
  .site-card p{
    margin:0;
    color:var(--ink-soft);
    line-height:1.65;
    font-size:.92rem;
    flex:1;
  }
  .visit{
    align-self:flex-start;
    font-family:'Space Mono', monospace;
    font-size:.74rem;
    letter-spacing:.06em;
    text-transform:uppercase;
    color:var(--ink);
    text-decoration:none;
    border-bottom:1px solid var(--koi-red);
    padding-bottom:2px;
  }
  .visit:hover{ color:var(--koi-red); }

  .empty-note{
    padding:1.6rem;
    text-align:center;
    border:1px dashed rgba(21,17,13,.18);
    border-radius:20px;
    color:var(--ink-soft);
    font-family:'Space Mono', monospace;
    font-size:.84rem;
  }

  .lock-card{
    max-width:440px;
    margin:2rem auto 0;
    padding:2rem;
    border-radius:28px;
    text-align:center;
  }
  .lock-icon{
    width:44px;
    height:44px;
    margin:0 auto 1rem;
    color:var(--koi-red);
  }
  .lock-card h3{
    margin:0 0 .4rem;
    font-family:'Fraunces', serif;
    font-size:1.25rem;
  }
  .lock-card p{
    margin:0 0 1.2rem;
    color:var(--ink-soft);
    font-size:.92rem;
  }
  .lock-form{
    display:flex;
    gap:.6rem;
  }
  .lock-form input{
    flex:1;
    padding:.78rem .95rem;
    border:1px solid var(--line);
    border-radius:14px;
    background:rgba(243,232,215,.72);
    font-family:'Space Mono', monospace;
    font-size:.95rem;
    letter-spacing:.14em;
    text-transform:uppercase;
  }
  .lock-form input:focus,
  input:focus,
  textarea:focus{
    outline:2px solid rgba(182,31,52,.36);
    outline-offset:1px;
  }
  .lock-error{
    display:none;
    margin-top:.9rem;
    color:var(--koi-red-deep);
    font-family:'Space Mono', monospace;
    font-size:.78rem;
  }
  .lock-error.show{
    display:block;
    animation:shake .3s ease;
  }
  @keyframes shake{
    0%,100%{ transform:translateX(0); }
    25%{ transform:translateX(-6px); }
    75%{ transform:translateX(6px); }
  }

  .manage-panel{ display:none; }
  .manage-panel.show{ display:block; }

  .form-card{
    border-radius:28px;
    padding:1.7rem;
    margin-bottom:1.2rem;
  }
  .form-card h4{
    margin:0 0 1rem;
    font-family:'Fraunces', serif;
    font-size:1.2rem;
  }

  .form-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:1rem;
  }
  .form-grid .full{ grid-column:1 / -1; }

  @media (max-width:640px){
    .form-grid{ grid-template-columns:1fr; }
    .lock-form{ flex-direction:column; }
    .hero-grid{ grid-template-columns:1fr; }
    .pond-wrap{ min-height:360px; }
    .about-block{ grid-template-columns:1fr; }
  }

  label{
    display:block;
    margin:0 0 .38rem;
    font-family:'Space Mono', monospace;
    font-size:.68rem;
    letter-spacing:.08em;
    text-transform:uppercase;
    color:var(--ink-soft);
  }

  input[type=text],
  input[type=url],
  textarea{
    width:100%;
    padding:.72rem .82rem;
    border:1px solid var(--line);
    border-radius:14px;
    background:rgba(243,232,215,.70);
    color:var(--ink);
    font-family:'Manrope', sans-serif;
    font-size:.92rem;
    resize:vertical;
  }

  .manage-item{
    border-radius:26px;
    padding:1.3rem;
    margin-bottom:1rem;
  }

  .item-actions{
    display:flex;
    gap:.6rem;
    justify-content:flex-end;
    margin-top:.8rem;
    flex-wrap:wrap;
  }

  .btn.small{
    padding:.62rem .95rem;
    font-size:.7rem;
  }
  .btn.danger{
    background:transparent;
    color:var(--koi-red-deep);
    border-color:var(--koi-red-deep);
  }
  .btn.danger:hover{
    background:var(--koi-red-deep);
    color:var(--paper);
  }

  .save-msg{
    display:none;
    margin-top:.7rem;
    color:var(--koi-red-deep);
    font-family:'Space Mono', monospace;
    font-size:.72rem;
  }
  .save-msg.show{ display:block; }

  .manage-top-actions{
    display:flex;
    gap:.7rem;
    flex-wrap:wrap;
    margin-top:1rem;
  }

  .contact-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(230px, 1fr));
    gap:1.1rem;
  }
  .contact-card{
    border-radius:26px;
    padding:1.5rem;
    text-decoration:none;
    color:var(--ink);
    display:flex;
    flex-direction:column;
    gap:.75rem;
    transition:.18s ease;
  }
  .contact-card:hover{
    transform:translateY(-3px);
    border-color:rgba(182,31,52,.38);
  }
  .contact-card .icon{
    width:28px;
    height:28px;
    color:var(--koi-red);
  }
  .clabel{
    font-family:'Space Mono', monospace;
    font-size:.68rem;
    letter-spacing:.08em;
    text-transform:uppercase;
    color:var(--ink-soft);
  }
  .cvalue{
    font-family:'Fraunces', serif;
    font-size:1.15rem;
    font-weight:500;
  }

  .maker-note{
    margin-top:2.2rem;
    padding-top:1.7rem;
    border-top:1px solid var(--line);
    color:var(--ink-soft);
    font-family:'Space Mono', monospace;
    font-size:.8rem;
  }
  .maker-note b{ color:var(--koi-red-deep); }

  footer{
    position:relative;
    z-index:1;
    text-align:center;
    padding:2rem 1rem;
    border-top:1px solid var(--line);
    color:var(--ink-soft);
    font-family:'Space Mono', monospace;
    font-size:.72rem;
  }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    .view.active,
    .ripple,
    .koi,
    .fish-tail,
    .fish-fin,
    .bubbles span{
      animation:none !important;
    }
  }
 .hero-koi{
    position:absolute;
    inset:0;
    z-index:6;
    pointer-events:none;
}

.hero-koi canvas{
    width:100%;
    height:100%;
    display:block;
}
</style>
</head>
<body>

<header class="topbar">
  <button class="brand" data-view="home" title="Về trang chủ">
    <span class="seal">鯉</span>
    <span class="brand-name">KOI<span>FISH</span></span>
  </button>

  <nav class="mainnav">
    <button class="nav-link active" data-view="home">Trang chủ</button>
    <button class="nav-link" data-view="websites">Website</button>
    <button class="nav-link" data-view="manage">Quản lý</button>
    <button class="nav-link" data-view="contact">Liên hệ</button>
  </nav>
</header>

<main>
  <section id="view-home" class="view active">
    <div class="hero">
      <div class="hero-grid">
        <div>
          <span class="eyebrow">NISHIKI HUB</span>
          <h1 class="hero-title">NISHIKI<em>HUB</em></h1>
          <p class="hero-sub">
           Đây là Nishiki Hub lưu trữ từng dự án web,mỗi trang là một không gian độc đáo, được chăm chút và phát triển bởi KoiFish. Hãy khám NishikiHub này để tìm thấy những website dộc đáo
          </p>

          <div class="hero-actions">
            <button class="btn" data-view="websites">Xem website</button>
            <button class="btn ghost" data-view="manage">Vào quản lý</button>
          </div>

          <div class="stats">
            <div>
              <div class="stat-num" id="stat-count">00</div>
              <div class="stat-label">website đang được lưu giữ</div>
            </div>
            <div>
              <div class="stat-num">01</div>
              <div class="stat-label">người phát triển — KoiFish</div>
            </div>
          </div>
        </div>

        <div class="pond-wrap" aria-hidden="true">
          <div class="pond"></div>
          <div class="ripples">
            <div class="ripple"></div>
            <div class="ripple"></div>
            <div class="ripple"></div>
          </div>

          <div class="hero-koi">
            <canvas id="koiCanvas"></canvas>
          </div>

          <div class="bubbles">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
          </div>

        </div>
      </div>
    </div>

    <div class="about-block">
      <div>
        <span class="eyebrow">Giới thiệu</span>
        <h2 class="section-title" style="margin-top:.35rem;">Kho tàng web<br><em style="color:var(--koi-red); font-style:italic; font-weight:400;">NISHIKI HUB</em></h2>
      </div>
      <div>
        <p>NISHIKI HUB là nơi lưu trữ toàn bộ những website Koi đã tự tay xây dựng từ những trang nhỏ thử nghiệm đến các dự án được đầu tư kỹ hơn. Thay vì để chúng nằm rải rác, mọi thứ được gom lại một chỗ, có tên gọi, có mô tả và có đường dẫn rõ ràng.</p>
       <p>Vào mục <b>Website</b> để xem toàn bộ danh sách, mục <b>Quản lý</b> để thêm/sửa/xoá (cần mật khẩu), và mục <b>Liên hệ</b> nếu muốn nói chuyện trực tiếp với KOI để được hỗ trợ hoặc góp ý.</p>
    </div>
        </div>
  </section>

  <section id="view-websites" class="view">
    <div class="section-shell">
      <div class="section-head">
        <span class="eyebrow">Danh sách</span>
        <h2 class="section-title">Website</h2>
      </div>
      <div class="site-grid" id="site-grid"></div>
    </div>
  </section>

  <section id="view-manage" class="view">
    <div class="section-shell">
      <div class="section-head">
        <span class="eyebrow">Khu vực riêng</span>
        <h2 class="section-title">Quản lý Hub</h2>
      </div>

      <div class="lock-card" id="lock-card">
        <svg class="lock-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round">
          <rect x="4" y="10" width="16" height="10" rx="1.8"></rect>
          <path d="M7 10V7a5 5 0 0 1 10 0v3"></path>
        </svg>
        <h3>Khu vực đang khoá</h3>
        <p>Nhập mật khẩu để mở khoá phần thêm, sửa và xoá website.</p>
        <div class="lock-form">
          <input type="text" id="pw-input" placeholder="Mật khẩu" autocomplete="off">
          <button class="btn" id="unlock-btn">Mở khoá</button>
        </div>
        <div class="lock-error" id="lock-error">Sai mật khẩu, vui lòng thử lại.</div>
      </div>

      <div class="manage-panel" id="manage-panel">
        <div class="form-card">
          <h4>Thêm website mới</h4>
          <div class="form-grid">
            <div>
              <label>Tên website</label>
              <input type="text" id="new-title" placeholder="Ví dụ: Website 03">
            </div>
            <div>
              <label>Đường dẫn (URL)</label>
              <input type="url" id="new-url" placeholder="https://...">
            </div>
            <div class="full">
              <label>Giới thiệu</label>
              <textarea id="new-desc" rows="2" placeholder="Mô tả ngắn cho website này"></textarea>
            </div>
          </div>
          <div style="margin-top:1rem; display:flex; justify-content:flex-end; gap:.7rem; flex-wrap:wrap;">
            <button class="btn soft" id="clear-form-btn" type="button">Xoá ô nhập</button>
            <button class="btn" id="add-btn" type="button">Thêm website</button>
          </div>

          <div class="manage-top-actions">
            <button class="btn danger small" id="delete-all-btn" type="button">Xoá toàn bộ website</button>
          </div>
        </div>

        <div id="manage-list"></div>
      </div>
    </div>
  </section>

  <section id="view-contact" class="view">
    <div class="section-shell">
      <div class="section-head">
        <span class="eyebrow">Kết nối</span>
        <h2 class="section-title">Liên hệ</h2>
      </div>

      <div class="contact-grid">
        <a class="contact-card" href="https://www.tiktok.com/@_oki__ne_" target="_blank" rel="noopener">
          <svg class="icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
            <path d="M16.6 5.82c-.9-.78-1.47-1.9-1.6-3.14h-3.14v13.3c0 1.53-1.24 2.77-2.77 2.77a2.77 2.77 0 0 1 0-5.54c.25 0 .5.03.73.09V9.9a6.1 6.1 0 0 0-.73-.04A6.13 6.13 0 0 0 3 16.06 6.13 6.13 0 0 0 9.09 22a6.13 6.13 0 0 0 6.13-6.13V9.01a9.1 9.1 0 0 0 5.28 1.7V7.6a5.6 5.6 0 0 1-3.9-1.78Z"/>
          </svg>
          <span class="clabel">TikTok</span>
          <span class="cvalue">@_oki__ne_</span>
        </a>

        <a class="contact-card" href="https://www.facebook.com/share/1Uj8VCKwVm/" target="_blank" rel="noopener">
          <svg class="icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
            <path d="M13.5 21v-7.6h2.6l.4-3H13.5V8.4c0-.87.24-1.46 1.5-1.46h1.6V4.24C16.3 4.17 15.3 4 14.2 4c-2.3 0-3.9 1.4-3.9 4v2.4H7.7v3h2.6V21h3.2Z"/>
          </svg>
          <span class="clabel">Facebook</span>
          <span class="cvalue">KoiFish</span>
        </a>

        <a class="contact-card" href="tel:0367634821">
          <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <path d="M4 5c0-.6.4-1 1-1h3l2 5-2 1.5a11 11 0 0 0 5.5 5.5L15 14l5 2v3c0 .6-.4 1-1 1C10.5 20 4 13.5 4 5Z"></path>
          </svg>
          <span class="clabel">Điện thoại</span>
          <span class="cvalue">0367 634 821</span>
        </a>
      </div>

      <div class="maker-note">
        Website được tạo và phát triển bởi <b>KoiFish</b>.
      </div>
    </div>
  </section>
</main>

<footer>© <span id="year"></span> KOIFISH — NISHIKI HUB</footer>

<script>
(() => {

  const PASSWORD = '24102011';

  let unlocked = false;
  let websites = loadWebsites();

function loadWebsites() {
   
    return [

        {
            id:1,
            title:"KOI DICTIONARY",
            url:"https://2410phongnguyen-eng.github.io/KOIDICTIONARY/",
            desc:"Bạn có thể tra cứu các từ vựng Anh,Trung,Nhật,Việt.Bạn có thể luyện tập nghe, nói về các từ vựng trong từ điển để nâng cao vốn từ vừng."
        },

        {
            id:2,
            title:"KOI LABORATORY",
            url:"https://2410phongnguyen-eng.github.io/KOILABORATORY/",
            desc:"Nơi bạn có thể thực hành các thí nghiệm hóa học và mở khóa chất mới.Đồng thời,có thể thực hiện nhiều phương trình hóa học vô cơ và hữu cơ khác nhau."
        },
 {
            id:3,
            title:"KOI MUSIC",
            url:"https://2410phongnguyen-eng.github.io/KOIMUSIC/",
            desc:"Nơi bạn có thể kiến tạo một không gian âm nhạc không giới hạn của riêng mình. Bạn có thể nghe nhạc, tạo nhạc, tạo danh sách phát và chia sẻ với bạn bè."
        },

        {
            id:4,
            title:"KOI HOROSCOPE",
            url:"https://2410phongnguyen-eng.github.io/KOIHOROSCOPE/",
            desc:"Nơi bạn có thể chiêm nghiệm vận số của riêng mình. Bạn có thể gieo quẻ kinh dịch và luận tử vi của chính mình"
        }, 
    ];
}

  function saveWebsites() {
    try {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(websites));
    } catch (_) {}
  }

  function escapeHtml(str) {
    return String(str ?? '')
      .replace(/&/g, '&amp;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;')
      .replace(/"/g, '&quot;')
      .replace(/'/g, '&#39;');
  }

  function nextId() {
    return websites.reduce((max, w) => Math.max(max, Number(w.id) || 0), 0) + 1;
  }

  function updateHomeStats() {
    document.getElementById('stat-count').textContent = String(websites.length).padStart(2, '0');
  }

  function renderSiteGrid() {
    const grid = document.getElementById('site-grid');

    if (!websites.length) {
      grid.innerHTML = '<div class="empty-note">Hub hiện chưa có website nào. Vào mục Quản lý để thêm website đầu tiên.</div>';
      return;
    }

    grid.innerHTML = websites.map((w, i) => {
      const safeUrl = String(w.url || '#').trim();
      return `
        <div class="site-card">
          <span class="tag">#${String(i + 1).padStart(2, '0')}</span>
          <h3>${escapeHtml(w.title || 'Không tên')}</h3>
          <p>${escapeHtml(w.desc || 'Chưa có mô tả.')}</p>
          <a class="visit" href="${escapeHtml(safeUrl)}" target="_blank" rel="noopener">Truy cập website →</a>
        </div>
      `;
    }).join('');
  }

function renderManageList() {
    const list = document.getElementById("manage-list");

    list.innerHTML = "";

    if (websites.length === 0) {
        list.innerHTML =
            '<div class="empty-note">Chưa có website nào trong hub.</div>';
        return;
    }

    websites.forEach((w) => {

        const div = document.createElement("div");
        div.className = "manage-item";
        div.dataset.id = w.id;

        div.innerHTML = `
        <div class="form-grid">

            <div>
                <label>Tên website</label>
                <input class="f-title" value="${escapeHtml(w.title)}">
            </div>

            <div>
                <label>URL</label>
                <input class="f-url" value="${escapeHtml(w.url)}">
            </div>

            <div class="full">
                <label>Mô tả</label>
                <textarea class="f-desc">${escapeHtml(w.desc)}</textarea>
            </div>

        </div>

        <div class="item-actions">
            <button class="btn danger small act-delete">Xóa</button>
            <button class="btn small act-save">Lưu</button>
        </div>

        <div class="save-msg">Đã lưu.</div>
        `;

        list.appendChild(div);
    });

    list.querySelectorAll(".act-save").forEach(btn=>{
        btn.onclick=saveWebsite;
    });

    list.querySelectorAll(".act-delete").forEach(btn=>{
        btn.onclick=deleteWebsite;
    });
}
localStorage.removeItem('koifish_websites_v2_empty');
localStorage.clear();
function saveWebsite(e){

}

function deleteWebsite(e){

    const item=e.target.closest(".manage-item");

    const id=Number(item.dataset.id);

    if(!confirm("Xóa website này?")) return;

    websites=websites.filter(x=>x.id!==id);

    saveWebsites();

    renderManageList();

    renderSiteGrid();

    updateHomeStats();
}
  function switchView(view) {
    document.querySelectorAll('.view').forEach(v => v.classList.remove('active'));
    const target = document.getElementById('view-' + view);
    if (target) target.classList.add('active');

    document.querySelectorAll('.nav-link').forEach(btn => {
      btn.classList.toggle('active', btn.getAttribute('data-view') === view);
    });

    if (view === 'websites') renderSiteGrid();
    if (view === 'home') updateHomeStats();
    if (view === 'manage' && unlocked) renderManageList();

    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  document.querySelectorAll('[data-view]').forEach(el => {
    el.addEventListener('click', () => switchView(el.getAttribute('data-view')));
  });

  const pwInput = document.getElementById('pw-input');
  const unlockBtn = document.getElementById('unlock-btn');
  const lockCard = document.getElementById('lock-card');
  const lockError = document.getElementById('lock-error');
  const managePanel = document.getElementById('manage-panel');

  function tryUnlock() {
    if (pwInput.value === PASSWORD) {
      unlocked = true;
      lockCard.style.display = 'none';
      managePanel.classList.add('show');
      renderManageList();
    } else {
      lockError.classList.remove('show');
      void lockError.offsetWidth;
      lockError.classList.add('show');
    }
  }

  unlockBtn.addEventListener('click', tryUnlock);
  pwInput.addEventListener('keydown', e => {
    if (e.key === 'Enter') tryUnlock();
  });

  document.getElementById('add-btn').addEventListener('click', () => {
    const title = document.getElementById('new-title').value.trim();
    const url = document.getElementById('new-url').value.trim();
    const desc = document.getElementById('new-desc').value.trim();

    if (!title || !url) {
      alert('Vui lòng nhập tên và đường dẫn website.');
      return;
    }

   websites.push({
    id: Date.now(),
    title: title,
    url: url,
    desc: desc || "Chưa có mô tả."
});

    saveWebsites();
    document.getElementById('new-title').value = '';
    document.getElementById('new-url').value = '';
    document.getElementById('new-desc').value = '';

    if (unlocked) renderManageList();
    renderSiteGrid();
    updateHomeStats();
  });

  document.getElementById('clear-form-btn').addEventListener('click', () => {
    document.getElementById('new-title').value = '';
    document.getElementById('new-url').value = '';
    document.getElementById('new-desc').value = '';
  });

  document.getElementById('delete-all-btn').addEventListener('click', () => {
    if (!confirm('Xoá toàn bộ website trong hub?')) return;
    websites = [];
    saveWebsites();
    renderSiteGrid();
    updateHomeStats();
    if (unlocked) renderManageList();
  });

  document.getElementById('year').textContent = new Date().getFullYear();

  updateHomeStats();
  renderSiteGrid();
})();
</script>

<script>
/* ============================================================
   CÁ KOI BƠI TRONG HỒ (canvas) — chuyển thể từ vẽ cá Koi
   trong "Cá Koi Thần - Hành Trình Hóa Rồng"
============================================================ */
(() => {
  const canvas = document.getElementById('koiCanvas');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  const wrap = canvas.closest('.pond-wrap');

  let W = 0, H = 0, DPR = Math.min(window.devicePixelRatio || 1, 2);

  function resize() {
    const rect = wrap.getBoundingClientRect();
    W = rect.width; H = rect.height;
    canvas.width = W * DPR; canvas.height = H * DPR;
    canvas.style.width = W + 'px'; canvas.style.height = H + 'px';
    ctx.setTransform(DPR, 0, 0, DPR, 0, 0);
  }
  window.addEventListener('resize', resize);

  // Hai chú cá koi bơi lượn tự do trong khung hồ
  function makeKoi(opts) {
    return {
      x: opts.x, y: opts.y, angle: opts.angle,
      vx: 0, vy: 0, tailPhase: Math.random() * 10,
      targetX: opts.x, targetY: opts.y, retargetT: 0,
      scale: opts.scale, palette: opts.palette,
      speed: opts.speed,
    };
  }

  let kois = [];
  function initKois() {
    kois = [
      makeKoi({ x: W * 0.35, y: H * 0.4, angle: 0, scale: 1, speed: 46, palette: 'red' }),
      makeKoi({ x: W * 0.6, y: H * 0.62, angle: Math.PI, scale: 0.72, speed: 38, palette: 'gold' }),
    ];
  }

  function pickTarget(k) {
    const pad = 60 * k.scale;
    k.targetX = pad + Math.random() * Math.max(10, (W - pad * 2));
    k.targetY = pad + Math.random() * Math.max(10, (H - pad * 2));
    k.retargetT = 3 + Math.random() * 4;
  }

  function updateKoi(k, dt) {
    k.retargetT -= dt;
    if (k.retargetT <= 0 || Math.hypot(k.targetX - k.x, k.targetY - k.y) < 24) {
      pickTarget(k);
    }
    const dx = k.targetX - k.x, dy = k.targetY - k.y;
    const dist = Math.hypot(dx, dy) || 1;
    const targetAngle = Math.atan2(dy, dx);
    let diff = targetAngle - k.angle;
    while (diff > Math.PI) diff -= Math.PI * 2;
    while (diff < -Math.PI) diff += Math.PI * 2;
    k.angle += diff * Math.min(1, dt * 2.2);

    const spd = Math.min(dist * 1.4, k.speed);
    k.vx += (Math.cos(k.angle) * spd - k.vx) * Math.min(1, dt * 2.4);
    k.vy += (Math.sin(k.angle) * spd - k.vy) * Math.min(1, dt * 2.4);
    k.x += k.vx * dt; k.y += k.vy * dt;
    k.tailPhase += dt * (3.2 + Math.hypot(k.vx, k.vy) * 0.03);
  }

  function drawKoi(k) {
    const stage = k.palette;
    ctx.save();
    ctx.translate(k.x, k.y);
    ctx.rotate(k.angle);
    ctx.scale(k.scale, k.scale);

    const bob = Math.sin(k.tailPhase * 1.2) * 1.6;
    ctx.translate(0, bob);

    const bodyLen = 46, bodyW = 18;

    // hào quang mờ dưới nước
    ctx.save();
    ctx.globalAlpha = 0.18;
    const glow = ctx.createRadialGradient(0, 0, 4, 0, 0, bodyLen * 1.3);
    glow.addColorStop(0, stage === 'gold' ? 'rgba(201,154,83,0.55)' : 'rgba(182,31,52,0.4)');
    glow.addColorStop(1, 'rgba(0,0,0,0)');
    ctx.fillStyle = glow;
    ctx.beginPath(); ctx.arc(0, 0, bodyLen * 1.3, 0, Math.PI * 2); ctx.fill();
    ctx.restore();

    // đuôi
    const tailWave = Math.sin(k.tailPhase * 6) * 0.5;
    ctx.save();
    ctx.translate(-bodyLen * 0.55, 0);
    ctx.rotate(tailWave * 0.6);
    ctx.fillStyle = stage === 'gold' ? '#C99A53' : '#B61F34';
    ctx.beginPath();
    ctx.moveTo(0, 0);
    ctx.quadraticCurveTo(-bodyLen * 0.55, -bodyW * 1.1, -bodyLen * 0.95, 0);
    ctx.quadraticCurveTo(-bodyLen * 0.55, bodyW * 1.1, 0, 0);
    ctx.closePath(); ctx.fill();
    ctx.restore();

    // vây lưng
    ctx.fillStyle = stage === 'gold' ? 'rgba(201,154,83,0.85)' : 'rgba(182,31,52,0.85)';
    ctx.beginPath();
    ctx.moveTo(-6, -bodyW * 0.6);
    ctx.quadraticCurveTo(4, -bodyW * 1.5, 18, -bodyW * 0.5);
    ctx.quadraticCurveTo(6, -bodyW * 0.6, -6, -bodyW * 0.6);
    ctx.fill();

    // thân
    const bodyGrad = ctx.createLinearGradient(-bodyLen * 0.5, 0, bodyLen * 0.5, 0);
    if (stage === 'gold') {
      bodyGrad.addColorStop(0, '#FBF7EF'); bodyGrad.addColorStop(0.55, '#F3E8D7'); bodyGrad.addColorStop(1, '#C99A53');
    } else {
      bodyGrad.addColorStop(0, '#FBF7EF'); bodyGrad.addColorStop(0.55, '#FBF7EF'); bodyGrad.addColorStop(1, '#B61F34');
    }
    ctx.fillStyle = bodyGrad;
    ctx.beginPath();
    ctx.ellipse(0, 0, bodyLen * 0.5, bodyW * 0.5, 0, 0, Math.PI * 2);
    ctx.fill();

    // đốm hoa văn
    ctx.fillStyle = 'rgba(138,21,37,0.5)';
    ctx.beginPath(); ctx.ellipse(8, -4, 7, 5, 0.4, 0, Math.PI * 2); ctx.fill();
    ctx.beginPath(); ctx.ellipse(-6, 5, 5, 4, 0.2, 0, Math.PI * 2); ctx.fill();

    // vây ngực
    ctx.fillStyle = 'rgba(251,247,239,0.75)';
    ctx.beginPath();
    ctx.ellipse(6, bodyW * 0.45, 12, 5, 0.6, 0, Math.PI * 2);
    ctx.fill();

    // đầu + mắt
    ctx.fillStyle = '#FBF7EF';
    ctx.beginPath(); ctx.ellipse(bodyLen * 0.42, 0, bodyW * 0.42, bodyW * 0.38, 0, 0, Math.PI * 2); ctx.fill();
    ctx.fillStyle = '#15110D';
    ctx.beginPath(); ctx.arc(bodyLen * 0.52, -bodyW * 0.14, 2.6, 0, Math.PI * 2); ctx.fill();


    ctx.restore();
  }

  let lastT = performance.now();
  function loop(now) {
    const dt = Math.min(0.04, (now - lastT) / 1000);
    lastT = now;
    if (W > 0 && H > 0) {
      ctx.clearRect(0, 0, W, H);
      for (const k of kois) { updateKoi(k, dt); drawKoi(k); }
    }
    requestAnimationFrame(loop);
  }

  function boot() {
    resize();
    initKois();
    requestAnimationFrame(loop);
  }

  if (document.readyState === 'complete' || document.readyState === 'interactive') {
    boot();
  } else {
    window.addEventListener('DOMContentLoaded', boot);
  }
})();
</script>

</body>
</html>
