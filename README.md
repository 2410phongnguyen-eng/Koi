<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kho Tàng Của Koi</title>
  <meta name="description" content="Trang chủ Kho Tàng Của Koi - một nơi lưu trữ các website yêu thích với giao diện thanh lịch và tinh tế." />
  <style>
    :root{
      --bg: #f5ead9;
      --bg-2: #efe0c7;
      --paper: rgba(255, 251, 245, .72);
      --paper-strong: rgba(255, 254, 251, .92);
      --paper-dark: rgba(28, 22, 20, .92);
      --text: #241b18;
      --muted: #705e54;
      --line: rgba(36, 27, 24, .10);
      --line-2: rgba(180, 35, 24, .14);
      --accent: #b42318;
      --accent-2: #7e231c;
      --dark: #161110;
      --shadow: 0 24px 60px rgba(58, 36, 26, .12);
      --shadow-soft: 0 12px 28px rgba(58, 36, 26, .08);
      --radius-xl: 34px;
      --radius-lg: 24px;
      --radius-md: 18px;
      --radius-sm: 14px;
      --max: 1220px;
    }

    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      min-height:100vh;
      overflow-x:hidden;
      color:var(--text);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
      background:
        radial-gradient(circle at 8% 10%, rgba(180,35,24,.11), transparent 22%),
        radial-gradient(circle at 92% 16%, rgba(20,16,15,.09), transparent 20%),
        radial-gradient(circle at 50% 115%, rgba(180,35,24,.08), transparent 26%),
        linear-gradient(180deg, var(--bg), var(--bg-2));
    }

    a{color:inherit; text-decoration:none}
    button,input,textarea{font:inherit}
    button{border:none}
    ::selection{background:rgba(180,35,24,.18)}

    .ambient{
      position:fixed;
      inset:auto;
      pointer-events:none;
      z-index:0;
      border-radius:50%;
      filter:blur(12px);
      opacity:.6;
    }
    .ambient.a{width:320px; height:320px; top:-120px; right:-100px; background:radial-gradient(circle, rgba(180,35,24,.18), transparent 66%);}
    .ambient.b{width:380px; height:380px; bottom:-160px; left:-140px; background:radial-gradient(circle, rgba(36,27,24,.09), transparent 72%);}

    .wrap{
      width:min(var(--max), calc(100% - 28px));
      margin:0 auto;
      position:relative;
      z-index:1;
    }

    .topbar{
      position:sticky;
      top:0;
      z-index:30;
      backdrop-filter: blur(20px);
      background: rgba(245, 234, 217, .72);
      border-bottom:1px solid rgba(36,27,24,.08);
    }
    .topbar-inner{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:18px;
      padding:14px 0;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:14px;
      min-width:0;
    }
    .brand-mark{
      width:54px;
      height:54px;
      border-radius:18px;
      display:grid;
      place-items:center;
      color:#f7ead7;
      background: linear-gradient(145deg, #2a1f1c, #0f0b0a);
      box-shadow: var(--shadow-soft);
      position:relative;
      overflow:hidden;
      flex:0 0 auto;
    }
    .brand-mark::after{
      content:"";
      position:absolute;
      inset:-40% -20%;
      background: linear-gradient(45deg, transparent 42%, rgba(180,35,24,.48), transparent 58%);
      transform: rotate(18deg);
    }
    .brand-mark span{
      position:relative;
      z-index:1;
      font-size:22px;
      font-weight:900;
      letter-spacing:.5px;
    }
    .brand h1{
      margin:0;
      font-size:1.06rem;
      line-height:1.15;
      letter-spacing:.2px;
    }
    .brand p{
      margin:4px 0 0;
      color:var(--muted);
      font-size:.92rem;
      line-height:1.4;
    }

    .pill-row{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      justify-content:flex-end;
    }
    .pill{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:10px 14px;
      border-radius:999px;
      border:1px solid rgba(36,27,24,.10);
      background: rgba(255, 251, 245, .68);
      color:var(--text);
      box-shadow: 0 8px 18px rgba(58,36,26,.05);
      cursor:pointer;
      transition:.22s ease;
    }
    .pill:hover{
      transform: translateY(-1px);
      border-color: rgba(180,35,24,.22);
      box-shadow: 0 12px 22px rgba(58,36,26,.08);
    }
    .pill strong{color:var(--accent)}

    .hero{
      padding:28px 0 18px;
    }
    .hero-card{
      position:relative;
      overflow:hidden;
      border-radius: 36px;
      border:1px solid rgba(36,27,24,.10);
      background:
        linear-gradient(135deg, rgba(255,255,255,.62), rgba(255,249,239,.82));
      box-shadow: var(--shadow);
      padding: 28px;
    }
    .hero-card::before,
    .hero-card::after{
      content:"";
      position:absolute;
      border-radius:50%;
      pointer-events:none;
    }
    .hero-card::before{
      width:260px;
      height:260px;
      right:-90px;
      top:-110px;
      background: radial-gradient(circle, rgba(180,35,24,.18), transparent 70%);
    }
    .hero-card::after{
      width:300px;
      height:300px;
      left:-130px;
      bottom:-170px;
      background: radial-gradient(circle, rgba(36,27,24,.08), transparent 72%);
    }

    .hero-grid{
      position:relative;
      z-index:1;
      display:grid;
      grid-template-columns: 1.2fr .8fr;
      gap:22px;
      align-items:stretch;
    }

    .eyebrow{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:8px 12px;
      border-radius:999px;
      background: rgba(180,35,24,.08);
      color:var(--accent-2);
      border:1px solid rgba(180,35,24,.10);
      font-size:.84rem;
      font-weight:700;
      letter-spacing:.18px;
      margin-bottom:14px;
    }

    .hero h2{
      margin:0 0 12px;
      font-size: clamp(2rem, 4.3vw, 4rem);
      line-height:1.02;
      letter-spacing:-.04em;
    }
    .hero h2 .accent{color:var(--accent)}
    .hero p{
      margin:0;
      max-width:64ch;
      color:var(--muted);
      font-size:1.02rem;
      line-height:1.8;
    }

    .hero-actions{
      display:flex;
      gap:12px;
      flex-wrap:wrap;
      margin-top:22px;
    }
    .btn{
      border:none;
      border-radius: 16px;
      padding:13px 18px;
      cursor:pointer;
      transition:.2s ease;
      display:inline-flex;
      align-items:center;
      gap:10px;
      font-weight:700;
      letter-spacing:.1px;
      box-shadow: var(--shadow-soft);
      user-select:none;
    }
    .btn:hover{transform: translateY(-1px)}
    .btn.primary{
      background: linear-gradient(135deg, var(--accent), var(--accent-2));
      color:#fff;
    }
    .btn.dark{
      background: linear-gradient(135deg, #241b18, #130f0e);
      color:#fff;
    }
    .btn.soft{
      background: rgba(255,255,255,.74);
      color:var(--text);
      border:1px solid rgba(36,27,24,.08);
    }

    .stats{
      display:grid;
      gap:12px;
      align-content:stretch;
    }
    .stat{
      border-radius: 26px;
      padding:18px;
      box-shadow: var(--shadow-soft);
      overflow:hidden;
      position:relative;
      min-height: 146px;
      display:flex;
      flex-direction:column;
      justify-content:space-between;
      border:1px solid rgba(36,27,24,.08);
      background: var(--paper-strong);
    }
    .stat::after{
      content:"";
      position:absolute;
      right:-40px;
      bottom:-40px;
      width:150px;
      height:150px;
      border-radius:50%;
      background: radial-gradient(circle, rgba(180,35,24,.14), transparent 68%);
    }
    .stat.dark{
      color:#f8ead6;
      background: linear-gradient(145deg, #201714, #0f0b0a);
      border-color: rgba(255,255,255,.05);
    }
    .stat.dark::after{
      background: radial-gradient(circle, rgba(180,35,24,.36), transparent 68%);
    }
    .stat .label{
      font-size:.88rem;
      color:inherit;
      opacity:.72;
    }
    .stat .num{
      font-size:2rem;
      font-weight:900;
      margin-top:4px;
      letter-spacing:-.03em;
    }
    .stat .small{
      font-size:.94rem;
      line-height:1.6;
      opacity:.88;
      max-width:30ch;
    }

    section{padding: 18px 0 0}

    .section-head{
      display:flex;
      align-items:end;
      justify-content:space-between;
      gap:12px;
      margin: 10px 0 16px;
    }
    .section-head h3{
      margin:0;
      font-size:1.2rem;
      letter-spacing:.1px;
    }
    .section-head p{
      margin:0;
      color:var(--muted);
      font-size:.95rem;
      line-height:1.5;
    }

    .toolbar{
      display:grid;
      grid-template-columns: 1.25fr .9fr auto;
      gap:12px;
      margin-bottom:16px;
    }
    .field{
      display:flex;
      align-items:center;
      gap:10px;
      background: rgba(255,255,255,.68);
      border:1px solid rgba(36,27,24,.10);
      border-radius: 18px;
      padding: 0 14px;
      box-shadow: 0 8px 20px rgba(58,36,26,.05);
      min-height:54px;
    }
    .field input, .field textarea{
      border:none;
      outline:none;
      background:transparent;
      width:100%;
      color:var(--text);
      font-size:.98rem;
      resize:none;
    }
    .field textarea{padding-top:12px;padding-bottom:12px}
    .field input::placeholder, .field textarea::placeholder{color:#8b786f}
    .field .ico{
      width:22px;
      display:grid;
      place-items:center;
      color:var(--accent);
      font-weight:900;
      flex:0 0 auto;
    }

    .grid{
      display:grid;
      grid-template-columns: repeat(3, minmax(0,1fr));
      gap:16px;
    }
    .card{
      position:relative;
      background: linear-gradient(180deg, rgba(255,255,255,.78), rgba(255,249,240,.88));
      border:1px solid rgba(36,27,24,.10);
      border-radius: 26px;
      padding: 18px;
      box-shadow: var(--shadow-soft);
      overflow:hidden;
      transition: transform .22s ease, box-shadow .22s ease, border-color .22s ease;
    }
    .card:hover{
      transform: translateY(-4px);
      border-color: rgba(180,35,24,.20);
      box-shadow: 0 20px 36px rgba(58,36,26,.12);
    }
    .card-top{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap:12px;
      margin-bottom:14px;
    }
    .tag{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:7px 10px;
      border-radius:999px;
      background: rgba(180,35,24,.08);
      color:var(--accent-2);
      font-size:.82rem;
      font-weight:700;
    }
    .badge{
      width:36px;
      height:36px;
      border-radius:14px;
      display:grid;
      place-items:center;
      background: rgba(36,27,24,.06);
      color:var(--accent-2);
      font-weight:800;
      flex:0 0 auto;
    }
    .card h4{
      margin:0 0 8px;
      font-size:1.08rem;
      line-height:1.35;
    }
    .card p{
      margin:0 0 16px;
      color:var(--muted);
      line-height:1.68;
      min-height:48px;
    }
    .url{
      display:block;
      word-break:break-word;
      font-size:.9rem;
      color:#5d4a43;
      background: rgba(36,27,24,.04);
      border-radius: 16px;
      padding:10px 12px;
      margin-bottom:14px;
      border:1px dashed rgba(36,27,24,.12);
    }
    .actions{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
    }
    .link-btn, .edit-btn{
      border:none;
      border-radius:14px;
      padding:10px 14px;
      cursor:pointer;
      font-weight:700;
      transition:.18s ease;
      text-align:center;
    }
    .link-btn{
      background: linear-gradient(135deg, #1f1715, #0f0c0b);
      color:#fff;
      flex:1;
      min-width: 110px;
    }
    .link-btn:hover{opacity:.96; transform: translateY(-1px)}
    .edit-btn{
      background: rgba(180,35,24,.10);
      color: var(--accent-2);
      border:1px solid rgba(180,35,24,.14);
      min-width: 96px;
    }
    .edit-btn:hover{background: rgba(180,35,24,.16)}

    .empty{
      padding: 30px 20px;
      text-align:center;
      border:1px dashed rgba(36,27,24,.18);
      border-radius: 26px;
      background: rgba(255,255,255,.50);
      color:var(--muted);
      box-shadow: var(--shadow-soft);
    }

    .manage{
      margin-top:16px;
      border-radius: 30px;
      background: linear-gradient(180deg, rgba(255,255,255,.82), rgba(255,249,240,.92));
      border:1px solid rgba(36,27,24,.10);
      box-shadow: var(--shadow);
      overflow:hidden;
    }
    .manage-head{
      padding:18px 20px;
      display:flex;
      flex-wrap:wrap;
      justify-content:space-between;
      gap:12px;
      align-items:center;
      border-bottom:1px solid rgba(36,27,24,.08);
      background: linear-gradient(135deg, rgba(180,35,24,.06), rgba(255,255,255,.1));
    }
    .manage-head h3{
      margin:0;
      font-size:1.06rem;
    }
    .manage-head p{
      margin:4px 0 0;
      color:var(--muted);
      font-size:.92rem;
      line-height:1.5;
    }
    .manage-body{
      padding:20px;
      display:grid;
      grid-template-columns: 1fr 1fr 1.15fr auto;
      gap:12px;
    }
    .manage .field{
      background: rgba(255,255,255,.78);
    }
    .manage .field textarea{min-height:54px}
    .manage .btn.primary,
    .manage .btn.soft{
      min-height:54px;
      box-shadow:none;
      align-self:stretch;
    }

    .footer{
      padding: 18px 0 34px;
      margin-top:22px;
    }
    .footer-card{
      background: linear-gradient(180deg, rgba(24,18,16,.97), rgba(32,23,20,.99));
      color:#f8ead6;
      border-radius: 30px;
      padding: 24px;
      box-shadow: var(--shadow);
      border:1px solid rgba(255,255,255,.06);
    }
    .footer-grid{
      display:grid;
      grid-template-columns: 1.05fr .95fr;
      gap:18px;
      align-items:start;
    }
    .footer h4{
      margin:0 0 10px;
      font-size:1.08rem;
      letter-spacing:.1px;
    }
    .footer p{
      margin:0;
      color:rgba(248,234,214,.82);
      line-height:1.75;
    }
    .contact-list{
      display:grid;
      gap:12px;
    }
    .contact-item{
      background: rgba(255,255,255,.05);
      border:1px solid rgba(255,255,255,.07);
      border-radius: 18px;
      padding: 12px 14px;
    }
    .contact-item b{
      display:block;
      margin-bottom:5px;
      color:#fff2df;
      font-size:.95rem;
    }
    .contact-item a, .contact-item span{
      color:#f0c3b9;
      word-break:break-word;
    }
    .footer-bottom{
      margin-top:18px;
      padding-top:14px;
      border-top:1px solid rgba(255,255,255,.08);
      display:flex;
      gap:8px;
      flex-wrap:wrap;
      justify-content:space-between;
      color:rgba(248,234,214,.68);
      font-size:.92rem;
    }

    .modal{
      position:fixed;
      inset:0;
      background: rgba(18,13,12,.68);
      display:none;
      align-items:center;
      justify-content:center;
      z-index:100;
      padding:18px;
      backdrop-filter: blur(8px);
    }
    .modal.show{display:flex}
    .modal-card{
      width:min(580px, 100%);
      background: linear-gradient(180deg, rgba(255,252,247,.98), rgba(246,236,221,.98));
      border-radius: 28px;
      box-shadow: 0 30px 70px rgba(0,0,0,.34);
      border:1px solid rgba(36,27,24,.12);
      overflow:hidden;
    }
    .modal-head{
      padding:18px 20px 14px;
      background: linear-gradient(135deg, rgba(180,35,24,.12), rgba(36,27,24,.03));
      border-bottom:1px solid rgba(36,27,24,.08);
    }
    .modal-head h3{margin:0 0 5px}
    .modal-head p{margin:0;color:var(--muted);line-height:1.6}
    .modal-body{
      padding:20px;
      display:grid;
      gap:12px;
    }
    .modal-actions{
      display:flex;
      gap:12px;
      justify-content:flex-end;
      padding:0 20px 20px;
      flex-wrap:wrap;
    }
    .hint{
      font-size:.9rem;
      color:var(--muted);
      margin-top:-2px;
    }
    .error{
      color:#b42318;
      font-weight:700;
      min-height:22px;
    }
    .success{
      color:#0b7a34;
      font-weight:700;
      min-height:22px;
    }
    .hidden{display:none !important;}

    @media (max-width: 1020px){
      .hero-grid,
      .toolbar,
      .footer-grid,
      .manage-body{
        grid-template-columns:1fr;
      }
      .grid{grid-template-columns: repeat(2, minmax(0,1fr));}
      .pill-row{justify-content:flex-start}
    }
    @media (max-width: 680px){
      .wrap{width:min(100% - 18px, var(--max));}
      .topbar-inner{flex-direction:column; align-items:flex-start}
      .hero-card{padding:20px}
      .grid{grid-template-columns:1fr}
      .brand h1{font-size:1rem}
      .brand-mark{width:46px;height:46px;border-radius:16px}
      .brand-mark span{font-size:19px}
      .footer-bottom{flex-direction:column}
    }
  </style>
</head>
<body>
  <div class="ambient a"></div>
  <div class="ambient b"></div>

  <header class="topbar">
    <div class="wrap topbar-inner">
      <div class="brand">
        <div class="brand-mark" aria-hidden="true"><span>K</span></div>
        <div>
          <h1>Kho Tàng Của Koi</h1>
          <p>Thanh lịch, gọn gàng và dễ quản lý các website riêng</p>
        </div>
      </div>
      <div class="pill-row">
        <button class="pill" onclick="scrollToSection('sites')">✦ <strong>Website</strong></button>
        <button class="pill" onclick="scrollToSection('manageArea')">◌ <strong>Quản lý</strong></button>
        <button class="pill" onclick="scrollToSection('contact')">♡ <strong>Liên hệ</strong></button>
      </div>
    </div>
  </header>

  <main class="wrap">
    <section class="hero">
      <div class="hero-card">
        <div class="hero-grid">
          <div>
            <div class="eyebrow">Elegant Home · Private Link Hub</div>
            <h2>Chào mừng đến với <span class="accent">Kho Tàng Của Koi</span></h2>
            <p>
              Một trang chủ được thiết kế theo hướng thanh lịch, sáng sủa và tinh tế để lưu trữ toàn bộ website của bạn.
              Giao diện chú trọng khoảng thở, độ tương phản vừa phải và cảm giác cao cấp.
            </p>
            <div class="hero-actions">
              <button class="btn primary" onclick="scrollToSection('sites')">Mở danh sách website</button>
              <button class="btn dark" id="unlockBtn" onclick="openPasswordModal()">Mở khóa chỉnh sửa</button>
            </div>
          </div>

          <div class="stats">
            <div class="stat">
              <div>
                <div class="label">Tổng số website</div>
                <div class="num" id="siteCount">0</div>
              </div>
              <div class="small">Danh sách được lưu trong trình duyệt, thuận tiện thêm mới mọi lúc.</div>
            </div>
            <div class="stat dark">
              <div>
                <div class="label">Trạng thái chỉnh sửa</div>
                <div class="num" id="editState">Đã khóa</div>
              </div>
              <div class="small">Chỉ cần nhập mật khẩu để bật chế độ thêm, sửa và xóa liên kết.</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="sites">
      <div class="section-head">
        <div>
          <h3>Danh sách website</h3>
          <p>Nhấp để mở trang bạn muốn truy cập.</p>
        </div>
      </div>

      <div class="toolbar">
        <div class="field">
          <div class="ico">⌕</div>
          <input id="searchInput" type="text" placeholder="Tìm website theo tên hoặc đường dẫn..." />
        </div>
        <div class="field">
          <div class="ico">◎</div>
          <input id="filterInput" type="text" placeholder="Lọc nhanh theo từ khóa..." />
        </div>
        <button class="btn soft" onclick="clearFilters()">Xóa bộ lọc</button>
      </div>

      <div id="cardGrid" class="grid"></div>
      <div id="emptyState" class="empty hidden">Không tìm thấy website phù hợp.</div>
    </section>

    <section id="manageArea">
      <div class="section-head">
        <div>
          <h3>Quản lý liên kết</h3>
          <p>Chế độ này chỉ mở khi nhập đúng mật khẩu.</p>
        </div>
      </div>

      <div class="manage">
        <div class="manage-head">
          <div>
            <h3>Thêm website mới</h3>
            <p>Nhập tên, đường dẫn và ghi chú ngắn gọn.</p>
          </div>
          <button class="btn soft" id="lockToggleBtn" onclick="toggleLockPanel()">Mở bảng mật khẩu</button>
        </div>
        <div class="manage-body">
          <div class="field">
            <div class="ico">✎</div>
            <input id="newTitle" type="text" placeholder="Tên website" disabled />
          </div>
          <div class="field">
            <div class="ico">⛓</div>
            <input id="newUrl" type="url" placeholder="Dán URL đầy đủ" disabled />
          </div>
          <div class="field" style="align-items:flex-start;">
            <div class="ico" style="padding-top:12px;">📝</div>
            <textarea id="newDesc" rows="1" placeholder="Ghi chú ngắn" disabled></textarea>
          </div>
          <button class="btn primary" id="addBtn" onclick="addSite()" disabled>Thêm</button>
        </div>
      </div>
    </section>

    <section id="contact" class="footer">
      <div class="footer-card">
        <div class="footer-grid">
          <div>
            <h4>Liên hệ</h4>
            <p>
              Đây là phần liên hệ của Koi. Bạn có thể kết nối qua các nền tảng dưới đây để trao đổi, góp ý hoặc cập nhật website mới.
            </p>
          </div>
          <div class="contact-list">
            <div class="contact-item">
              <b>TikTok</b>
              <a href="https://www.tiktok.com/@_oki__ne_" target="_blank" rel="noopener noreferrer">@_oki__ne_</a>
            </div>
            <div class="contact-item">
              <b>Số điện thoại</b>
              <a href="tel:0367634821">0367634821</a>
            </div>
            <div class="contact-item">
              <b>Facebook</b>
              <a href="https://www.facebook.com/share/1Uj8VCKwVm/" target="_blank" rel="noopener noreferrer">KoiFish</a>
            </div>
            <div class="contact-item">
              <b>Người tạo website</b>
              <span>KoiFish</span>
            </div>
          </div>
        </div>
        <div class="footer-bottom">
          <div>© <span id="year"></span> Kho Tàng Của Koi</div>
          <div>Thiết kế thanh lịch bởi KoiFish</div>
        </div>
      </div>
    </section>
  </main>

  <div class="modal" id="passwordModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
    <div class="modal-card">
      <div class="modal-head">
        <h3 id="modalTitle">Nhập mật khẩu để chỉnh sửa</h3>
        <p>Chỉ khi đúng mật khẩu, bạn mới có thể chỉnh sửa các website.</p>
      </div>
      <div class="modal-body">
        <div class="field">
          <div class="ico">🔒</div>
          <input id="passwordInput" type="password" placeholder="Nhập mật khẩu" autocomplete="current-password" />
        </div>
        <div class="hint">Mật khẩu đang được yêu cầu để mở chế độ chỉnh sửa.</div>
        <div id="passwordMsg" class="error"></div>
      </div>
      <div class="modal-actions">
        <button class="btn soft" onclick="closePasswordModal()">Hủy</button>
        <button class="btn primary" onclick="checkPassword()">Xác nhận</button>
      </div>
    </div>
  </div>

  <div class="modal" id="editModal" role="dialog" aria-modal="true" aria-labelledby="editTitle">
    <div class="modal-card">
      <div class="modal-head">
        <h3 id="editTitle">Sửa website</h3>
        <p>Chỉnh tên, đường dẫn và ghi chú của website.</p>
      </div>
      <div class="modal-body">
        <div class="field">
          <div class="ico">✎</div>
          <input id="editTitleInput" type="text" placeholder="Tên website" />
        </div>
        <div class="field">
          <div class="ico">⛓</div>
          <input id="editUrlInput" type="url" placeholder="URL đầy đủ" />
        </div>
        <div class="field" style="align-items:flex-start;">
          <div class="ico" style="padding-top:12px;">📝</div>
          <textarea id="editDescInput" rows="3" placeholder="Ghi chú"></textarea>
        </div>
        <div id="editMsg" class="error"></div>
      </div>
      <div class="modal-actions">
        <button class="btn soft" onclick="closeEditModal()">Hủy</button>
        <button class="btn primary" onclick="saveEditSite()">Lưu thay đổi</button>
      </div>
    </div>
  </div>

  <script>
    const PASSWORD = "24102011";
    const STORAGE_KEY = "koi_sites_v1";
    const AUTH_KEY = "koi_edit_auth_v1";

    const defaultSites = [
      {
        title: "Từ điển ngoại ngữ của Koi",
        url: "https://2410phongnguyen-eng.github.io/-/",
        desc: "Nơi bạn có thể tra cứu từ vựng tiếng Anh, Trung và Nhật theo mọi chủ đề."
      },
      {
        title: "Phòng thực hành hóa học của Koi",
        url: "https://2410phongnguyen-eng.github.io/----/",
        desc: "Nơi bạn có thể thực hành các thí nghiệm hóa học và mở khóa chất mới."
      }
    ];

    let sites = loadSites();
    let isUnlocked = sessionStorage.getItem(AUTH_KEY) === "1";
    let editIndex = -1;

    const grid = document.getElementById("cardGrid");
    const emptyState = document.getElementById("emptyState");
    const siteCount = document.getElementById("siteCount");
    const editState = document.getElementById("editState");
    const searchInput = document.getElementById("searchInput");
    const filterInput = document.getElementById("filterInput");
    const passwordModal = document.getElementById("passwordModal");
    const passwordInput = document.getElementById("passwordInput");
    const passwordMsg = document.getElementById("passwordMsg");
    const newTitle = document.getElementById("newTitle");
    const newUrl = document.getElementById("newUrl");
    const newDesc = document.getElementById("newDesc");
    const addBtn = document.getElementById("addBtn");
    const lockToggleBtn = document.getElementById("lockToggleBtn");

    const editModal = document.getElementById("editModal");
    const editTitleInput = document.getElementById("editTitleInput");
    const editUrlInput = document.getElementById("editUrlInput");
    const editDescInput = document.getElementById("editDescInput");
    const editMsg = document.getElementById("editMsg");

    document.getElementById("year").textContent = new Date().getFullYear();

    function loadSites(){
      try{
        const raw = localStorage.getItem(STORAGE_KEY);
        if(!raw) return structuredClone(defaultSites);
        const parsed = JSON.parse(raw);
        if(!Array.isArray(parsed)) return structuredClone(defaultSites);
        return parsed.filter(item => item && typeof item.title === "string" && typeof item.url === "string");
      }catch{
        return structuredClone(defaultSites);
      }
    }

    function saveSites(){
      localStorage.setItem(STORAGE_KEY, JSON.stringify(sites));
      renderSites();
    }

    function normalizeUrl(url){
      let trimmed = String(url || "").trim();
      if(!trimmed) return "";
      if(!/^https?:\/\//i.test(trimmed)){
        if(trimmed.startsWith("www.")) trimmed = "https://" + trimmed;
        else trimmed = "https://" + trimmed;
      }
      return trimmed;
    }

    function escapeHtml(text){
      return String(text)
        .replaceAll("&","&amp;")
        .replaceAll("<","&lt;")
        .replaceAll(">","&gt;")
        .replaceAll('"',"&quot;")
        .replaceAll("'","&#39;");
    }

    function renderSites(){
      const q1 = searchInput.value.trim().toLowerCase();
      const q2 = filterInput.value.trim().toLowerCase();

      const filtered = sites.filter(site => {
        const hay = `${site.title} ${site.url} ${site.desc || ""}`.toLowerCase();
        return hay.includes(q1) && hay.includes(q2);
      });

      siteCount.textContent = sites.length;
      editState.textContent = isUnlocked ? "Đã mở" : "Đã khóa";
      newTitle.disabled = !isUnlocked;
      newUrl.disabled = !isUnlocked;
      newDesc.disabled = !isUnlocked;
      addBtn.disabled = !isUnlocked;
      lockToggleBtn.textContent = isUnlocked ? "Khóa chỉnh sửa" : "Mở bảng mật khẩu";

      grid.innerHTML = "";

      if(filtered.length === 0){
        emptyState.classList.remove("hidden");
      }else{
        emptyState.classList.add("hidden");
      }

      filtered.forEach((site) => {
        const index = sites.indexOf(site);
        const card = document.createElement("article");
        card.className = "card";
        const initials = (site.title || "K").trim().slice(0,1).toUpperCase();
        card.innerHTML = `
          <div class="card-top">
            <div class="tag">★ Website ${index + 1}</div>
            <div class="badge">${escapeHtml(initials)}</div>
          </div>
          <h4>${escapeHtml(site.title)}</h4>
          <p>${escapeHtml(site.desc || "Liên kết nhanh tới trang web của bạn.")}</p>
          <span class="url">${escapeHtml(site.url)}</span>
          <div class="actions">
            <a class="link-btn" href="${escapeHtml(site.url)}" target="_blank" rel="noopener noreferrer">Mở trang</a>
            ${isUnlocked ? `<button class="edit-btn" onclick="openEditModal(${index})">Sửa</button>
            <button class="edit-btn" onclick="removeSite(${index})">Xóa</button>` : ""}
          </div>
        `;
        grid.appendChild(card);
      });
    }

    function scrollToSection(id){
      document.getElementById(id).scrollIntoView({behavior:"smooth", block:"start"});
    }

    function clearFilters(){
      searchInput.value = "";
      filterInput.value = "";
      renderSites();
    }

    function openPasswordModal(){
      passwordMsg.textContent = "";
      passwordInput.value = "";
      passwordModal.classList.add("show");
      setTimeout(() => passwordInput.focus(), 100);
    }

    function closePasswordModal(){
      passwordModal.classList.remove("show");
      passwordMsg.textContent = "";
    }

    function checkPassword(){
      const val = passwordInput.value.trim();
      if(val === PASSWORD){
        isUnlocked = true;
        sessionStorage.setItem(AUTH_KEY, "1");
        closePasswordModal();
        renderSites();
        toast("Đã mở khóa chỉnh sửa.");
      }else{
        passwordMsg.textContent = "Mật khẩu chưa đúng.";
      }
    }

    function toggleLockPanel(){
      if(isUnlocked){
        isUnlocked = false;
        sessionStorage.removeItem(AUTH_KEY);
        renderSites();
        toast("Đã khóa chỉnh sửa.");
      }else{
        openPasswordModal();
      }
    }

    function addSite(){
      if(!isUnlocked){
        openPasswordModal();
        return;
      }
      const title = newTitle.value.trim();
      const url = normalizeUrl(newUrl.value);
      const desc = newDesc.value.trim();

      if(!title || !url){
        toast("Vui lòng nhập đủ tên và đường dẫn.");
        return;
      }

      sites.unshift({
        title,
        url,
        desc: desc || "Website do bạn thêm vào."
      });

      newTitle.value = "";
      newUrl.value = "";
      newDesc.value = "";
      saveSites();
      toast("Đã thêm website mới.");
    }

    function removeSite(index){
      if(!isUnlocked){
        openPasswordModal();
        return;
      }
      const site = sites[index];
      if(!site) return;
      const ok = confirm(`Xóa website "${site.title}"?`);
      if(!ok) return;
      sites.splice(index, 1);
      saveSites();
      toast("Đã xóa website.");
    }

    function openEditModal(index){
      if(!isUnlocked){
        openPasswordModal();
        return;
      }
      const site = sites[index];
      if(!site) return;
      editIndex = index;
      editTitleInput.value = site.title || "";
      editUrlInput.value = site.url || "";
      editDescInput.value = site.desc || "";
      editMsg.textContent = "";
      editModal.classList.add("show");
      setTimeout(() => editTitleInput.focus(), 100);
    }

    function closeEditModal(){
      editModal.classList.remove("show");
      editMsg.textContent = "";
      editIndex = -1;
    }

    function saveEditSite(){
      if(editIndex < 0 || !sites[editIndex]) return;

      const title = editTitleInput.value.trim();
      const url = normalizeUrl(editUrlInput.value);
      const desc = editDescInput.value.trim();

      if(!title || !url){
        editMsg.textContent = "Tên website và đường dẫn không được để trống.";
        return;
      }

      sites[editIndex] = {
        ...sites[editIndex],
        title,
        url,
        desc: desc || "Liên kết nhanh tới trang web của bạn."
      };

      saveSites();
      closeEditModal();
      toast("Đã lưu thay đổi.");
    }

    function toast(message){
      const el = document.createElement("div");
      el.textContent = message;
      el.style.position = "fixed";
      el.style.left = "50%";
      el.style.bottom = "24px";
      el.style.transform = "translateX(-50%)";
      el.style.background = "rgba(24,18,16,.96)";
      el.style.color = "#f8ead6";
      el.style.padding = "12px 16px";
      el.style.borderRadius = "999px";
      el.style.boxShadow = "0 18px 40px rgba(0,0,0,.28)";
      el.style.zIndex = "999";
      el.style.border = "1px solid rgba(255,255,255,.08)";
      el.style.maxWidth = "calc(100vw - 24px)";
      el.style.textAlign = "center";
      document.body.appendChild(el);
      setTimeout(() => {
        el.style.transition = "opacity .25s ease, transform .25s ease";
        el.style.opacity = "0";
        el.style.transform = "translateX(-50%) translateY(6px)";
        setTimeout(() => el.remove(), 260);
      }, 1800);
    }

    searchInput.addEventListener("input", renderSites);
    filterInput.addEventListener("input", renderSites);

    passwordInput.addEventListener("keydown", (e) => {
      if(e.key === "Enter") checkPassword();
      if(e.key === "Escape") closePasswordModal();
    });

    [editTitleInput, editUrlInput, editDescInput].forEach(el => {
      el.addEventListener("keydown", (e) => {
        if(e.key === "Escape") closeEditModal();
        if(e.key === "Enter" && e.target !== editDescInput){
          e.preventDefault();
          saveEditSite();
        }
      });
    });

    passwordModal.addEventListener("click", (e) => {
      if(e.target === passwordModal) closePasswordModal();
    });

    editModal.addEventListener("click", (e) => {
      if(e.target === editModal) closeEditModal();
    });

    document.addEventListener("keydown", (e) => {
      if(e.key === "Escape"){
        closePasswordModal();
        closeEditModal();
      }
    });

    renderSites();
  </script>
</body>
</html>
