<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Бриф на монтаж відео — ONEREYN</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,600;9..144,700&family=Inter:wght@400;500;600;700&family=Space+Mono:wght@400;700&family=Montserrat:wght@600;700&family=Unbounded:wght@600;700&family=Golos+Text:wght@500;700&family=PT+Serif:wght@400;700&family=Playfair+Display:wght@600;700&family=Comfortaa:wght@600;700&family=Rubik:wght@500;700&family=Oswald:wght@500;700&family=Marck+Script&family=Caveat:wght@600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg-void:#0A0A0A;
    --bg-panel:#161616;
    --bg-panel-2:#1F1F1F;
    --ink:#FFFFFF;
    --ink-dim:#9A9A9A;
    --ink-faint:#545454;
    --rec-red:#BE1712;
    --amber:#FFFFFF;
    --line:#2C2C2C;
    --radius:10px;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--bg-void);
    color:var(--ink);
    font-family:'Inter',sans-serif;
    min-height:100vh;
    -webkit-font-smoothing:antialiased;
  }
  .mono{font-family:'Space Mono',monospace;}
  .app{max-width:840px;margin:0 auto;padding:0 20px 60px;}

  /* ---------- Masthead ---------- */
  .masthead{
    display:flex;align-items:center;justify-content:space-between;
    padding:22px 0 16px;border-bottom:1px solid var(--line);
    margin-bottom:22px;
  }
  .mast-left{display:flex;align-items:center;gap:9px;}
  .mast-logo{width:26px;height:26px;flex:0 0 auto;}
  .mast-brand{font-family:'Space Mono',monospace;font-size:11px;letter-spacing:.14em;color:var(--rec-red);}
  .rec-dot{width:8px;height:8px;border-radius:50%;background:var(--rec-red);box-shadow:0 0 8px var(--rec-red);animation:pulse 1.8s ease-in-out infinite;}
  @media (prefers-reduced-motion:reduce){.rec-dot{animation:none;}}
  @keyframes pulse{0%,100%{opacity:1;}50%{opacity:.35;}}
  .masthead h1{
    font-family:'Fraunces',serif;font-weight:700;font-size:19px;letter-spacing:.01em;
    margin:0;text-align:center;flex:1;padding:0 12px;
  }
  .mast-right{color:var(--ink-faint);font-size:12px;letter-spacing:.05em;min-width:90px;text-align:right;}

  /* ---------- Timeline scrubber ---------- */
  .timeline{position:relative;margin-bottom:6px;}
  .timeline-track{position:relative;height:46px;border-top:1px solid var(--line);border-bottom:1px solid var(--line);overflow-x:auto;overflow-y:hidden;scrollbar-width:none;}
  .timeline-track::-webkit-scrollbar{display:none;}
  .timeline-row{position:relative;display:flex;min-width:max-content;height:100%;}
  .chapter{
    position:relative;flex:0 0 auto;width:58px;height:100%;
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    cursor:pointer;border-right:1px solid var(--line);color:var(--ink-faint);
    background:transparent;font-family:'Space Mono',monospace;font-size:10px;
    transition:background .15s ease,color .15s ease;
  }
  .chapter:hover{background:var(--bg-panel);}
  .chapter .num{font-size:11px;font-weight:700;}
  .chapter .tc{font-size:9px;opacity:.7;}
  .chapter.done{color:var(--amber);}
  .chapter.active{color:var(--ink);background:var(--bg-panel-2);}
  .chapter.active::after{
    content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--rec-red);
  }
  .playhead{position:absolute;top:-1px;width:2px;height:48px;background:var(--rec-red);pointer-events:none;transition:left .25s cubic-bezier(.4,0,.2,1);box-shadow:0 0 6px var(--rec-red);}
  .playhead::before{content:'';position:absolute;top:-5px;left:-4px;border-left:5px solid transparent;border-right:5px solid transparent;border-top:6px solid var(--rec-red);}
  .scene-label{text-align:center;color:var(--ink-dim);font-size:11px;letter-spacing:.1em;margin:10px 0 26px;}

  /* ---------- Frame / viewport ---------- */
  .viewport{position:relative;}
  .frame{
    background:var(--bg-panel);border:1px solid var(--line);border-radius:var(--radius);
    padding:32px 30px 28px;min-height:320px;
    animation:fadein .35s ease;
  }
  @keyframes fadein{from{opacity:0;transform:translateY(6px);}to{opacity:1;transform:translateY(0);}}
  @media (prefers-reduced-motion:reduce){.frame{animation:none;}}
  .step-eyebrow{font-family:'Space Mono',monospace;color:var(--rec-red);font-size:11px;letter-spacing:.15em;margin-bottom:8px;}
  .step-title{font-family:'Fraunces',serif;font-weight:700;font-size:26px;margin:0 0 6px;}
  .step-sub{color:var(--ink-dim);font-size:14px;margin:0 0 26px;line-height:1.5;}

  /* ---------- Fields ---------- */
  .field{margin-bottom:20px;}
  .field label{display:block;font-size:13px;color:var(--ink-dim);margin-bottom:7px;letter-spacing:.01em;}
  .field label .req{color:var(--rec-red);margin-left:3px;}
  .field input[type=text],.field input[type=tel],.field input[type=email],.field input[type=date],.field textarea{
    width:100%;background:var(--bg-void);border:1px solid var(--line);border-radius:6px;
    color:var(--ink);padding:11px 13px;font-family:'Inter',sans-serif;font-size:14.5px;
    transition:border-color .15s ease;
  }
  .field textarea{resize:vertical;min-height:80px;line-height:1.5;}
  .field input:focus,.field textarea:focus{outline:2px solid var(--amber);outline-offset:1px;border-color:var(--amber);}
  .field.error input,.field.error textarea{border-color:var(--rec-red);}
  .field .err-msg{color:var(--rec-red);font-size:12px;margin-top:5px;display:none;}
  .field.error .err-msg{display:block;}

  .card-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:10px;}
  .opt-card{
    border:1px solid var(--line);background:var(--bg-void);border-radius:8px;padding:13px 14px;
    cursor:pointer;font-size:14px;color:var(--ink-dim);transition:all .15s ease;user-select:none;
    display:flex;align-items:center;gap:9px;
  }
  .opt-card:hover{border-color:var(--ink-faint);color:var(--ink);}
  .opt-card.selected{border-color:var(--amber);color:var(--ink);background:rgba(240,180,41,0.08);}
  .opt-card .chk{width:15px;height:15px;border-radius:3px;border:1.5px solid var(--ink-faint);flex:0 0 auto;position:relative;}
  .opt-card.selected .chk{border-color:var(--amber);background:var(--amber);}
  .opt-card.selected .chk::after{content:'✓';position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:11px;color:var(--bg-void);}
  .opt-card[data-radio] .chk{border-radius:50%;}
  .opt-card[data-radio].selected .chk::after{content:'';width:7px;height:7px;border-radius:50%;background:var(--bg-void);margin:auto;}

  .ref-group{margin-bottom:16px;}
  .ref-group-title{font-size:12.5px;color:var(--ink-dim);margin-bottom:9px;line-height:1.4;}
  .ref-row{display:flex;flex-wrap:wrap;gap:8px;}
  .ref-card{
    display:flex;align-items:center;gap:7px;border:1px solid var(--line);border-radius:20px;
    padding:5px 13px 5px 6px;cursor:pointer;font-size:12.5px;color:var(--ink-dim);background:var(--bg-void);
    transition:all .15s ease;user-select:none;
  }
  .ref-card:hover{border-color:var(--ink-faint);color:var(--ink);}
  .ref-card.selected{border-color:var(--rec-red);color:var(--ink);background:rgba(190,23,18,.14);}
  .ref-play{
    width:19px;height:19px;border-radius:50%;background:var(--rec-red);color:#fff;
    display:flex;align-items:center;justify-content:center;font-size:9px;text-decoration:none;flex:0 0 auto;
  }
  .ref-card.selected .ref-play{background:var(--ink);color:var(--bg-void);}
  .ref-check{width:14px;height:14px;border-radius:3px;border:1.5px solid var(--ink-faint);flex:0 0 auto;position:relative;}
  .ref-card.selected .ref-check{border-color:var(--rec-red);background:var(--rec-red);}
  .ref-card.selected .ref-check::after{content:'✓';position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:9px;color:#fff;}

  /* ---------- Font picker ---------- */
  .font-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));gap:10px;}
  .font-card{
    border:1px solid var(--line);background:var(--bg-void);border-radius:8px;padding:14px 14px 11px;
    cursor:pointer;transition:all .15s ease;position:relative;
  }
  .font-card:hover{border-color:var(--ink-faint);}
  .font-card.selected{border-color:var(--rec-red);background:rgba(190,23,18,.08);}
  .font-card .font-sample{font-size:24px;line-height:1.15;color:var(--ink);margin-bottom:6px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
  .font-card .font-name{font-family:'Space Mono',monospace;font-size:10.5px;color:var(--ink-dim);letter-spacing:.04em;}
  .font-card .chk{position:absolute;top:10px;right:10px;width:15px;height:15px;border-radius:50%;border:1.5px solid var(--ink-faint);}
  .font-card.selected .chk{border-color:var(--rec-red);background:var(--rec-red);}
  .font-card.selected .chk::after{content:'✓';display:flex;align-items:center;justify-content:center;font-size:9px;color:#fff;width:100%;height:100%;}

  /* ---------- Color palette ---------- */
  .color-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(52px,1fr));gap:12px 10px;}
  .swatch{cursor:pointer;text-align:center;}
  .swatch .sw-box{width:100%;aspect-ratio:1;border-radius:8px;border:2px solid var(--line);position:relative;transition:all .15s ease;}
  .swatch:hover .sw-box{border-color:var(--ink-dim);}
  .swatch.selected .sw-box{border-color:var(--ink);box-shadow:0 0 0 2px var(--rec-red);}
  .swatch.selected .sw-box::after{content:'✓';position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:14px;color:#fff;text-shadow:0 1px 3px rgba(0,0,0,.6);}
  .swatch .sw-hex{font-family:'Space Mono',monospace;font-size:9px;color:var(--ink-faint);margin-top:5px;display:block;}
  .custom-color-row{display:flex;align-items:center;gap:10px;margin-top:16px;flex-wrap:wrap;}
  .custom-color-row input[type=color]{width:44px;height:44px;border:1px solid var(--line);border-radius:8px;background:var(--bg-void);cursor:pointer;padding:2px;}
  .picked-colors{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px;}
  .picked-chip{display:flex;align-items:center;gap:7px;border:1px solid var(--line);border-radius:20px;padding:5px 10px;font-family:'Space Mono',monospace;font-size:11px;color:var(--ink);background:var(--bg-void);}
  .picked-chip .dot{width:14px;height:14px;border-radius:50%;border:1px solid var(--line);flex:0 0 auto;}
  .picked-chip button{background:none;border:none;color:var(--ink-faint);cursor:pointer;font-size:13px;line-height:1;padding:0;}
  .picked-chip button:hover{color:var(--rec-red);}

  .field-row-2{display:grid;grid-template-columns:1fr 1fr;gap:0 16px;}
  .conditional{border-left:2px solid var(--rec-red);padding-left:16px;margin:6px 0 20px;}

  /* ---------- Review ---------- */
  .review-group{border-bottom:1px solid var(--line);padding:14px 0;}
  .review-group:last-child{border-bottom:none;}
  .review-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;}
  .review-head h3{font-family:'Space Mono',monospace;font-size:11.5px;letter-spacing:.1em;color:var(--rec-red);margin:0;}
  .edit-link{background:none;border:none;color:var(--ink-faint);font-size:12px;cursor:pointer;text-decoration:underline;font-family:'Inter',sans-serif;}
  .edit-link:hover{color:var(--amber);}
  .review-row{font-size:13.5px;color:var(--ink);margin:3px 0;}
  .review-row .k{color:var(--ink-dim);}
  .review-empty{color:var(--ink-faint);font-style:italic;font-size:13px;}

  /* ---------- Slate (signature step) ---------- */
  .slate{border:1.5px solid var(--line);border-radius:8px;overflow:hidden;background:var(--bg-void);}
  .slate-top{background:repeating-linear-gradient(135deg,#1a1714,#1a1714 14px,#221e19 14px,#221e19 28px);padding:16px 18px;border-bottom:1.5px solid var(--line);}
  .slate-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px 22px;font-family:'Space Mono',monospace;font-size:12px;}
  .slate-grid div span.k{color:var(--ink-faint);display:block;font-size:10px;letter-spacing:.08em;margin-bottom:2px;}
  .slate-grid div span.v{color:var(--amber);}
  .slate-body{padding:20px 18px 22px;}
  .confirm-row{display:flex;gap:11px;align-items:flex-start;margin-bottom:20px;font-size:13.5px;color:var(--ink-dim);cursor:pointer;}
  .confirm-row input{margin-top:3px;accent-color:var(--amber);width:16px;height:16px;flex:0 0 auto;}

  .sig-wrap{margin-top:6px;}
  .sig-pad-frame{border:1px dashed var(--ink-faint);border-radius:8px;position:relative;background:#0F0D0B;}
  #sigCanvas{display:block;width:100%;height:160px;touch-action:none;cursor:crosshair;border-radius:8px;}
  .sig-hint{position:absolute;top:50%;left:0;right:0;text-align:center;transform:translateY(-50%);color:var(--ink-faint);font-size:12px;pointer-events:none;letter-spacing:.03em;}
  .sig-tools{display:flex;justify-content:space-between;align-items:center;margin-top:9px;}
  .sig-clear{background:none;border:1px solid var(--line);color:var(--ink-dim);border-radius:6px;padding:6px 12px;font-size:12px;cursor:pointer;}
  .sig-clear:hover{border-color:var(--rec-red);color:var(--rec-red);}
  .stamp{font-family:'Space Mono',monospace;font-size:11px;color:var(--ink-faint);letter-spacing:.08em;}

  /* ---------- Reglament box ---------- */
  .reglament-box{border:1px solid var(--line);border-radius:8px;background:var(--bg-void);margin-bottom:18px;}
  .reglament-box summary{
    cursor:pointer;padding:13px 15px;font-size:13.5px;color:var(--ink);list-style:none;
    display:flex;align-items:center;justify-content:space-between;gap:10px;
  }
  .reglament-box summary::-webkit-details-marker{display:none;}
  .reglament-box summary::after{content:'Розгорнути ▾';font-family:'Space Mono',monospace;font-size:10.5px;color:var(--ink-dim);flex:0 0 auto;}
  .reglament-box[open] summary::after{content:'Згорнути ▴';}
  .reglament-content{
    max-height:280px;overflow-y:auto;padding:0 15px 16px;border-top:1px solid var(--line);
    font-size:12.5px;line-height:1.6;color:var(--ink-dim);
  }
  .reglament-content h4{color:var(--ink);font-size:12.5px;letter-spacing:.03em;margin:14px 0 6px;font-family:'Space Mono',monospace;}
  .reglament-content h4:first-child{margin-top:14px;}
  .reglament-content p{margin:0 0 8px;}
  .reglament-content ol{margin:0 0 8px;padding-left:18px;}

  /* ---------- Transport / nav buttons ---------- */
  .transport{display:flex;align-items:center;justify-content:space-between;margin-top:22px;}
  .btn{
    font-family:'Inter',sans-serif;font-weight:600;font-size:14px;border-radius:7px;padding:12px 22px;
    cursor:pointer;border:1px solid var(--line);background:var(--bg-panel);color:var(--ink);
    transition:all .15s ease;
  }
  .btn:hover{border-color:var(--ink-faint);}
  .btn.primary{background:var(--rec-red);border-color:var(--rec-red);color:#fff;}
  .btn.primary:hover{background:#c93a26;}
  .btn.primary:disabled{background:var(--bg-panel-2);border-color:var(--line);color:var(--ink-faint);cursor:not-allowed;}
  .btn.ghost{background:transparent;}
  .btn:focus-visible{outline:2px solid var(--amber);outline-offset:2px;}

  .final-panel{text-align:center;padding:30px 10px 6px;}
  .final-panel .step-title{font-size:22px;}
  .doc-id{color:var(--ink-faint);font-size:12px;margin-top:14px;}

  @media(max-width:600px){
    .card-grid{grid-template-columns:1fr 1fr;}
    .field-row-2{grid-template-columns:1fr;}
    .slate-grid{grid-template-columns:1fr;}
    .frame{padding:24px 18px 22px;}
    .step-title{font-size:21px;}
    .masthead h1{font-size:15px;}
  }

  /* ---------- Printable document (used for "Save as PDF") — DSTU-style official doc ---------- */
  #printArea{display:none;}
  @media print{
    body *{visibility:hidden;}
    #printArea, #printArea *{visibility:visible;}
    #printArea{display:block;position:absolute;top:0;left:0;width:100%;}
    @page{size:A4;margin:20mm 10mm 20mm 30mm;}
  }
  #printArea{
    font-family:'Times New Roman',Times,serif;color:#000;background:#fff;
    width:170mm;margin:0 auto;padding:0;font-size:13pt;line-height:1.3;
  }
  #printArea .pd-page{width:170mm;break-after:page;}
  #printArea .pd-page:last-child{break-after:auto;}
  #printArea .pd-pagenum{text-align:center;font-size:11pt;margin:0 0 8mm;}
  #printArea .pd-letterhead{display:flex;align-items:flex-start;gap:10mm;border-bottom:1pt solid #000;padding-bottom:4mm;margin-bottom:6mm;}
  #printArea .pd-letterhead img{width:14mm;height:14mm;flex:0 0 auto;margin-top:1mm;}
  #printArea .pd-req{font-size:10.5pt;line-height:1.35;}
  #printArea .pd-req b{font-weight:700;}
  #printArea .pd-doctype{text-align:center;margin:2mm 0 6mm;}
  #printArea .pd-doctype .kind{font-size:14pt;font-weight:700;letter-spacing:.06em;text-transform:uppercase;margin:0 0 2mm;}
  #printArea .pd-doctype .idx{font-size:11pt;}
  #printArea .pd-doctype .title{font-size:13pt;font-style:italic;margin-top:2mm;}
  #printArea .pd-section{margin-bottom:5mm;}
  #printArea .pd-section h3{font-size:13pt;font-weight:700;margin:0 0 2.5mm;}
  #printArea .pd-row{font-size:12pt;line-height:1.3;margin:1.2mm 0;text-align:justify;}
  #printArea .pd-row b{font-weight:700;}
  #printArea .pd-sign{margin-top:6mm;padding-top:4mm;border-top:1pt solid #000;}
  #printArea .pd-row-lead{font-size:12pt;line-height:1.3;text-align:justify;margin:0 0 3mm;}
  #printArea .pd-sign-cols{display:flex;gap:10mm;margin-top:5mm;}
  #printArea .pd-sign-col{flex:1;}
  #printArea .pd-sign-col h4{font-size:11.5pt;font-weight:700;margin:0 0 3mm;text-transform:uppercase;}
  #printArea .pd-sign-box{border:1pt solid #999;border-radius:2px;padding:2mm;width:100%;height:26mm;display:flex;align-items:center;justify-content:center;}
  #printArea .pd-sign-box img{max-width:100%;max-height:100%;}
  #printArea .pd-sign-name{font-size:11pt;margin-top:2mm;}
  #printArea .pd-sign-meta{font-family:'Courier New',monospace;font-size:8.5pt;color:#555;margin-top:1.5mm;}
  #printArea .pd-footer-note{margin-top:6mm;font-family:'Courier New',monospace;font-size:8pt;color:#555;text-align:right;}
  #printArea .pd-reglament-text{font-size:11pt;line-height:1.3;text-align:justify;}
  #printArea .pd-reglament-text h4{font-size:12pt;font-weight:700;margin:4mm 0 2mm;}
  #printArea .pd-reglament-text h4:first-child{margin-top:0;}
  #printArea .pd-reglament-text p{margin:0 0 2.5mm;}
  #printArea .pd-reglament-text ol{margin:0 0 2.5mm;padding-left:6mm;}
</style>
</head>
<body>
<div class="app">
  <header class="masthead">
    <div class="mast-left">
      <img class="mast-logo" src="data:image/png;base64,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" alt="ONEREYN logo">
      <span class="mast-brand">ONEREYN</span>
    </div>
    <h1>Бриф на монтаж відео</h1>
    <div class="mast-right mono" id="clock">00:00:00:00</div>
  </header>

  <nav class="timeline">
    <div class="timeline-track">
      <div class="timeline-row" id="timelineRow"></div>
      <div class="playhead" id="playhead"></div>
    </div>
  </nav>
  <div class="scene-label mono" id="sceneLabel"></div>

  <main class="viewport">
    <div class="frame" id="stage"></div>
  </main>

  <footer class="transport" id="transport">
    <button class="btn ghost" id="prevBtn">◀ Назад</button>
    <button class="btn primary" id="nextBtn">Далі ▶</button>
  </footer>
</div>

<div id="printArea"></div>

<script>
/* ============ STATE ============ */
const state = {
  clientName:'', company:'', studio:'ONEREYN', phone:'', email:'', messenger:'',
  projectType:'', projectTypeOther:'',
  goal:'', audience:'', keyMessage:'',
  hasFootage:'', filmingDate:'', filmingLocation:'', filmingEquipment:'',
  footageDescription:'', footageLink:'',
  duration:'', platforms:[], deliveryCount:'',
  styleTags:[], hasBrandbook:'', brandbookLink:'', selectedFont:'', pickedColors:[], brandColors:'', brandFonts:'',
  references:'', referenceFocus:[], referenceExamples:[],
  voiceover:'', music:'', musicMood:'',
  subtitles:'', subtitleLang:'', titles:'', branding:'',
  deadline:'', urgentNote:'', budget:'',
  extraNotes:'',
  confirmed:false, agreeReglament:false, signerName:'', signatureData:''
};

/* ============ STEP DEFINITIONS ============ */
const steps = [
  { key:'contacts', title:'Контакти замовника', sub:'Хто звертається і як з вами звʼязатись.', fields:[
      {name:'clientName', label:"Ім'я та прізвище", type:'text', required:true},
      {name:'company', label:'Компанія / бренд (якщо є)', type:'text'},
      {name:'studio', label:'Кому адресовано бриф (студія / монтажер)', type:'text'},
      {name:'phone', label:'Телефон', type:'tel', required:true},
      {name:'email', label:'Email', type:'email'},
      {name:'messenger', label:'Telegram / інший месенджер', type:'text'},
  ]},
  { key:'projectType', title:'Тип проєкту', sub:'Оберіть, що найближче описує ваше відео.', custom:'projectType' },
  { key:'goal', title:'Мета та аудиторія', sub:'Що глядач має зрозуміти, відчути чи зробити.', fields:[
      {name:'goal', label:'Яка мета відео? Що глядач має зробити або відчути після перегляду?', type:'textarea', required:true},
      {name:'audience', label:'Хто ваша цільова аудиторія?', type:'textarea'},
      {name:'keyMessage', label:'Головне повідомлення / слоган (якщо є)', type:'text'},
  ]},
  { key:'materials', title:'Матеріали', sub:'Що вже знято і що ще треба зняти.', custom:'materials' },
  { key:'format', title:'Хронометраж і формат', sub:'Тривалість, платформи, кількість версій.', custom:'format' },
  { key:'style', title:'Стиль і референси', sub:'Настрій монтажу та приклади, які подобаються.', custom:'style' },
  { key:'brandkit', title:'Шрифти та кольори бренду', sub:'Оберіть шрифт і кольори, які пасують вашому бренду — з живим прев’ю.', custom:'brandkit' },
  { key:'sound', title:'Звук і музика', sub:'Закадровий голос та музичний супровід.', custom:'sound' },
  { key:'graphics', title:'Текст, графіка, субтитри', sub:'Титри, лоуерти, брендування.', custom:'graphics' },
  { key:'deadline', title:'Терміни та бюджет', sub:'Коли потрібен результат і орієнтовний бюджет.', fields:[
      {name:'deadline', label:'Бажана дата здачі', type:'date', required:true},
      {name:'urgentNote', label:'Чи привʼязано до жорсткої дати (подія, ефір)? Вкажіть деталі', type:'text'},
      {name:'budget', label:'Бюджет / орієнтовний діапазон', type:'text'},
  ]},
  { key:'notes', title:'Додаткові побажання', sub:'Все, що не увійшло в попередні пункти.', fields:[
      {name:'extraNotes', label:'Побажання, обмеження, приклади того, чого точно не має бути', type:'textarea'},
  ]},
  { key:'review', title:'Перегляд брифу', sub:'Перевірте дані перед підписанням — все можна редагувати.', custom:'review' },
  { key:'slate', title:'Затвердження', sub:'Підпишіть бриф — і документ буде готовий.', custom:'slate' },
];

const PROJECT_TYPES = ['Рекламний ролик','Відео для соцмереж (Reels/Shorts/TikTok)','Весільний фільм','Корпоративне відео','Музичний кліп','Документальне / інтервʼю','Подієве відео (захід, концерт)','Інше'];
const PLATFORMS = ['YouTube · 16:9','Instagram/TikTok · 9:16','Facebook','ТВ / презентація','Сайт / лендінг','Інше'];
const STYLE_TAGS = ['Динамічний','Спокійний / атмосферний','Кінематографічний','Влоговий / живий','Мінімалістичний','Емоційний','Стримано-корпоративний','Яскравий / креативний'];
const REFERENCE_FOCUS = ['Монтаж / темп','Кольорокорекція','Композиція кадру','Музика / звук','Графіка / текст','Загальний настрій'];

const REFERENCE_EXAMPLES = [
  { cat:'16:9 · showreel / динамічний монтаж / моушн дизайн', links:[
      'https://youtu.be/vTM3hS0W8wM',
  ]},
  { cat:'Reels · мобільні застосунки / зйомка та сценарій / моушн дизайн', links:[
      'https://youtube.com/shorts/XDnn21T2XEU?feature=share',
      'https://youtube.com/shorts/U1cseutFPe4',
  ]},
  { cat:'Reels · відео з нуля / нерухомість / динамічний монтаж', links:[
      'https://youtube.com/shorts/s3w7bQFZtgY',
  ]},
  { cat:'Reels · реклама OneReyn / моушн графіка / динамічний монтаж', links:[
      'https://youtube.com/shorts/RDPwc69sh0s?feature=share',
      'https://youtube.com/shorts/hzgxe2CA5OQ?feature=share',
      'https://youtube.com/shorts/iPcumtH04nY?feature=share',
  ]},
];

const FONT_OPTIONS = [
  { name:'Montserrat', family:"'Montserrat',sans-serif", tag:'Геометричний sans' },
  { name:'Unbounded', family:"'Unbounded',sans-serif", tag:'Смілий дисплей' },
  { name:'Golos Text', family:"'Golos Text',sans-serif", tag:'Сучасний гротеск' },
  { name:'PT Serif', family:"'PT Serif',serif", tag:'Класичний серіф' },
  { name:'Playfair Display', family:"'Playfair Display',serif", tag:'Елегантний серіф' },
  { name:'Comfortaa', family:"'Comfortaa',sans-serif", tag:'Заокруглений дисплей' },
  { name:'Rubik', family:"'Rubik',sans-serif", tag:'М’який sans' },
  { name:'Oswald', family:"'Oswald',sans-serif", tag:'Вузький / постерний' },
  { name:'Marck Script', family:"'Marck Script',cursive", tag:'Рукописний' },
  { name:'Caveat', family:"'Caveat',cursive", tag:'Живий рукописний' },
];

const COLOR_PALETTE = [
  '#000000','#FFFFFF','#F5F5F0','#BE1712','#8B0000','#FF6B35',
  '#F2C14E','#FFB703','#606C38','#2E7D32','#00A896','#118AB2',
  '#073B4C','#3A0CA3','#7209B7','#F72585','#FF477E','#4A4E69',
  '#22223B','#9A8C98','#C9ADA7','#283618','#FB8500','#8ECAE6',
];

const REGLAMENT_HTML = `
  <h4>1. Порядок передачі матеріалів та строки</h4>
  <p>1.1. Усі вихідні відео-, аудіо- та графічні матеріали, а також затверджене ТЗ повинні бути передані Виконавцю завчасно — до узгодженої дати початку фактичного виробництва (монтажу).</p>
  <p>1.2. Матеріали передаються у формі посилання на хмарне сховище (Google Drive / Dropbox) із відкритими правами доступу. Файли мають надаватися в оригінальній якості (без стиснення через месенджери).</p>
  <p>1.3. Затримка в наданні матеріалів або ТЗ з боку Замовника тягне за собою автоматичне зміщення підсумкових строків здачі проєкту.</p>
  <h4>2. Вимоги до Технічного Завдання (ТЗ) та референсів</h4>
  <p>2.1. Робота над проєктом розпочинається виключно після повного заповнення та затвердження бланка ТЗ установленого зразка.</p>
  <p>2.2. Якщо Замовник замовляє декілька відеороликів, які є ідентичними за стилістикою, складністю монтажу та графічним оформленням, опис стилю та референс надаються один раз для всієї серії.</p>
  <p>2.3. Якщо ролики відрізняються за стилем або концепцією, для кожного окремого відео у бланку ТЗ складається окремий опис та додаються відповідні посилання на референси.</p>
  <p>2.4. У разі відсутності у Замовника підготовленого референсу, Виконавець (ФОП Фіняк М.М.) залишає за собою право самостійно підібрати референсний матеріал та погодити його із Замовником до початку монтажу.</p>
  <h4>3. Правила сортування матеріалів та умови роботи з непросортованим контентом</h4>
  <p><b>3.1. Стандартне сортування:</b></p>
  <ol>
    <li>Кожне окреме відео (або ролик, що відрізняється за стилем) має розміщуватися в окремій папці.</li>
    <li>Назва папки повинна чітко відповідати назві відповідного відео, вказаній у ТЗ.</li>
  </ol>
  <p><b>3.2. Додаткова плата за відсутність сортування:</b></p>
  <ol>
    <li>Якщо Виконавець отримує вихідні матеріали у хаотичному/непосортованому вигляді, ця послуга є додатковою і сплачується Замовником окремо згідно з тарифами.</li>
    <li>Терміни виконання робіт у такому разі продовжуються на час, необхідний для систематизації матеріалів.</li>
  </ol>
  <p><b>3.3. Вимога «Маркування в кадрі» (за відсутності сортування):</b></p>
  <ol>
    <li>Якщо матеріали надаються без сортування по папках, на початку кожного відеодублю диктор/спікер повинен голосом озвучити ідентифікаційну інформацію (назву відео відповідно до сценарію, номер дублю/кадру) за принципом кінематографічної «хлопавки».</li>
  </ol>
  <h4>4. Вимоги до контенту з іноземними мовами</h4>
  <p>4.1. У зв'язку з залученням спеціалістів з монтажу, які можуть не володіти іноземними мовами в мірі, достатній для смислового редагування, для всіх іноземних матеріалів є обов'язковим надання: повного текстового сценарію, або деталізованого опису/конспекту структури відео з таймкодами та поясненням змісту кожного блоку.</p>
  <p>4.2. Робота з іншомовними вихідниками без наданого тексту/сценарію розпочата не буде.</p>
  <h4>5. Додаткові графічні та брендові вихідники</h4>
  <p>5.1. Графічні елементи (логотипи, плашки, іконки) надаються у векторних форматах або файлами .PNG із прозорим тлом.</p>
  <p>5.2. Корпоративні шрифти та брендбук (за наявності) додаються до загальної папки проєкту окремим архівом або посиланням.</p>
  <h4>6. Обов'язковість дотримання Регламенту та відповідальність</h4>
  <p>6.1. Дотримання умов та вимог даного Регламенту є обов'язковим для прийняття проєкту у виробництво та якісного його виконання.</p>
  <p>6.2. У разі порушення Замовником будь-якого з пунктів цього Регламенту (відсутність ТЗ, недотримання правил сортування, відсутність сценаріїв для іншомовного контенту, несвоєчасна передача файлів тощо), Виконавець (ФОП Фіняк М.М.) залишає за собою право: розрахувати додаткову вартість підготовчих робіт (сортування, транскрибація, складання ТЗ за Замовника) згідно з актуальним прайсом компанії; переглянути та змінити кінцеві терміни здачі проєкту пропорційно до часу, витраченого на усунення недоліків; односторонньо відмовитися від виконання робіт або призупинити їх до повного виконання вимог Замовником без застосування до Виконавця штрафних санкцій.</p>
`;

const ORG_REQUISITES = {
  fop:'ФОП ФІНЯК МАКСИМ МИКОЛАЙОВИЧ',
  brand:'що діє під комерційною назвою «Агентство з цифровізації візуальних комунікацій "ONEREYN PRODUCTION"»',
  code:'3967203319',
  phone:'0735575325',
  address:'Україна, Івано-Франківська область, м. Івано-Франківськ, вулиця Володимира Івасюка, буд. 126',
};
const EXECUTOR_SIGNATURE_SRC = 'data:image/png;base64,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';

let current = 0;

/* ============ TIMELINE RENDER ============ */
function fmtTC(i){ const m=String(i+1).padStart(2,'0'); return `00:${m}:00`; }
function renderTimeline(){
  const row = document.getElementById('timelineRow');
  row.innerHTML = '';
  steps.forEach((s,i)=>{
    const el = document.createElement('button');
    el.type='button';
    el.className='chapter'+(i===current?' active':'')+(i<current?' done':'');
    el.innerHTML = `<span class="num">${String(i+1).padStart(2,'0')}</span><span class="tc">${fmtTC(i)}</span>`;
    el.addEventListener('click', ()=>goTo(i));
    row.appendChild(el);
  });
  const totalW = steps.length*58;
  const ph = document.getElementById('playhead');
  ph.style.left = (current*58 + 29 - 1) + 'px';
  row.parentElement.scrollTo({left: Math.max(0, current*58 - 200), behavior:'smooth'});
  document.getElementById('sceneLabel').textContent = `СЦЕНА ${String(current+1).padStart(2,'0')} / ${steps.length} — ${steps[current].title.toUpperCase()}`;
}

/* ============ FIELD RENDERERS ============ */
function fieldHTML(f){
  const val = state[f.name] ?? '';
  const req = f.required ? '<span class="req">*</span>' : '';
  let input='';
  if(f.type==='textarea'){
    input = `<textarea data-field="${f.name}" rows="3">${escapeHTML(val)}</textarea>`;
  } else {
    input = `<input type="${f.type}" data-field="${f.name}" value="${escapeHTML(val)}">`;
  }
  return `<div class="field" id="field-${f.name}">
    <label>${f.label}${req}</label>
    ${input}
    <div class="err-msg">Заповніть це поле</div>
  </div>`;
}

function renderFields(container, fields){
  container.innerHTML = fields.map(fieldHTML).join('');
  fields.forEach(f=>{
    const el = container.querySelector(`[data-field="${f.name}"]`);
    el.addEventListener('input', e=>{
      state[f.name] = e.target.value;
      clearError(f.name);
    });
  });
}

function cardGridHTML(options, selectedValueOrArray, multi, groupName){
  return `<div class="card-grid" data-group="${groupName}">` + options.map(opt=>{
    const selected = multi ? selectedValueOrArray.includes(opt) : selectedValueOrArray===opt;
    return `<div class="opt-card${selected?' selected':''}" ${multi?'':'data-radio'} data-value="${escapeHTML(opt)}">
      <span class="chk"></span><span>${opt}</span>
    </div>`;
  }).join('') + `</div>`;
}

function wireCardGrid(container, groupName, multi, onChange){
  const grid = container.querySelector(`[data-group="${groupName}"]`);
  grid.querySelectorAll('.opt-card').forEach(card=>{
    card.addEventListener('click', ()=>{
      const val = card.dataset.value;
      if(multi){
        const arr = state[groupName];
        const idx = arr.indexOf(val);
        if(idx>-1) arr.splice(idx,1); else arr.push(val);
      } else {
        state[groupName] = val;
      }
      onChange();
    });
  });
}

function escapeHTML(s){ return String(s).replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c])); }

