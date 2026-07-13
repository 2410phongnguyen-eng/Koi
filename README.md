<!DOCTYPE html>
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
  food:'Đồ ăn & thức uống', animal:'Động vật', verb:'Động từ', adj:'Tính từ', place:'Nơi chốn'
};

const DATA = [
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
    empty.style.display='block'; empty.textContent='Không tìm thấy từ nào khớp. Thử một từ khác nhé.';
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
