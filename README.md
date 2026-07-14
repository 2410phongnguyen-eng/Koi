
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kho Tàng Của Koi</title>
  <meta name="description" content="Trang chủ của Kho Tàng Của Koi - nơi tổng hợp các website và trang web yêu thích." />
  <style>
    :root{
      --bg: #f3ead7;
      --bg-2: #efe2c8;
      --card: rgba(255,255,255,.55);
      --card-2: rgba(255,248,235,.8);
      --text: #221815;
      --muted: #6b584f;
      --red: #b42318;
      --red-2: #8f1d15;
      --black: #171211;
      --line: rgba(34,24,21,.12);
      --shadow: 0 16px 40px rgba(57, 33, 25, .12);
      --shadow-2: 0 10px 24px rgba(57, 33, 25, .10);
      --radius: 24px;
      --radius-sm: 18px;
      --radius-xs: 14px;
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
      color:var(--text);
      background:
        radial-gradient(circle at top left, rgba(180,35,24,.11), transparent 28%),
        radial-gradient(circle at top right, rgba(23,18,17,.09), transparent 22%),
        linear-gradient(180deg, var(--bg), var(--bg-2));
      min-height:100vh;
      overflow-x:hidden;
    }
    a{color:inherit; text-decoration:none}
    button,input{
      font:inherit;
    }

    .wrap{
      width:min(1180px, calc(100% - 32px));
      margin:0 auto;
    }

    .topbar{
      position:sticky;
      top:0;
      z-index:20;
      backdrop-filter: blur(16px);
      background: rgba(243,234,215,.72);
      border-bottom:1px solid rgba(34,24,21,.08);
    }
    .topbar-inner{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      padding:14px 0;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:14px;
      min-width:0;
    }
    .logo{
      width:52px;
      height:52px;
      border-radius:18px;
      display:grid;
      place-items:center;
      background:
        linear-gradient(145deg, #2a201d, #0f0c0b);
      color:#f5e6cf;
      box-shadow: var(--shadow-2);
      position:relative;
      overflow:hidden;
      flex:0 0 auto;
    }
    .logo::after{
      content:"";
      position:absolute;
      inset:-40% -25%;
      background: linear-gradient(45deg, transparent 40%, rgba(180,35,24,.45), transparent 60%);
      transform: rotate(18deg);
    }
    .logo span{
      position:relative;
      z-index:1;
      font-size:22px;
      font-weight:800;
      letter-spacing:.5px;
    }
    .brand h1{
      margin:0;
      font-size:1.2rem;
      line-height:1.15;
      letter-spacing:.2px;
    }
    .brand p{
      margin:4px 0 0;
      color:var(--muted);
      font-size:.92rem;
    }

    .pill-row{
      display:flex;
      flex-wrap:wrap;
      justify-content:flex-end;
      gap:10px;
    }
    .pill{
      padding:10px 14px;
      border:1px solid rgba(34,24,21,.12);
      background: rgba(255,248,235,.66);
      border-radius:999px;
      color:var(--text);
      box-shadow: 0 6px 18px rgba(57, 33, 25, .06);
      transition:.2s ease;
      display:inline-flex;
      align-items:center;
      gap:8px;
      cursor:pointer;
    }
    .pill:hover{transform:translateY(-1px); border-color: rgba(180,35,24,.25)}
    .pill strong{color:var(--red)}

    .hero{
      padding:34px 0 18px;
    }
    .hero-card{
      position:relative;
      overflow:hidden;
      border:1px solid rgba(34,24,21,.10);
      border-radius: 32px;
      background:
        linear-gradient(135deg, rgba(255,255,255,.56), rgba(255,248,235,.78));
      box-shadow: var(--shadow);
      padding: 28px;
    }
    .hero-card::before,
    .hero-card::after{
      content:"";
      position:absolute;
      border-radius:999px;
      filter: blur(0);
      pointer-events:none;
    }
    .hero-card::before{
      width:220px;
      height:220px;
      right:-70px;
      top:-90px;
      background: radial-gradient(circle, rgba(180,35,24,.20), transparent 70%);
    }
    .hero-card::after{
      width:260px;
      height:260px;
      left:-120px;
      bottom:-150px;
      background: radial-gradient(circle, rgba(23,18,17,.08), transparent 68%);
    }

    .hero-grid{
      display:grid;
      grid-template-columns: 1.25fr .75fr;
      gap:22px;
      align-items:stretch;
      position:relative;
      z-index:1;
    }

    .hero h2{
      margin:0 0 10px;
      font-size: clamp(2rem, 4vw, 3.7rem);
      line-height:1.02;
      letter-spacing:-.03em;
    }
    .hero h2 .accent{
      color:var(--red);
    }
    .hero p{
      margin:0;
      color:var(--muted);
      font-size:1.02rem;
      line-height:1.7;
      max-width: 62ch;
    }

    .hero-actions{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      margin-top:20px;
    }
    .btn{
      border:none;
      padding:13px 18px;
      border-radius: 16px;
      cursor:pointer;
      transition:.2s ease;
      display:inline-flex;
      align-items:center;
      gap:10px;
      font-weight:700;
      letter-spacing:.1px;
      box-shadow: var(--shadow-2);
      user-select:none;
    }
    .btn:hover{transform:translateY(-1px)}
    .btn.primary{
      background: linear-gradient(135deg, var(--red), var(--red-2));
      color:#fff;
    }
    .btn.dark{
      background: linear-gradient(135deg, #231b19, #0f0c0b);
      color:#fff;
    }
    .btn.soft{
      background: rgba(255,255,255,.72);
      color:var(--text);
      border:1px solid rgba(34,24,21,.08);
    }

    .stat-box{
      display:grid;
      grid-template-columns:1fr;
      gap:12px;
      align-content:stretch;
    }
    .mini{
      border-radius: 24px;
      background: rgba(23,18,17,.95);
      color:#f7ead3;
      padding:18px;
      box-shadow: var(--shadow);
      display:flex;
      flex-direction:column;
      justify-content:space-between;
      min-height: 140px;
      position:relative;
      overflow:hidden;
    }
    .mini::after{
      content:"";
      position:absolute;
      inset:auto -40px -40px auto;
      width:140px;
      height:140px;
      border-radius:50%;
      background: radial-gradient(circle, rgba(180,35,24,.45), transparent 68%);
    }
    .mini .label{
      font-size:.9rem;
      color:rgba(247,234,211,.75);
    }
    .mini .num{
      font-size:2rem;
      font-weight:900;
      margin-top:4px;
    }
    .mini .small{
      font-size:.94rem;
      color:rgba(247,234,211,.85);
      line-height:1.55;
      max-width: 28ch;
    }

    section{
      padding: 18px 0 0;
    }

    .section-head{
      display:flex;
      align-items:end;
      justify-content:space-between;
      gap:12px;
      margin: 10px 0 16px;
    }
    .section-head h3{
      margin:0;
      font-size:1.25rem;
      letter-spacing:.1px;
    }
    .section-head p{
      margin:0;
      color:var(--muted);
      font-size:.95rem;
    }

    .tools{
      display:grid;
      grid-template-columns: 1.2fr .55fr auto;
      gap:12px;
      margin-bottom:16px;
    }
    .field{
      display:flex;
      align-items:center;
      gap:10px;
      background: rgba(255,255,255,.64);
      border:1px solid rgba(34,24,21,.10);
      border-radius: 18px;
      padding: 0 14px;
      box-shadow: 0 8px 20px rgba(57, 33, 25, .05);
      min-height:52px;
    }
    .field input{
      border:none;
      outline:none;
      background:transparent;
      width:100%;
      color:var(--text);
      font-size:.98rem;
    }
    .field input::placeholder{color:#8a766f}
    .field .ico{
      width:22px;
      display:grid;
      place-items:center;
      color:var(--red);
      font-weight:900;
    }

    .grid{
      display:grid;
      grid-template-columns: repeat(3, minmax(0,1fr));
      gap:16px;
    }
    .card{
      position:relative;
      background: linear-gradient(180deg, rgba(255,255,255,.72), rgba(255,248,235,.76));
      border:1px solid rgba(34,24,21,.10);
      border-radius: 24px;
      padding: 18px;
      box-shadow: var(--shadow-2);
      overflow:hidden;
      transition: transform .22s ease, box-shadow .22s ease, border-color .22s ease;
    }
    .card:hover{
      transform: translateY(-3px);
      border-color: rgba(180,35,24,.18);
      box-shadow: 0 16px 28px rgba(57, 33, 25, .12);
    }
    .card .tag{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:7px 10px;
      border-radius:999px;
      background: rgba(180,35,24,.08);
      color:var(--red-2);
      font-size:.82rem;
      font-weight:700;
      margin-bottom:12px;
    }
    .card h4{
      margin:0 0 8px;
      font-size:1.1rem;
    }
    .card p{
      margin:0 0 16px;
      color:var(--muted);
      line-height:1.6;
      min-height: 48px;
    }
    .card .url{
      display:block;
      word-break:break-word;
      font-size:.9rem;
      color:#5e4b44;
      background: rgba(34,24,21,.04);
      border-radius: 14px;
      padding:10px 12px;
      margin-bottom:14px;
      border:1px dashed rgba(34,24,21,.10);
    }
    .card .actions{
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
      background: linear-gradient(135deg, var(--black), #352724);
      color:#fff;
      flex:1;
      min-width: 110px;
    }
    .link-btn:hover{opacity:.96; transform:translateY(-1px)}
    .edit-btn{
      background: rgba(180,35,24,.10);
      color: var(--red-2);
      border:1px solid rgba(180,35,24,.14);
      min-width: 98px;
    }
    .edit-btn:hover{background: rgba(180,35,24,.14)}

    .manage{
      margin-top:16px;
      border-radius: 28px;
      background: rgba(23,18,17,.95);
      color:#f7ead3;
      overflow:hidden;
      box-shadow: var(--shadow);
    }
    .manage-head{
      padding:18px 20px;
      display:flex;
      flex-wrap:wrap;
      justify-content:space-between;
      gap:12px;
      align-items:center;
      border-bottom:1px solid rgba(247,234,211,.09);
    }
    .manage-head h3{
      margin:0;
      font-size:1.08rem;
    }
    .manage-head p{
      margin:4px 0 0;
      color:rgba(247,234,211,.74);
      font-size:.92rem;
    }
    .manage-body{
      padding:20px;
      display:grid;
      grid-template-columns: 1fr 1fr auto;
      gap:12px;
    }
    .manage .field{
      background: rgba(255,255,255,.06);
      border:1px solid rgba(255,255,255,.10);
      box-shadow:none;
      color:#fff;
    }
    .manage .field input{
      color:#fff;
    }
    .manage .field input::placeholder{color:rgba(247,234,211,.5)}
    .manage .btn.primary{
      min-height:52px;
      box-shadow:none;
    }
    .manage .btn.soft{
      min-height:52px;
      box-shadow:none;
    }

    .footer{
      margin-top:24px;
      padding: 22px 0 34px;
    }
    .footer-card{
      background: linear-gradient(180deg, rgba(23,18,17,.96), rgba(34,24,21,.98));
      color:#f7ead3;
      border-radius: 28px;
      padding: 22px;
      box-shadow: var(--shadow);
      border:1px solid rgba(255,255,255,.06);
    }
    .footer-grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap:18px;
      align-items:start;
    }
    .footer h4{
      margin:0 0 10px;
      font-size:1.08rem;
    }
    .footer p{
      margin:0;
      color:rgba(247,234,211,.82);
      line-height:1.7;
    }
    .contact-list{
      display:grid;
      gap:12px;
    }
    .contact-item{
      background: rgba(255,255,255,.05);
      border:1px solid rgba(255,255,255,.06);
      border-radius: 18px;
      padding: 12px 14px;
    }
    .contact-item b{
      display:block;
      margin-bottom:5px;
      color:#fff1dd;
    }
    .contact-item a{
      color:#f2c6ba;
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
      color:rgba(247,234,211,.7);
      font-size:.92rem;
    }

    .empty{
      padding: 26px;
      text-align:center;
      border:1px dashed rgba(34,24,21,.18);
      border-radius: 24px;
      background: rgba(255,255,255,.45);
      color:var(--muted);
    }

    /* Modal */
    .modal{
      position:fixed;
      inset:0;
      background: rgba(17,12,11,.68);
      display:none;
      align-items:center;
      justify-content:center;
      z-index:100;
      padding: 18px;
    }
    .modal.show{display:flex}
    .modal-card{
      width:min(520px, 100%);
      background: linear-gradient(180deg, rgba(255,248,235,.98), rgba(243,234,215,.98));
      border-radius: 28px;
      box-shadow: 0 30px 70px rgba(0,0,0,.35);
      border:1px solid rgba(34,24,21,.12);
      overflow:hidden;
    }
    .modal-head{
      padding:18px 20px 14px;
      background: linear-gradient(135deg, rgba(180,35,24,.12), rgba(23,18,17,.04));
      border-bottom:1px solid rgba(34,24,21,.08);
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
      padding: 0 20px 20px;
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
      min-height: 22px;
    }
    .success{
      color:#0b7a34;
      font-weight:700;
      min-height: 22px;
    }

    .hidden{display:none !important;}

    @media (max-width: 980px){
      .hero-grid,
      .footer-grid,
      .tools,
      .manage-body{
        grid-template-columns:1fr;
      }
      .grid{grid-template-columns: repeat(2, minmax(0,1fr));}
      .pill-row{justify-content:flex-start}
    }
    @media (max-width: 640px){
      .wrap{width:min(100% - 20px, 1180px);}
      .topbar-inner{flex-direction:column; align-items:flex-start}
      .hero-card{padding:20px}
      .grid{grid-template-columns:1fr}
      .brand h1{font-size:1.05rem}
      .logo{width:46px;height:46px;border-radius:16px}
      .logo span{font-size:19px}
      .footer-bottom{flex-direction:column}
    }
  </style>
</head>
<body>
  <header class="topbar">
    <div class="wrap topbar-inner">
      <div class="brand">
        <div class="logo" aria-hidden="true"><span>K</span></div>
        <div>
          <h1>Kho Tàng Của Koi</h1>
          <p>Nơi gom lại các website và trang web của riêng Koi</p>
        </div>
      </div>
      <div class="pill-row">
        <button class="pill" onclick="scrollToSection('sites')">🌐 <strong>Trang web</strong></button>
        <button class="pill" onclick="scrollToSection('manageArea')">✦ <strong>Chỉnh sửa</strong></button>
        <button class="pill" onclick="scrollToSection('contact')">♡ <strong>Liên hệ</strong></button>
      </div>
    </div>
  </header>

  <main class="wrap">
    <section class="hero">
      <div class="hero-card">
        <div class="hero-grid">
          <div>
            <h2>Chào mừng đến với <span class="accent">Kho Tàng Của Koi</span></h2>
            <p>
              Đây là trang chủ tập hợp các website của Koi được xếp gọn gàng, dễ truy cập, dễ thêm mới và dễ quản lý.
              Chỉ cần mở khóa chỉnh sửa, bạn có thể thêm hoặc xóa liên kết theo ý muốn (mật khẩu là do Koi cung cấp).
            </p>
            <div class="hero-actions">
              <button class="btn primary" onclick="scrollToSection('sites')">Mở danh sách website</button>
              <button class="btn dark" id="unlockBtn" onclick="openPasswordModal()">Mở khóa chỉnh sửa</button>
            
            </div>
          </div>
          <div class="stat-box">
            <div class="mini">
              <div>
                <div class="label">Tổng số website</div>
                <div class="num" id="siteCount">0</div>
              </div>
              <div class="small">Danh sách được lưu trên trình duyệt để bạn có thể tự thêm web mới bất cứ lúc nào.</div>
            </div>
            <div class="mini" style="background:linear-gradient(145deg,#b42318,#221815);">
              <div>
                <div class="label">Trạng thái chỉnh sửa</div>
                <div class="num" id="editState">Đã khóa</div>
              </div>
              <div class="small">Nhập mật khẩu để bật chế độ thêm hoặc xóa website.</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="sites">
      <div class="section-head">
        <div>
          <h3>Danh sách website</h3>
          <p>Nhấp để mở trang web bạn muốn truy cập.</p>
        </div>
      </div>

      <div class="tools">
        <div class="field">
          <div class="ico">⌕</div>
          <input id="searchInput" type="text" placeholder="Tìm website theo tên hoặc đường dẫn..." />
        </div>
        <div class="field">
          <div class="ico">⟲</div>
          <input id="filterInput" type="text" placeholder="Lọc nhanh..." />
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
          <p>Phần này chỉ mở khi nhập đúng mật khẩu.</p>
        </div>
      </div>

      <div class="manage">
        <div class="manage-head">
          <div>
            <h3>Thêm website mới</h3>
            <p>Ví dụ: tên website và đường dẫn của bạn.</p>
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
              Đây là phần liên hệ của Koi.
              Bạn có thể liên hệ với Koi qua các nền tảng dưới đây để được hỗ trợ hoặc góp ý.
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
          <div>Thiết kế bởi KoiFish</div>
        </div>
      </div>
    </section>
  </main>

  <!-- Password modal -->
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

  <script>
    const PASSWORD = "24102011";
    const STORAGE_KEY = "koi_sites_v1";
    const AUTH_KEY = "koi_edit_auth_v1";

    const defaultSites = [
      {
        title: "Từ điển ngoại ngữ của Koi",
        url: "https://2410phongnguyen-eng.github.io/-/",
        desc: "Nơi bạn có thể tra cứu từ vựng tiếng Anh,Trung và Nhật theo mọi chủ đề.Đồng thời,cũng có thể luyện tập nghe, nói các từ vựng."
      },
      {
        title: "Phòng thực hành hóa học của Koi",
        url: "https://2410phongnguyen-eng.github.io/----/",
        desc: "Nơi bạn có thể thực hành các thí nghiệm hóa học .Từ những chất ban đầu bạn có thể mở khoa các chất mới bằng tài năng hóa học."
      },
      

      
    ];

    let sites = loadSites();
    let isUnlocked = sessionStorage.getItem(AUTH_KEY) === "1";

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
    const addBtn = document.getElementById("addBtn");
    const lockToggleBtn = document.getElementById("lockToggleBtn");

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
      if(!/^https?:\/\//i.test(trimmed)) {
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
      addBtn.disabled = !isUnlocked;
      lockToggleBtn.textContent = isUnlocked ? "Khóa chỉnh sửa" : "Mở bảng mật khẩu";

      grid.innerHTML = "";

      if(filtered.length === 0){
        emptyState.classList.remove("hidden");
      }else{
        emptyState.classList.add("hidden");
      }

      filtered.forEach((site, index) => {
        const card = document.createElement("article");
        card.className = "card";
        card.innerHTML = `
          <div class="tag">★ Website ${index + 1}</div>
          <h4>${escapeHtml(site.title)}</h4>
          <p>${escapeHtml(site.desc || "Liên kết nhanh tới trang web của bạn.")}</p>
          <span class="url">${escapeHtml(site.url)}</span>
          <div class="actions">
            <a class="link-btn" href="${escapeHtml(site.url)}" target="_blank" rel="noopener noreferrer">Mở trang</a>
            ${isUnlocked ? `<button class="edit-btn" onclick="removeSite(${sites.indexOf(site)})">Xóa</button>` : ""}
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
      if(!title || !url){
        toast("Vui lòng nhập đủ tên và đường dẫn.");
        return;
      }
      sites.unshift({
        title,
        url,
        desc: "Website do bạn thêm vào."
      });
      newTitle.value = "";
      newUrl.value = "";
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

    function toast(message){
      const el = document.createElement("div");
      el.textContent = message;
      el.style.position = "fixed";
      el.style.left = "50%";
      el.style.bottom = "24px";
      el.style.transform = "translateX(-50%)";
      el.style.background = "rgba(23,18,17,.96)";
      el.style.color = "#f7ead3";
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

    passwordModal.addEventListener("click", (e) => {
      if(e.target === passwordModal) closePasswordModal();
    });

    document.addEventListener("keydown", (e) => {
      if(e.key === "Escape") closePasswordModal();
    });

    // Nếu đã mở khóa từ trước trong phiên hiện tại thì hiện luôn trạng thái chỉnh sửa
    if(isUnlocked){
      document.body.classList.add("unlocked");
    }

    renderSites();
  </script>
</body>
</html>