/* ============ CUSTOM STEP RENDERERS ============ */
function renderProjectType(container){
  container.innerHTML = cardGridHTML(PROJECT_TYPES, state.projectType, false, 'projectType');
  wireCardGrid(container, 'projectType', false, ()=>renderStep());
  if(state.projectType==='Інше'){
    const div = document.createElement('div');
    div.className='conditional';
    div.style.marginTop='16px';
    div.innerHTML = fieldHTML({name:'projectTypeOther', label:'Опишіть тип проєкту', type:'text'});
    container.appendChild(div);
    div.querySelector('[data-field="projectTypeOther"]').addEventListener('input', e=>{state.projectTypeOther=e.target.value;});
  }
}

function renderMaterials(container){
  container.innerHTML = `<div class="field"><label>Чи є вже відзнятий матеріал?<span class="req">*</span></label></div>`;
  container.innerHTML += cardGridHTML(['Так','Ні','Частково'], state.hasFootage, false, 'hasFootage');
  const rest = document.createElement('div');
  rest.style.marginTop='20px';
  container.appendChild(rest);
  const renderRest = ()=>{
    let html='';
    if(state.hasFootage==='Ні' || state.hasFootage==='Частково'){
      html += `<div class="conditional">`;
      html += fieldHTML({name:'filmingDate', label:'Бажана дата зйомки', type:'date'});
      html += fieldHTML({name:'filmingLocation', label:'Локація зйомки', type:'text'});
      html += fieldHTML({name:'filmingEquipment', label:'Чи потрібне обладнання / оператор від студії?', type:'text'});
      html += `</div>`;
    }
    if(state.hasFootage==='Так' || state.hasFootage==='Частково'){
      html += fieldHTML({name:'footageDescription', label:'Опишіть наявні матеріали (кількість, формат, джерело)', type:'textarea'});
      html += fieldHTML({name:'footageLink', label:'Посилання на файли (Google Drive, Dropbox тощо)', type:'text'});
    }
    rest.innerHTML = html;
    rest.querySelectorAll('[data-field]').forEach(el=>{
      el.addEventListener('input', e=>{ state[e.target.dataset.field]=e.target.value; });
    });
  };
  wireCardGrid(container, 'hasFootage', false, ()=>{ renderRest(); clearError('hasFootage'); });
  renderRest();
}

