<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tứ Ngữ Điển — Việt · Trung · Anh · Nhật</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif:wght@400;600;700&family=Noto+Serif+SC:wght@600;700&family=Noto+Sans:wght@400;500;700&family=Noto+Sans+JP:wght@400;600&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
<style>
  :root{
    --paper:#F6F1E4;
    --paper-dim:#EDE5D2;
    --ink:#1F2A3C;
    --ink-soft:#4A5568;
    --lacquer:#B33A32;
    --lacquer-dim:#D97A6E;
    --jade:#3F6B5D;
    --gold:#C7963A;
    --line:#D9CFB6;
    --card:#FFFDF7;
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    background:var(--paper);
    color:var(--ink);
    font-family:'Noto Sans','Noto Sans JP',sans-serif;
    line-height:1.5;
  }
  ::selection{background:var(--gold);color:var(--ink);}
  h1,h2,h3{font-family:'Noto Serif','Noto Serif SC',serif;margin:0;}

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    padding:64px 24px 48px;
    max-width:960px;
    margin:0 auto;
    text-align:center;
    overflow:visible;
  }
  .seals{
    display:flex;
    justify-content:center;
    gap:-18px;
    margin-bottom:18px;
    position:relative;
    height:96px;
  }
  .seal{
    width:80px;height:80px;
    border-radius:50%;
    display:flex;align-items:center;justify-content:center;
    font-family:'Noto Serif SC','Noto Serif',serif;
    font-size:34px;font-weight:700;
    border:3px solid currentColor;
    position:absolute;
    top:8px;
    opacity:0.92;
    background:var(--paper);
  }
  .seal.vi{left:calc(50% - 148px);color:var(--lacquer);transform:rotate(-8deg);}
  .seal.zh{left:calc(50% - 74px);color:var(--gold);transform:rotate(4deg);z-index:2;}
  .seal.en{left:calc(50% + 0px);color:var(--jade);transform:rotate(-5deg);z-index:1;}
  .seal.ja{left:calc(50% + 74px);color:var(--ink);transform:rotate(7deg);}

  .eyebrow{
    letter-spacing:.22em;text-transform:uppercase;
    font-size:12px;color:var(--ink-soft);font-weight:700;
    margin-bottom:10px;
  }
  h1.title{font-size:clamp(32px,5vw,52px);color:var(--ink);}
  .title .accent{color:var(--lacquer);}
  .subtitle{max-width:560px;margin:14px auto 0;color:var(--ink-soft);font-size:16px;}

  /* ---------- SEARCH ---------- */
  .search-wrap{max-width:640px;margin:36px auto 0;}
  .search-box{
    display:flex;align-items:center;gap:10px;
    background:var(--card);
    border:2px solid var(--ink);
    border-radius:999px;
    padding:8px 8px 8px 22px;
    box-shadow:4px 4px 0 var(--gold);
  }
  .search-box input{
    flex:1;border:none;outline:none;background:transparent;
    font-size:17px;font-family:'Noto Sans',sans-serif;color:var(--ink);
    padding:10px 0;
  }
  .search-box button{
    background:var(--lacquer);color:#fff;border:none;border-radius:999px;
    padding:12px 22px;font-weight:700;cursor:pointer;font-size:15px;
    transition:transform .15s ease;
  }
  .search-box button:hover{transform:scale(1.04);}
  .search-hint{text-align:center;font-size:13px;color:var(--ink-soft);margin-top:10px;}

  /* ---------- CATEGORY CHIPS ---------- */
  .chips{
    display:flex;flex-wrap:wrap;gap:8px;justify-content:center;
    max-width:760px;margin:20px auto 0;
  }
  .chip{
    border:1.5px solid var(--line);
    background:var(--card);
    padding:7px 16px;border-radius:999px;
    font-size:13.5px;cursor:pointer;color:var(--ink-soft);
    transition:all .15s ease;
  }
  .chip:hover, .chip.active{background:var(--ink);color:var(--paper);border-color:var(--ink);}

  /* ---------- RESULTS ---------- */
  .results{max-width:900px;margin:36px auto 0;padding:0 20px;}
  .results-count{font-size:13px;color:var(--ink-soft);margin-bottom:14px;text-align:center;}
  .empty{
    text-align:center;color:var(--ink-soft);padding:40px 20px;
    border:1.5px dashed var(--line);border-radius:16px;background:var(--card);
  }
  .card-grid{display:grid;gap:16px;}
  .word-card{
    background:var(--card);
    border:1.5px solid var(--line);
    border-radius:18px;
    padding:20px 22px;
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:14px;
    position:relative;
  }
  .word-card .cat-tag{
    position:absolute;top:-10px;left:18px;
    background:var(--gold);color:#fff;font-size:11px;font-weight:700;
    padding:3px 10px;border-radius:999px;letter-spacing:.04em;
  }
  .lang-block{display:flex;flex-direction:column;gap:4px;padding-right:8px;}
  .lang-block + .lang-block{border-left:1px solid var(--line);padding-left:14px;}
  .lang-label{font-size:11px;text-transform:uppercase;letter-spacing:.08em;color:var(--ink-soft);font-weight:700;}
  .lang-main{font-size:19px;font-weight:600;font-family:'Noto Serif','Noto Serif SC','Noto Sans JP',serif;}
  .lang-sub{font-size:12.5px;color:var(--ink-soft);font-family:'JetBrains Mono',monospace;}
  .play-btn{
    align-self:flex-start;margin-top:4px;
    border:1.5px solid var(--ink);background:transparent;
    border-radius:999px;width:30px;height:30px;
    display:flex;align-items:center;justify-content:center;
    cursor:pointer;font-size:13px;color:var(--ink);
    transition:all .15s ease;
  }
  .play-btn:hover{background:var(--ink);color:var(--paper);}

  @media(max-width:820px){
    .word-card{grid-template-columns:1fr 1fr;}
    .lang-block:nth-child(2){border-left:none;padding-left:0;}
    .lang-block:nth-child(3){border-left:1px solid var(--line);padding-left:14px;}
  }
  @media(max-width:520px){
    .word-card{grid-template-columns:1fr;}
    .lang-block{border-left:none !important;padding-left:0 !important;border-top:1px solid var(--line);padding-top:10px;}
    .lang-block:first-child{border-top:none;padding-top:0;}
  }

  /* ---------- PRACTICE SECTION ---------- */
  .practice{max-width:900px;margin:64px auto;padding:0 20px 60px;}
  .practice-header{text-align:center;margin-bottom:24px;}
  .practice-header h2{font-size:28px;}
  .practice-header p{color:var(--ink-soft);font-size:14.5px;margin-top:6px;}
  .tabs{display:flex;justify-content:center;gap:6px;margin-bottom:28px;flex-wrap:wrap;}
  .tab{
    padding:10px 20px;border-radius:12px;border:1.5px solid var(--ink);
    background:transparent;color:var(--ink);font-weight:700;cursor:pointer;font-size:14.5px;
  }
  .tab.active{background:var(--ink);color:var(--paper);}
  .panel{display:none;background:var(--card);border:1.5px solid var(--line);border-radius:20px;padding:32px;}
  .panel.active{display:block;}

  .row{display:flex;gap:10px;flex-wrap:wrap;align-items:center;justify-content:center;margin-bottom:22px;}
  select{
    border:1.5px solid var(--ink);border-radius:10px;padding:8px 12px;
    background:var(--paper);font-size:14px;font-family:'Noto Sans',sans-serif;color:var(--ink);
  }

  /* Flashcard */
  .flash-stage{display:flex;flex-direction:column;align-items:center;gap:18px;}
  .flashcard{
    width:100%;max-width:420px;min-height:200px;
    border:2px solid var(--ink);border-radius:20px;
    display:flex;flex-direction:column;align-items:center;justify-content:center;gap:10px;
    padding:28px;cursor:pointer;background:var(--paper);
    box-shadow:5px 5px 0 var(--lacquer-dim);
    text-align:center;
  }
  .flashcard .front{font-size:30px;font-weight:700;font-family:'Noto Serif','Noto Serif SC','Noto Sans JP',serif;}
  .flashcard .flip-hint{font-size:12px;color:var(--ink-soft);}
  .flashcard .back{display:none;flex-direction:column;gap:8px;width:100%;}
  .flashcard.flipped .front{display:none;}
  .flashcard.flipped .back{display:flex;}
  .back-row{display:flex;justify-content:space-between;align-items:center;font-size:15px;border-top:1px dashed var(--line);padding-top:8px;}
  .back-row:first-child{border-top:none;padding-top:0;}
  .back-lbl{font-size:11px;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.06em;min-width:70px;text-align:left;}
  .flash-controls{display:flex;gap:10px;}
  .btn{
    border:none;border-radius:10px;padding:10px 20px;font-weight:700;cursor:pointer;font-size:14px;
  }
  .btn-primary{background:var(--ink);color:var(--paper);}
  .btn-ghost{background:transparent;border:1.5px solid var(--ink);color:var(--ink);}
  .btn-jade{background:var(--jade);color:#fff;}
  .btn-lacquer{background:var(--lacquer);color:#fff;}

  /* Listening */
  .listen-stage{text-align:center;}
  .listen-play{
    width:90px;height:90px;border-radius:50%;border:3px solid var(--ink);
    background:var(--paper);font-size:32px;cursor:pointer;margin:0 auto 20px;
    display:flex;align-items:center;justify-content:center;
  }
  .options{display:grid;grid-template-columns:1fr 1fr;gap:12px;max-width:500px;margin:0 auto;}
  @media(max-width:520px){.options{grid-template-columns:1fr;}}
  .option{
    border:1.5px solid var(--ink);border-radius:12px;padding:14px;background:var(--paper);
    cursor:pointer;font-size:15px;font-weight:600;font-family:'Noto Serif','Noto Serif SC','Noto Sans JP',serif;
  }
  .option.correct{background:var(--jade);color:#fff;border-color:var(--jade);}
  .option.wrong{background:var(--lacquer);color:#fff;border-color:var(--lacquer);}
  .score{margin-top:18px;font-size:14px;color:var(--ink-soft);}
  .feedback{margin-top:14px;font-weight:700;min-height:20px;}

  /* Speaking */
  .speak-stage{text-align:center;}
  .speak-target{font-size:32px;font-weight:700;font-family:'Noto Serif','Noto Serif SC','Noto Sans JP',serif;margin-bottom:6px;}
  .speak-sub{color:var(--ink-soft);font-size:14px;margin-bottom:22px;}
  .mic-btn{
    width:100px;height:100px;border-radius:50%;border:3px solid var(--lacquer);
    background:var(--paper);font-size:36px;cursor:pointer;margin:0 auto 16px;
    display:flex;align-items:center;justify-content:center;transition:all .2s ease;
  }
  .mic-btn.recording{background:var(--lacquer);color:#fff;animation:pulse 1s infinite;}
  @keyframes pulse{0%{box-shadow:0 0 0 0 rgba(179,58,50,.5);}70%{box-shadow:0 0 0 16px rgba(179,58,50,0);}100%{box-shadow:0 0 0 0 rgba(179,58,50,0);}}
  .heard{margin-top:14px;font-size:15px;}
  .heard b{font-family:'JetBrains Mono',monospace;}
  .not-supported{color:var(--ink-soft);font-size:14px;background:var(--paper-dim);padding:14px;border-radius:10px;}

  footer{text-align:center;padding:30px 20px 50px;color:var(--ink-soft);font-size:12.5px;}
  footer a{color:var(--lacquer);}
</style>
</head>
<body>

<div class="hero">
  <div class="seals">
    <div class="seal vi">越</div>
    <div class="seal zh">中</div>
    <div class="seal en">A</div>
    <div class="seal ja">日</div>
  </div>
  <div class="eyebrow">Tra cứu · Nghe · Nói</div>
  <h1 class="title">TỨ NGỮ <span class="accent">ĐIỂN</span></h1>
  <p class="subtitle">Từ điển đối chiếu Việt – Trung (Phồn thể &amp; Giản thể) – Anh – Nhật, kèm luyện phát âm và nghe hiểu từ vựng ngay trên trình duyệt.</p>

  <div class="search-wrap">
    <div class="search-box">
      <input id="searchInput" type="text" placeholder="Nhập một từ bằng tiếng Việt, 中文, English hoặc 日本語…" autocomplete="off">
      <button onclick="performSearch()">Tra cứu</button>
    </div>
    <div class="search-hint">Ví dụ: "cảm ơn", "谢谢", "thank you", "ありがとう"</div>
  </div>

  <div class="chips" id="chips"></div>
</div>

<div class="results" id="results">
  <div class="empty" id="emptyState">Gõ một từ ở trên, hoặc chọn một chủ đề để bắt đầu tra cứu 100+ từ vựng cốt lõi.</div>
  <div class="results-count" id="resultsCount" style="display:none;"></div>
  <div class="card-grid" id="cardGrid"></div>
</div>

<div class="practice">
  <div class="practice-header">
    <h2>Góc luyện tập</h2>
    <p>Ôn từ vựng bằng thẻ ghi nhớ, luyện nghe đa ngữ, và luyện nói với micro của bạn.</p>
  </div>
  <div class="tabs">
    <button class="tab active" data-tab="flash">🗂️ Thẻ ghi nhớ</button>
    <button class="tab" data-tab="listen">🎧 Luyện nghe</button>
    <button class="tab" data-tab="speak">🎙️ Luyện nói</button>
  </div>

  <!-- FLASHCARD PANEL -->
  <div class="panel active" id="panel-flash">
    <div class="row">
      <label>Chủ đề: <select id="flashCat"></select></label>
      <label>Mặt trước: <select id="flashFront">
        <option value="v">Tiếng Việt</option>
        <option value="t">Trung – Phồn thể</option>
        <option value="s">Trung – Giản thể</option>
        <option value="e">Tiếng Anh</option>
        <option value="j">Tiếng Nhật</option>
      </select></label>
    </div>
    <div class="flash-stage">
      <div class="flashcard" id="flashcard" onclick="flipCard()">
        <div class="front" id="flashFrontText">—</div>
        <div class="flip-hint">Chạm để lật thẻ</div>
        <div class="back" id="flashBack"></div>
      </div>
      <div class="flash-controls">
        <button class="btn btn-ghost" onclick="nextFlash()">Từ tiếp theo ▸</button>
        <button class="btn btn-jade" onclick="markFlash(true)">✓ Đã thuộc</button>
        <button class="btn btn-lacquer" onclick="markFlash(false)">✗ Cần ôn lại</button>
      </div>
      <div class="score" id="flashScore">Đã thuộc: 0 · Cần ôn lại: 0</div>
    </div>
  </div>

  <!-- LISTENING PANEL -->
  <div class="panel" id="panel-listen">
    <div class="row">
      <label>Nghe bằng: <select id="listenFrom">
        <option value="v">Tiếng Việt</option>
        <option value="t">Trung – Phồn thể</option>
        <option value="s">Trung – Giản thể</option>
        <option value="e">Tiếng Anh</option>
        <option value="j" selected>Tiếng Nhật</option>
      </select></label>
      <label>Chọn nghĩa bằng: <select id="listenTo">
        <option value="v" selected>Tiếng Việt</option>
        <option value="t">Trung – Phồn thể</option>
        <option value="s">Trung – Giản thể</option>
        <option value="e">Tiếng Anh</option>
        <option value="j">Tiếng Nhật</option>
      </select></label>
      <button class="btn btn-primary" onclick="newListenQuestion()">Câu hỏi mới</button>
    </div>
    <div class="listen-stage">
      <button class="listen-play" id="listenPlayBtn" onclick="playListenAudio()">▶</button>
      <div class="options" id="listenOptions"></div>
      <div class="feedback" id="listenFeedback"></div>
      <div class="score" id="listenScore">Điểm: 0 / 0</div>
    </div>
  </div>

  <!-- SPEAKING PANEL -->
  <div class="panel" id="panel-speak">
    <div class="row">
      <label>Chủ đề: <select id="speakCat"></select></label>
      <label>Luyện nói bằng: <select id="speakLang">
        <option value="v" selected>Tiếng Việt</option>
        <option value="t">Trung – Phồn thể</option>
        <option value="s">Trung – Giản thể</option>
        <option value="e">Tiếng Anh</option>
        <option value="j">Tiếng Nhật</option>
      </select></label>
      <button class="btn btn-ghost" onclick="newSpeakWord()">Từ khác</button>
    </div>
    <div class="speak-stage">
      <div class="speak-target" id="speakTarget">—</div>
      <div class="speak-sub" id="speakSub"></div>
      <button class="play-btn" style="width:40px;height:40px;font-size:16px;margin-bottom:18px;" onclick="playSpeakReference()">🔊</button>
      <div id="speakArea"></div>
    </div>
  </div>
</div>

<footer>
  Bộ từ vựng cốt lõi ~100 từ được biên soạn thủ công để minh hoạ; phát âm dùng Web Speech API của trình duyệt (chất lượng phụ thuộc trình duyệt/thiết bị). Luyện nói cần quyền truy cập micro.
</footer>

<script>
/* ============== DATA ============== */
// v=Tiếng Việt, t=Trung phồn thể, s=Trung giản thể, p=pinyin, e=Tiếng Anh, j=Nhật (chữ), k=Nhật (kana đọc), r=romaji, c=chủ đề
const CATS = {
  greet:'Chào hỏi', num:'Số đếm', fam:'Gia đình', color:'Màu sắc', time:'Thời gian',
  food:'Đồ ăn & thức uống', animal:'Động vật', verb:'Động từ', adj:'Tính từ', place:'Nơi chốn',body:"Cơ quan",cloth:"Quần áo",weather:"Thời tiết",transport:"Phương tiện",job:"Nghề nghiệp",school:"Trường học",fruit:"Trái cây",vegetable:"Rau củ",electronics:"Điện tử",sport:"Thể thao",music:"Âm nhạc",
nature:"Thiên nhiên",furniture:"Nội thất",tool:"Dụng cụ",emotion:"Cảm xúc",health:"Sức khỏe",holiday:"Ngày lễ",tech:"Công nghệ",travel:"Du lịch",art:"Nghệ thuật"
};

const DATA = [
    // ===== Animal (Động vật) =====
{v:'Con sư tử',t:'獅子',s:'狮子',p:'shīzi',e:'Lion',j:'ライオン',k:'ライオン',r:'raion',c:'animal'},
{v:'Con báo',t:'豹',s:'豹',p:'bào',e:'Leopard',j:'ヒョウ',k:'ヒョウ',r:'hyou',c:'animal'},
{v:'Con báo đốm',t:'獵豹',s:'猎豹',p:'lièbào',e:'Cheetah',j:'チーター',k:'チーター',r:'chiitaa',c:'animal'},
{v:'Con linh cẩu',t:'鬣狗',s:'鬣狗',p:'liègǒu',e:'Hyena',j:'ハイエナ',k:'ハイエナ',r:'haiena',c:'animal'},
{v:'Con tê giác',t:'犀牛',s:'犀牛',p:'xīniú',e:'Rhinoceros',j:'サイ',k:'サイ',r:'sai',c:'animal'},
{v:'Con hà mã',t:'河馬',s:'河马',p:'hémǎ',e:'Hippopotamus',j:'カバ',k:'カバ',r:'kaba',c:'animal'},
{v:'Con lạc đà',t:'駱駝',s:'骆驼',p:'luòtuo',e:'Camel',j:'ラクダ',k:'ラクダ',r:'rakuda',c:'animal'},
{v:'Con lạc đà không bướu',t:'羊駝',s:'羊驼',p:'yángtuó',e:'Alpaca',j:'アルパカ',k:'アルパカ',r:'arupaka',c:'animal'},
{v:'Con tuần lộc',t:'馴鹿',s:'驯鹿',p:'xùnlù',e:'Reindeer',j:'トナカイ',k:'トナカイ',r:'tonakai',c:'animal'},
{v:'Con nai',t:'鹿',s:'鹿',p:'lù',e:'Deer',j:'鹿',k:'しか',r:'shika',c:'animal'},
{v:'Con hươu cao cổ',t:'長頸鹿',s:'长颈鹿',p:'chángjǐnglù',e:'Giraffe',j:'キリン',k:'キリン',r:'kirin',c:'animal'},
{v:'Con ngựa vằn',t:'斑馬',s:'斑马',p:'bānmǎ',e:'Zebra',j:'シマウマ',k:'シマウマ',r:'shimauma',c:'animal'},
{v:'Con sóc',t:'松鼠',s:'松鼠',p:'sōngshǔ',e:'Squirrel',j:'リス',k:'リス',r:'risu',c:'animal'},
{v:'Con nhím',t:'刺蝟',s:'刺猬',p:'cìwei',e:'Hedgehog',j:'ハリネズミ',k:'ハリネズミ',r:'harinezumi',c:'animal'},
{v:'Con dơi',t:'蝙蝠',s:'蝙蝠',p:'biānfú',e:'Bat',j:'コウモリ',k:'コウモリ',r:'koumori',c:'animal'},
{v:'Con chuột',t:'老鼠',s:'老鼠',p:'lǎoshǔ',e:'Mouse',j:'ねずみ',k:'ねずみ',r:'nezumi',c:'animal'},
{v:'Con chuột lang',t:'天竺鼠',s:'天竺鼠',p:'tiānzhúshǔ',e:'Guinea pig',j:'モルモット',k:'モルモット',r:'morumotto',c:'animal'},
{v:'Con hải ly',t:'海狸',s:'海狸',p:'hǎilí',e:'Beaver',j:'ビーバー',k:'ビーバー',r:'biibaa',c:'animal'},
{v:'Con rái cá',t:'水獺',s:'水獭',p:'shuǐtǎ',e:'Otter',j:'カワウソ',k:'カワウソ',r:'kawauso',c:'animal'},
{v:'Con chồn',t:'黃鼠狼',s:'黄鼠狼',p:'huángshǔláng',e:'Weasel',j:'イタチ',k:'イタチ',r:'itachi',c:'animal'},
{v:'Con gấu trúc',t:'熊貓',s:'熊猫',p:'xióngmāo',e:'Panda',j:'パンダ',k:'パンダ',r:'panda',c:'animal'},
{v:'Con gấu Bắc Cực',t:'北極熊',s:'北极熊',p:'běijíxióng',e:'Polar bear',j:'ホッキョクグマ',k:'ホッキョクグマ',r:'hokkyoku guma',c:'animal'},
{v:'Con cá voi',t:'鯨魚',s:'鲸鱼',p:'jīngyú',e:'Whale',j:'クジラ',k:'クジラ',r:'kujira',c:'animal'},
{v:'Con cá heo',t:'海豚',s:'海豚',p:'hǎitún',e:'Dolphin',j:'イルカ',k:'イルカ',r:'iruka',c:'animal'},
{v:'Con cá mập',t:'鯊魚',s:'鲨鱼',p:'shāyú',e:'Shark',j:'サメ',k:'サメ',r:'same',c:'animal'},
{v:'Con bạch tuộc',t:'章魚',s:'章鱼',p:'zhāngyú',e:'Octopus',j:'タコ',k:'タコ',r:'tako',c:'animal'},
{v:'Con mực',t:'魷魚',s:'鱿鱼',p:'yóuyú',e:'Squid',j:'イカ',k:'イカ',r:'ika',c:'animal'},
{v:'Con cua',t:'螃蟹',s:'螃蟹',p:'pángxiè',e:'Crab',j:'カニ',k:'カニ',r:'kani',c:'animal'},
{v:'Con tôm',t:'蝦',s:'虾',p:'xiā',e:'Shrimp',j:'エビ',k:'エビ',r:'ebi',c:'animal'},
{v:'Con sứa',t:'水母',s:'水母',p:'shuǐmǔ',e:'Jellyfish',j:'クラゲ',k:'クラゲ',r:'kurage',c:'animal'},
{v:'Con sao biển',t:'海星',s:'海星',p:'hǎixīng',e:'Starfish',j:'ヒトデ',k:'ヒトデ',r:'hitode',c:'animal'},
{v:'Con hải cẩu',t:'海豹',s:'海豹',p:'hǎibào',e:'Seal',j:'アザラシ',k:'アザラシ',r:'azarashi',c:'animal'},
{v:'Con sư tử biển',t:'海獅',s:'海狮',p:'hǎishī',e:'Sea lion',j:'アシカ',k:'アシカ',r:'ashika',c:'animal'},
{v:'Con chim cánh cụt',t:'企鵝',s:'企鹅',p:'qǐ',e:'Penguin',j:'ペンギン',k:'ペンギン',r:'pengin',c:'animal'},
{v:'Con đà điểu',t:'鴕鳥',s:'鸵鸟',p:'tuóniǎo',e:'Ostrich',j:'ダチョウ',k:'ダチョウ',r:'dachou',c:'animal'},
{v:'Con công',t:'孔雀',s:'孔雀',p:'kǒngquè',e:'Peacock',j:'クジャク',k:'クジャク',r:'kujaku',c:'animal'},
{v:'Con vẹt',t:'鸚鵡',s:'鹦鹉',p:'yīngwǔ',e:'Parrot',j:'オウム',k:'オウム',r:'oumu',c:'animal'},
{v:'Con cú',t:'貓頭鷹',s:'猫头鹰',p:'māotóuyīng',e:'Owl',j:'フクロウ',k:'フクロウ',r:'fukurou',c:'animal'},
{v:'Con đại bàng',t:'老鷹',s:'老鹰',p:'lǎoyīng',e:'Eagle',j:'ワシ',k:'ワシ',r:'washi',c:'animal'},
{v:'Con chim ưng',t:'隼',s:'隼',p:'sǔn',e:'Falcon',j:'ハヤブサ',k:'ハヤブサ',r:'hayabusa',c:'animal'},
{v:'Con thiên nga',t:'天鵝',s:'天鹅',p:'tiān',e:'Swan',j:'白鳥',k:'はくちょう',r:'hakuchou',c:'animal'},
{v:'Con vịt',t:'鴨子',s:'鸭子',p:'yāzi',e:'Duck',j:'アヒル',k:'アヒル',r:'ahiru',c:'animal'},
{v:'Con ngỗng',t:'鵝',s:'鹅',p:'é',e:'Goose',j:'ガチョウ',k:'ガチョウ',r:'gachou',c:'animal'},
{v:'Con bồ câu',t:'鴿子',s:'鸽子',p:'gēzi',e:'Pigeon',j:'ハト',k:'ハト',r:'hato',c:'animal'},
{v:'Con quạ',t:'烏鴉',s:'乌鸦',p:'wūyā',e:'Crow',j:'カラス',k:'カラス',r:'karasu',c:'animal'},
{v:'Con ong',t:'蜜蜂',s:'蜜蜂',p:'mìfēng',e:'Bee',j:'ハチ',k:'ハチ',r:'hachi',c:'animal'},
{v:'Con bướm',t:'蝴蝶',s:'蝴蝶',p:'húdié',e:'Butterfly',j:'チョウ',k:'ちょう',r:'chou',c:'animal'},
{v:'Con chuồn chuồn',t:'蜻蜓',s:'蜻蜓',p:'qīngtíng',e:'Dragonfly',j:'トンボ',k:'トンボ',r:'tonbo',c:'animal'},
{v:'Con kiến',t:'螞蟻',s:'蚂蚁',p:'mǎyǐ',e:'Ant',j:'アリ',k:'アリ',r:'ari',c:'animal'},
{v:'Con muỗi',t:'蚊子',s:'蚊子',p:'wénzi',e:'Mosquito',j:'蚊',k:'か',r:'ka',c:'animal'},
{v:'Con ruồi',t:'蒼蠅',s:'苍蝇',p:'cāngying',e:'Fly',j:'ハエ',k:'ハエ',r:'hae',c:'animal'},
{v:'Con giun',t:'蚯蚓',s:'蚯蚓',p:'qiūyǐn',e:'Earthworm',j:'ミミズ',k:'ミミズ',r:'mimizu',c:'animal'},
{v:'Con ốc sên',t:'蝸牛',s:'蜗牛',p:'wōniú',e:'Snail',j:'カタツムリ',k:'カタツムリ',r:'katatsumuri',c:'animal'},
{v:'Con tắc kè',t:'壁虎',s:'壁虎',p:'bìhǔ',e:'Gecko',j:'ヤモリ',k:'ヤモリ',r:'yamori',c:'animal'},
{v:'Con kỳ nhông',t:'蜥蜴',s:'蜥蜴',p:'xīyì',e:'Lizard',j:'トカゲ',k:'トカゲ',r:'tokage',c:'animal'},
{v:'Con cá sấu',t:'鱷魚',s:'鳄鱼',p:'èyú',e:'Crocodile',j:'ワニ',k:'ワニ',r:'wani',c:'animal'},
{v:'Con rùa',t:'烏龜',s:'乌龟',p:'wūguī',e:'Turtle',j:'カメ',k:'カメ',r:'kame',c:'animal'},
   // ===== Furniture (Nội thất) =====
{v:'Kệ sách',t:'書架',s:'书架',p:'shūjià',e:'Bookshelf',j:'本棚',k:'ほんだな',r:'hondana',c:'furniture'},
{v:'Tủ quần áo',t:'衣櫃',s:'衣柜',p:'yīguì',e:'Wardrobe',j:'洋服だんす',k:'ようふくだんす',r:'youfuku dansu',c:'furniture'},
{v:'Bàn làm việc',t:'書桌',s:'书桌',p:'shūzhuō',e:'Desk',j:'机',k:'つくえ',r:'tsukue',c:'furniture'},
{v:'Bàn ăn',t:'餐桌',s:'餐桌',p:'cānzhuō',e:'Dining table',j:'食卓',k:'しょくたく',r:'shokutaku',c:'furniture'},
{v:'Ghế bành',t:'扶手椅',s:'扶手椅',p:'fúshǒuyǐ',e:'Armchair',j:'肘掛け椅子',k:'ひじかけいす',r:'hijikake isu',c:'furniture'},
{v:'Ghế đẩu',t:'凳子',s:'凳子',p:'dèngzi',e:'Stool',j:'スツール',k:'スツール',r:'sutsuuru',c:'furniture'},
{v:'Giá treo',t:'衣架',s:'衣架',p:'yījià',e:'Clothes rack',j:'ハンガーラック',k:'ハンガーラック',r:'hangaa rakku',c:'furniture'},
{v:'Màn cửa',t:'窗簾',s:'窗帘',p:'chuānglián',e:'Curtain',j:'カーテン',k:'カーテン',r:'kaaten',c:'furniture'},
{v:'Thảm',t:'地毯',s:'地毯',p:'dìtǎn',e:'Carpet',j:'じゅうたん',k:'じゅうたん',r:'juutan',c:'furniture'},
{v:'Gối',t:'枕頭',s:'枕头',p:'zhěntou',e:'Pillow',j:'枕',k:'まくら',r:'makura',c:'furniture'},
{v:'Chăn',t:'棉被',s:'棉被',p:'miánbèi',e:'Blanket',j:'毛布',k:'もうふ',r:'moufu',c:'furniture'},
{v:'Nệm',t:'床墊',s:'床垫',p:'chuángdiàn',e:'Mattress',j:'マットレス',k:'マットレス',r:'mattoresu',c:'furniture'},
{v:'Móc áo',t:'衣架',s:'衣架',p:'yījià',e:'Hanger',j:'ハンガー',k:'ハンガー',r:'hangaa',c:'furniture'},
{v:'Tủ đầu giường',t:'床頭櫃',s:'床头柜',p:'chuángtóuguì',e:'Bedside table',j:'ナイトテーブル',k:'ナイトテーブル',r:'naito teeburu',c:'furniture'},
{v:'Quạt trần',t:'吊扇',s:'吊扇',p:'diàoshàn',e:'Ceiling fan',j:'天井扇風機',k:'てんじょうせんぷうき',r:'tenjou senpuuki',c:'furniture'},

// ===== Tool (Dụng cụ) =====
{v:'Búa',t:'錘子',s:'锤子',p:'chuízi',e:'Hammer',j:'ハンマー',k:'ハンマー',r:'hanmaa',c:'tool'},
{v:'Tua vít',t:'螺絲起子',s:'螺丝刀',p:'luósīdāo',e:'Screwdriver',j:'ドライバー',k:'ドライバー',r:'doraibaa',c:'tool'},
{v:'Kìm',t:'鉗子',s:'钳子',p:'qiánzi',e:'Pliers',j:'ペンチ',k:'ペンチ',r:'penchi',c:'tool'},
{v:'Cờ lê',t:'扳手',s:'扳手',p:'bānshǒu',e:'Wrench',j:'レンチ',k:'レンチ',r:'renchi',c:'tool'},
{v:'Mỏ lết',t:'活動扳手',s:'活动扳手',p:'huódòng bānshǒu',e:'Adjustable wrench',j:'モンキーレンチ',k:'モンキーレンチ',r:'monkii renchi',c:'tool'},
{v:'Cưa',t:'鋸子',s:'锯子',p:'jùzi',e:'Saw',j:'のこぎり',k:'のこぎり',r:'nokogiri',c:'tool'},
{v:'Khoan',t:'電鑽',s:'电钻',p:'diànzuàn',e:'Drill',j:'ドリル',k:'ドリル',r:'doriru',c:'tool'},
{v:'Thước dây',t:'捲尺',s:'卷尺',p:'juǎnchǐ',e:'Tape measure',j:'メジャー',k:'メジャー',r:'mejaa',c:'tool'},
{v:'Dao',t:'刀',s:'刀',p:'dāo',e:'Knife',j:'ナイフ',k:'ナイフ',r:'naifu',c:'tool'},
{v:'Kéo',t:'剪刀',s:'剪刀',p:'jiǎndāo',e:'Scissors',j:'はさみ',k:'はさみ',r:'hasami',c:'tool'},
{v:'Đèn pin',t:'手電筒',s:'手电筒',p:'shǒudiàntǒng',e:'Flashlight',j:'懐中電灯',k:'かいちゅうでんとう',r:'kaichuu dentou',c:'tool'},
{v:'Xẻng',t:'鏟子',s:'铲子',p:'chǎnzi',e:'Shovel',j:'シャベル',k:'シャベル',r:'shaberu',c:'tool'},
{v:'Cuốc',t:'鋤頭',s:'锄头',p:'chútou',e:'Hoe',j:'くわ',k:'くわ',r:'kuwa',c:'tool'},
{v:'Rìu',t:'斧頭',s:'斧头',p:'fǔtou',e:'Axe',j:'斧',k:'おの',r:'ono',c:'tool'},
{v:'Bàn chải',t:'刷子',s:'刷子',p:'shuāzi',e:'Brush',j:'ブラシ',k:'ブラシ',r:'burashi',c:'tool'},

// ===== Emotion (Cảm xúc) =====
{v:'Phấn khởi',t:'興奮',s:'兴奋',p:'xīngfèn',e:'Excited',j:'興奮',k:'こうふん',r:'koufun',c:'emotion'},
{v:'Lo lắng',t:'擔心',s:'担心',p:'dānxīn',e:'Worried',j:'心配',k:'しんぱい',r:'shinpai',c:'emotion'},
{v:'Sợ hãi',t:'害怕',s:'害怕',p:'hàipà',e:'Afraid',j:'怖い',k:'こわい',r:'kowai',c:'emotion'},
{v:'Tức giận',t:'生氣',s:'生气',p:'shēngqì',e:'Angry',j:'怒る',k:'おこる',r:'okoru',c:'emotion'},
{v:'Bình tĩnh',t:'冷靜',s:'冷静',p:'lěngjìng',e:'Calm',j:'落ち着く',k:'おちつく',r:'ochitsuku',c:'emotion'},
{v:'Ngạc nhiên',t:'驚訝',s:'惊讶',p:'jīngyà',e:'Surprised',j:'驚く',k:'おどろく',r:'odoroku',c:'emotion'},
{v:'Tự hào',t:'驕傲',s:'骄傲',p:'jiāo',e:'Proud',j:'誇らしい',k:'ほこらしい',r:'hokorashii',c:'emotion'},    
{v:'Xấu hổ',t:'害羞',s:'害羞',p:'hàixiū',e:'Shy',j:'恥ずかしい',k:'はずかしい',r:'hazukashii',c:'emotion'},
{v:'Chán',t:'無聊',s:'无聊',p:'wúliáo',e:'Bored',j:'退屈',k:'たいくつ',r:'taikutsu',c:'emotion'},
{v:'Hy vọng',t:'希望',s:'希望',p:'xīwàng',e:'Hopeful',j:'希望',k:'きぼう',r:'kibou',c:'emotion'},
{v:'Thất vọng',t:'失望',s:'失望',p:'shīwàng',e:'Disappointed',j:'失望',k:'しつぼう',r:'shitsubou',c:'emotion'},
{v:'Biết ơn',t:'感激',s:'感激',p:'gǎnjī',e:'Grateful',j:'感謝',k:'かんしゃ',r:'kansha',c:'emotion'},
{v:'Ghen tị',t:'嫉妒',s:'嫉妒',p:'jídù',e:'Jealous',j:'嫉妬',k:'しっと',r:'shitto',c:'emotion'},
{v:'Yên tâm',t:'放心',s:'放心',p:'fàngxīn',e:'Relieved',j:'安心',k:'あんしん',r:'anshin',c:'emotion'},
{v:'Cô đơn',t:'孤單',s:'孤单',p:'gūdān',e:'Lonely',j:'寂しい',k:'さびしい',r:'sabishii',c:'emotion'},

// ===== Health (Sức khỏe) =====
{v:'Sức khỏe',t:'健康',s:'健康',p:'jiànkāng',e:'Health',j:'健康',k:'けんこう',r:'kenkou',c:'health'},
{v:'Bệnh',t:'疾病',s:'疾病',p:'jíbìng',e:'Disease',j:'病気',k:'びょうき',r:'byouki',c:'health'},
{v:'Sốt',t:'發燒',s:'发烧',p:'fāshāo',e:'Fever',j:'熱',k:'ねつ',r:'netsu',c:'health'},
{v:'Ho',t:'咳嗽',s:'咳嗽',p:'késou',e:'Cough',j:'咳',k:'せき',r:'seki',c:'health'},
{v:'Đau đầu',t:'頭痛',s:'头痛',p:'tóutòng',e:'Headache',j:'頭痛',k:'ずつう',r:'zutsuu',c:'health'},
{v:'Đau bụng',t:'肚子痛',s:'肚子痛',p:'dùzitòng',e:'Stomachache',j:'腹痛',k:'ふくつう',r:'fukutsuu',c:'health'},
{v:'Thuốc',t:'藥',s:'药',p:'yào',e:'Medicine',j:'薬',k:'くすり',r:'kusuri',c:'health'},
{v:'Băng gạc',t:'繃帶',s:'绷带',p:'bēngdài',e:'Bandage',j:'包帯',k:'ほうたい',r:'houtai',c:'health'},
{v:'Tiêm',t:'注射',s:'注射',p:'zhùshè',e:'Injection',j:'注射',k:'ちゅうしゃ',r:'chuusha',c:'health'},
{v:'Nhiệt kế',t:'體溫計',s:'体温计',p:'tǐwēnjì',e:'Thermometer',j:'体温計',k:'たいおんけい',r:'taionkei',c:'health'},
{v:'Khám bệnh',t:'看病',s:'看病',p:'kànbìng',e:'Medical checkup',j:'診察',k:'しんさつ',r:'shinsatsu',c:'health'},
{v:'Cấp cứu',t:'急救',s:'急救',p:'jíjiù',e:'First aid',j:'救急',k:'きゅうきゅう',r:'kyuukyuu',c:'health'},

// ===== Holiday (Ngày lễ) =====
{v:'Tết Nguyên Đán',t:'春節',s:'春节',p:'chūnjié',e:'Lunar New Year',j:'旧正月',k:'きゅうしょうがつ',r:'kyuu shougatsu',c:'holiday'},
{v:'Giáng sinh',t:'聖誕節',s:'圣诞节',p:'shèngdànjié',e:'Christmas',j:'クリスマス',k:'クリスマス',r:'kurisumasu',c:'holiday'},
{v:'Năm mới',t:'新年',s:'新年',p:'xīnnián',e:'New Year',j:'お正月',k:'おしょうがつ',r:'oshougatsu',c:'holiday'},
{v:'Sinh nhật',t:'生日',s:'生日',p:'shēngrì',e:'Birthday',j:'誕生日',k:'たんじょうび',r:'tanjoubi',c:'holiday'},
{v:'Lễ cưới',t:'婚禮',s:'婚礼',p:'hūnlǐ',e:'Wedding',j:'結婚式',k:'けっこんしき',r:'kekkonshiki',c:'holiday'},
{v:'Lễ hội',t:'節日',s:'节日',p:'jiérì',e:'Festival',j:'祭り',k:'まつり',r:'matsuri',c:'holiday'},
{v:'Pháo hoa',t:'煙火',s:'烟花',p:'yānhuā',e:'Fireworks',j:'花火',k:'はなび',r:'hanabi',c:'holiday'},
{v:'Quà tặng',t:'禮物',s:'礼物',p:'lǐwù',e:'Gift',j:'贈り物',k:'おくりもの',r:'okurimono',c:'holiday'},
{v:'Thiệp chúc mừng',t:'賀卡',s:'贺卡',p:'hèkǎ',e:'Greeting card',j:'カード',k:'カード',r:'kaado',c:'holiday'},
{v:'Nến',t:'蠟燭',s:'蜡烛',p:'làzhú',e:'Candle',j:'ろうそく',k:'ろうそく',r:'rousoku',c:'holiday'},

// ===== Technology (Công nghệ) =====
{v:'Phần mềm',t:'軟體',s:'软件',p:'ruǎnjiàn',e:'Software',j:'ソフトウェア',k:'ソフトウェア',r:'sofutowea',c:'tech'},
{v:'Phần cứng',t:'硬體',s:'硬件',p:'yìngjiàn',e:'Hardware',j:'ハードウェア',k:'ハードウェア',r:'haadowea',c:'tech'},
{v:'Mạng',t:'網路',s:'网络',p:'wǎngluò',e:'Network',j:'ネットワーク',k:'ネットワーク',r:'nettowaaku',c:'tech'},
{v:'Wi-Fi',t:'無線網路',s:'无线网络',p:'wúxiàn wǎngluò',e:'Wi-Fi',j:'Wi-Fi',k:'ワイファイ',r:'waifai',c:'tech'},
{v:'Internet',t:'網際網路',s:'互联网',p:'hùliánwǎng',e:'Internet',j:'インターネット',k:'インターネット',r:'intaanetto',c:'tech'},
{v:'Trang web',t:'網站',s:'网站',p:'wǎngzhàn',e:'Website',j:'ウェブサイト',k:'ウェブサイト',r:'webusaito',c:'tech'},
{v:'Ứng dụng',t:'應用程式',s:'应用程序',p:'yìngyòng chéngxù',e:'Application',j:'アプリ',k:'アプリ',r:'apuri',c:'tech'},
{v:'Tải xuống',t:'下載',s:'下载',p:'xiàzài',e:'Download',j:'ダウンロード',k:'ダウンロード',r:'daunroodo',c:'tech'},
{v:'Tải lên',t:'上傳',s:'上传',p:'shàngchuán',e:'Upload',j:'アップロード',k:'アップロード',r:'appuroodo',c:'tech'},
{v:'Mật khẩu',t:'密碼',s:'密码',p:'mìmǎ',e:'Password',j:'パスワード',k:'パスワード',r:'pasuwaado',c:'tech'},
{v:'Tài khoản',t:'帳號',s:'账号',p:'zhànghào',e:'Account',j:'アカウント',k:'アカウント',r:'akaunto',c:'tech'},
{v:'Trí tuệ nhân tạo',t:'人工智慧',s:'人工智能',p:'réngōng zhìnéng',e:'Artificial intelligence',j:'人工知能',k:'じんこうちのう',r:'jinkou chinou',c:'tech'},

// ===== Travel (Du lịch) =====
{v:'Hộ chiếu',t:'護照',s:'护照',p:'hùzhào',e:'Passport',j:'パスポート',k:'パスポート',r:'pasupooto',c:'travel'},
{v:'Thị thực',t:'簽證',s:'签证',p:'qiānzhèng',e:'Visa',j:'ビザ',k:'ビザ',r:'biza',c:'travel'},
{v:'Vé máy bay',t:'機票',s:'机票',p:'jīpiào',e:'Air ticket',j:'航空券',k:'こうくうけん',r:'koukuuken',c:'travel'},
{v:'Khách sạn',t:'飯店',s:'饭店',p:'fàndiàn',e:'Hotel',j:'ホテル',k:'ホテル',r:'hoteru',c:'travel'},
{v:'Đặt phòng',t:'訂房',s:'订房',p:'dìngfáng',e:'Book a room',j:'予約',k:'よやく',r:'yoyaku',c:'travel'},
{v:'Hành lý',t:'行李',s:'行李',p:'xíngli',e:'Luggage',j:'荷物',k:'にもつ',r:'nimotsu',c:'travel'},
{v:'Bản đồ',t:'地圖',s:'地图',p:'dìtú',e:'Map',j:'地図',k:'ちず',r:'chizu',c:'travel'},
{v:'Hướng dẫn viên',t:'導遊',s:'导游',p:'dǎoyóu',e:'Tour guide',j:'ガイド',k:'ガイド',r:'gaido',c:'travel'},
{v:'Tham quan',t:'觀光',s:'观光',p:'guānguāng',e:'Sightseeing',j:'観光',k:'かんこう',r:'kankou',c:'travel'},
{v:'Kỳ nghỉ',t:'假期',s:'假期',p:'jiàqī',e:'Vacation',j:'休暇',k:'きゅうか',r:'kyuuka',c:'travel'},

// ===== Art (Nghệ thuật) =====
{v:'Hội họa',t:'繪畫',s:'绘画',p:'huìhuà',e:'Painting',j:'絵画',k:'かいが',r:'kaiga',c:'art'},
{v:'Bức tranh',t:'畫',s:'画',p:'huà',e:'Painting',j:'絵',k:'え',r:'e',c:'art'},
{v:'Điêu khắc',t:'雕塑',s:'雕塑',p:'diāosù',e:'Sculpture',j:'彫刻',k:'ちょうこく',r:'choukoku',c:'art'},
{v:'Bảo tàng',t:'博物館',s:'博物馆',p:'bówùguǎn',e:'Museum',j:'博物館',k:'はくぶつかん',r:'hakubutsukan',c:'art'},
{v:'Triển lãm',t:'展覽',s:'展览',p:'zhǎnlǎn',e:'Exhibition',j:'展覧会',k:'てんらんかい',r:'tenrankai',c:'art'},
{v:'Họa sĩ',t:'畫家',s:'画家',p:'huàjiā',e:'Painter',j:'画家',k:'がか',r:'gaka',c:'art'},
{v:'Nhà điêu khắc',t:'雕刻家',s:'雕刻家',p:'diāokèjiā',e:'Sculptor',j:'彫刻家',k:'ちょうこくか',r:'choukokuka',c:'art'},
{v:'Cọ vẽ',t:'畫筆',s:'画笔',p:'huàbǐ',e:'Paintbrush',j:'絵筆',k:'えふで',r:'efude',c:'art'},
{v:'Sơn màu',t:'顏料',s:'颜料',p:'yánliào',e:'Paint',j:'絵の具',k:'えのぐ',r:'enogu',c:'art'},
{v:'Phòng trưng bày',t:'畫廊',s:'画廊',p:'huàláng',e:'Gallery',j:'画廊',k:'がろう',r:'garou',c:'art'}, 
// ===== Body (Cơ thể) =====
{v:'Vai',t:'肩膀',s:'肩膀',p:'jiānbǎng',e:'Shoulder',j:'肩',k:'かた',r:'kata',c:'body'},
{v:'Cánh tay',t:'手臂',s:'手臂',p:'shǒubì',e:'Arm',j:'腕',k:'うで',r:'ude',c:'body'},
{v:'Khuỷu tay',t:'手肘',s:'手肘',p:'shǒuzhǒu',e:'Elbow',j:'肘',k:'ひじ',r:'hiji',c:'body'},
{v:'Ngón tay',t:'手指',s:'手指',p:'shǒuzhǐ',e:'Finger',j:'指',k:'ゆび',r:'yubi',c:'body'},
{v:'Móng tay',t:'指甲',s:'指甲',p:'zhǐjia',e:'Fingernail',j:'爪',k:'つめ',r:'tsume',c:'body'},
{v:'Ngực',t:'胸',s:'胸',p:'xiōng',e:'Chest',j:'胸',k:'むね',r:'mune',c:'body'},
{v:'Lưng',t:'背',s:'背',p:'bèi',e:'Back',j:'背中',k:'せなか',r:'senaka',c:'body'},
{v:'Bụng',t:'肚子',s:'肚子',p:'dùzi',e:'Stomach',j:'お腹',k:'おなか',r:'onaka',c:'body'},
{v:'Đầu gối',t:'膝蓋',s:'膝盖',p:'xīgài',e:'Knee',j:'膝',k:'ひざ',r:'hiza',c:'body'},
{v:'Bàn chân',t:'腳掌',s:'脚掌',p:'jiǎozhǎng',e:'Foot',j:'足裏',k:'あしうら',r:'ashiura',c:'body'},

// ===== Weather =====
{v:'Nóng',t:'炎熱',s:'炎热',p:'yánrè',e:'Hot weather',j:'暑い',k:'あつい',r:'atsui',c:'weather'},
{v:'Lạnh',t:'寒冷',s:'寒冷',p:'hánlěng',e:'Cold weather',j:'寒い',k:'さむい',r:'samui',c:'weather'},
{v:'Nhiều mây',t:'多雲',s:'多云',p:'duōyún',e:'Cloudy',j:'曇り',k:'くもり',r:'kumori',c:'weather'},
{v:'Sấm',t:'雷',s:'雷',p:'léi',e:'Thunder',j:'雷',k:'かみなり',r:'kaminari',c:'weather'},
{v:'Chớp',t:'閃電',s:'闪电',p:'shǎndiàn',e:'Lightning',j:'稲妻',k:'いなずま',r:'inazuma',c:'weather'},
{v:'Sương mù',t:'霧',s:'雾',p:'wù',e:'Fog',j:'霧',k:'きり',r:'kiri',c:'weather'},
{v:'Cầu vồng',t:'彩虹',s:'彩虹',p:'cǎihóng',e:'Rainbow',j:'虹',k:'にじ',r:'niji',c:'weather'},
{v:'Bão tuyết',t:'暴風雪',s:'暴风雪',p:'bàofēngxuě',e:'Blizzard',j:'吹雪',k:'ふぶき',r:'fubuki',c:'weather'},
{v:'Độ ẩm',t:'濕度',s:'湿度',p:'shīdù',e:'Humidity',j:'湿度',k:'しつど',r:'shitsudo',c:'weather'},
{v:'Nhiệt độ',t:'溫度',s:'温度',p:'wēndù',e:'Temperature',j:'温度',k:'おんど',r:'ondo',c:'weather'},

// ===== School =====
{v:'Bài tập',t:'作業',s:'作业',p:'zuòyè',e:'Homework',j:'宿題',k:'しゅくだい',r:'shukudai',c:'school'},
{v:'Kỳ thi',t:'考試',s:'考试',p:'kǎoshì',e:'Exam',j:'試験',k:'しけん',r:'shiken',c:'school'},
{v:'Điểm',t:'分數',s:'分数',p:'fēnshù',e:'Score',j:'点数',k:'てんすう',r:'tensuu',c:'school'},
{v:'Bài học',t:'課程',s:'课程',p:'kèchéng',e:'Lesson',j:'授業',k:'じゅぎょう',r:'jugyou',c:'school'},
{v:'Vở',t:'筆記本',s:'笔记本',p:'bǐjìběn',e:'Notebook',j:'ノート',k:'ノート',r:'nooto',c:'school'},
{v:'Bút chì',t:'鉛筆',s:'铅笔',p:'qiānbǐ',e:'Pencil',j:'鉛筆',k:'えんぴつ',r:'enpitsu',c:'school'},
{v:'Tẩy',t:'橡皮擦',s:'橡皮擦',p:'xiàngpícā',e:'Eraser',j:'消しゴム',k:'けしゴム',r:'keshigomu',c:'school'},
{v:'Thước kẻ',t:'尺',s:'尺子',p:'chǐzi',e:'Ruler',j:'定規',k:'じょうぎ',r:'jougi',c:'school'},
{v:'Ba lô',t:'書包',s:'书包',p:'shūbāo',e:'School bag',j:'ランドセル',k:'ランドセル',r:'randoseru',c:'school'},
{v:'Thư viện',t:'圖書館',s:'图书馆',p:'túshūguǎn',e:'Library',j:'図書館',k:'としょかん',r:'toshokan',c:'school'},

// ===== Furniture =====
{v:'Bàn',t:'桌子',s:'桌子',p:'zhuōzi',e:'Table',j:'机',k:'つくえ',r:'tsukue',c:'furniture'},
{v:'Ghế',t:'椅子',s:'椅子',p:'yǐzi',e:'Chair',j:'椅子',k:'いす',r:'isu',c:'furniture'},
{v:'Giường',t:'床',s:'床',p:'chuáng',e:'Bed',j:'ベッド',k:'ベッド',r:'beddo',c:'furniture'},
{v:'Tủ',t:'櫃子',s:'柜子',p:'guìzi',e:'Cabinet',j:'戸棚',k:'とだな',r:'todana',c:'furniture'},
{v:'Ghế sofa',t:'沙發',s:'沙发',p:'shāfā',e:'Sofa',j:'ソファ',k:'ソファ',r:'sofa',c:'furniture'},
{v:'Đèn',t:'燈',s:'灯',p:'dēng',e:'Lamp',j:'ランプ',k:'ランプ',r:'ranpu',c:'furniture'},
{v:'Cửa',t:'門',s:'门',p:'mén',e:'Door',j:'ドア',k:'ドア',r:'doa',c:'furniture'},
{v:'Cửa sổ',t:'窗戶',s:'窗户',p:'chuānghu',e:'Window',j:'窓',k:'まど',r:'mado',c:'furniture'},
{v:'Gương',t:'鏡子',s:'镜子',p:'jìngzi',e:'Mirror',j:'鏡',k:'かがみ',r:'kagami',c:'furniture'},
{v:'Đồng hồ',t:'時鐘',s:'时钟',p:'shízhōng',e:'Clock',j:'時計',k:'とけい',r:'tokei',c:'furniture'},

// ===== Nature =====
{v:'Trời',t:'天空',s:'天空',p:'tiānkōng',e:'Sky',j:'空',k:'そら',r:'sora',c:'nature'},
{v:'Mặt trời',t:'太陽',s:'太阳',p:'tàiyáng',e:'Sun',j:'太陽',k:'たいよう',r:'taiyou',c:'nature'},
{v:'Mặt trăng',t:'月亮',s:'月亮',p:'yuèliang',e:'Moon',j:'月',k:'つき',r:'tsuki',c:'nature'},
{v:'Ngôi sao',t:'星星',s:'星星',p:'xīngxing',e:'Star',j:'星',k:'ほし',r:'hoshi',c:'nature'},
{v:'Biển',t:'海洋',s:'海洋',p:'hǎiyáng',e:'Sea',j:'海',k:'うみ',r:'umi',c:'nature'},
{v:'Hồ',t:'湖',s:'湖',p:'hú',e:'Lake',j:'湖',k:'みずうみ',r:'mizuumi',c:'nature'},
{v:'Rừng',t:'森林',s:'森林',p:'sēnlín',e:'Forest',j:'森',k:'もり',r:'mori',c:'nature'},
{v:'Đá',t:'石頭',s:'石头',p:'shítou',e:'Stone',j:'石',k:'いし',r:'ishi',c:'nature'},
{v:'Cát',t:'沙子',s:'沙子',p:'shāzi',e:'Sand',j:'砂',k:'すな',r:'suna',c:'nature'},
{v:'Đất',t:'土地',s:'土地',p:'tǔdì',e:'Soil',j:'土',k:'つち',r:'tsuchi',c:'nature'},

    // ===== Fruit (Trái cây) =====
{v:'Táo',t:'蘋果',s:'苹果',p:'píngguǒ',e:'Apple',j:'りんご',k:'りんご',r:'ringo',c:'fruit'},
{v:'Chuối',t:'香蕉',s:'香蕉',p:'xiāngjiāo',e:'Banana',j:'バナナ',k:'バナナ',r:'banana',c:'fruit'},
{v:'Cam',t:'橙子',s:'橙子',p:'chéngzi',e:'Orange',j:'オレンジ',k:'オレンジ',r:'orenji',c:'fruit'},
{v:'Nho',t:'葡萄',s:'葡萄',p:'pútáo',e:'Grape',j:'ぶどう',k:'ぶどう',r:'budou',c:'fruit'},
{v:'Dưa hấu',t:'西瓜',s:'西瓜',p:'xīguā',e:'Watermelon',j:'すいか',k:'すいか',r:'suika',c:'fruit'},
{v:'Xoài',t:'芒果',s:'芒果',p:'mángguǒ',e:'Mango',j:'マンゴー',k:'マンゴー',r:'mangoo',c:'fruit'},
{v:'Dứa',t:'鳳梨',s:'菠萝',p:'bōluó',e:'Pineapple',j:'パイナップル',k:'パイナップル',r:'painappuru',c:'fruit'},
{v:'Dâu tây',t:'草莓',s:'草莓',p:'cǎoméi',e:'Strawberry',j:'いちご',k:'いちご',r:'ichigo',c:'fruit'},
{v:'Lê',t:'梨',s:'梨',p:'lí',e:'Pear',j:'なし',k:'なし',r:'nashi',c:'fruit'},
{v:'Đào',t:'桃子',s:'桃子',p:'táozi',e:'Peach',j:'もも',k:'もも',r:'momo',c:'fruit'},

// ===== Vegetable (Rau củ) =====
{v:'Cà chua',t:'番茄',s:'番茄',p:'fānqié',e:'Tomato',j:'トマト',k:'トマト',r:'tomato',c:'vegetable'},
{v:'Khoai tây',t:'馬鈴薯',s:'土豆',p:'tǔdòu',e:'Potato',j:'じゃがいも',k:'じゃがいも',r:'jagaimo',c:'vegetable'},
{v:'Cà rốt',t:'胡蘿蔔',s:'胡萝卜',p:'húluóbo',e:'Carrot',j:'にんじん',k:'にんじん',r:'ninjin',c:'vegetable'},
{v:'Hành tây',t:'洋蔥',s:'洋葱',p:'yángcōng',e:'Onion',j:'たまねぎ',k:'たまねぎ',r:'tamanegi',c:'vegetable'},
{v:'Tỏi',t:'大蒜',s:'大蒜',p:'dàsuàn',e:'Garlic',j:'にんにく',k:'にんにく',r:'ninniku',c:'vegetable'},
{v:'Ớt',t:'辣椒',s:'辣椒',p:'làjiāo',e:'Chili',j:'とうがらし',k:'とうがらし',r:'tougarashi',c:'vegetable'},
{v:'Bắp cải',t:'高麗菜',s:'卷心菜',p:'juǎnxīncài',e:'Cabbage',j:'キャベツ',k:'キャベツ',r:'kyabetsu',c:'vegetable'},
{v:'Dưa leo',t:'黃瓜',s:'黄瓜',p:'huángguā',e:'Cucumber',j:'きゅうり',k:'きゅうり',r:'kyuuri',c:'vegetable'},
{v:'Bí ngô',t:'南瓜',s:'南瓜',p:'nánguā',e:'Pumpkin',j:'かぼちゃ',k:'かぼちゃ',r:'kabocha',c:'vegetable'},
{v:'Nấm',t:'蘑菇',s:'蘑菇',p:'mógu',e:'Mushroom',j:'きのこ',k:'きのこ',r:'kinoko',c:'vegetable'},

// ===== Electronics =====
{v:'Điện thoại',t:'手機',s:'手机',p:'shǒujī',e:'Phone',j:'携帯電話',k:'けいたいでんわ',r:'keitai denwa',c:'electronics'},
{v:'Máy tính',t:'電腦',s:'电脑',p:'diànnǎo',e:'Computer',j:'コンピューター',k:'コンピューター',r:'konpyuutaa',c:'electronics'},
{v:'Máy tính xách tay',t:'筆記型電腦',s:'笔记本电脑',p:'bǐjìběn diànnǎo',e:'Laptop',j:'ノートパソコン',k:'ノートパソコン',r:'nooto pasokon',c:'electronics'},
{v:'Bàn phím',t:'鍵盤',s:'键盘',p:'jiànpán',e:'Keyboard',j:'キーボード',k:'キーボード',r:'kiiboodo',c:'electronics'},
{v:'Chuột máy tính',t:'滑鼠',s:'鼠标',p:'shǔbiāo',e:'Mouse',j:'マウス',k:'マウス',r:'mausu',c:'electronics'},
{v:'Màn hình',t:'螢幕',s:'屏幕',p:'píngmù',e:'Screen',j:'画面',k:'がめん',r:'gamen',c:'electronics'},
{v:'Tai nghe',t:'耳機',s:'耳机',p:'ěrjī',e:'Headphones',j:'ヘッドホン',k:'ヘッドホン',r:'heddohon',c:'electronics'},
{v:'Loa',t:'喇叭',s:'喇叭',p:'lǎba',e:'Speaker',j:'スピーカー',k:'スピーカー',r:'supiikaa',c:'electronics'},
{v:'Camera',t:'相機',s:'相机',p:'xiàngjī',e:'Camera',j:'カメラ',k:'カメラ',r:'kamera',c:'electronics'},
{v:'Pin',t:'電池',s:'电池',p:'diànchí',e:'Battery',j:'電池',k:'でんち',r:'denchi',c:'electronics'},

// ===== Sport =====
{v:'Bóng đá',t:'足球',s:'足球',p:'zúqiú',e:'Football',j:'サッカー',k:'サッカー',r:'sakkaa',c:'sport'},
{v:'Bóng rổ',t:'籃球',s:'篮球',p:'lánqiú',e:'Basketball',j:'バスケットボール',k:'バスケットボール',r:'basukettobooru',c:'sport'},
{v:'Bóng chuyền',t:'排球',s:'排球',p:'páiqiú',e:'Volleyball',j:'バレーボール',k:'バレーボール',r:'bareebooru',c:'sport'},
{v:'Cầu lông',t:'羽毛球',s:'羽毛球',p:'yǔmáoqiú',e:'Badminton',j:'バドミントン',k:'バドミントン',r:'badominton',c:'sport'},
{v:'Quần vợt',t:'網球',s:'网球',p:'wǎngqiú',e:'Tennis',j:'テニス',k:'テニス',r:'tenisu',c:'sport'},
{v:'Bơi lội',t:'游泳',s:'游泳',p:'yóuyǒng',e:'Swimming',j:'水泳',k:'すいえい',r:'suiei',c:'sport'},
{v:'Chạy bộ',t:'跑步',s:'跑步',p:'pǎobù',e:'Running',j:'ランニング',k:'ランニング',r:'ranningu',c:'sport'},
{v:'Đạp xe',t:'騎自行車',s:'骑自行车',p:'qí zìxíngchē',e:'Cycling',j:'サイクリング',k:'サイクリング',r:'saikuringu',c:'sport'},
{v:'Cờ vua',t:'西洋棋',s:'国际象棋',p:'guójì xiàngqí',e:'Chess',j:'チェス',k:'チェス',r:'chesu',c:'sport'},
{v:'Võ thuật',t:'武術',s:'武术',p:'wǔshù',e:'Martial arts',j:'武道',k:'ぶどう',r:'budou',c:'sport'},

// ===== Music =====
{v:'Âm nhạc',t:'音樂',s:'音乐',p:'yīnyuè',e:'Music',j:'音楽',k:'おんがく',r:'ongaku',c:'music'},
{v:'Bài hát',t:'歌曲',s:'歌曲',p:'gēqǔ',e:'Song',j:'歌',k:'うた',r:'uta',c:'music'},
{v:'Ca sĩ',t:'歌手',s:'歌手',p:'gēshǒu',e:'Singer',j:'歌手',k:'かしゅ',r:'kashu',c:'music'},
{v:'Đàn guitar',t:'吉他',s:'吉他',p:'jítā',e:'Guitar',j:'ギター',k:'ギター',r:'gitaa',c:'music'},
{v:'Đàn piano',t:'鋼琴',s:'钢琴',p:'gāngqín',e:'Piano',j:'ピアノ',k:'ピアノ',r:'piano',c:'music'},
{v:'Trống',t:'鼓',s:'鼓',p:'gǔ',e:'Drum',j:'ドラム',k:'ドラム',r:'doramu',c:'music'},
{v:'Violin',t:'小提琴',s:'小提琴',p:'xiǎotíqín',e:'Violin',j:'バイオリン',k:'バイオリン',r:'baiorin',c:'music'},
{v:'Nhạc cụ',t:'樂器',s:'乐器',p:'yuèqì',e:'Instrument',j:'楽器',k:'がっき',r:'gakki',c:'music'},
{v:'Giai điệu',t:'旋律',s:'旋律',p:'xuánlǜ',e:'Melody',j:'メロディー',k:'メロディー',r:'merodii',c:'music'},
{v:'Buổi hòa nhạc',t:'音樂會',s:'音乐会',p:'yīnyuèhuì',e:'Concert',j:'コンサート',k:'コンサート',r:'konsaato',c:'music'},  
// ===== Cơ thể =====
{v:'Đầu',t:'頭',s:'头',p:'tóu',e:'Head',j:'頭',k:'あたま',r:'atama',c:'body'},
{v:'Tóc',t:'頭髮',s:'头发',p:'tóufa',e:'Hair',j:'髪',k:'かみ',r:'kami',c:'body'},
{v:'Mắt',t:'眼睛',s:'眼睛',p:'yǎnjing',e:'Eye',j:'目',k:'め',r:'me',c:'body'},
{v:'Tai',t:'耳朵',s:'耳朵',p:'ěrduo',e:'Ear',j:'耳',k:'みみ',r:'mimi',c:'body'},
{v:'Mũi',t:'鼻子',s:'鼻子',p:'bízi',e:'Nose',j:'鼻',k:'はな',r:'hana',c:'body'},
{v:'Miệng',t:'嘴巴',s:'嘴巴',p:'zuǐba',e:'Mouth',j:'口',k:'くち',r:'kuchi',c:'body'},
{v:'Tay',t:'手',s:'手',p:'shǒu',e:'Hand',j:'手',k:'て',r:'te',c:'body'},
{v:'Chân',t:'腳',s:'脚',p:'jiǎo',e:'Foot',j:'足',k:'あし',r:'ashi',c:'body'},
{v:'Tim',t:'心臟',s:'心脏',p:'xīnzàng',e:'Heart',j:'心臓',k:'しんぞう',r:'shinzou',c:'body'},
{v:'Não',t:'大腦',s:'大脑',p:'dànǎo',e:'Brain',j:'脳',k:'のう',r:'nou',c:'body'},

// ===== Quần áo =====
{v:'Áo',t:'衣服',s:'衣服',p:'yīfu',e:'Shirt',j:'シャツ',k:'シャツ',r:'shatsu',c:'cloth'},
{v:'Quần',t:'褲子',s:'裤子',p:'kùzi',e:'Pants',j:'ズボン',k:'ズボン',r:'zubon',c:'cloth'},
{v:'Váy',t:'裙子',s:'裙子',p:'qúnzi',e:'Skirt',j:'スカート',k:'スカート',r:'sukaato',c:'cloth'},
{v:'Giày',t:'鞋子',s:'鞋子',p:'xiézi',e:'Shoes',j:'靴',k:'くつ',r:'kutsu',c:'cloth'},
{v:'Mũ',t:'帽子',s:'帽子',p:'màozi',e:'Hat',j:'帽子',k:'ぼうし',r:'boushi',c:'cloth'},

// ===== Thời tiết =====
{v:'Mưa',t:'下雨',s:'下雨',p:'xiàyǔ',e:'Rain',j:'雨',k:'あめ',r:'ame',c:'weather'},
{v:'Nắng',t:'晴天',s:'晴天',p:'qíngtiān',e:'Sunny',j:'晴れ',k:'はれ',r:'hare',c:'weather'},
{v:'Tuyết',t:'雪',s:'雪',p:'xuě',e:'Snow',j:'雪',k:'ゆき',r:'yuki',c:'weather'},
{v:'Gió',t:'風',s:'风',p:'fēng',e:'Wind',j:'風',k:'かぜ',r:'kaze',c:'weather'},
{v:'Bão',t:'暴風雨',s:'暴风雨',p:'bàofēngyǔ',e:'Storm',j:'嵐',k:'あらし',r:'arashi',c:'weather'},

// ===== Phương tiện =====
{v:'Xe đạp',t:'自行車',s:'自行车',p:'zìxíngchē',e:'Bicycle',j:'自転車',k:'じてんしゃ',r:'jitensha',c:'transport'},
{v:'Xe máy',t:'摩托車',s:'摩托车',p:'mótuōchē',e:'Motorcycle',j:'バイク',k:'バイク',r:'baiku',c:'transport'},
{v:'Ô tô',t:'汽車',s:'汽车',p:'qìchē',e:'Car',j:'車',k:'くるま',r:'kuruma',c:'transport'},
{v:'Xe buýt',t:'公車',s:'公交车',p:'gōngjiāochē',e:'Bus',j:'バス',k:'バス',r:'basu',c:'transport'},
{v:'Tàu thủy',t:'船',s:'船',p:'chuán',e:'Ship',j:'船',k:'ふね',r:'fune',c:'transport'},

// ===== Nghề nghiệp =====
{v:'Bác sĩ',t:'醫生',s:'医生',p:'yīshēng',e:'Doctor',j:'医者',k:'いしゃ',r:'isha',c:'job'},
{v:'Giáo viên',t:'老師',s:'老师',p:'lǎoshī',e:'Teacher',j:'先生',k:'せんせい',r:'sensei',c:'job'},
{v:'Kỹ sư',t:'工程師',s:'工程师',p:'gōngchéngshī',e:'Engineer',j:'技術者',k:'ぎじゅつしゃ',r:'gijutsusha',c:'job'},
{v:'Cảnh sát',t:'警察',s:'警察',p:'jǐngchá',e:'Police',j:'警察',k:'けいさつ',r:'keisatsu',c:'job'},
{v:'Đầu bếp',t:'廚師',s:'厨师',p:'chúshī',e:'Chef',j:'料理人',k:'りょうりにん',r:'ryourinin',c:'job'},

// ===== Trường học =====
{v:'Học sinh',t:'學生',s:'学生',p:'xuéshēng',e:'Student',j:'学生',k:'がくせい',r:'gakusei',c:'school'},
{v:'Lớp học',t:'教室',s:'教室',p:'jiàoshì',e:'Classroom',j:'教室',k:'きょうしつ',r:'kyoushitsu',c:'school'},
{v:'Bảng',t:'黑板',s:'黑板',p:'hēibǎn',e:'Blackboard',j:'黒板',k:'こくばん',r:'kokuban',c:'school'},
{v:'Bút',t:'筆',s:'笔',p:'bǐ',e:'Pen',j:'ペン',k:'ペン',r:'pen',c:'school'},
{v:'Sách',t:'書',s:'书',p:'shū',e:'Book',j:'本',k:'ほん',r:'hon',c:'school'},,

{v:'Xin chào',t:'你好',s:'你好',p:'nǐ hǎo',e:'Hello',j:'こんにちは',k:'こんにちは',r:'konnichiwa',c:'greet'},
{v:'Cảm ơn',t:'謝謝',s:'谢谢',p:'xièxie',e:'Thank you',j:'ありがとう',k:'ありがとう',r:'arigatou',c:'greet'},
{v:'Xin lỗi',t:'對不起',s:'对不起',p:'duìbùqǐ',e:'Sorry',j:'すみません',k:'すみません',r:'sumimasen',c:'greet'},
{v:'Tạm biệt',t:'再見',s:'再见',p:'zàijiàn',e:'Goodbye',j:'さようなら',k:'さようなら',r:'sayounara',c:'greet'},
{v:'Vâng',t:'是的',s:'是的',p:'shì de',e:'Yes',j:'はい',k:'はい',r:'hai',c:'greet'},
{v:'Không',t:'不',s:'不',p:'bù',e:'No',j:'いいえ',k:'いいえ',r:'iie',c:'greet'},
{v:'Làm ơn',t:'請',s:'请',p:'qǐng',e:'Please',j:'お願いします',k:'おねがいします',r:'onegaishimasu',c:'greet'},
{v:'Không sao',t:'沒關係',s:'没关系',p:'méi guānxi',e:"It's okay",j:'大丈夫',k:'だいじょうぶ',r:'daijoubu',c:'greet'},
{v:'Chúc mừng',t:'恭喜',s:'恭喜',p:'gōngxǐ',e:'Congratulations',j:'おめでとう',k:'おめでとう',r:'omedetou',c:'greet'},
{v:'Tôi yêu bạn',t:'我愛你',s:'我爱你',p:'wǒ ài nǐ',e:'I love you',j:'愛してる',k:'あいしてる',r:'aishiteru',c:'greet'},

{v:'Một',t:'一',s:'一',p:'yī',e:'One',j:'一',k:'いち',r:'ichi',c:'num'},
{v:'Hai',t:'二',s:'二',p:'èr',e:'Two',j:'二',k:'に',r:'ni',c:'num'},
{v:'Ba',t:'三',s:'三',p:'sān',e:'Three',j:'三',k:'さん',r:'san',c:'num'},
{v:'Bốn',t:'四',s:'四',p:'sì',e:'Four',j:'四',k:'よん',r:'yon',c:'num'},
{v:'Năm',t:'五',s:'五',p:'wǔ',e:'Five',j:'五',k:'ご',r:'go',c:'num'},
{v:'Sáu',t:'六',s:'六',p:'liù',e:'Six',j:'六',k:'ろく',r:'roku',c:'num'},
{v:'Bảy',t:'七',s:'七',p:'qī',e:'Seven',j:'七',k:'なな',r:'nana',c:'num'},
{v:'Tám',t:'八',s:'八',p:'bā',e:'Eight',j:'八',k:'はち',r:'hachi',c:'num'},
{v:'Chín',t:'九',s:'九',p:'jiǔ',e:'Nine',j:'九',k:'きゅう',r:'kyuu',c:'num'},
{v:'Mười',t:'十',s:'十',p:'shí',e:'Ten',j:'十',k:'じゅう',r:'juu',c:'num'},
{v:'Hai mươi',t:'二十',s:'二十',p:'èrshí',e:'Twenty',j:'二十',k:'にじゅう',r:'nijuu',c:'num'},
{v:'Một trăm',t:'一百',s:'一百',p:'yìbǎi',e:'One hundred',j:'百',k:'ひゃく',r:'hyaku',c:'num'},

{v:'Gia đình',t:'家庭',s:'家庭',p:'jiātíng',e:'Family',j:'家族',k:'かぞく',r:'kazoku',c:'fam'},
{v:'Bố',t:'爸爸',s:'爸爸',p:'bàba',e:'Father',j:'父',k:'ちち',r:'chichi',c:'fam'},
{v:'Mẹ',t:'媽媽',s:'妈妈',p:'māma',e:'Mother',j:'母',k:'はは',r:'haha',c:'fam'},
{v:'Anh trai',t:'哥哥',s:'哥哥',p:'gēge',e:'Older brother',j:'兄',k:'あに',r:'ani',c:'fam'},
{v:'Em trai',t:'弟弟',s:'弟弟',p:'dìdi',e:'Younger brother',j:'弟',k:'おとうと',r:'otouto',c:'fam'},
{v:'Chị gái',t:'姐姐',s:'姐姐',p:'jiějie',e:'Older sister',j:'姉',k:'あね',r:'ane',c:'fam'},
{v:'Em gái',t:'妹妹',s:'妹妹',p:'mèimei',e:'Younger sister',j:'妹',k:'いもうと',r:'imouto',c:'fam'},
{v:'Ông',t:'爺爺',s:'爷爷',p:'yéye',e:'Grandfather',j:'祖父',k:'そふ',r:'sofu',c:'fam'},
{v:'Bà',t:'奶奶',s:'奶奶',p:'nǎinai',e:'Grandmother',j:'祖母',k:'そぼ',r:'sobo',c:'fam'},
{v:'Con cái',t:'孩子',s:'孩子',p:'háizi',e:'Children',j:'子供',k:'こども',r:'kodomo',c:'fam'},

{v:'Màu đỏ',t:'紅色',s:'红色',p:'hóngsè',e:'Red',j:'赤',k:'あか',r:'aka',c:'color'},
{v:'Màu xanh dương',t:'藍色',s:'蓝色',p:'lánsè',e:'Blue',j:'青',k:'あお',r:'ao',c:'color'},
{v:'Màu vàng',t:'黃色',s:'黄色',p:'huángsè',e:'Yellow',j:'黄色',k:'きいろ',r:'kiiro',c:'color'},
{v:'Màu xanh lá',t:'綠色',s:'绿色',p:'lǜsè',e:'Green',j:'緑',k:'みどり',r:'midori',c:'color'},
{v:'Màu trắng',t:'白色',s:'白色',p:'báisè',e:'White',j:'白',k:'しろ',r:'shiro',c:'color'},
{v:'Màu đen',t:'黑色',s:'黑色',p:'hēisè',e:'Black',j:'黒',k:'くろ',r:'kuro',c:'color'},
{v:'Màu tím',t:'紫色',s:'紫色',p:'zǐsè',e:'Purple',j:'紫',k:'むらさき',r:'murasaki',c:'color'},
{v:'Màu cam',t:'橙色',s:'橙色',p:'chéngsè',e:'Orange',j:'オレンジ色',k:'オレンジいろ',r:'orenji iro',c:'color'},
{v:'Màu hồng',t:'粉紅色',s:'粉红色',p:'fěnhóngsè',e:'Pink',j:'ピンク',k:'ピンク',r:'pinku',c:'color'},
{v:'Màu nâu',t:'棕色',s:'棕色',p:'zōngsè',e:'Brown',j:'茶色',k:'ちゃいろ',r:'chairo',c:'color'},

{v:'Hôm nay',t:'今天',s:'今天',p:'jīntiān',e:'Today',j:'今日',k:'きょう',r:'kyou',c:'time'},
{v:'Ngày mai',t:'明天',s:'明天',p:'míngtiān',e:'Tomorrow',j:'明日',k:'あした',r:'ashita',c:'time'},
{v:'Hôm qua',t:'昨天',s:'昨天',p:'zuótiān',e:'Yesterday',j:'昨日',k:'きのう',r:'kinou',c:'time'},
{v:'Thứ Hai',t:'星期一',s:'星期一',p:'xīngqīyī',e:'Monday',j:'月曜日',k:'げつようび',r:'getsuyoubi',c:'time'},
{v:'Thứ Ba',t:'星期二',s:'星期二',p:'xīngqīèr',e:'Tuesday',j:'火曜日',k:'かようび',r:'kayoubi',c:'time'},
{v:'Buổi sáng',t:'早上',s:'早上',p:'zǎoshang',e:'Morning',j:'朝',k:'あさ',r:'asa',c:'time'},
{v:'Buổi tối',t:'晚上',s:'晚上',p:'wǎnshang',e:'Evening',j:'夜',k:'よる',r:'yoru',c:'time'},
{v:'Tuần',t:'星期',s:'星期',p:'xīngqī',e:'Week',j:'週',k:'しゅう',r:'shuu',c:'time'},
{v:'Tháng',t:'月',s:'月',p:'yuè',e:'Month',j:'月',k:'つき',r:'tsuki',c:'time'},
{v:'Năm (year)',t:'年',s:'年',p:'nián',e:'Year',j:'年',k:'とし',r:'toshi',c:'time'},

{v:'Cơm',t:'米飯',s:'米饭',p:'mǐfàn',e:'Rice',j:'ご飯',k:'ごはん',r:'gohan',c:'food'},
{v:'Nước',t:'水',s:'水',p:'shuǐ',e:'Water',j:'水',k:'みず',r:'mizu',c:'food'},
{v:'Trà',t:'茶',s:'茶',p:'chá',e:'Tea',j:'お茶',k:'おちゃ',r:'ocha',c:'food'},
{v:'Cà phê',t:'咖啡',s:'咖啡',p:'kāfēi',e:'Coffee',j:'コーヒー',k:'コーヒー',r:'koohii',c:'food'},
{v:'Thịt',t:'肉',s:'肉',p:'ròu',e:'Meat',j:'肉',k:'にく',r:'niku',c:'food'},
{v:'Cá',t:'魚',s:'鱼',p:'yú',e:'Fish',j:'魚',k:'さかな',r:'sakana',c:'food'},
{v:'Rau',t:'蔬菜',s:'蔬菜',p:'shūcài',e:'Vegetable',j:'野菜',k:'やさい',r:'yasai',c:'food'},
{v:'Trái cây',t:'水果',s:'水果',p:'shuǐguǒ',e:'Fruit',j:'果物',k:'くだもの',r:'kudamono',c:'food'},
{v:'Bánh mì',t:'麵包',s:'面包',p:'miànbāo',e:'Bread',j:'パン',k:'パン',r:'pan',c:'food'},
{v:'Sữa',t:'牛奶',s:'牛奶',p:'niúnǎi',e:'Milk',j:'牛乳',k:'ぎゅうにゅう',r:'gyuunyuu',c:'food'},

{v:'Con chó',t:'狗',s:'狗',p:'gǒu',e:'Dog',j:'犬',k:'いぬ',r:'inu',c:'animal'},
{v:'Con mèo',t:'貓',s:'猫',p:'māo',e:'Cat',j:'猫',k:'ねこ',r:'neko',c:'animal'},
{v:'Con chim',t:'鳥',s:'鸟',p:'niǎo',e:'Bird',j:'鳥',k:'とり',r:'tori',c:'animal'},
{v:'Con voi',t:'大象',s:'大象',p:'dàxiàng',e:'Elephant',j:'象',k:'ぞう',r:'zou',c:'animal'},
{v:'Con hổ',t:'老虎',s:'老虎',p:'lǎohǔ',e:'Tiger',j:'虎',k:'とら',r:'tora',c:'animal'},
{v:'Con rồng',t:'龍',s:'龙',p:'lóng',e:'Dragon',j:'竜',k:'りゅう',r:'ryuu',c:'animal'},
{v:'Con ngựa',t:'馬',s:'马',p:'mǎ',e:'Horse',j:'馬',k:'うま',r:'uma',c:'animal'},
{v:'Con gà',t:'雞',s:'鸡',p:'jī',e:'Chicken',j:'鶏',k:'にわとり',r:'niwatori',c:'animal'},
{v:'Con khỉ',t:'猴子',s:'猴子',p:'hóuzi',e:'Monkey',j:'猿',k:'さる',r:'saru',c:'animal'},
{v:'Con rắn',t:'蛇',s:'蛇',p:'shé',e:'Snake',j:'蛇',k:'へび',r:'hebi',c:'animal'},

{v:'Ăn',t:'吃',s:'吃',p:'chī',e:'To eat',j:'食べる',k:'たべる',r:'taberu',c:'verb'},
{v:'Uống',t:'喝',s:'喝',p:'hē',e:'To drink',j:'飲む',k:'のむ',r:'nomu',c:'verb'},
{v:'Đi',t:'去',s:'去',p:'qù',e:'To go',j:'行く',k:'いく',r:'iku',c:'verb'},
{v:'Đến',t:'來',s:'来',p:'lái',e:'To come',j:'来る',k:'くる',r:'kuru',c:'verb'},
{v:'Ngủ',t:'睡覺',s:'睡觉',p:'shuìjiào',e:'To sleep',j:'寝る',k:'ねる',r:'neru',c:'verb'},
{v:'Nói',t:'說',s:'说',p:'shuō',e:'To speak',j:'話す',k:'はなす',r:'hanasu',c:'verb'},
{v:'Nghe',t:'聽',s:'听',p:'tīng',e:'To listen',j:'聞く',k:'きく',r:'kiku',c:'verb'},
{v:'Đọc',t:'讀',s:'读',p:'dú',e:'To read',j:'読む',k:'よむ',r:'yomu',c:'verb'},
{v:'Viết',t:'寫',s:'写',p:'xiě',e:'To write',j:'書く',k:'かく',r:'kaku',c:'verb'},
{v:'Học',t:'學習',s:'学习',p:'xuéxí',e:'To study',j:'勉強する',k:'べんきょうする',r:'benkyou suru',c:'verb'},

{v:'Đẹp',t:'漂亮',s:'漂亮',p:'piàoliang',e:'Beautiful',j:'美しい',k:'うつくしい',r:'utsukushii',c:'adj'},
{v:'Lớn',t:'大',s:'大',p:'dà',e:'Big',j:'大きい',k:'おおきい',r:'ookii',c:'adj'},
{v:'Nhỏ',t:'小',s:'小',p:'xiǎo',e:'Small',j:'小さい',k:'ちいさい',r:'chiisai',c:'adj'},
{v:'Nóng',t:'熱',s:'热',p:'rè',e:'Hot',j:'熱い',k:'あつい',r:'atsui',c:'adj'},
{v:'Lạnh',t:'冷',s:'冷',p:'lěng',e:'Cold',j:'寒い',k:'さむい',r:'samui',c:'adj'},
{v:'Nhanh',t:'快',s:'快',p:'kuài',e:'Fast',j:'速い',k:'はやい',r:'hayai',c:'adj'},
{v:'Chậm',t:'慢',s:'慢',p:'màn',e:'Slow',j:'遅い',k:'おそい',r:'osoi',c:'adj'},
{v:'Vui',t:'開心',s:'开心',p:'kāixīn',e:'Happy',j:'嬉しい',k:'うれしい',r:'ureshii',c:'adj'},
{v:'Buồn',t:'傷心',s:'伤心',p:'shāngxīn',e:'Sad',j:'悲しい',k:'かなしい',r:'kanashii',c:'adj'},
{v:'Khó',t:'難',s:'难',p:'nán',e:'Difficult',j:'難しい',k:'むずかしい',r:'muzukashii',c:'adj'},

// ===== Place (Nơi chốn) =====
{v:'Thư viện',t:'圖書館',s:'图书馆',p:'túshūguǎn',e:'Library',j:'図書館',k:'としょかん',r:'toshokan',c:'place'},
{v:'Bưu điện',t:'郵局',s:'邮局',p:'yóujú',e:'Post office',j:'郵便局',k:'ゆうびんきょく',r:'yuubinkyoku',c:'place'},
{v:'Ngân hàng',t:'銀行',s:'银行',p:'yínháng',e:'Bank',j:'銀行',k:'ぎんこう',r:'ginkou',c:'place'},
{v:'Hiệu thuốc',t:'藥局',s:'药店',p:'yàodiàn',e:'Pharmacy',j:'薬局',k:'やっきょく',r:'yakkyoku',c:'place'},
{v:'Tiệm bánh',t:'麵包店',s:'面包店',p:'miànbāodiàn',e:'Bakery',j:'パン屋',k:'パンや',r:'panya',c:'place'},
{v:'Siêu thị',t:'超市',s:'超市',p:'chāoshì',e:'Supermarket',j:'スーパー',k:'スーパー',r:'suupaa',c:'place'},
{v:'Trung tâm mua sắm',t:'購物中心',s:'购物中心',p:'gòuwù zhōngxīn',e:'Shopping mall',j:'ショッピングモール',k:'ショッピングモール',r:'shoppingu mooru',c:'place'},
{v:'Rạp chiếu phim',t:'電影院',s:'电影院',p:'diànyǐngyuàn',e:'Cinema',j:'映画館',k:'えいがかん',r:'eigakan',c:'place'},
{v:'Nhà hát',t:'劇院',s:'剧院',p:'jùyuàn',e:'Theater',j:'劇場',k:'げきじょう',r:'gekijou',c:'place'},
{v:'Sân vận động',t:'體育場',s:'体育场',p:'tǐyùchǎng',e:'Stadium',j:'スタジアム',k:'スタジアム',r:'sutajiamu',c:'place'},
{v:'Phòng tập thể dục',t:'健身房',s:'健身房',p:'jiànshēnfáng',e:'Gym',j:'ジム',k:'ジム',r:'jimu',c:'place'},
{v:'Hồ bơi',t:'游泳池',s:'游泳池',p:'yóuyǒngchí',e:'Swimming pool',j:'プール',k:'プール',r:'puuru',c:'place'},
{v:'Bãi biển',t:'海灘',s:'海滩',p:'hǎitān',e:'Beach',j:'海岸',k:'かいがん',r:'kaigan',c:'place'},
{v:'Đảo',t:'島',s:'岛',p:'dǎo',e:'Island',j:'島',k:'しま',r:'shima',c:'place'},
{v:'Núi',t:'山',s:'山',p:'shān',e:'Mountain',j:'山',k:'やま',r:'yama',c:'place'},
{v:'Đồi',t:'山丘',s:'山丘',p:'shānqiū',e:'Hill',j:'丘',k:'おか',r:'oka',c:'place'},
{v:'Thung lũng',t:'山谷',s:'山谷',p:'shāngǔ',e:'Valley',j:'谷',k:'たに',r:'tani',c:'place'},
{v:'Rừng',t:'森林',s:'森林',p:'sēnlín',e:'Forest',j:'森',k:'もり',r:'mori',c:'place'},
{v:'Sa mạc',t:'沙漠',s:'沙漠',p:'shāmò',e:'Desert',j:'砂漠',k:'さばく',r:'sabaku',c:'place'},
{v:'Hang động',t:'洞穴',s:'洞穴',p:'dòngxué',e:'Cave',j:'洞窟',k:'どうくつ',r:'doukutsu',c:'place'},
{v:'Thác nước',t:'瀑布',s:'瀑布',p:'pùbù',e:'Waterfall',j:'滝',k:'たき',r:'taki',c:'place'},
{v:'Sông',t:'河流',s:'河流',p:'héliú',e:'River',j:'川',k:'かわ',r:'kawa',c:'place'},
{v:'Hồ',t:'湖',s:'湖',p:'hú',e:'Lake',j:'湖',k:'みずうみ',r:'mizuumi',c:'place'},
{v:'Biển',t:'海',s:'海',p:'hǎi',e:'Sea',j:'海',k:'うみ',r:'umi',c:'place'},
{v:'Đại dương',t:'海洋',s:'海洋',p:'hǎiyáng',e:'Ocean',j:'海洋',k:'かいよう',r:'kaiyou',c:'place'},
{v:'Cầu',t:'橋',s:'桥',p:'qiáo',e:'Bridge',j:'橋',k:'はし',r:'hashi',c:'place'},
{v:'Đường',t:'道路',s:'道路',p:'dàolù',e:'Road',j:'道路',k:'どうろ',r:'douro',c:'place'},
{v:'Ngã tư',t:'十字路口',s:'十字路口',p:'shízìlùkǒu',e:'Crossroad',j:'交差点',k:'こうさてん',r:'kousaten',c:'place'},
{v:'Bãi đỗ xe',t:'停車場',s:'停车场',p:'tíngchēchǎng',e:'Parking lot',j:'駐車場',k:'ちゅうしゃじょう',r:'chuushajou',c:'place'},
{v:'Khách sạn',t:'飯店',s:'饭店',p:'fàndiàn',e:'Hotel',j:'ホテル',k:'ホテル',r:'hoteru',c:'place'},
{v:'Nhà nghỉ',t:'旅館',s:'旅馆',p:'lǚguǎn',e:'Inn',j:'旅館',k:'りょかん',r:'ryokan',c:'place'},
{v:'Quán cà phê',t:'咖啡館',s:'咖啡馆',p:'kāfēiguǎn',e:'Cafe',j:'喫茶店',k:'きっさてん',r:'kissaten',c:'place'},
{v:'Quán ăn',t:'小吃店',s:'小吃店',p:'xiǎochīdiàn',e:'Eatery',j:'食堂',k:'しょくどう',r:'shokudou',c:'place'},
{v:'Đồn cảnh sát',t:'警察局',s:'警察局',p:'jǐngchájú',e:'Police station',j:'警察署',k:'けいさつしょ',r:'keisatsusho',c:'place'},
{v:'Trạm cứu hỏa',t:'消防局',s:'消防局',p:'xiāofángjú',e:'Fire station',j:'消防署',k:'しょうぼうしょ',r:'shoubousho',c:'place'},
{v:'Tòa thị chính',t:'市政府',s:'市政府',p:'shìzhèngfǔ',e:'City hall',j:'市役所',k:'しやくしょ',r:'shiyakusho',c:'place'},
{v:'Văn phòng',t:'辦公室',s:'办公室',p:'bàngōngshì',e:'Office',j:'事務所',k:'じむしょ',r:'jimusho',c:'place'},
{v:'Nhà máy',t:'工廠',s:'工厂',p:'gōngchǎng',e:'Factory',j:'工場',k:'こうじょう',r:'koujou',c:'place'},
{v:'Kho hàng',t:'倉庫',s:'仓库',p:'cāngkù',e:'Warehouse',j:'倉庫',k:'そうこ',r:'souko',c:'place'},
{v:'Nông trại',t:'農場',s:'农场',p:'nóngchǎng',e:'Farm',j:'農場',k:'のうじょう',r:'noujou',c:'place'},
{v:'Vườn',t:'花園',s:'花园',p:'huāyuán',e:'Garden',j:'庭',k:'にわ',r:'niwa',c:'place'},
{v:'Sở thú',t:'動物園',s:'动物园',p:'dòngwùyuán',e:'Zoo',j:'動物園',k:'どうぶつえん',r:'doubutsuen',c:'place'},
{v:'Thủy cung',t:'水族館',s:'水族馆',p:'shuǐzúguǎn',e:'Aquarium',j:'水族館',k:'すいぞくかん',r:'suizokukan',c:'place'},
{v:'Đền',t:'寺廟',s:'寺庙',p:'sìmiào',e:'Temple',j:'寺',k:'てら',r:'tera',c:'place'},
{v:'Chùa',t:'佛寺',s:'佛寺',p:'fósì',e:'Buddhist temple',j:'お寺',k:'おてら',r:'otera',c:'place'},
{v:'Nhà thờ',t:'教堂',s:'教堂',p:'jiàotáng',e:'Church',j:'教会',k:'きょうかい',r:'kyoukai',c:'place'},
{v:'Nhà ga tàu điện ngầm',t:'地鐵站',s:'地铁站',p:'dìtiězhàn',e:'Subway station',j:'地下鉄駅',k:'ちかてつえき',r:'chikatetsu eki',c:'place'},
{v:'Bến xe buýt',t:'公車站',s:'公交车站',p:'gōngjiāochēzhàn',e:'Bus stop',j:'バス停',k:'バスてい',r:'basutei',c:'place'},
{v:'Cảng biển',t:'港口',s:'港口',p:'gǎngkǒu',e:'Harbor',j:'港',k:'みなと',r:'minato',c:'place'},
{v:'Bến phà',t:'渡口',s:'渡口',p:'dùkǒu',e:'Ferry terminal',j:'フェリー乗り場',k:'フェリーのりば',r:'ferii noriba',c:'place'},

{v:'Nhà',t:'家',s:'家',p:'jiā',e:'Home',j:'家',k:'いえ',r:'ie',c:'place'},
{v:'Trường học',t:'學校',s:'学校',p:'xuéxiào',e:'School',j:'学校',k:'がっこう',r:'gakkou',c:'place'},
{v:'Bệnh viện',t:'醫院',s:'医院',p:'yīyuàn',e:'Hospital',j:'病院',k:'びょういん',r:'byouin',c:'place'},
{v:'Chợ',t:'市場',s:'市场',p:'shìchǎng',e:'Market',j:'市場',k:'いちば',r:'ichiba',c:'place'},
{v:'Sân bay',t:'機場',s:'机场',p:'jīchǎng',e:'Airport',j:'空港',k:'くうこう',r:'kuukou',c:'place'},
{v:'Ga tàu',t:'火車站',s:'火车站',p:'huǒchēzhàn',e:'Train station',j:'駅',k:'えき',r:'eki',c:'place'},
{v:'Công viên',t:'公園',s:'公园',p:'gōngyuán',e:'Park',j:'公園',k:'こうえん',r:'kouen',c:'place'},
{v:'Nhà hàng',t:'餐廳',s:'餐厅',p:'cāntīng',e:'Restaurant',j:'レストラン',k:'レストラン',r:'resutoran',c:'place'},
{v:'Thành phố',t:'城市',s:'城市',p:'chéngshì',e:'City',j:'都市',k:'とし',r:'toshi',c:'place'},
{v:'Đất nước',t:'國家',s:'国家',p:'guójiā',e:'Country',j:'国',k:'くに',r:'kuni',c:'place'},

// ===== Greeting =====
{v:'Chào buổi sáng',t:'早安',s:'早安',p:'zǎo ān',e:'Good morning',j:'おはよう',k:'おはよう',r:'ohayou',c:'greet'},
{v:'Chúc ngủ ngon',t:'晚安',s:'晚安',p:'wǎn ān',e:'Good night',j:'おやすみ',k:'おやすみ',r:'oyasumi',c:'greet'},
{v:'Hẹn gặp lại',t:'回頭見',s:'回头见',p:'huítóu jiàn',e:'See you later',j:'またね',k:'またね',r:'matane',c:'greet'},
{v:'Rất vui được gặp bạn',t:'很高興認識你',s:'很高兴认识你',p:'hěn gāoxìng rènshi nǐ',e:'Nice to meet you',j:'はじめまして',k:'はじめまして',r:'hajimemashite',c:'greet'},
{v:'Chào mừng',t:'歡迎',s:'欢迎',p:'huānyíng',e:'Welcome',j:'ようこそ',k:'ようこそ',r:'youkoso',c:'greet'},

// ===== Number =====
{v:'Mười một',t:'十一',s:'十一',p:'shí yī',e:'Eleven',j:'十一',k:'じゅういち',r:'juuichi',c:'num'},
{v:'Mười hai',t:'十二',s:'十二',p:'shí èr',e:'Twelve',j:'十二',k:'じゅうに',r:'juuni',c:'num'},
{v:'Ba mươi',t:'三十',s:'三十',p:'sānshí',e:'Thirty',j:'三十',k:'さんじゅう',r:'sanjuu',c:'num'},
{v:'Năm mươi',t:'五十',s:'五十',p:'wǔshí',e:'Fifty',j:'五十',k:'ごじゅう',r:'gojuu',c:'num'},
{v:'Một nghìn',t:'一千',s:'一千',p:'yìqiān',e:'One thousand',j:'千',k:'せん',r:'sen',c:'num'},

// ===== Family =====
{v:'Chồng',t:'丈夫',s:'丈夫',p:'zhàngfu',e:'Husband',j:'夫',k:'おっと',r:'otto',c:'fam'},
{v:'Vợ',t:'妻子',s:'妻子',p:'qīzi',e:'Wife',j:'妻',k:'つま',r:'tsuma',c:'fam'},
{v:'Cháu',t:'孫子',s:'孙子',p:'sūnzi',e:'Grandchild',j:'孫',k:'まご',r:'mago',c:'fam'},
{v:'Chú',t:'叔叔',s:'叔叔',p:'shūshu',e:'Uncle',j:'叔父',k:'おじ',r:'oji',c:'fam'},
{v:'Cô',t:'阿姨',s:'阿姨',p:'āyí',e:'Aunt',j:'叔母',k:'おば',r:'oba',c:'fam'},

// ===== Color =====
{v:'Màu xám',t:'灰色',s:'灰色',p:'huīsè',e:'Gray',j:'灰色',k:'はいいろ',r:'haiiro',c:'color'},
{v:'Màu bạc',t:'銀色',s:'银色',p:'yínsè',e:'Silver',j:'銀色',k:'ぎんいろ',r:'giniro',c:'color'},
{v:'Màu vàng kim',t:'金色',s:'金色',p:'jīnsè',e:'Gold',j:'金色',k:'きんいろ',r:'kiniro',c:'color'},
{v:'Nhiều màu',t:'彩色',s:'彩色',p:'cǎisè',e:'Colorful',j:'カラフル',k:'カラフル',r:'karafuru',c:'color'},
{v:'Trong suốt',t:'透明',s:'透明',p:'tòumíng',e:'Transparent',j:'透明',k:'とうめい',r:'toumei',c:'color'},

// ===== Time =====
{v:'Hôm kia',t:'前天',s:'前天',p:'qiántiān',e:'The day before yesterday',j:'一昨日',k:'おととい',r:'ototoi',c:'time'},
{v:'Ngày kia',t:'後天',s:'后天',p:'hòutiān',e:'The day after tomorrow',j:'明後日',k:'あさって',r:'asatte',c:'time'},
{v:'Buổi trưa',t:'中午',s:'中午',p:'zhōngwǔ',e:'Noon',j:'昼',k:'ひる',r:'hiru',c:'time'},
{v:'Đêm',t:'夜晚',s:'夜晚',p:'yèwǎn',e:'Night',j:'夜',k:'よる',r:'yoru',c:'time'},
{v:'Giờ',t:'小時',s:'小时',p:'xiǎoshí',e:'Hour',j:'時間',k:'じかん',r:'jikan',c:'time'},

// ===== Food =====
{v:'Trứng',t:'雞蛋',s:'鸡蛋',p:'jīdàn',e:'Egg',j:'卵',k:'たまご',r:'tamago',c:'food'},
{v:'Mì',t:'麵條',s:'面条',p:'miàntiáo',e:'Noodles',j:'麺',k:'めん',r:'men',c:'food'},
{v:'Canh',t:'湯',s:'汤',p:'tāng',e:'Soup',j:'スープ',k:'スープ',r:'suupu',c:'food'},
{v:'Đường',t:'糖',s:'糖',p:'táng',e:'Sugar',j:'砂糖',k:'さとう',r:'satou',c:'food'},
{v:'Muối',t:'鹽',s:'盐',p:'yán',e:'Salt',j:'塩',k:'しお',r:'shio',c:'food'},
{v:'Bơ',t:'奶油',s:'奶油',p:'nǎiyóu',e:'Butter',j:'バター',k:'バター',r:'bataa',c:'food'},
{v:'Phô mai',t:'起司',s:'奶酪',p:'nǎilào',e:'Cheese',j:'チーズ',k:'チーズ',r:'chiizu',c:'food'},

// ===== Animal =====
{v:'Con bò',t:'牛',s:'牛',p:'niú',e:'Cow',j:'牛',k:'うし',r:'ushi',c:'animal'},
{v:'Con lợn',t:'豬',s:'猪',p:'zhū',e:'Pig',j:'豚',k:'ぶた',r:'buta',c:'animal'},
{v:'Con cừu',t:'羊',s:'羊',p:'yáng',e:'Sheep',j:'羊',k:'ひつじ',r:'hitsuji',c:'animal'},
{v:'Con dê',t:'山羊',s:'山羊',p:'shānyáng',e:'Goat',j:'山羊',k:'やぎ',r:'yagi',c:'animal'},
{v:'Con thỏ',t:'兔子',s:'兔子',p:'tùzi',e:'Rabbit',j:'兎',k:'うさぎ',r:'usagi',c:'animal'},
{v:'Con cá',t:'魚',s:'鱼',p:'yú',e:'Fish',j:'魚',k:'さかな',r:'sakana',c:'animal'},
{v:'Con cá sấu',t:'鱷魚',s:'鳄鱼',p:'èyú',e:'Crocodile',j:'ワニ',k:'わに',r:'wani',c:'animal'},
{v:'Con gấu',t:'熊',s:'熊',p:'xióng',e:'Bear',j:'熊',k:'くま',r:'kuma',c:'animal'},
{v:'Con sói',t:'狼',s:'狼',p:'láng',e:'Wolf',j:'狼',k:'おおかみ',r:'ookami',c:'animal'},
{v:'Con cáo',t:'狐狸',s:'狐狸',p:'húli',e:'Fox',j:'狐',k:'きつね',r:'kitsune',c:'animal'},

// ===== Verb =====
{v:'Mở',t:'打開',s:'打开',p:'dǎkāi',e:'To open',j:'開ける',k:'あける',r:'akeru',c:'verb'},
{v:'Đóng',t:'關',s:'关',p:'guān',e:'To close',j:'閉める',k:'しめる',r:'shimeru',c:'verb'},
{v:'Chạy',t:'跑',s:'跑',p:'pǎo',e:'To run',j:'走る',k:'はしる',r:'hashiru',c:'verb'},
{v:'Đi bộ',t:'走路',s:'走路',p:'zǒulù',e:'To walk',j:'歩く',k:'あるく',r:'aruku',c:'verb'},
{v:'Bơi',t:'游泳',s:'游泳',p:'yóuyǒng',e:'To swim',j:'泳ぐ',k:'およぐ',r:'oyogu',c:'verb'},
{v:'Mua',t:'買',s:'买',p:'mǎi',e:'To buy',j:'買う',k:'かう',r:'kau',c:'verb'},
{v:'Bán',t:'賣',s:'卖',p:'mài',e:'To sell',j:'売る',k:'うる',r:'uru',c:'verb'},
{v:'Làm việc',t:'工作',s:'工作',p:'gōngzuò',e:'To work',j:'働く',k:'はたらく',r:'hataraku',c:'verb'},
{v:'Chơi',t:'玩',s:'玩',p:'wán',e:'To play',j:'遊ぶ',k:'あそぶ',r:'asobu',c:'verb'},
{v:'Xem',t:'看',s:'看',p:'kàn',e:'To watch',j:'見る',k:'みる',r:'miru',c:'verb'},

// ===== Adjective =====
{v:'Mới',t:'新',s:'新',p:'xīn',e:'New',j:'新しい',k:'あたらしい',r:'atarashii',c:'adj'},
{v:'Cũ',t:'舊',s:'旧',p:'jiù',e:'Old',j:'古い',k:'ふるい',r:'furui',c:'adj'},
{v:'Dễ',t:'容易',s:'容易',p:'róngyì',e:'Easy',j:'簡単',k:'かんたん',r:'kantan',c:'adj'},
{v:'Cao',t:'高',s:'高',p:'gāo',e:'Tall',j:'高い',k:'たかい',r:'takai',c:'adj'},
{v:'Thấp',t:'低',s:'低',p:'dī',e:'Low',j:'低い',k:'ひくい',r:'hikui',c:'adj'},
{v:'Dài',t:'長',s:'长',p:'cháng',e:'Long',j:'長い',k:'ながい',r:'nagai',c:'adj'},
{v:'Ngắn',t:'短',s:'短',p:'duǎn',e:'Short',j:'短い',k:'みじかい',r:'mijikai',c:'adj'},
{v:'Đắt',t:'貴',s:'贵',p:'guì',e:'Expensive',j:'高い',k:'たかい',r:'takai',c:'adj'},
{v:'Rẻ',t:'便宜',s:'便宜',p:'piányi',e:'Cheap',j:'安い',k:'やすい',r:'yasui',c:'adj'},
{v:'Mạnh',t:'強',s:'强',p:'qiáng',e:'Strong',j:'強い',k:'つよい',r:'tsuyoi',c:'adj'},

// ===== Place =====
{v:'Ngân hàng',t:'銀行',s:'银行',p:'yínháng',e:'Bank',j:'銀行',k:'ぎんこう',r:'ginkou',c:'place'},
{v:'Bưu điện',t:'郵局',s:'邮局',p:'yóujú',e:'Post office',j:'郵便局',k:'ゆうびんきょく',r:'yuubinkyoku',c:'place'},
{v:'Khách sạn',t:'飯店',s:'饭店',p:'fàndiàn',e:'Hotel',j:'ホテル',k:'ホテル',r:'hoteru',c:'place'},
{v:'Hiệu sách',t:'書店',s:'书店',p:'shūdiàn',e:'Bookstore',j:'本屋',k:'ほんや',r:'honya',c:'place'},
{v:'Siêu thị',t:'超市',s:'超市',p:'chāoshì',e:'Supermarket',j:'スーパー',k:'スーパー',r:'suupaa',c:'place'},
{v:'Thư viện',t:'圖書館',s:'图书馆',p:'túshūguǎn',e:'Library',j:'図書館',k:'としょかん',r:'toshokan',c:'place'},
{v:'Nhà vệ sinh',t:'洗手間',s:'洗手间',p:'xǐshǒujiān',e:'Restroom',j:'トイレ',k:'トイレ',r:'toire',c:'place'},
{v:'Bãi biển',t:'海灘',s:'海滩',p:'hǎitān',e:'Beach',j:'海',k:'うみ',r:'umi',c:'place'},
{v:'Núi',t:'山',s:'山',p:'shān',e:'Mountain',j:'山',k:'やま',r:'yama',c:'place'},
{v:'Sông',t:'河流',s:'河流',p:'héliú',e:'River',j:'川',k:'かわ',r:'kawa',c:'place'},

];

/* ============== HELPERS ============== */
function stripDiacritics(str){
  return str.normalize('NFD').replace(/[\u0300-\u036f]/g,'').toLowerCase();
}
function norm(str){ return stripDiacritics((str||'').trim()); }

function speak(text, lang){
  if(!('speechSynthesis' in window)){ alert('Trình duyệt của bạn không hỗ trợ phát âm (Web Speech API).'); return; }
  window.speechSynthesis.cancel();
  const u = new SpeechSynthesisUtterance(text);
  u.lang = lang;
  u.rate = 0.9;
  window.speechSynthesis.speak(u);
}
const LANGMAP = { v:'vi-VN', t:'zh-TW', s:'zh-CN', e:'en-US', j:'ja-JP' };
const LANGNAME = { v:'Tiếng Việt', t:'Trung (Phồn thể)', s:'Trung (Giản thể)', e:'Tiếng Anh', j:'Tiếng Nhật' };

function textFor(entry, key){
  if(key==='j') return entry.j;
  return entry[key];
}

/* ============== CHIPS & SEARCH ============== */
const chipsEl = document.getElementById('chips');
let activeCat = null;
Object.keys(CATS).forEach(key=>{
  const c = document.createElement('div');
  c.className='chip';
  c.textContent = CATS[key];
  c.onclick = ()=>{ activeCat = (activeCat===key)? null : key; renderChips(); runFilter(); };
  c.dataset.cat = key;
  chipsEl.appendChild(c);
});
function renderChips(){
  [...chipsEl.children].forEach(c=> c.classList.toggle('active', c.dataset.cat===activeCat));
}

const searchInput = document.getElementById('searchInput');
searchInput.addEventListener('keydown', e=>{ if(e.key==='Enter') performSearch(); });
searchInput.addEventListener('input', ()=>{ if(searchInput.value.trim()==='') runFilter(); });

function performSearch(){ runFilter(); }

function runFilter(){
  const q = norm(searchInput.value);
  let list = DATA;
  if(activeCat) list = list.filter(d=>d.c===activeCat);
  if(q){
    list = list.filter(d=>{
      return [d.v,d.t,d.s,d.p,d.e,d.j,d.k,d.r].some(field=> norm(field||'').includes(q));
    });
  }
  renderResults(list, !!q || !!activeCat);
}

function renderResults(list, active){
  const grid = document.getElementById('cardGrid');
  const empty = document.getElementById('emptyState');
  const countEl = document.getElementById('resultsCount');
  grid.innerHTML = '';
  if(!active){
    empty.style.display='block'; countEl.style.display='none'; return;
  }
  if(list.length===0){
    empty.style.display='block'; empty.textContent='Không tìm thấy từ nào khớp hoặc chưa bổ sung từ. Thử một từ khác nhé.';
    countEl.style.display='none'; return;
  }
  empty.style.display='none';
  countEl.style.display='block';
  countEl.textContent = `Tìm thấy ${list.length} từ`;
  list.forEach(d=>{
    const card = document.createElement('div');
    card.className='word-card';
    card.innerHTML = `
      <div class="cat-tag">${CATS[d.c]}</div>
      <div class="lang-block">
        <div class="lang-label">Tiếng Việt</div>
        <div class="lang-main">${d.v}</div>
        <button class="play-btn" onclick="speak('${escAttr(d.v)}','vi-VN')">🔊</button>
      </div>
      <div class="lang-block">
        <div class="lang-label">Trung (Phồn / Giản)</div>
        <div class="lang-main">${d.t} ／ ${d.s}</div>
        <div class="lang-sub">${d.p}</div>
        <button class="play-btn" onclick="speak('${escAttr(d.t)}','zh-TW')">🔊</button>
      </div>
      <div class="lang-block">
        <div class="lang-label">Tiếng Anh</div>
        <div class="lang-main">${d.e}</div>
        <button class="play-btn" onclick="speak('${escAttr(d.e)}','en-US')">🔊</button>
      </div>
      <div class="lang-block">
        <div class="lang-label">Tiếng Nhật</div>
        <div class="lang-main">${d.j}</div>
        <div class="lang-sub">${d.k} · ${d.r}</div>
        <button class="play-btn" onclick="speak('${escAttr(d.j)}','ja-JP')">🔊</button>
      </div>
    `;
    grid.appendChild(card);
  });
}
function escAttr(s){ return (s||'').replace(/'/g,"\\'"); }

/* ============== TABS ============== */
document.querySelectorAll('.tab').forEach(tab=>{
  tab.onclick = ()=>{
    document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
    document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
    tab.classList.add('active');
    document.getElementById('panel-'+tab.dataset.tab).classList.add('active');
  };
});

/* ============== FLASHCARDS ============== */
const flashCatSel = document.getElementById('flashCat');
const speakCatSel = document.getElementById('speakCat');
[flashCatSel, speakCatSel].forEach(sel=>{
  const optAll = document.createElement('option'); optAll.value=''; optAll.textContent='Tất cả chủ đề';
  sel.appendChild(optAll);
  Object.keys(CATS).forEach(k=>{
    const o = document.createElement('option'); o.value=k; o.textContent=CATS[k]; sel.appendChild(o);
  });
});

let flashPool = [...DATA];
let flashCurrent = null;
let flashKnown = 0, flashReview = 0;

function poolFor(catValue){
  return catValue? DATA.filter(d=>d.c===catValue) : DATA;
}
function pickRandom(pool){ return pool[Math.floor(Math.random()*pool.length)]; }

function nextFlash(){
  flashPool = poolFor(flashCatSel.value);
  flashCurrent = pickRandom(flashPool);
  const card = document.getElementById('flashcard');
  card.classList.remove('flipped');
  const frontKey = document.getElementById('flashFront').value;
  document.getElementById('flashFrontText').textContent = textFor(flashCurrent, frontKey);
  document.getElementById('flashBack').innerHTML = `
    <div class="back-row"><span class="back-lbl">Việt</span><span>${flashCurrent.v}</span></div>
    <div class="back-row"><span class="back-lbl">Phồn thể</span><span>${flashCurrent.t}</span></div>
    <div class="back-row"><span class="back-lbl">Giản thể</span><span>${flashCurrent.s}</span></div>
    <div class="back-row"><span class="back-lbl">Pinyin</span><span>${flashCurrent.p}</span></div>
    <div class="back-row"><span class="back-lbl">Anh</span><span>${flashCurrent.e}</span></div>
    <div class="back-row"><span class="back-lbl">Nhật</span><span>${flashCurrent.j} (${flashCurrent.k})</span></div>
  `;
}
function flipCard(){ document.getElementById('flashcard').classList.toggle('flipped'); }
function markFlash(known){
  if(known) flashKnown++; else flashReview++;
  document.getElementById('flashScore').textContent = `Đã thuộc: ${flashKnown} · Cần ôn lại: ${flashReview}`;
  nextFlash();
}
flashCatSel.onchange = nextFlash;
document.getElementById('flashFront').onchange = ()=>{
  document.getElementById('flashFrontText').textContent = textFor(flashCurrent, document.getElementById('flashFront').value);
};

/* ============== LISTENING PRACTICE ============== */
let listenCurrent = null;
let listenScore = 0, listenTotal = 0;

function newListenQuestion(){
  document.getElementById('listenFeedback').textContent='';
  listenCurrent = pickRandom(DATA);
  const fromKey = document.getElementById('listenFrom').value;
  const toKey = document.getElementById('listenTo').value;
  // build options: correct + 3 distractors, prefer same category
  let sameCat = DATA.filter(d=>d.c===listenCurrent.c && d!==listenCurrent);
  let others = DATA.filter(d=>d!==listenCurrent && !sameCat.includes(d));
  let distractors = [];
  const pool1 = [...sameCat];
  while(distractors.length<3 && pool1.length){
    distractors.push(pool1.splice(Math.floor(Math.random()*pool1.length),1)[0]);
  }
  const pool2 = [...others];
  while(distractors.length<3 && pool2.length){
    distractors.push(pool2.splice(Math.floor(Math.random()*pool2.length),1)[0]);
  }
  const optionEntries = shuffle([listenCurrent, ...distractors]);
  const optsEl = document.getElementById('listenOptions');
  optsEl.innerHTML='';
  optionEntries.forEach(entry=>{
    const btn = document.createElement('div');
    btn.className='option';
    btn.textContent = textFor(entry, toKey);
    btn.onclick = ()=> checkListen(entry===listenCurrent, btn);
    optsEl.appendChild(btn);
  });
  // auto play once loaded
  setTimeout(playListenAudio, 250);
}
function shuffle(arr){ return arr.map(v=>[Math.random(),v]).sort((a,b)=>a[0]-b[0]).map(v=>v[1]); }

function playListenAudio(){
  if(!listenCurrent) newListenQuestion();
  const fromKey = document.getElementById('listenFrom').value;
  speak(textFor(listenCurrent, fromKey), LANGMAP[fromKey]);
}
function checkListen(isCorrect, btnEl){
  listenTotal++;
  if(isCorrect){
    listenScore++;
    btnEl.classList.add('correct');
    document.getElementById('listenFeedback').textContent='✓ Chính xác!';
    document.getElementById('listenFeedback').style.color='var(--jade)';
  } else {
    btnEl.classList.add('wrong');
    document.getElementById('listenFeedback').textContent = '✗ Chưa đúng — đáp án là: ' + textFor(listenCurrent, document.getElementById('listenTo').value);
    document.getElementById('listenFeedback').style.color='var(--lacquer)';
  }
  document.getElementById('listenScore').textContent = `Điểm: ${listenScore} / ${listenTotal}`;
  [...document.getElementById('listenOptions').children].forEach(o=>o.onclick=null);
  setTimeout(newListenQuestion, 1400);
}
document.getElementById('listenFrom').onchange = newListenQuestion;
document.getElementById('listenTo').onchange = newListenQuestion;

/* ============== SPEAKING PRACTICE ============== */
let speakCurrent = null;
const SpeechRecognitionCtor = window.SpeechRecognition || window.webkitSpeechRecognition;

function newSpeakWord(){
  speakCurrent = pickRandom(poolFor(speakCatSel.value));
  const langKey = document.getElementById('speakLang').value;
  document.getElementById('speakTarget').textContent = textFor(speakCurrent, langKey);
  document.getElementById('speakSub').textContent = `${LANGNAME[langKey]} · Nghĩa tiếng Việt: ${speakCurrent.v}`;
  buildSpeakArea();
}
function playSpeakReference(){
  const langKey = document.getElementById('speakLang').value;
  speak(textFor(speakCurrent, langKey), LANGMAP[langKey]);
}
function buildSpeakArea(){
  const area = document.getElementById('speakArea');
  if(!SpeechRecognitionCtor){
    area.innerHTML = `<div class="not-supported">Trình duyệt này không hỗ trợ nhận diện giọng nói (Speech Recognition). Bạn vẫn có thể nghe phát âm mẫu và tự luyện nói theo. Gợi ý: dùng Google Chrome trên máy tính hoặc Android.</div>`;
    return;
  }
  area.innerHTML = `
    <button class="mic-btn" id="micBtn" onclick="toggleRecording()">🎙️</button>
    <div style="font-size:13px;color:var(--ink-soft);">Nhấn micro, đọc to từ trên, rồi xem kết quả nhận diện.</div>
    <div class="heard" id="heardResult"></div>
  `;
}
let recognizing = false, recognizer = null;
function toggleRecording(){
  if(!SpeechRecognitionCtor) return;
  const micBtn = document.getElementById('micBtn');
  if(recognizing){ recognizer && recognizer.stop(); return; }
  const langKey = document.getElementById('speakLang').value;
  recognizer = new SpeechRecognitionCtor();
  recognizer.lang = LANGMAP[langKey];
  recognizer.interimResults = false;
  recognizer.maxAlternatives = 1;
  recognizer.onstart = ()=>{ recognizing=true; micBtn.classList.add('recording'); document.getElementById('heardResult').textContent=''; };
  recognizer.onend = ()=>{ recognizing=false; micBtn.classList.remove('recording'); };
  recognizer.onerror = (e)=>{
    recognizing=false; micBtn.classList.remove('recording');
    document.getElementById('heardResult').innerHTML = `<span style="color:var(--lacquer)">Không nhận diện được (${e.error}). Hãy thử lại hoặc kiểm tra quyền micro.</span>`;
  };
  recognizer.onresult = (event)=>{
    const transcript = event.results[0][0].transcript;
    const langKey2 = document.getElementById('speakLang').value;
    const target = textFor(speakCurrent, langKey2);
    const isMatch = compareSpeech(transcript, target);
    let verdict;
    if(isMatch==='full') verdict = `<span style="color:var(--jade)">✓ Chính xác!</span>`;
    else if(isMatch==='close') verdict = `<span style="color:var(--gold)">≈ Gần đúng, cố lên!</span>`;
    else verdict = `<span style="color:var(--lacquer)">✗ Chưa khớp, thử lại nhé.</span>`;
    document.getElementById('heardResult').innerHTML = `Bạn nói: <b>${transcript}</b><br>${verdict}`;
  };
  recognizer.start();
}
function compareSpeech(heard, target){
  const h = norm(heard).replace(/[^\p{L}\p{N}]+/gu,'');
  const t = norm(target).replace(/[^\p{L}\p{N}]+/gu,'');
  if(!h) return 'none';
  if(h===t) return 'full';
  if(h.includes(t) || t.includes(h)) return 'close';
  return 'none';
}
speakCatSel.onchange = newSpeakWord;
document.getElementById('speakLang').onchange = newSpeakWord;

/* ============== INIT ============== */
nextFlash();
newListenQuestion();
newSpeakWord();
</script>
</body>
</html>
