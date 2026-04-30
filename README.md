<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Regional Manager Interview Test | Towne Properties</title>
<link href="https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700;900&family=Merriweather:wght@400;700&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
<style>
  :root {
    --tp-navy:#1a3a5c; --tp-blue:#1e5799; --tp-sky:#3a7fc1; --tp-light:#d6e8f7;
    --tp-white:#fff; --tp-gray-50:#f4f7fb; --tp-gray-100:#e8eef5; --tp-gray-200:#c8d6e5;
    --tp-gray-400:#8098b4; --tp-gray-600:#4d6680; --tp-text:#1e2f42;
    --tp-correct:#1a6b3a; --tp-correct-bg:#e8f5ee;
    --tp-wrong:#9b1c1c; --tp-wrong-bg:#fde8e8;
    --tp-warn:#7c5100; --tp-warn-bg:#fff3cd;
    --r:6px;
  }
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
  body{font-family:'Lato',sans-serif;background:var(--tp-gray-50);color:var(--tp-text);min-height:100vh;}

  /* COVER */
  #cover{min-height:100vh;background:linear-gradient(160deg,var(--tp-navy) 0%,var(--tp-blue) 55%,#2d6fb5 100%);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:3rem 1.5rem;text-align:center;position:relative;overflow:hidden;}
  #cover::before{content:'';position:absolute;top:-80px;right:-80px;width:460px;height:460px;border-radius:50%;background:rgba(255,255,255,.04);}
  #cover::after{content:'';position:absolute;bottom:-100px;left:-100px;width:560px;height:560px;border-radius:50%;background:rgba(255,255,255,.03);}

  .cover-logo-card{background:#fff;border-radius:10px;padding:1.6rem 2.4rem 1.2rem;margin-bottom:2rem;box-shadow:0 10px 40px rgba(0,0,0,.22);position:relative;z-index:1;}
  .cover-badge{display:inline-block;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.25);color:rgba(255,255,255,.85);font-size:.72rem;letter-spacing:.2em;text-transform:uppercase;padding:.35rem 1.1rem;border-radius:999px;margin-bottom:1.25rem;position:relative;z-index:1;}
  .cover-title{font-family:'Merriweather',serif;font-size:clamp(1.6rem,4vw,2.6rem);color:#fff;line-height:1.2;margin-bottom:.6rem;max-width:640px;position:relative;z-index:1;}
  .cover-sub{font-size:.95rem;color:rgba(255,255,255,.6);margin-bottom:2rem;position:relative;z-index:1;}

  .cover-stats{display:flex;background:rgba(255,255,255,.1);border:1px solid rgba(255,255,255,.18);border-radius:8px;overflow:hidden;margin-bottom:2rem;position:relative;z-index:1;}
  .stat-item{padding:.9rem 2rem;border-right:1px solid rgba(255,255,255,.15);text-align:center;}
  .stat-item:last-child{border-right:none;}
  .stat-n{font-family:'Merriweather',serif;font-size:1.8rem;color:#fff;line-height:1;}
  .stat-l{font-size:.65rem;letter-spacing:.12em;text-transform:uppercase;color:rgba(255,255,255,.5);margin-top:4px;}

  .intake-card{background:rgba(255,255,255,.1);border:1px solid rgba(255,255,255,.22);border-radius:10px;padding:1.5rem 1.75rem;margin-bottom:1.75rem;width:100%;max-width:420px;position:relative;z-index:1;text-align:left;}
  .intake-card h3{font-family:'Merriweather',serif;font-size:.95rem;color:#fff;margin-bottom:1rem;text-align:center;letter-spacing:.04em;}
  .field-row{margin-bottom:.9rem;}
  .field-row label{display:block;font-size:.75rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:rgba(255,255,255,.65);margin-bottom:.35rem;}
  .field-row input{width:100%;background:rgba(255,255,255,.12);border:1.5px solid rgba(255,255,255,.25);border-radius:var(--r);padding:.65rem .85rem;font-family:'Lato',sans-serif;font-size:.9rem;color:#fff;outline:none;transition:border-color .15s;}
  .field-row input::placeholder{color:rgba(255,255,255,.38);}
  .field-row input:focus{border-color:rgba(255,255,255,.7);background:rgba(255,255,255,.18);}
  .field-err{font-size:.75rem;color:#fca5a5;margin-top:.3rem;display:none;}

  .start-btn{background:var(--tp-white);color:var(--tp-navy);border:none;padding:1rem 3.5rem;font-family:'Lato',sans-serif;font-size:.92rem;font-weight:900;letter-spacing:.1em;text-transform:uppercase;border-radius:var(--r);cursor:pointer;position:relative;z-index:1;transition:all .2s;box-shadow:0 4px 20px rgba(0,0,0,.25);}
  .start-btn:hover{background:var(--tp-light);transform:translateY(-2px);box-shadow:0 8px 30px rgba(0,0,0,.3);}

  /* TEST */
  #test{display:none;}
  .test-header{background:var(--tp-navy);height:58px;padding:0 2rem;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100;box-shadow:0 2px 12px rgba(0,0,0,.25);}
  .hdr-left{display:flex;align-items:center;gap:12px;}
  .hdr-div{width:1px;height:28px;background:rgba(255,255,255,.2);}
  .hdr-name{font-size:.78rem;color:rgba(255,255,255,.65);}
  .hdr-prog{font-size:.82rem;color:rgba(255,255,255,.55);font-weight:300;}
  .hdr-prog strong{color:#fff;font-weight:700;}
  .prog-track{height:3px;background:var(--tp-gray-200);position:sticky;top:58px;z-index:99;}
  .prog-fill{height:100%;background:linear-gradient(90deg,var(--tp-sky),#5ba8e5);width:0%;transition:width .4s ease;}

  .test-body{max-width:860px;margin:0 auto;padding:2rem 1.5rem 7rem;}
  .sec-hdr{display:flex;align-items:center;gap:1rem;margin:2.5rem 0 1.25rem;padding-bottom:.65rem;border-bottom:2px solid var(--tp-blue);}
  .sec-hdr:first-child{margin-top:0;}
  .sec-pill{background:var(--tp-blue);color:#fff;font-size:.68rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;padding:.25rem .7rem;border-radius:3px;white-space:nowrap;}
  .sec-title{font-family:'Merriweather',serif;font-size:1.05rem;color:var(--tp-navy);}

  .q-card{background:#fff;border:1px solid var(--tp-gray-200);border-radius:var(--r);padding:1.35rem 1.5rem;margin-bottom:.85rem;transition:box-shadow .15s;}
  .q-card:hover{box-shadow:0 2px 12px rgba(26,58,92,.09);}
  .q-row{display:flex;gap:.85rem;align-items:flex-start;margin-bottom:.9rem;}
  .q-num{background:var(--tp-navy);color:#fff;font-size:.7rem;font-weight:700;padding:.2rem .5rem;border-radius:3px;flex-shrink:0;margin-top:2px;}
  .q-txt{font-size:.94rem;font-weight:700;line-height:1.5;}
  .opts{display:grid;gap:.45rem;}
  .opt{display:flex;align-items:flex-start;gap:.7rem;padding:.6rem .9rem;border:1.5px solid var(--tp-gray-200);border-radius:4px;cursor:pointer;font-size:.875rem;line-height:1.4;color:var(--tp-gray-600);transition:all .12s;user-select:none;}
  .opt:hover{border-color:var(--tp-sky);background:var(--tp-gray-50);color:var(--tp-text);}
  .opt input{display:none;}
  .opt-dot{width:15px;height:15px;border:2px solid var(--tp-gray-200);border-radius:50%;flex-shrink:0;margin-top:2px;transition:all .12s;}
  .opt.sel{border-color:var(--tp-blue);background:#eef5fc;color:var(--tp-navy);font-weight:700;}
  .opt.sel .opt-dot{border-color:var(--tp-blue);background:var(--tp-blue);box-shadow:inset 0 0 0 3px #fff;}
  .opt.c-ans{border-color:var(--tp-correct);background:var(--tp-correct-bg);color:var(--tp-correct);font-weight:700;}
  .opt.w-ans{border-color:var(--tp-wrong);background:var(--tp-wrong-bg);color:var(--tp-wrong);text-decoration:line-through;}
  .opt.sh-ans{border-color:var(--tp-correct);background:var(--tp-correct-bg);color:var(--tp-correct);font-weight:700;}
  .q-card.ua-border{border-left:4px solid #f59e0b;}

  .sub-bar{position:fixed;bottom:0;left:0;right:0;background:#fff;border-top:1px solid var(--tp-gray-200);padding:.9rem 2rem;display:flex;align-items:center;justify-content:space-between;gap:1rem;box-shadow:0 -3px 16px rgba(26,58,92,.1);z-index:200;}
  .ua-lbl{font-size:.85rem;color:var(--tp-gray-600);}
  .ua-lbl strong{color:var(--tp-text);}
  .sub-btn{background:var(--tp-blue);color:#fff;border:none;padding:.7rem 2.2rem;font-family:'Lato',sans-serif;font-size:.88rem;font-weight:900;letter-spacing:.08em;text-transform:uppercase;border-radius:var(--r);cursor:pointer;transition:all .2s;}
  .sub-btn:hover{background:var(--tp-navy);transform:translateY(-1px);}
  .sub-btn:disabled{opacity:.5;cursor:not-allowed;transform:none;}

  /* RESULTS */
  #results{display:none;}
  .res-hero{background:linear-gradient(160deg,var(--tp-navy) 0%,var(--tp-blue) 100%);padding:3.5rem 2rem 2.5rem;text-align:center;position:relative;overflow:hidden;}
  .res-hero::before{content:'';position:absolute;top:-80px;right:-80px;width:320px;height:320px;border-radius:50%;background:rgba(255,255,255,.05);}
  .res-logo-box{background:#fff;display:inline-block;border-radius:8px;padding:.9rem 1.6rem .7rem;margin-bottom:1.5rem;box-shadow:0 4px 20px rgba(0,0,0,.2);position:relative;z-index:1;}
  .res-candidate{font-size:.85rem;color:rgba(255,255,255,.65);margin-bottom:.5rem;position:relative;z-index:1;}
  .res-candidate strong{color:#fff;}
  .res-eye{font-size:.72rem;letter-spacing:.2em;text-transform:uppercase;color:rgba(255,255,255,.6);margin-bottom:.6rem;position:relative;z-index:1;}
  .res-score{font-family:'Merriweather',serif;font-size:clamp(3.5rem,10vw,6rem);color:#fff;line-height:1;position:relative;z-index:1;}
  .res-score span{color:var(--tp-light);}
  .res-pct{font-family:'Merriweather',serif;font-size:1.25rem;color:rgba(255,255,255,.7);margin-top:.5rem;position:relative;z-index:1;}
  .res-grade{display:inline-block;margin-top:1.25rem;padding:.5rem 1.75rem;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.3);border-radius:999px;font-size:.9rem;color:#fff;font-weight:700;letter-spacing:.05em;position:relative;z-index:1;}

  .email-status{margin:1rem 1.5rem 0;padding:.75rem 1rem;border-radius:var(--r);font-size:.85rem;font-weight:700;text-align:center;display:none;}
  .email-status.sending{background:#e0f0ff;color:#1a3a5c;display:block;}
  .email-status.sent{background:var(--tp-correct-bg);color:var(--tp-correct);display:block;}
  .email-status.failed{background:var(--tp-wrong-bg);color:var(--tp-wrong);display:block;}

  .res-body{max-width:860px;margin:0 auto;padding:2rem 1.5rem 4rem;}
  .sc-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:1rem;margin-bottom:2rem;}
  .sc-card{background:#fff;border:1px solid var(--tp-gray-200);border-radius:var(--r);padding:1.25rem 1rem;text-align:center;}
  .sc-n{font-family:'Merriweather',serif;font-size:2.2rem;line-height:1;margin-bottom:.35rem;}
  .sc-l{font-size:.7rem;text-transform:uppercase;letter-spacing:.1em;color:var(--tp-gray-400);}
  .sc-ok .sc-n{color:var(--tp-correct);} .sc-bad .sc-n{color:var(--tp-wrong);} .sc-sk .sc-n{color:var(--tp-warn);} .sc-pt .sc-n{color:var(--tp-blue);}

  .sec-tbl{background:#fff;border:1px solid var(--tp-gray-200);border-radius:var(--r);overflow:hidden;margin-bottom:1.5rem;}
  .sec-tbl-hd{background:var(--tp-navy);color:#fff;padding:.85rem 1.5rem;font-size:.82rem;font-weight:700;letter-spacing:.07em;text-transform:uppercase;}
  .st-row{display:flex;align-items:center;padding:.8rem 1.5rem;border-bottom:1px solid var(--tp-gray-100);gap:1rem;}
  .st-row:last-child{border-bottom:none;}
  .st-nm{flex:1;font-size:.875rem;font-weight:700;}
  .st-fr{font-family:'Merriweather',serif;font-size:.95rem;color:var(--tp-navy);min-width:48px;text-align:right;}
  .st-bw{flex:2;height:7px;background:var(--tp-gray-100);border-radius:999px;overflow:hidden;}
  .st-bf{height:100%;background:linear-gradient(90deg,var(--tp-blue),var(--tp-sky));border-radius:999px;transition:width .7s ease .2s;}
  .st-pc{font-size:.8rem;color:var(--tp-gray-400);min-width:38px;text-align:right;}

  .act-btns{display:flex;flex-direction:column;gap:.75rem;}
  .btn-p{display:block;width:100%;background:var(--tp-blue);color:#fff;border:none;padding:.95rem;font-family:'Lato',sans-serif;font-size:.92rem;font-weight:900;letter-spacing:.07em;text-transform:uppercase;border-radius:var(--r);cursor:pointer;transition:all .2s;}
  .btn-p:hover{background:var(--tp-navy);}
  .btn-o{display:block;width:100%;background:transparent;color:var(--tp-blue);border:2px solid var(--tp-blue);padding:.85rem;font-family:'Lato',sans-serif;font-size:.92rem;font-weight:900;letter-spacing:.07em;text-transform:uppercase;border-radius:var(--r);cursor:pointer;transition:all .2s;}
  .btn-o:hover{background:var(--tp-blue);color:#fff;}
  .footer-bar{text-align:center;padding:1.25rem;border-top:1px solid var(--tp-gray-200);font-size:.75rem;color:var(--tp-gray-400);background:#fff;}

  @media(max-width:600px){
    .test-header{padding:0 1rem;} .hdr-name,.hdr-div{display:none;}
    .test-body{padding:1.25rem .85rem 7rem;}
    .sub-bar{flex-direction:column;align-items:stretch;} .ua-lbl{text-align:center;}
    .cover-stats{flex-direction:column;}
    .stat-item{border-right:none;border-bottom:1px solid rgba(255,255,255,.15);}
    .stat-item:last-child{border-bottom:none;}
    .intake-card{padding:1.1rem;}
  }
</style>
</head>
<body>

<!-- ══ COVER ══ -->
<div id="cover">
  <div class="cover-logo-card">
    <svg width="260" height="72" viewBox="0 0 260 72" xmlns="http://www.w3.org/2000/svg">
      <rect x="2" y="32" width="26" height="28" fill="#1a3a5c"/>
      <polygon points="2,32 15,16 28,32" fill="#1e5799"/>
      <rect x="6" y="40" width="7" height="9" fill="#fff" opacity=".9"/>
      <rect x="17" y="40" width="6" height="7" fill="#d6e8f7" opacity=".85"/>
      <rect x="9" y="52" width="8" height="8" fill="#3a7fc1" opacity=".45"/>
      <rect x="30" y="22" width="30" height="38" fill="#1e5799"/>
      <polygon points="30,22 45,6 60,22" fill="#1a3a5c"/>
      <rect x="34" y="30" width="8" height="10" fill="#fff" opacity=".9"/>
      <rect x="46" y="30" width="8" height="10" fill="#d6e8f7" opacity=".85"/>
      <rect x="34" y="44" width="8" height="9" fill="#fff" opacity=".7"/>
      <rect x="46" y="44" width="8" height="9" fill="#d6e8f7" opacity=".7"/>
      <rect x="38" y="55" width="10" height="5" fill="#3a7fc1" opacity=".45"/>
      <rect x="62" y="28" width="24" height="32" fill="#1a3a5c"/>
      <polygon points="62,28 74,14 86,28" fill="#1e5799"/>
      <rect x="65" y="36" width="7" height="9" fill="#fff" opacity=".9"/>
      <rect x="75" y="36" width="7" height="9" fill="#d6e8f7" opacity=".85"/>
      <rect x="67" y="50" width="8" height="10" fill="#3a7fc1" opacity=".45"/>
      <rect x="0" y="60" width="92" height="3" rx="1" fill="#1a3a5c" opacity=".5"/>
      <text x="130" y="38" text-anchor="middle" font-family="Georgia,serif" font-size="18" font-weight="700" fill="#1a3a5c" letter-spacing="5">TOWNE</text>
      <text x="130" y="54" text-anchor="middle" font-family="Arial,sans-serif" font-size="9" fill="#3a7fc1" letter-spacing="6">PROPERTIES</text>
      <line x1="95" y1="64" x2="165" y2="64" stroke="#c8d6e5" stroke-width="1"/>
      <text x="130" y="72" text-anchor="middle" font-family="Arial,sans-serif" font-size="6.5" fill="#8098b4" letter-spacing="3">CINCINNATI, OHIO · EST. 1961</text>
    </svg>
  </div>

  <span class="cover-badge">Confidential · Human Resources</span>
  <h1 class="cover-title">Regional Manager Interview Assessment</h1>
  <p class="cover-sub">LIHTC &nbsp;·&nbsp; HUD PBV &nbsp;·&nbsp; OHFA Compliance Knowledge Evaluation</p>

  <div class="cover-stats">
    <div class="stat-item"><div class="stat-n">90</div><div class="stat-l">Questions</div></div>
    <div class="stat-item"><div class="stat-n">9</div><div class="stat-l">Sections</div></div>
    <div class="stat-item"><div class="stat-n">MC</div><div class="stat-l">Format</div></div>
  </div>

  <div class="intake-card">
    <h3>Candidate Information</h3>
    <div class="field-row">
      <label for="candidateName">Full Name</label>
      <input type="text" id="candidateName" placeholder="First Last" autocomplete="name">
      <div class="field-err" id="nameErr">Please enter your full name.</div>
    </div>
    <div class="field-row">
      <label for="candidateEmail">Email Address</label>
      <input type="email" id="candidateEmail" placeholder="you@email.com" autocomplete="email">
      <div class="field-err" id="emailErr">Please enter a valid email address.</div>
    </div>
  </div>

  <button class="start-btn" onclick="validateAndStart()">Begin Assessment →</button>
</div>

<!-- ══ TEST ══ -->
<div id="test">
  <div class="test-header">
    <div class="hdr-left">
      <svg width="110" height="36" viewBox="0 0 110 36" xmlns="http://www.w3.org/2000/svg">
        <rect x="1" y="14" width="14" height="16" fill="rgba(255,255,255,.8)"/>
        <polygon points="1,14 8,5 15,14" fill="rgba(214,232,247,.9)"/>
        <rect x="3" y="18" width="5" height="6" fill="rgba(255,255,255,.5)"/>
        <rect x="17" y="9" width="16" height="21" fill="rgba(255,255,255,.85)"/>
        <polygon points="17,9 25,1 33,9" fill="rgba(214,232,247,.9)"/>
        <rect x="20" y="14" width="5" height="6" fill="rgba(255,255,255,.5)"/>
        <rect x="27" y="14" width="5" height="6" fill="rgba(214,232,247,.5)"/>
        <rect x="35" y="12" width="13" height="18" fill="rgba(255,255,255,.8)"/>
        <polygon points="35,12 41,4 48,12" fill="rgba(214,232,247,.9)"/>
        <rect x="37" y="16" width="5" height="6" fill="rgba(255,255,255,.5)"/>
        <rect x="0" y="30" width="50" height="2" fill="rgba(255,255,255,.25)"/>
        <text x="57" y="20" font-family="Georgia,serif" font-size="9" font-weight="700" fill="#fff" letter-spacing="2">TOWNE</text>
        <text x="57" y="30" font-family="Arial,sans-serif" font-size="5.5" fill="rgba(255,255,255,.6)" letter-spacing="2.5">PROPERTIES</text>
      </svg>
      <div class="hdr-div"></div>
      <span class="hdr-name" id="hdrName">Regional Manager Assessment</span>
    </div>
    <span class="hdr-prog"><strong id="answeredCt">0</strong> / <span id="totalCt">90</span> answered</span>
  </div>
  <div class="prog-track"><div class="prog-fill" id="progFill"></div></div>
  <div class="test-body" id="testBody"></div>
  <div class="sub-bar">
    <span class="ua-lbl" id="uaLbl"><strong>90</strong> questions remaining</span>
    <button class="sub-btn" id="subBtn" onclick="submitTest()">Submit Assessment</button>
  </div>
</div>

<!-- ══ RESULTS ══ -->
<div id="results">
  <div class="res-hero">
    <div class="res-logo-box">
      <svg width="180" height="52" viewBox="0 0 180 52" xmlns="http://www.w3.org/2000/svg">
        <rect x="1" y="20" width="18" height="22" fill="#1a3a5c"/>
        <polygon points="1,20 10,8 19,20" fill="#1e5799"/>
        <rect x="4" y="26" width="6" height="8" fill="#fff" opacity=".85"/>
        <rect x="22" y="12" width="22" height="30" fill="#1e5799"/>
        <polygon points="22,12 33,1 44,12" fill="#1a3a5c"/>
        <rect x="25" y="20" width="7" height="8" fill="#fff" opacity=".9"/>
        <rect x="35" y="20" width="7" height="8" fill="#d6e8f7" opacity=".85"/>
        <rect x="47" y="16" width="18" height="26" fill="#1a3a5c"/>
        <polygon points="47,16 56,5 65,16" fill="#1e5799"/>
        <rect x="50" y="22" width="6" height="8" fill="#fff" opacity=".85"/>
        <rect x="0" y="42" width="67" height="2" fill="#1a3a5c" opacity=".4"/>
        <text x="78" y="26" font-family="Georgia,serif" font-size="13" font-weight="700" fill="#1a3a5c" letter-spacing="3">TOWNE</text>
        <text x="78" y="40" font-family="Arial,sans-serif" font-size="7" fill="#3a7fc1" letter-spacing="3.5">PROPERTIES</text>
      </svg>
    </div>
    <div class="res-candidate">Candidate: <strong id="resName">—</strong></div>
    <div class="res-eye">Assessment Complete</div>
    <div class="res-score" id="resScore">—</div>
    <div class="res-pct" id="resPct"></div>
    <div class="res-grade" id="resGrade"></div>
  </div>

  <div class="email-status" id="emailStatus"></div>

  <div class="res-body">
    <div class="sc-grid" id="scGrid"></div>
    <div class="sec-tbl">
      <div class="sec-tbl-hd">Section Performance Breakdown</div>
      <div id="secRows"></div>
    </div>
    <div class="act-btns">
      <button class="btn-p" onclick="reviewAnswers()">Review My Answers</button>
      <button class="btn-o" onclick="retakeTest()">Retake Assessment</button>
    </div>
  </div>
  <div class="footer-bar">© Towne Properties &nbsp;·&nbsp; Confidential Assessment &nbsp;·&nbsp; For Internal Use Only</div>
</div>

<script>
// ── EmailJS config ── replace these after following the hosting guide
const EMAILJS_PUBLIC_KEY  = 'l032ox5AvvxQC56Ve';
const EMAILJS_SERVICE_ID  = 'service_gn00n0d';
const EMAILJS_TEMPLATE_ID = 'template_csydyj4';
const RESULTS_EMAIL       = 'sam@mainhigh.com';

(function(){ try{ emailjs.init({publicKey:EMAILJS_PUBLIC_KEY}); }catch(e){} })();

// ── Question bank (90 questions, revised per updated document) ──
const Q = [
  // ── SECTION 1: LIHTC Advanced Compliance (12 questions) ──
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"When calculating LIHTC rent, which approach is correct?",o:["Use market rent minus utilities","Use AMI limits, multiply by 30%, subtract utility allowance","Use tenant income directly","Use contract rent from PHA"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"If a tenant becomes over-income, what is the correct action?",o:["Immediate eviction","Raise rent to market","Apply Available Unit Rule","Terminate tax credit status"],a:2},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"What is the biggest operational risk with the Average Income Test?",o:["Rent overcharging","Losing entire building compliance if average exceeds limit","Tenant turnover","Inspection failures"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"Incorrect initial income qualification requires:",o:["Ignore if minor","Evict tenant immediately","Report and correct, potential 8823","Recalculate rent only"],a:2},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"What is the first step in a LIHTC audit?",o:["Check maintenance logs","Review rent roll","Review tenant files and certifications","Check marketing"],a:2},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"What is the most common LIHTC error?",o:["Late rent","Incorrect income calculation","Maintenance delay","Lease errors only"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"Utility allowance consistency requires:",o:["Each site chooses freely","Annual review and documented method","Only HUD approval","Tenant selection"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"What is the lease-up compliance priority?",o:["Fill units fast","Proper income qualification upfront","Offer discounts","Skip verifications temporarily"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"What is the key document in a file audit?",o:["Lease only","TIC and verifications","Maintenance tickets","Marketing plan"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"What is the student eligibility risk?",o:["Rent increase","Entire unit ineligible if violated","Maintenance issue","Waitlist issue"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"Extended use compliance means:",o:["No rules apply","Continued rent and income restrictions","Only inspections matter","Only PHA rules apply"],a:1},
  {s:"Section 1",st:"LIHTC Advanced Compliance",q:"Preventing 8823s during lease-up requires:",o:["Speed leasing","Strong file review before move-in","Marketing only","Rent discounts"],a:1},

  // ── SECTION 2: HUD PBV Execution (12 questions) ──
  {s:"Section 2",st:"HUD PBV Execution",q:"The PBV lifecycle starts with:",o:["Lease signing","Waitlist selection","Inspection","Rent payment"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"Rent reasonableness must be:",o:["Done once","Documented and comparable","Based on tenant income","Ignored for PBV"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"Tenant rent errors often come from:",o:["Maintenance","Incorrect adjusted income","Lease terms","Waitlist issues"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"An interim recertification is triggered by:",o:["Lease renewal only","Income changes","Inspection","Marketing"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"EIV is used to:",o:["Set rent","Verify income discrepancies","Manage waitlist","Inspect units"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"How should an income increase be handled?",o:["Ignore until annual","Process interim recertification","Evict tenant","Raise contract rent"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"PHA coordination requires:",o:["No communication","Regular compliance alignment","Tenant communication only","Maintenance reporting only"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"HAP errors require:",o:["Ignore","Adjustment and repayment","Eviction","Lease change"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"Adjusted income includes:",o:["Gross income only","Deductions applied","Rent only","Market rate"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"File standards must be:",o:["Minimal","Audit-ready","Optional","Tenant-managed"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"PHA audit prep includes:",o:["Cleaning units","File review and corrections","Marketing","Leasing"],a:1},
  {s:"Section 2",st:"HUD PBV Execution",q:"PBV compliance control requires:",o:["None","Standardized processes and audits","Tenant-led","Maintenance only"],a:1},

  // ── SECTION 3: Income Qualification (10 questions) ──
  {s:"Section 3",st:"Income Qualification",q:"What is the first step in verifying income?",o:["Estimate","Collect documentation","Set rent","Approve tenant"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"What is the best verification method?",o:["Verbal","Third-party written","Tenant estimate","Online guess"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"Asset income includes:",o:["Rent only","Actual or imputed income","Salary only","None"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"Self-employment requires:",o:["Ignore","Detailed review of records","Flat estimate","Denial"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"What is a common income qualification error?",o:["Maintenance delay","Miscalculation of income","Lease timing","Marketing"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"Consistency in income qualification is ensured by:",o:["Each site decides","Standard policy and training","Tenant input","PHA only"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"What is a red flag during income verification?",o:["High income","Missing verification","Full file","Lease signed"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"Training staff on income compliance requires:",o:["Minimal effort","Structured compliance training","Ignore","Tenant input"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"What documentation is required for income qualification?",o:["Lease only","Full verification and certification","Maintenance logs","Marketing"],a:1},
  {s:"Section 3",st:"Income Qualification",q:"If verification is missing after move-in:",o:["Ignore","Correct and document immediately","Evict","Raise rent"],a:1},

  // ── SECTION 4: NSPIRE (6 questions) ──
  {s:"Section 4",st:"NSPIRE",q:"What is the best NSPIRE prep strategy?",o:["Last-minute fixes","Ongoing maintenance standards","Ignore","Tenant responsibility"],a:1},
  {s:"Section 4",st:"NSPIRE",q:"Avoiding NSPIRE deficiencies requires:",o:["Inspect annually only","Routine inspections and tracking","Ignore","Outsource only"],a:1},
  {s:"Section 4",st:"NSPIRE",q:"The correct response to a failed inspection is:",o:["Ignore","Correct deficiencies quickly and track","Evict tenants","Raise rent"],a:1},
  {s:"Section 4",st:"NSPIRE",q:"How should corrections be tracked?",o:["None","Systematic tracking system","Verbal only","Tenant reports"],a:1},
  {s:"Section 4",st:"NSPIRE",q:"What is the impact of NSPIRE changes?",o:["Less strict","More focus on health and safety","No change","Rent-based"],a:1},
  {s:"Section 4",st:"NSPIRE",q:"Maintenance training should:",o:["None","Align with NSPIRE standards","Tenant-led","Optional"],a:1},

  // ── SECTION 5: OHFA (10 questions) ──
  {s:"Section 5",st:"OHFA",q:"OHFA audit prep includes:",o:["Cleaning only","File and physical readiness","Marketing","Leasing"],a:1},
  {s:"Section 5",st:"OHFA",q:"Common OHFA findings include:",o:["Landscaping","File errors and income issues","Rent only","Waitlist"],a:1},
  {s:"Section 5",st:"OHFA",q:"What is the purpose of a mock audit?",o:["Marketing","Identify compliance gaps","Leasing","Rent setting"],a:1},
  {s:"Section 5",st:"OHFA",q:"Correction timelines require:",o:["Ignore","Prompt correction and documentation","Delay","Tenant responsibility"],a:1},
  {s:"Section 5",st:"OHFA",q:"OHFA reporting includes:",o:["None","Annual certifications and compliance reports","Rent only","Marketing"],a:1},
  {s:"Section 5",st:"OHFA",q:"How does OHFA differ from other oversight?",o:["None","Stricter monitoring expectations","Less strict","Only physical inspections"],a:1},
  {s:"Section 5",st:"OHFA",q:"How often should internal audits occur?",o:["Never","Regular (at least annually or more)","Once per decade","Tenant-led"],a:1},
  {s:"Section 5",st:"OHFA",q:"Compliance systems require:",o:["None","Structured oversight and audits","Tenant-based","Maintenance only"],a:1},
  {s:"Section 5",st:"OHFA",q:"Staff alignment on compliance requires:",o:["Ignore","Training and accountability","Tenant input","Marketing"],a:1},
  {s:"Section 5",st:"OHFA",q:"Repeat OHFA findings require:",o:["Ignore","Root cause correction","Blame staff","Raise rent"],a:1},

  // ── SECTION 6: MOR (5 questions) ──
  {s:"Section 6",st:"MOR",q:"MOR prep requires:",o:["Cleaning","Full compliance audit","Marketing","Leasing"],a:1},
  {s:"Section 6",st:"MOR",q:"Priority review during MOR focuses on:",o:["Landscaping","Files and certifications","Rent only","Waitlist"],a:1},
  {s:"Section 6",st:"MOR",q:"Common MOR findings include:",o:["Paint issues","Documentation errors","Landscaping","Parking"],a:1},
  {s:"Section 6",st:"MOR",q:"Response to MOR findings requires:",o:["Ignore","Correct and implement controls","Delay","Tenant-led"],a:1},
  {s:"Section 6",st:"MOR",q:"Long-term compliance after MOR requires:",o:["None","Ongoing monitoring","Ignore","Lease changes"],a:1},

  // ── SECTION 7: PBV Waitlist & Leasing Control (15 questions) ──
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Waitlist establishment must include:",o:["Verbal tracking","Written policy, opening/closing procedures, and documentation","Tenant selection only","Marketing plan"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Fair housing compliance in waitlists requires:",o:["Owner discretion","Consistent and non-discriminatory selection order","First come only without documentation","Preference to higher income"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"When pulling from a PBV waitlist, you must:",o:["Choose best applicant","Follow documented order and eligibility screening","Skip documentation","Ask PHA to choose randomly"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Proper waitlist documentation includes:",o:["Names only","Timestamped entries and actions","Verbal notes","Lease copies"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"If an applicant is unresponsive, best practice is:",o:["Skip immediately","Follow written outreach policy and document attempts","Remove without documentation","Keep indefinitely"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Who ultimately controls PBV eligibility approval?",o:["Owner","PHA","Tenant","Maintenance"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"A waitlist audit should show:",o:["Only current tenants","Full history of additions, removals, and selections","Lease terms","Rent rolls only"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Communication with applicants should be:",o:["Sporadic","Consistent and documented","Verbal only","Tenant-initiated only"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"A major compliance risk with waitlists is:",o:["Vacancy","Fair housing violations and inconsistent selection","Rent errors","Maintenance"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Correcting a poorly managed waitlist requires:",o:["Ignoring past issues","Reconstructing and documenting a compliant process","Deleting all applicants","Letting PHA handle entirely"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"When opening a waitlist, you must:",o:["Notify selectively","Publicly advertise and follow policy","Only notify current tenants","Skip documentation"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Preferences in PBV waitlists must be:",o:["Informal","PHA-approved and consistently applied","Owner-created anytime","Ignored"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Denial from waitlist must include:",o:["Verbal notice","Written notice and reason with appeal rights","No notice","Lease only"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Tracking waitlist movement requires:",o:["Memory","Software or log with audit trail","Tenant input","Lease file only"],a:1},
  {s:"Section 7",st:"PBV Waitlist & Leasing Control",q:"Coordination with PHA on waitlist requires:",o:["None","Alignment on eligibility, referrals, and approvals","Tenant communication only","Maintenance reports"],a:1},

  // ── SECTION 8: PBV Advanced Operations (15 questions — REVISED with HUD-92458) ──
  {s:"Section 8",st:"PBV Advanced Operations",q:"The HUD-92458 Rent Schedule is primarily used to:",o:["Track tenant payments","Establish and approve contract rents for HUD-assisted properties","Calculate utility allowances","Manage waitlists"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"When preparing a HUD-92458, rent comparability must be:",o:["Estimated by owner","Supported by market data and comparable units","Based on tenant income","Ignored for PBV"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"An incorrect HUD-92458 submission can result in:",o:["Faster approvals","Delays or rejection of rent approval","Higher rents automatically","Tenant eviction"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"Who typically reviews and approves the HUD-92458?",o:["Property manager","HUD or Contract Administrator","Tenant","Maintenance supervisor"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"Best practice when updating a HUD-92458 is:",o:["Reuse old data","Ensure current market comps and accurate unit data","Skip documentation","Only update rent totals"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"A PBV unit cannot be leased without:",o:["Lease only","Passed inspection and executed HAP contract","Rent payment","Waitlist only"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"If rent reasonableness fails, you must:",o:["Lease anyway","Adjust rent to compliant level","Ignore","Charge tenant more"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"PBV inspections must occur:",o:["Once only","Before move-in and periodically thereafter","Only after complaints","Never"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"A failed HQS/NSPIRE item requires:",o:["Ignore","Correction before assistance begins or continues","Tenant payment","Lease change"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"If HAP is overpaid, you must:",o:["Ignore","Repay and correct records","Evict tenant","Raise rent"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"Tenant portion increases when:",o:["Rent decreases","Income increases through recertification","Inspection fails","Waitlist changes"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"A key internal control for PBV is:",o:["Verbal processes","Standardized file review and approval steps","Tenant-led review","Maintenance logs"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"PBV lease-up risk includes:",o:["Vacancy only","Leasing before approvals/inspections complete","Rent collection","Marketing"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"A PHA file discrepancy requires:",o:["Ignore","Immediate reconciliation and documentation","Eviction","Lease change"],a:1},
  {s:"Section 8",st:"PBV Advanced Operations",q:"Strong PBV oversight requires:",o:["Minimal review","Ongoing audits, training, and coordination with PHA","Tenant management","Maintenance only"],a:1},

  // ── SECTION 9: Scenario-Based Questions (15 questions) ──
  {s:"Section 9",st:"Scenario-Based Questions",q:"You discover incorrect income files across several units. You should:",o:["Ignore","Audit and correct all","Evict","Raise rent"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"A property fails NSPIRE inspection. Your first action is:",o:["Ignore","Develop an immediate correction plan","Evict","Change leases"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"OHFA issues findings. You should:",o:["Ignore","Correct and implement controls","Delay","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"PHA challenges your compliance records. You should:",o:["Ignore","Provide a documented compliance trail","Argue verbally","Evict"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"Processes are inconsistent across your portfolio. You should:",o:["Ignore","Standardize across all sites","Let each site decide","Let tenants decide"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"A tenant refuses to recertify. You should:",o:["Ignore","Follow enforcement procedures","Raise rent","Evict immediately"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"A utility allowance error is discovered. You should:",o:["Ignore","Correct and retroactively fix","Raise rent","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"Staff are making recurring compliance errors. You should:",o:["Ignore","Retrain and monitor","Fire immediately","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"A waitlist audit reveals documentation gaps. You should:",o:["Ignore","Reconstruct documentation","Delete the list","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"You identify a risk of noncompliance at a property. You should:",o:["Ignore","Intervene immediately","Delay action","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"You take over a new noncompliant property. You should:",o:["Ignore","Create a 30/60/90-day compliance plan","Change all leases","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"A tenant has fluctuating income throughout the year. You should:",o:["Ignore","Use proper interim and annual certification handling","Raise rent","Evict"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"EIV shows a discrepancy with tenant-reported income. You should:",o:["Ignore","Investigate and resolve","Evict","Raise rent"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"Multiple audits are scheduled simultaneously. You should:",o:["Ignore","Prioritize and prepare for both","Delay all","Let tenants handle"],a:1},
  {s:"Section 9",st:"Scenario-Based Questions",q:"How do you build a culture of compliance at your properties?",o:["None","Implement training, systems, and accountability","Ignore","Let tenants handle"],a:1},
];

const L=['A','B','C','D'];
let ans=new Array(Q.length).fill(null);
let isDone=false, candidateName='', candidateEmail='';

function validateAndStart(){
  const n=document.getElementById('candidateName').value.trim();
  const e=document.getElementById('candidateEmail').value.trim();
  let ok=true;
  document.getElementById('nameErr').style.display='none';
  document.getElementById('emailErr').style.display='none';
  if(!n){document.getElementById('nameErr').style.display='block';ok=false;}
  if(!e||!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(e)){document.getElementById('emailErr').style.display='block';ok=false;}
  if(!ok)return;
  candidateName=n; candidateEmail=e;
  document.getElementById('cover').style.display='none';
  document.getElementById('test').style.display='block';
  document.getElementById('hdrName').textContent=n;
  document.getElementById('totalCt').textContent=Q.length;
  buildTest();
}

function buildTest(){
  const body=document.getElementById('testBody');
  body.innerHTML=''; let curS='';
  Q.forEach((q,i)=>{
    if(q.s!==curS){
      curS=q.s;
      const h=document.createElement('div');
      h.className='sec-hdr';
      h.innerHTML=`<span class="sec-pill">${q.s}</span><span class="sec-title">${q.st}</span>`;
      body.appendChild(h);
    }
    const card=document.createElement('div');
    card.className='q-card'; card.id=`c${i}`;
    card.innerHTML=`<div class="q-row"><span class="q-num">${i+1}</span><span class="q-txt">${q.q}</span></div><div class="opts">${q.o.map((o,j)=>`<label class="opt" id="o${i}${j}" onclick="pick(${i},${j})"><input type="radio" name="q${i}"><span class="opt-dot"></span><span>${L[j]}. ${o}</span></label>`).join('')}</div>`;
    body.appendChild(card);
  });
  tick();
}

function pick(qi,oi){
  if(isDone)return;
  ans[qi]=oi;
  for(let j=0;j<4;j++){const l=document.getElementById(`o${qi}${j}`);if(l)l.classList.toggle('sel',j===oi);}
  tick();
}

function tick(){
  const d=ans.filter(a=>a!==null).length, left=Q.length-d;
  document.getElementById('answeredCt').textContent=d;
  document.getElementById('progFill').style.width=`${d/Q.length*100}%`;
  document.getElementById('uaLbl').innerHTML=left===0?'<strong>All questions answered ✓</strong>':`<strong>${left}</strong> question${left!==1?'s':''} remaining`;
}

function submitTest(){
  isDone=true;
  document.getElementById('subBtn').disabled=true;
  showResults();
}

function showResults(){
  document.getElementById('test').style.display='none';
  document.getElementById('results').style.display='block';
  let c=0,w=0,sk=0;
  Q.forEach((q,i)=>{if(ans[i]===null)sk++;else if(ans[i]===q.a)c++;else w++;});
  const pct=Math.round(c/Q.length*100);
  const grades=[[90,'Excellent — Outstanding Performance'],[80,'Strong — Above Average'],[70,'Satisfactory — Meets Expectations'],[60,'Marginal — Below Expectations'],[0,'Needs Improvement']];
  const grade=grades.find(([t])=>pct>=t)[1];
  document.getElementById('resName').textContent=candidateName;
  document.getElementById('resScore').innerHTML=`${c}<span>/${Q.length}</span>`;
  document.getElementById('resPct').textContent=`${pct}% Correct`;
  document.getElementById('resGrade').textContent=grade;
  document.getElementById('scGrid').innerHTML=`<div class="sc-card sc-ok"><div class="sc-n">${c}</div><div class="sc-l">Correct</div></div><div class="sc-card sc-bad"><div class="sc-n">${w}</div><div class="sc-l">Incorrect</div></div><div class="sc-card sc-sk"><div class="sc-n">${sk}</div><div class="sc-l">Skipped</div></div><div class="sc-card sc-pt"><div class="sc-n">${pct}%</div><div class="sc-l">Score</div></div>`;
  const secs={};
  Q.forEach((q,i)=>{if(!secs[q.s])secs[q.s]={t:q.st,c:0,tot:0};secs[q.s].tot++;if(ans[i]===q.a)secs[q.s].c++;});
  document.getElementById('secRows').innerHTML=Object.entries(secs).map(([,d])=>{const p=Math.round(d.c/d.tot*100);return`<div class="st-row"><span class="st-nm">${d.t}</span><span class="st-fr">${d.c}/${d.tot}</span><div class="st-bw"><div class="st-bf" style="width:${p}%"></div></div><span class="st-pc">${p}%</span></div>`;}).join('');
  const secBreakdown=Object.entries(secs).map(([,d])=>{const p=Math.round(d.c/d.tot*100);return`${d.t}: ${d.c}/${d.tot} (${p}%)`;}).join('\n');
  sendResultsEmail({name:candidateName,email:candidateEmail,score:`${c}/${Q.length}`,pct:`${pct}%`,grade,correct:c,wrong:w,skipped:sk,breakdown:secBreakdown,date:new Date().toLocaleString()});
}

function sendResultsEmail(data){
  const st=document.getElementById('emailStatus');
  st.style.display='block';
  st.className='email-status sending';
  st.textContent='⏳ Attempting to send email — please wait…';

  // Log config to confirm values loaded
  console.log('EmailJS config:', EMAILJS_PUBLIC_KEY, EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ID);

  const params = {
    to_email: RESULTS_EMAIL,
    reply_to: data.email,
    candidate_name: data.name,
    candidate_email: data.email,
    score: data.score,
    percentage: data.pct,
    grade: data.grade,
    correct: String(data.correct),
    wrong: String(data.wrong),
    skipped: String(data.skipped),
    breakdown: data.breakdown,
    date_taken: data.date
  };

  try {
    emailjs.init({publicKey: EMAILJS_PUBLIC_KEY});
    emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ID, params)
      .then(function(resp){
        st.className='email-status sent';
        st.textContent='✅ Email sent! Status: '+resp.status+' / '+resp.text;
      }, function(err){
        st.className='email-status failed';
        st.textContent='❌ EmailJS error: status='+err.status+' text='+err.text+' | '+JSON.stringify(err);
      });
  } catch(e) {
    st.className='email-status failed';
    st.textContent='❌ JS Exception: '+e.message;
  }
}

function reviewAnswers(){
  document.getElementById('results').style.display='none';
  document.getElementById('test').style.display='block';
  Q.forEach((q,i)=>{
    const card=document.getElementById(`c${i}`);if(!card)return;
    card.classList.remove('ua-border');
    q.o.forEach((_,j)=>{
      const l=document.getElementById(`o${i}${j}`);if(!l)return;
      l.classList.remove('sel','c-ans','w-ans','sh-ans');
      if(ans[i]===null){card.classList.add('ua-border');if(j===q.a)l.classList.add('sh-ans');}
      else if(j===ans[i]&&ans[i]!==q.a)l.classList.add('w-ans');
      else if(j===q.a)l.classList.add('c-ans');
    });
  });
  document.querySelector('.sub-bar').innerHTML=`<span class="ua-lbl"><span style="color:#1a6b3a;font-weight:700">■</span> Correct &nbsp;|&nbsp; <span style="color:#9b1c1c;font-weight:700">■</span> Your wrong answer &nbsp;|&nbsp; <span style="color:#f59e0b;font-weight:700">■</span> Skipped</span><button class="sub-btn" onclick="document.getElementById('test').style.display='none';document.getElementById('results').style.display='block'">← Back to Results</button>`;
}

function retakeTest(){
  ans=new Array(Q.length).fill(null); isDone=false;
  document.getElementById('results').style.display='none';
  document.getElementById('test').style.display='block';
  document.querySelector('.sub-bar').innerHTML=`<span class="ua-lbl" id="uaLbl"><strong>${Q.length}</strong> questions remaining</span><button class="sub-btn" id="subBtn" onclick="submitTest()">Submit Assessment</button>`;
  buildTest();
}
</script>
</body>
</html>