function renderFormat(container){
  container.innerHTML = fieldHTML({name:'duration', label:'Бажаний хронометраж (напр. 30–60 сек)', type:'text', required:true});
  container.innerHTML += `<div class="field"><label>Платформи публікації<span class="req">*</span></label></div>`;
  container.innerHTML += cardGridHTML(PLATFORMS, state.platforms, true, 'platforms');
  container.innerHTML += fieldHTML({name:'deliveryCount', label:'Скільки версій потрібно (напр. основна + 3 нарізки для сторіз)', type:'text'});
  container.querySelectorAll('[data-field]').forEach(el=>{
    el.addEventListener('input', e=>{ state[e.target.dataset.field]=e.target.value; clearError(e.target.dataset.field); });
  });
  wireCardGrid(container, 'platforms', true, ()=>{ clearError('platforms'); syncCardSelection(container,'platforms',true); });
}
function syncCardSelection(container, group, multi){
  const grid = container.querySelector(`[data-group="${group}"]`);
  grid.querySelectorAll('.opt-card').forEach(card=>{
    const val = card.dataset.value;
    const selected = multi ? state[group].includes(val) : state[group]===val;
    card.classList.toggle('selected', selected);
  });
}

function renderReferenceExamples(container){
  let n = 0;
  container.innerHTML = REFERENCE_EXAMPLES.map(group=>{
    const cards = group.links.map(url=>{
      n++;
      const selected = state.referenceExamples.includes(url);
      return `<div class="ref-card${selected?' selected':''}" data-url="${escapeHTML(url)}">
        <a class="ref-play" href="${escapeHTML(url)}" target="_blank" rel="noopener" aria-label="Дивитись приклад">▶</a>
        <span>Приклад ${n}</span>
        <span class="ref-check"></span>
      </div>`;
    }).join('');
    return `<div class="ref-group">
      <div class="ref-group-title">${escapeHTML(group.cat)}</div>
      <div class="ref-row">${cards}</div>
    </div>`;
  }).join('');

  container.querySelectorAll('.ref-play').forEach(a=>{
    a.addEventListener('click', e=> e.stopPropagation());
  });
  container.querySelectorAll('.ref-card').forEach(card=>{
    card.addEventListener('click', ()=>{
      const url = card.dataset.url;
      const idx = state.referenceExamples.indexOf(url);
      if(idx>-1) state.referenceExamples.splice(idx,1); else state.referenceExamples.push(url);
      card.classList.toggle('selected');
    });
  });
}

function renderStyle(container){
  container.innerHTML = `<div class="field"><label>Стиль монтажу (можна декілька)</label></div>`;
  container.innerHTML += cardGridHTML(STYLE_TAGS, state.styleTags, true, 'styleTags');

  const refBlock = document.createElement('div');
  refBlock.innerHTML = `<div class="field" style="margin-top:22px"><label>На що звернути увагу в референсах</label></div>`;
  refBlock.innerHTML += cardGridHTML(REFERENCE_FOCUS, state.referenceFocus, true, 'referenceFocus');
  container.appendChild(refBlock);

  const examplesBlock = document.createElement('div');
  examplesBlock.style.marginTop = '22px';
  examplesBlock.innerHTML = `<div class="field"><label>Приклади наших робіт — позначте ті, що резонують із задумом</label></div>`;
  container.appendChild(examplesBlock);
  renderReferenceExamples(examplesBlock);

  const refLinksBlock = document.createElement('div');
  refLinksBlock.style.marginTop = '18px';
  refLinksBlock.innerHTML = fieldHTML({name:'references', label:'Ваш власний референс — щонайменше одне посилання на відео, рілс чи приклад стилю', type:'textarea', required:true});
  container.appendChild(refLinksBlock);

  container.querySelectorAll('[data-field]').forEach(el=>{
    el.addEventListener('input', e=>{ state[e.target.dataset.field]=e.target.value; });
  });
  wireCardGrid(container, 'styleTags', true, ()=>syncCardSelection(container,'styleTags',true));
  wireCardGrid(container, 'referenceFocus', true, ()=>syncCardSelection(container,'referenceFocus',true));
}

function renderBrandkit(container){
  container.innerHTML = `<div class="field"><label>Чи є у вас брендбук / гайдлайни?</label></div>`;
  container.innerHTML += cardGridHTML(['Так, надамо','Частково (лого + кольори)','Немає — покладаємось на вас'], state.hasBrandbook, false, 'hasBrandbook');
  const brandbookCond = document.createElement('div');
  container.appendChild(brandbookCond);

  const fontBlock = document.createElement('div');
  fontBlock.style.marginTop = '26px';
  fontBlock.innerHTML = `<div class="field"><label>Оберіть шрифт, який пасує бренду</label></div>
    <div class="font-grid" data-group="selectedFont">
      ${FONT_OPTIONS.map(f=>`
        <div class="font-card${state.selectedFont===f.name?' selected':''}" data-value="${f.name}">
          <div class="chk"></div>
          <div class="font-sample" style="font-family:${f.family}">Аа Бб Вв — ${escapeHTML(f.name)}</div>
          <div class="font-name">${f.tag}</div>
        </div>`).join('')}
    </div>`;
  container.appendChild(fontBlock);

  const fontOtherRow = document.createElement('div');
  fontOtherRow.style.marginTop = '14px';
  fontOtherRow.innerHTML = fieldHTML({name:'brandFonts', label:'Або вкажіть конкретний шрифт (наприклад, преміум зі rentafont.com.ua) — назва + опційно посилання', type:'text'});
  fontOtherRow.innerHTML += `<div style="margin-top:-10px;margin-bottom:4px"><a href="https://rentafont.com.ua/fonts" target="_blank" rel="noopener" style="color:var(--ink-dim);font-size:12px;text-decoration:underline">Переглянути каталог шрифтів rentafont.com.ua ↗</a></div>`;
  container.appendChild(fontOtherRow);

  const colorBlock = document.createElement('div');
  colorBlock.style.marginTop = '30px';
  colorBlock.innerHTML = `<div class="field"><label>Кольорова палітра — оберіть кольори, які подобаються</label></div>
    <div class="color-grid" data-group="pickedColors">
      ${COLOR_PALETTE.map(c=>`
        <div class="swatch${state.pickedColors.includes(c)?' selected':''}" data-value="${c}">
          <div class="sw-box" style="background:${c}"></div>
          <span class="sw-hex">${c}</span>
        </div>`).join('')}
    </div>
    <div class="custom-color-row">
      <input type="color" id="customColorInput" value="#BE1712">
      <button type="button" class="btn ghost" id="addCustomColorBtn" style="padding:9px 16px;font-size:13px">Додати свій колір</button>
    </div>
    <div class="picked-colors" id="pickedColorsList"></div>`;
  container.appendChild(colorBlock);

  const colorNoteRow = document.createElement('div');
  colorNoteRow.style.marginTop = '18px';
  colorNoteRow.innerHTML = fieldHTML({name:'brandColors', label:'Додатково опишіть кольори словами (за потреби)', type:'text'});
  container.appendChild(colorNoteRow);

  container.querySelectorAll('[data-field]').forEach(el=>{
    el.addEventListener('input', e=>{ state[e.target.dataset.field]=e.target.value; });
  });

  const renderBrandbookCond = ()=>{
    if(state.hasBrandbook && state.hasBrandbook!=='Немає — покладаємось на вас'){
      brandbookCond.innerHTML = `<div class="conditional" style="margin:16px 0 4px">` + fieldHTML({name:'brandbookLink', label:'Посилання на брендбук / файли (Google Drive, Figma тощо)', type:'text'}) + `</div>`;
      brandbookCond.querySelector('[data-field="brandbookLink"]').addEventListener('input', e=>{state.brandbookLink=e.target.value;});
    } else { brandbookCond.innerHTML=''; }
  };
  wireCardGrid(container, 'hasBrandbook', false, ()=>{ syncCardSelection(container,'hasBrandbook',false); renderBrandbookCond(); });
  renderBrandbookCond();

  // Font selection (single choice)
  container.querySelectorAll('.font-card').forEach(card=>{
    card.addEventListener('click', ()=>{
      state.selectedFont = card.dataset.value;
      container.querySelectorAll('.font-card').forEach(c=>c.classList.toggle('selected', c.dataset.value===state.selectedFont));
    });
  });

  // Color palette selection (multi choice)
  function renderPickedList(){
    const list = container.querySelector('#pickedColorsList');
    list.innerHTML = state.pickedColors.map(c=>`
      <div class="picked-chip"><span class="dot" style="background:${c}"></span>${c}<button type="button" data-remove="${c}">✕</button></div>
    `).join('');
    list.querySelectorAll('[data-remove]').forEach(btn=>{
      btn.addEventListener('click', ()=>{
        const c = btn.dataset.remove;
        state.pickedColors = state.pickedColors.filter(x=>x!==c);
        syncSwatches(); renderPickedList();
      });
    });
  }
  function syncSwatches(){
    container.querySelectorAll('.swatch').forEach(sw=>{
      sw.classList.toggle('selected', state.pickedColors.includes(sw.dataset.value));
    });
  }
  container.querySelectorAll('.swatch').forEach(sw=>{
    sw.addEventListener('click', ()=>{
      const c = sw.dataset.value;
      const idx = state.pickedColors.indexOf(c);
      if(idx>-1) state.pickedColors.splice(idx,1); else state.pickedColors.push(c);
      syncSwatches(); renderPickedList();
    });
  });
  container.querySelector('#addCustomColorBtn').addEventListener('click', ()=>{
    const c = container.querySelector('#customColorInput').value.toUpperCase();
    if(!state.pickedColors.includes(c)){ state.pickedColors.push(c); syncSwatches(); renderPickedList(); }
  });
  renderPickedList();
}

function renderSound(container){
  container.innerHTML = `<div class="field"><label>Закадровий голос</label></div>`;
  container.innerHTML += cardGridHTML(['Потрібен','Не потрібен','Ще не вирішено'], state.voiceover, false, 'voiceover');
  container.innerHTML += `<div class="field" style="margin-top:20px"><label>Музичний супровід</label></div>`;
  container.innerHTML += cardGridHTML(['Є своя музика','Потрібно підібрати','Без музики'], state.music, false, 'music');
  const rest = document.createElement('div');
  rest.style.marginTop='16px';
  container.appendChild(rest);
  const renderRest = ()=>{
    if(state.music==='Потрібно підібрати'){
      rest.innerHTML = `<div class="conditional">` + fieldHTML({name:'musicMood', label:'Який настрій музики?', type:'text'}) + `</div>`;
      rest.querySelector('[data-field="musicMood"]').addEventListener('input', e=>{state.musicMood=e.target.value;});
    } else { rest.innerHTML=''; }
  };
  wireCardGrid(container, 'voiceover', false, ()=>syncCardSelection(container,'voiceover',false));
  wireCardGrid(container, 'music', false, ()=>{ syncCardSelection(container,'music',false); renderRest(); });
  renderRest();
}

function renderGraphics(container){
  container.innerHTML = `<div class="field"><label>Субтитри</label></div>`;
  container.innerHTML += cardGridHTML(['Так','Ні','Тільки для соцмереж'], state.subtitles, false, 'subtitles');
  const sub = document.createElement('div'); container.appendChild(sub);
  container.innerHTML += `<div class="field" style="margin-top:20px"><label>Титри / імена / лоуерти</label></div>`;
  container.innerHTML += cardGridHTML(['Потрібні','Не потрібні'], state.titles, false, 'titles');
  container.innerHTML += fieldHTML({name:'branding', label:'Чи є брендбук, лого, фірмові кольори? Додайте посилання', type:'textarea'});
  container.querySelectorAll('[data-field]').forEach(el=>{
    el.addEventListener('input', e=>{ state[e.target.dataset.field]=e.target.value; });
  });
  const subField = container.querySelector('#field-branding') ? null : null;
  const renderSubtitleLang = ()=>{
    let el = container.querySelector('#cond-sub-lang');
    if(el) el.remove();
    if(state.subtitles && state.subtitles!=='Ні'){
      const div = document.createElement('div');
      div.className='conditional'; div.id='cond-sub-lang'; div.style.margin='16px 0 20px';
      div.innerHTML = fieldHTML({name:'subtitleLang', label:'Якою мовою субтитри?', type:'text'});
      container.querySelector('[data-group="subtitles"]').after(div);
      div.querySelector('[data-field="subtitleLang"]').addEventListener('input', e=>{state.subtitleLang=e.target.value;});
    }
  };
  wireCardGrid(container, 'subtitles', false, ()=>{ syncCardSelection(container,'subtitles',false); renderSubtitleLang(); });
  wireCardGrid(container, 'titles', false, ()=>syncCardSelection(container,'titles',false));
  renderSubtitleLang();
}

function renderReview(container){
  const groups = [
    ['Контакти', [["Ім'я",state.clientName],['Компанія',state.company],['Студія/монтажер',state.studio],['Телефон',state.phone],['Email',state.email],['Месенджер',state.messenger]], 0],
    ['Тип проєкту', [['Тип', state.projectType==='Інше' ? state.projectTypeOther : state.projectType]], 1],
    ['Мета та аудиторія', [['Мета',state.goal],['Аудиторія',state.audience],['Меседж',state.keyMessage]], 2],
    ['Матеріали', [['Наявність',state.hasFootage],['Дата зйомки',state.filmingDate],['Локація',state.filmingLocation],['Обладнання',state.filmingEquipment],['Опис матеріалів',state.footageDescription],['Посилання',state.footageLink]], 3],
    ['Формат', [['Хронометраж',state.duration],['Платформи',state.platforms.join(', ')],['Версії',state.deliveryCount]], 4],
    ['Стиль', [['Теги стилю',state.styleTags.join(', ')],['Фокус референсів',state.referenceFocus.join(', ')],['Обрані приклади робіт',state.referenceExamples.join('  ·  ')],['Власні референси',state.references]], 5],
    ['Шрифти та кольори', [['Брендбук',state.hasBrandbook],['Посилання на брендбук',state.brandbookLink],['Обраний шрифт',state.selectedFont],['Свій шрифт',state.brandFonts],['Обрані кольори',state.pickedColors.join('  ')],['Опис кольорів',state.brandColors]], 6],
    ['Звук', [['Голос за кадром',state.voiceover],['Музика',state.music],['Настрій музики',state.musicMood]], 7],
    ['Графіка', [['Субтитри',state.subtitles],['Мова субтитрів',state.subtitleLang],['Титри',state.titles],['Брендинг',state.branding]], 8],
    ['Терміни та бюджет', [['Дедлайн',state.deadline],['Жорсткі рамки',state.urgentNote],['Бюджет',state.budget]], 9],
    ['Побажання', [['Нотатки',state.extraNotes]], 10],
  ];
  container.innerHTML = groups.map(([title, rows, stepIdx])=>{
    const rowsHTML = rows.filter(r=>r[1]).map(r=>`<div class="review-row"><span class="k">${r[0]}:</span> ${escapeHTML(r[1])}</div>`).join('');
    return `<div class="review-group">
      <div class="review-head"><h3>${title.toUpperCase()}</h3><button class="edit-link" data-goto="${stepIdx}">редагувати</button></div>
      ${rowsHTML || '<div class="review-empty">Не заповнено</div>'}
    </div>`;
  }).join('');
  container.querySelectorAll('[data-goto]').forEach(btn=>{
    btn.addEventListener('click', ()=>goTo(parseInt(btn.dataset.goto)));
  });
}

/* ---- Signature pad ---- */
let sigCtx, sigDrawing=false, sigHasDrawn=false;
function renderSlate(container){
  const today = new Date().toLocaleDateString('uk-UA');
  container.innerHTML = `
    <div class="slate">
      <div class="slate-top">
        <div class="slate-grid">
          <div><span class="k">ПРОЄКТ</span><span class="v">${escapeHTML(state.company||state.clientName||'—')}</span></div>
          <div><span class="k">ТИП</span><span class="v">${escapeHTML((state.projectType==='Інше'?state.projectTypeOther:state.projectType)||'—')}</span></div>
          <div><span class="k">ДЕДЛАЙН</span><span class="v">${escapeHTML(state.deadline||'—')}</span></div>
          <div><span class="k">ДАТА БРИФУ</span><span class="v">${today}</span></div>
        </div>
      </div>
      <div class="slate-body">
        <details class="reglament-box">
          <summary>Регламент студії — підготовка, сортування та передача вихідних матеріалів</summary>
          <div class="reglament-content">${REGLAMENT_HTML}</div>
        </details>
        <label class="confirm-row"><input type="checkbox" id="reglamentChk" ${state.agreeReglament?'checked':''}>
          Я ознайомлений(-а) з Регламентом підготовки, сортування та передачі вихідних матеріалів і погоджуюсь з його умовами.</label>
        <label class="confirm-row"><input type="checkbox" id="confirmChk" ${state.confirmed?'checked':''}>
          Я підтверджую, що ознайомлений(-а) з цим брифом і погоджую його умови для виконання монтажу.</label>
        <div class="field"><label>Ім'я, що підтверджує підпис<span class="req">*</span></label>
          <input type="text" id="signerName" value="${escapeHTML(state.signerName)}">
        </div>
        <div class="sig-wrap">
          <label>Підпис<span class="req">*</span></label>
          <div class="sig-pad-frame">
            <canvas id="sigCanvas"></canvas>
            <div class="sig-hint" id="sigHint">поставте підпис пальцем або мишкою</div>
          </div>
          <div class="sig-tools">
            <button type="button" class="sig-clear" id="sigClear">Очистити</button>
            <span class="stamp">SIGNED&nbsp;·&nbsp;${today}</span>
          </div>
        </div>
      </div>
    </div>
  `;
  container.querySelector('#reglamentChk').addEventListener('change', e=>{ state.agreeReglament = e.target.checked; clearError('agreeReglament'); });
  container.querySelector('#confirmChk').addEventListener('change', e=>{ state.confirmed = e.target.checked; });
  container.querySelector('#signerName').addEventListener('input', e=>{ state.signerName = e.target.value; });
  container.querySelector('#sigClear').addEventListener('click', clearSignature);
  setupSignaturePad();
}

function setupSignaturePad(){
  const canvas = document.getElementById('sigCanvas');
  const hint = document.getElementById('sigHint');
  const dpr = window.devicePixelRatio || 1;
  const rect = canvas.getBoundingClientRect();
  canvas.width = rect.width*dpr; canvas.height = 160*dpr;
  sigCtx = canvas.getContext('2d');
  sigCtx.scale(dpr,dpr);
  sigCtx.strokeStyle = '#F2EDE4';
  sigCtx.lineWidth = 2.2;
  sigCtx.lineCap = 'round';
  sigCtx.lineJoin = 'round';
  sigHasDrawn = !!state.signatureData;
  if(state.signatureData){
    hint.style.display='none';
    const img = new Image();
    img.onload = ()=> sigCtx.drawImage(img,0,0,rect.width,160);
    img.src = state.signatureData;
  }
  let last=null;
  function pos(e){
    const r = canvas.getBoundingClientRect();
    const p = e.touches ? e.touches[0] : e;
    return {x:p.clientX-r.left, y:p.clientY-r.top};
  }
  function start(e){ e.preventDefault(); sigDrawing=true; hint.style.display='none'; last=pos(e); }
  function move(e){
    if(!sigDrawing) return; e.preventDefault();
    const p = pos(e);
    sigCtx.beginPath(); sigCtx.moveTo(last.x,last.y); sigCtx.lineTo(p.x,p.y); sigCtx.stroke();
    last = p; sigHasDrawn = true;
  }
  function end(){
    if(!sigDrawing) return;
    sigDrawing=false;
    state.signatureData = canvas.toDataURL('image/png');
    clearError('signature');
  }
  canvas.addEventListener('pointerdown', start);
  canvas.addEventListener('pointermove', move);
  window.addEventListener('pointerup', end);
  canvas.addEventListener('touchstart', start, {passive:false});
  canvas.addEventListener('touchmove', move, {passive:false});
  canvas.addEventListener('touchend', end);
}
function clearSignature(){
  const canvas = document.getElementById('sigCanvas');
  const rect = canvas.getBoundingClientRect();
  sigCtx.clearRect(0,0,rect.width,160);
  document.getElementById('sigHint').style.display='block';
  sigHasDrawn=false; state.signatureData='';
}

/* ============ MAIN STEP RENDER ============ */
function renderStep(){
  const step = steps[current];
  const stage = document.getElementById('stage');
  stage.innerHTML = `
    <div class="step-eyebrow mono">СЦЕНА ${String(current+1).padStart(2,'0')} · ${fmtTC(current)}</div>
    <h2 class="step-title">${step.title}</h2>
    <p class="step-sub">${step.sub}</p>
    <div id="stepBody"></div>
  `;
  const body = document.getElementById('stepBody');
  if(step.fields){ renderFields(body, step.fields); }
  else if(step.custom==='projectType'){ renderProjectType(body); }
  else if(step.custom==='materials'){ renderMaterials(body); }
  else if(step.custom==='format'){ renderFormat(body); }
  else if(step.custom==='style'){ renderStyle(body); }
  else if(step.custom==='brandkit'){ renderBrandkit(body); }
  else if(step.custom==='sound'){ renderSound(body); }
  else if(step.custom==='graphics'){ renderGraphics(body); }
  else if(step.custom==='review'){ renderReview(body); }
  else if(step.custom==='slate'){ renderSlate(body); }

  document.getElementById('prevBtn').style.visibility = current===0 ? 'hidden' : 'visible';
  const nextBtn = document.getElementById('nextBtn');
  if(current === steps.length-1){
    nextBtn.textContent = 'Сформувати ТЗ і зберегти PDF';
  } else {
    nextBtn.textContent = 'Далі ▶';
  }
  renderTimeline();
  updateClock();
}

function clearError(name){
  const el = document.getElementById('field-'+name);
  if(el) el.classList.remove('error');
  const grid = document.querySelector(`[data-group="${name}"]`);
  if(grid) grid.parentElement.classList.remove('error');
}

function validateStep(){
  const step = steps[current];
  let ok = true;
  if(step.fields){
    step.fields.forEach(f=>{
      if(f.required && !String(state[f.name]||'').trim()){
        const el = document.getElementById('field-'+f.name);
        if(el) el.classList.add('error');
        ok=false;
      }
    });
  }
  if(step.key==='projectType' && !state.projectType) ok=false;
  if(step.key==='style'){
    if(!state.references.trim()){
      const el = document.getElementById('field-references');
      if(el) el.classList.add('error');
      ok=false;
    }
  }
  if(step.key==='materials' && !state.hasFootage) ok=false;
  if(step.key==='format'){
    if(!state.duration){ const el=document.getElementById('field-duration'); if(el) el.classList.add('error'); ok=false; }
    if(state.platforms.length===0) ok=false;
  }
  if(step.key==='slate'){
    if(!state.confirmed) ok=false;
    if(!state.agreeReglament) ok=false;
    if(!state.signerName.trim()){ const el=document.getElementById('field-signerName')||document.getElementById('signerName'); ok=false; }
    if(!state.signatureData) ok=false;
  }
  return ok;
}

function goTo(i){
  current = Math.max(0, Math.min(steps.length-1, i));
  renderStep();
  document.getElementById('stage').scrollIntoView({behavior:'smooth', block:'start'});
}

document.getElementById('prevBtn').addEventListener('click', ()=>{
  if(current>0) goTo(current-1);
});
document.getElementById('nextBtn').addEventListener('click', ()=>{
  if(!validateStep()){
    document.getElementById('stage').querySelector('.error')?.scrollIntoView({behavior:'smooth', block:'center'});
    return;
  }
  if(current === steps.length-1){
    generatePDF();
    return;
  }
  goTo(current+1);
});

/* ============ CLOCK (decorative) ============ */
let startT = Date.now();
function updateClock(){
  const el = document.getElementById('clock');
  const reduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  if(reduced){ el.textContent = '00:00:00:00'; return; }
  clearInterval(window.__clockTimer);
  window.__clockTimer = setInterval(()=>{
    const elapsed = Date.now()-startT;
    const totalSec = Math.floor(elapsed/1000);
    const h=String(Math.floor(totalSec/3600)).padStart(2,'0');
    const m=String(Math.floor((totalSec%3600)/60)).padStart(2,'0');
    const s=String(totalSec%60).padStart(2,'0');
    const f=String(Math.floor((elapsed%1000)/40)).padStart(2,'0');
    el.textContent = `${h}:${m}:${s}:${f}`;
  }, 40);
}

/* ============ PDF GENERATION (offline, via browser print) ============ */
function pdRow(label, value){
  if(!value) return '';
  return `<div class="pd-row"><b>${escapeHTML(label)}:</b> ${escapeHTML(value)}</div>`;
}
function pdSection(num, title, rowsHTML){
  const filled = rowsHTML.replace(/\s+/g,'');
  if(!filled) return '';
  return `<div class="pd-section"><h3>${num}. ${title}</h3>${rowsHTML}</div>`;
}

// Split a block of HTML (top-level siblings) into an array of individual element HTML strings,
// so the paginator can pack at paragraph-level granularity instead of one giant block.
function splitHTMLBlocks(html){
  const tmp = document.createElement('div');
  tmp.innerHTML = html;
  return Array.from(tmp.children).map(el => el.outerHTML);
}

// Greedily pack an array of HTML block-strings into pages that fit the printable area,
// measuring real rendered height in the current font/DPI context.
function paginateBlocks(blocks){
  const probeWidth = document.createElement('div');
  probeWidth.style.cssText = 'position:fixed;visibility:hidden;left:-9999px;width:170mm;';
  document.body.appendChild(probeWidth);
  const contentWidthPx = probeWidth.getBoundingClientRect().width;
  const probeHeight = document.createElement('div');
  probeHeight.style.cssText = 'position:fixed;visibility:hidden;left:-9999px;height:257mm;';
  document.body.appendChild(probeHeight);
  const pageHeightPx = probeHeight.getBoundingClientRect().height * 0.95;
  document.body.removeChild(probeHeight);

  const measurer = document.createElement('div');
  measurer.className = 'printarea-measurer';
  measurer.style.cssText = `position:fixed;visibility:hidden;left:-9999px;top:0;width:${contentWidthPx}px;font-family:'Times New Roman',Times,serif;font-size:13pt;line-height:1.3;`;
  document.body.appendChild(measurer);
  document.body.removeChild(probeWidth);

  const heights = blocks.map(html=>{
    measurer.innerHTML = html;
    return measurer.getBoundingClientRect().height;
  });
  document.body.removeChild(measurer);

  const pages = [];
  let cur = [];
  let curH = 0;
  const PAGENUM_H = 40; // reserved px for the page-number line on pages 2+
  blocks.forEach((html, i)=>{
    const isFirstPage = pages.length===0;
    const budget = pageHeightPx - (isFirstPage ? 0 : PAGENUM_H);
    if(cur.length && curH + heights[i] > budget){
      pages.push(cur);
      cur = [];
      curH = 0;
    }
    cur.push(html);
    curH += heights[i];
  });
  if(cur.length) pages.push(cur);
  return pages;
}

function generatePDF(){
  const docId = 'ТЗ-' + Date.now().toString(36).toUpperCase();
  const dateStr = new Date().toLocaleDateString('uk-UA');
  const timeStr = new Date().toLocaleTimeString('uk-UA');

  const letterheadHTML = `<div class="pd-letterhead">
    <img src="${document.querySelector('.mast-logo').src}" alt="ONEREYN">
    <div class="pd-req">
      <b>${ORG_REQUISITES.fop}</b> (${ORG_REQUISITES.brand})<br>
      ЄДРПОУ/ІПН: ${ORG_REQUISITES.code} · Тел.: ${ORG_REQUISITES.phone}<br>
      ${ORG_REQUISITES.address}
    </div>
  </div>
  <div class="pd-doctype">
    <div class="kind">Технічне завдання</div>
    <div class="idx">№ ${docId} від ${dateStr}</div>
    <div class="title">на монтаж відеоконтенту${state.company||state.clientName ? ' для «'+escapeHTML(state.company||state.clientName)+'»' : ''}</div>
  </div>`;

  const bodyBlocks = [];

  bodyBlocks.push(pdSection(1, 'Контакти замовника',
    pdRow("Ім'я", state.clientName) + pdRow('Компанія', state.company) +
    pdRow('Телефон', state.phone) + pdRow('Email', state.email) + pdRow('Месенджер', state.messenger)));

  bodyBlocks.push(pdSection(2, 'Тип проєкту',
    pdRow('Тип', state.projectType==='Інше' ? state.projectTypeOther : state.projectType)));

  bodyBlocks.push(pdSection(3, 'Мета та аудиторія',
    pdRow('Мета', state.goal) + pdRow('Аудиторія', state.audience) + pdRow('Ключове повідомлення', state.keyMessage)));

  bodyBlocks.push(pdSection(4, 'Матеріали',
    pdRow('Наявність матеріалу', state.hasFootage) + pdRow('Дата зйомки', state.filmingDate) +
    pdRow('Локація', state.filmingLocation) + pdRow('Обладнання/оператор', state.filmingEquipment) +
    pdRow('Опис матеріалів', state.footageDescription) + pdRow('Посилання на файли', state.footageLink)));

  bodyBlocks.push(pdSection(5, 'Хронометраж і формат',
    pdRow('Хронометраж', state.duration) + pdRow('Платформи', state.platforms.join(', ')) + pdRow('Кількість версій', state.deliveryCount)));

  bodyBlocks.push(pdSection(6, 'Стиль і референси',
    pdRow('Стиль', state.styleTags.join(', ')) + pdRow('Фокус референсів', state.referenceFocus.join(', ')) +
    pdRow('Обрані приклади робіт', state.referenceExamples.join('  ·  ')) +
    pdRow('Власні референси', state.references)));

  bodyBlocks.push(pdSection(7, 'Шрифти та кольори бренду',
    pdRow('Брендбук', state.hasBrandbook) + pdRow('Посилання на брендбук', state.brandbookLink) +
    pdRow('Обраний шрифт', state.selectedFont) + pdRow('Свій шрифт', state.brandFonts) +
    pdRow('Обрані кольори', state.pickedColors.join('  ')) + pdRow('Опис кольорів', state.brandColors)));

  bodyBlocks.push(pdSection(8, 'Звук і музика',
    pdRow('Закадровий голос', state.voiceover) + pdRow('Музика', state.music) + pdRow('Настрій музики', state.musicMood)));

  bodyBlocks.push(pdSection(9, 'Текст, графіка, субтитри',
    pdRow('Субтитри', state.subtitles) + pdRow('Мова субтитрів', state.subtitleLang) +
    pdRow('Титри/лоуерти', state.titles) + pdRow('Брендинг', state.branding)));

  bodyBlocks.push(pdSection(10, 'Терміни та бюджет',
    pdRow('Дедлайн', state.deadline) + pdRow('Жорсткі рамки', state.urgentNote) + pdRow('Бюджет', state.budget)));

  bodyBlocks.push(pdSection(11, 'Додаткові побажання', pdRow('Нотатки', state.extraNotes)));

  bodyBlocks.push(`<div class="pd-sign">
    <div class="pd-section"><h3>12. Затвердження брифу та Регламенту</h3>
      <div class="pd-row-lead">Підписант підтверджує ознайомлення з умовами цього брифу та Регламенту підготовки, сортування і передачі вихідних матеріалів (див. Додаток), і погоджує їх для виконання монтажу.</div>
      ${pdRow('Погодження Регламенту', state.agreeReglament ? 'Так, ознайомлений(-а) і погоджує умови' : '—')}
      ${pdRow('Дата підпису', dateStr)}
    </div>
    <div class="pd-sign-cols">
      <div class="pd-sign-col">
        <h4>Замовник</h4>
        <div class="pd-sign-box">${state.signatureData ? `<img src="${state.signatureData}">` : ''}</div>
        <div class="pd-sign-name">${escapeHTML(state.signerName||'')}</div>
        <div class="pd-sign-meta">Електронний підпис, накладений на сайті ${dateStr} о ${timeStr}</div>
      </div>
      <div class="pd-sign-col">
        <h4>Виконавець</h4>
        <div class="pd-sign-box"><img src="${EXECUTOR_SIGNATURE_SRC}"></div>
        <div class="pd-sign-name">${ORG_REQUISITES.fop}</div>
        <div class="pd-sign-meta">М.П. / без печатки — ФОП</div>
      </div>
    </div>
  </div>`);

  const appendixBlocks = [
    `<div class="pd-section"><h3>Додаток. Регламент підготовки, сортування та передачі вихідних матеріалів для обробки відеоконтенту</h3></div>`,
    ...splitHTMLBlocks(REGLAMENT_HTML).map(b=>`<div class="pd-reglament-text">${b}</div>`)
  ];

  const allBlocks = [letterheadHTML, ...bodyBlocks, ...appendixBlocks];
  const pages = paginateBlocks(allBlocks);

  let html = pages.map((pageBlocks, i)=>{
    const numHTML = i>0 ? `<div class="pd-pagenum">${i+1}</div>` : '';
    return `<div class="pd-page">${numHTML}${pageBlocks.join('')}</div>`;
  }).join('');
  html += `<div class="pd-footer-note">${docId}</div>`;

  document.getElementById('printArea').innerHTML = html;
  document.title = `TZ_${(state.clientName||'brief').replace(/\s+/g,'_')}_${dateStr.replace(/\./g,'-')}`;

  window.print();
  showFinalPanel();
}

function showFinalPanel(){
  const stage = document.getElementById('stage');
  stage.innerHTML = `
    <div class="final-panel">
      <div class="step-eyebrow mono" style="text-align:center">CUT · КІНЕЦЬ ЗАПИСУ</div>
      <h2 class="step-title">ТЗ сформовано ✓</h2>
      <p class="step-sub">У вікні друку, що відкрилось, оберіть <strong>«Зберегти як PDF»</strong> (замість принтера) і натисніть «Зберегти» — файл завантажиться на ваш пристрій. Якщо вікно не зʼявилось, натисніть кнопку нижче ще раз.</p>
      <button class="btn primary" id="printAgainBtn" style="margin-top:6px">Відкрити друк ще раз</button>
      <button class="btn ghost" id="restartBtn" style="margin-top:10px">Заповнити ще один бриф</button>
      <div class="doc-id mono">SESSION CLOSED</div>
    </div>
  `;
  document.getElementById('transport').style.display='none';
  document.getElementById('printAgainBtn').addEventListener('click', ()=> window.print());
  document.getElementById('restartBtn').addEventListener('click', ()=>{
    location.reload();
  });
}

/* ============ INIT ============ */
renderStep();
</script>
</body>
</html>
