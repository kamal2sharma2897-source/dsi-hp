<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HP Police — DSI Portal</title>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@600;700&family=Noto+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{--navy:#0a1628;--blue:#1a3a6b;--accent:#c8a84b;--gold:#e2c46a;--green:#1a6b3a;--red:#c0392b;--light:#f0f4f8;--muted:#6b7d95;--border:#cdd4dc;--sh:0 2px 16px rgba(10,22,40,.10);}
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Noto Sans',sans-serif;background:var(--light);color:#1a2a40;}
header{background:linear-gradient(135deg,#0d1f3c,var(--blue));color:#fff;padding:12px 18px;display:flex;align-items:center;gap:12px;border-bottom:3px solid var(--accent);}
.logo{width:46px;height:46px;border-radius:50%;background:var(--accent);display:flex;align-items:center;justify-content:center;font-size:20px;flex-shrink:0;border:2px solid var(--gold);}
.ht h1{font-family:'Rajdhani',sans-serif;font-size:17px;font-weight:700;letter-spacing:1px;text-transform:uppercase;}
.ht p{font-size:10px;opacity:.6;}
.tabs{background:var(--navy);display:flex;}
.tab{flex:1;background:none;border:none;color:rgba(255,255,255,.55);font-family:'Rajdhani',sans-serif;font-size:13px;font-weight:700;padding:11px 6px;cursor:pointer;border-bottom:3px solid transparent;text-transform:uppercase;letter-spacing:.5px;}
.tab.on{color:var(--gold);border-bottom-color:var(--accent);}
.pg{display:none;}.pg.on{display:block;}
main{max-width:960px;margin:0 auto;padding:16px 12px 60px;}
.card{background:#fff;border-radius:8px;box-shadow:var(--sh);padding:16px 18px;margin-bottom:14px;border-top:3px solid var(--blue);}
.card.g{border-top-color:var(--accent);}.card.r{border-top-color:var(--red);}.card.gn{border-top-color:var(--green);}
.ct{font-family:'Rajdhani',sans-serif;font-size:13px;font-weight:700;color:var(--blue);letter-spacing:.6px;text-transform:uppercase;margin-bottom:11px;}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:10px 14px;}
.row3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px 14px;}
.fg{display:flex;flex-direction:column;gap:4px;}
label{font-size:10px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:.4px;}
input,select,textarea{border:1.5px solid var(--border);border-radius:5px;padding:7px 9px;font-size:13px;font-family:'Noto Sans',sans-serif;color:#1a2a40;background:#fafbfc;outline:none;width:100%;}
input:focus,select:focus,textarea:focus{border-color:var(--blue);background:#fff;}
input[readonly]{background:#f0f4f8;color:var(--navy);font-weight:600;}
textarea{resize:vertical;min-height:55px;}
.btn{display:inline-flex;align-items:center;gap:5px;padding:9px 20px;border-radius:5px;font-family:'Rajdhani',sans-serif;font-size:14px;font-weight:700;letter-spacing:.5px;text-transform:uppercase;cursor:pointer;border:none;}
.bp{background:var(--blue);color:#fff;}.bgn{background:var(--green);color:#fff;}.br{background:var(--red);color:#fff;}.bg{background:var(--accent);color:var(--navy);}
.bo{background:transparent;color:var(--blue);border:2px solid var(--blue)!important;}
.btns{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap;}
.tw{overflow-x:auto;}
table{width:100%;border-collapse:collapse;font-size:12px;}
th{background:var(--navy);color:var(--gold);font-family:'Rajdhani',sans-serif;font-size:11px;font-weight:700;text-transform:uppercase;padding:7px 8px;text-align:left;}
td{padding:6px 8px;border-bottom:1px solid #edf0f4;vertical-align:middle;}
tr:hover td{background:#f4f7fb;}
.dr{background:none;border:none;color:var(--red);cursor:pointer;font-size:14px;}
.ar{display:inline-flex;align-items:center;gap:4px;margin-top:6px;background:none;border:1.5px dashed var(--blue);color:var(--blue);border-radius:5px;padding:4px 12px;font-size:12px;font-family:'Rajdhani',sans-serif;font-weight:600;cursor:pointer;}
.ok{background:#d4edda;border-left:4px solid var(--green);border-radius:5px;padding:10px 14px;font-size:13px;color:var(--green);margin-top:12px;}
.er{background:#f8d7da;border-left:4px solid var(--red);border-radius:5px;padding:10px 14px;font-size:13px;color:var(--red);margin-top:12px;}
.nt{background:#fff8e6;border:1px solid #f5c842;border-radius:5px;padding:8px 12px;font-size:11px;color:#7a5c00;margin-bottom:12px;}
.sts{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:10px;margin-bottom:14px;}
.st{background:#fff;border-radius:7px;padding:13px;box-shadow:var(--sh);border-left:4px solid var(--blue);}
.st.g{border-left-color:var(--accent);}.st.r{border-left-color:var(--red);}.st.gn{border-left-color:var(--green);}.st.or{border-left-color:#d35400;}
.sn{font-family:'Rajdhani',sans-serif;font-size:24px;font-weight:700;color:#0a1628;}
.sl{font-size:10px;color:var(--muted);text-transform:uppercase;margin-top:2px;}
.dg{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:8px;margin-bottom:12px;}
.dc{background:#fff;border-radius:6px;padding:9px 11px;box-shadow:0 2px 6px rgba(0,0,0,.07);border-left:4px solid #e2e8f0;}
.dc.s{border-left-color:var(--green);}.dc.p{border-left-color:#d35400;}
.dn{font-family:'Rajdhani',sans-serif;font-size:12px;font-weight:700;color:#0a1628;text-transform:uppercase;}
.bx{display:inline-block;padding:2px 7px;border-radius:20px;font-size:10px;font-weight:600;}
.bg2{background:#d4edda;color:#1a6b3a;}.by{background:#fff3cd;color:#856404;}.brd{background:#f8d7da;color:#721c24;}
.sp{display:inline-block;width:14px;height:14px;border:2px solid rgba(255,255,255,.3);border-top-color:#fff;border-radius:50%;animation:sp .8s linear infinite;vertical-align:middle;margin-right:4px;}
@keyframes sp{to{transform:rotate(360deg)}}
.pwin{min-height:60vh;display:flex;align-items:center;justify-content:center;}
.pbox{background:#fff;border-radius:10px;box-shadow:var(--sh);width:100%;max-width:320px;overflow:hidden;}
.phd{background:linear-gradient(135deg,#0d1f3c,var(--blue));padding:20px;text-align:center;color:#fff;}
.phd .ico{font-size:36px;margin-bottom:8px;}
.phd h2{font-family:'Rajdhani',sans-serif;font-size:17px;font-weight:700;letter-spacing:1px;text-transform:uppercase;}
@media print{
  header,.tabs,.btns,.ar,.dr,#pg-dist,#pg-hq{display:none!important;}
  #pg-pdf{display:block!important;}
  body{background:#fff;}
  .pw{box-shadow:none!important;max-width:100%!important;}
}
.pw{background:#fff;max-width:760px;margin:0 auto;box-shadow:var(--sh);padding:22px 26px;font-size:11.5px;}
.pw h2{font-family:'Rajdhani',sans-serif;font-size:18px;font-weight:700;text-align:center;text-transform:uppercase;color:var(--navy);margin-bottom:4px;}
.subtitle{text-align:center;font-size:11px;color:var(--muted);margin-bottom:6px;}
.ps h3{font-family:'Rajdhani',sans-serif;font-size:11.5px;font-weight:700;text-transform:uppercase;color:#fff;background:var(--navy);padding:4px 9px;margin-bottom:6px;margin-top:10px;}
.pt{width:100%;border-collapse:collapse;font-size:11px;margin-bottom:8px;}
.pt th{background:#e8edf5;color:var(--navy);font-weight:700;padding:4px 7px;border:1px solid #bbb;font-size:10px;text-transform:uppercase;}
.pt td{padding:4px 7px;border:1px solid #ccc;vertical-align:top;}
.pt td[contenteditable="true"]{background:#fffde7;outline:none;}
.veh-summary{background:#f0f7ff;border:2px solid var(--blue);border-radius:6px;padding:10px 14px;margin-bottom:8px;text-align:center;}
.veh-summary h4{font-family:'Rajdhani',sans-serif;font-size:12px;font-weight:700;color:var(--navy);text-transform:uppercase;margin-bottom:6px;}
.veh-nums{display:grid;grid-template-columns:1fr 1fr;gap:6px;}
.veh-num{background:#fff;border-radius:5px;padding:7px;border:1px solid var(--border);}
.veh-num .n{font-family:'Rajdhani',sans-serif;font-size:18px;font-weight:700;color:var(--navy);}
.veh-num .l{font-size:9px;color:var(--muted);text-transform:uppercase;}
.pf{border-top:2px solid var(--navy);margin-top:14px;padding-top:10px;display:flex;justify-content:space-between;font-size:10px;color:var(--muted);}
.sig{border-top:1.5px solid var(--navy);width:140px;margin-left:auto;padding-top:3px;font-size:10px;color:var(--navy);font-weight:600;text-transform:uppercase;text-align:center;}
@media(max-width:540px){.row2,.row3{grid-template-columns:1fr;}header{flex-wrap:wrap;}.sts{grid-template-columns:1fr 1fr;}}
</style>
</head>
<body>
<header>
  <div class="logo">🚦</div>
  <div class="ht">
    <h1>HP Police — DSI Portal</h1>
    <p>Traffic, Tourist &amp; Railways Wing &nbsp;|&nbsp; Daily Situation Report</p>
  </div>
  <span id="clk" style="margin-left:auto;font-size:11px;opacity:.7"></span>
</header>
<div class="tabs">
  <button class="tab on" onclick="go('dist')">📋 District Entry</button>
  <button class="tab" onclick="go('hq')">📊 HQ Dashboard</button>
  <button class="tab" onclick="go('pdf')">📄 PDF Report</button>
</div>

<!-- DISTRICT ENTRY -->
<div id="pg-dist" class="pg on">
<main>
  <div class="nt">Select your district and fill all sections. Click Submit when done.</div>
  <div class="card">
    <div class="ct">📌 Report Header</div>
    <div class="row3">
      <div class="fg"><label>Date *</label><input type="date" id="f-date"></div>
      <div class="fg"><label>District *</label>
        <select id="f-dist" onchange="onDistrictChange()">
          <option value="">— Select District —</option>
          <option>Baddi (BBN)</option><option>Bilaspur</option><option>Chamba</option>
          <option>PD Dehra</option><option>Hamirpur</option><option>Kangra</option>
          <option>Kinnaur</option><option>Kullu</option><option>Lahaul &amp; Spiti</option>
          <option>Mandi</option><option>PD Nurpur</option><option>Shimla</option>
          <option>Sirmour</option><option>Solan</option><option>Una</option>
          <option>TTPS Baghed</option><option>TTPS Nerchowk</option><option>TTPS Bhunter</option>
          <option>GRPS Kangra</option><option>GRPS Shimla</option><option>OPGRP Una</option>
        </select>
      </div>
      <div class="fg"><label>Officer Name *</label><input type="text" id="f-off" placeholder="Full Name"></div>
      <div class="fg"><label>Rank *</label>
        <select id="f-rank">
          <option value="">— Select —</option>
          <option>Constable</option><option>Head Constable</option><option>ASI</option>
          <option>Sub-Inspector</option><option>Inspector</option><option>DSP</option><option>SP</option>
        </select>
      </div>
    </div>
  </div>

  <div class="card g">
    <div class="ct">🚗 Section 1 — Vehicle Entry/Exit (ITMS Border Points)</div>
    <div id="veh-na" class="nt" style="display:none">Vehicle entry/exit not applicable for this district.</div>
    <div id="veh-sec" style="display:none">
      <div style="background:#e8f0fb;padding:8px 12px;border-radius:5px;margin-bottom:10px;font-size:12px;font-weight:600;color:var(--blue)" id="itms-lbl">ITMS Point</div>
      <div class="tw">
        <table>
          <thead><tr><th>ITMS Point</th><th>Vehicles Entered (24 Hrs)</th><th>Incoming Avg/Day (2026)</th><th>Vehicles Exited (24 Hrs)</th><th>Outgoing Avg/Day (2026)</th></tr></thead>
          <tbody id="veh-tb"></tbody>
          <tfoot><tr style="background:#f4f7fb;font-weight:700;font-family:'Rajdhani',sans-serif">
            <td>TOTAL</td><td id="t-vi">0</td><td id="t-via">0</td><td id="t-vo">0</td><td id="t-voa">0</td>
          </tr></tfoot>
        </table>
      </div>
    </div>
    <div style="margin-top:12px">
      <label style="font-size:11px;font-weight:600;color:var(--navy);text-transform:uppercase;display:block;margin-bottom:6px">Non-Working ITMS (if any)</label>
      <div class="tw"><table><thead><tr><th>#</th><th>District</th><th>No. of Non-Working ITMS &amp; Location/Reason</th><th></th></tr></thead><tbody id="itms-tb"></tbody></table></div>
      <button class="ar" onclick="addRow('itms')">+ Add Non-Working ITMS</button>
    </div>
  </div>

  <div class="card">
    <div class="ct">🏍️ Section 2 — Patrolling Vehicles &amp; Motorcycles (World Bank)</div>
    <div id="veh2-info" class="nt">Select district — vehicles will load automatically.</div>
    <div id="patrol-sec" style="display:none">
      <div style="font-size:11px;font-weight:700;color:var(--navy);text-transform:uppercase;background:#f4f7fb;padding:6px 10px;border-radius:4px;margin-bottom:8px">Patrolling Vehicles</div>
      <div class="tw"><table><thead><tr><th>#</th><th>Vehicle No.</th><th>Beat / Route</th><th>Patrolling KMs *</th><th>Challans *</th></tr></thead><tbody id="patrol-tb"></tbody></table></div>
    </div>
    <div id="moto-sec" style="display:none;margin-top:12px">
      <div style="font-size:11px;font-weight:700;color:var(--navy);text-transform:uppercase;background:#f4f7fb;padding:6px 10px;border-radius:4px;margin-bottom:8px">Motorcycles (World Bank Project)</div>
      <div class="tw"><table><thead><tr><th>#</th><th>Reg. No.</th><th>PS / Beat</th><th>Patrolling KMs *</th><th>Challans *</th></tr></thead><tbody id="moto-tb"></tbody></table></div>
    </div>
  </div>

  <div class="card">
    <div class="ct">🦺 Section 3 — Traffic Volunteers Deployed</div>
    <div class="tw"><table><thead><tr><th>#</th><th>No. of Volunteers</th><th>Place of Deployment</th><th>Nature of Duty</th><th></th></tr></thead><tbody id="vol-tb"></tbody></table></div>
    <button class="ar" onclick="addRow('vol')">+ Add Volunteer Entry</button>
  </div>

  <div class="card r">
    <div class="ct">🚨 Section 4 — Fatal Accident Cases</div>
    <div class="nt">CCTNS &amp; e-DAR totals are filled by HQ. Report fatal cases below.</div>
    <div class="tw"><table><thead><tr><th>#</th><th>FIR No. &amp; Date</th><th>PS Name</th><th>Brief Facts</th><th></th></tr></thead><tbody id="fat-tb"></tbody></table></div>
    <button class="ar" onclick="addRow('fat')">+ Add Fatal Case</button>
  </div>

  <div class="card gn">
    <div class="ct">Submit</div>
    <label style="display:flex;align-items:center;gap:7px;font-size:12px;cursor:pointer;margin-bottom:12px">
      <input type="checkbox" id="f-decl"> I confirm the above information is true and correct.
    </label>
    <div class="btns">
      <button class="btn bgn" id="sub-btn" onclick="submitData()">Submit</button>
      <button class="btn bo" onclick="resetForm()">Reset</button>
    </div>
    <div id="sub-msg" style="display:none"></div>
  </div>
</main>
</div>

<!-- HQ DASHBOARD -->
<div id="pg-hq" class="pg">
<div id="hq-lock">
  <div class="pwin">
    <div class="pbox">
      <div class="phd"><div class="ico">🛡️</div><h2>HQ Access</h2></div>
      <div style="padding:20px">
        <div class="fg" style="margin-bottom:14px"><label>Password</label><input type="password" id="hq-pass" placeholder="Enter HQ password" onkeydown="if(event.key==='Enter')checkHQ()"></div>
        <button class="btn bp" style="width:100%;justify-content:center" onclick="checkHQ()">Enter</button>
        <div id="hq-err" style="display:none;margin-top:10px" class="er"></div>
      </div>
    </div>
  </div>
</div>
<div id="hq-con" style="display:none">
<main>
  <div style="display:flex;gap:9px;margin-bottom:13px;align-items:flex-end;flex-wrap:wrap;background:#fff;padding:12px 16px;border-radius:8px;box-shadow:var(--sh)">
    <div class="fg" style="flex:1;min-width:130px"><label>Report Date</label><input type="date" id="hq-dt"></div>
    <button class="btn bp" onclick="loadHQ()">🔄 Load Data</button>
    <button class="btn bg" onclick="goPDF()">📄 Generate PDF</button>
    <button class="btn bo" style="font-size:12px;padding:7px 12px" onclick="hqLogout()">🚪 Lock</button>
  </div>
  <div class="sts">
    <div class="st"><div class="sn" id="ss-sub">0</div><div class="sl">Submitted</div></div>
    <div class="st or"><div class="sn" id="ss-pen">15</div><div class="sl">Pending</div></div>
    <div class="st g"><div class="sn" id="ss-veh">0</div><div class="sl">Veh Entered</div></div>
    <div class="st r"><div class="sn" id="ss-acc">0</div><div class="sl">Accidents</div></div>
    <div class="st r"><div class="sn" id="ss-fat">0</div><div class="sl">Fatal</div></div>
    <div class="st"><div class="sn" id="ss-ch">0</div><div class="sl">Challans</div></div>
    <div class="st gn"><div class="sn" id="ss-vol">0</div><div class="sl">Volunteers</div></div>
    <div class="st r"><div class="sn" id="ss-itms">0</div><div class="sl">ITMS Issues</div></div>
  </div>
  <div class="card r">
    <div class="ct">🚨 Section 4 — Accident Cases (HQ Entry Only)</div>
    <div class="nt">Fill total accident figures for the selected date.</div>
    <div class="row3" style="margin-bottom:12px">
      <div class="fg"><label>Total Accidents in CCTNS</label><input type="number" id="hq-cctns" value="0" min="0" style="font-size:15px;font-weight:600;border:2px solid var(--red)"></div>
      <div class="fg"><label>Total Accidents in e-DAR</label><input type="number" id="hq-edar" value="0" min="0" style="font-size:15px;font-weight:600;border:2px solid var(--red)"></div>
      <div class="fg"><label>Districts NOT in e-DAR</label><input type="text" id="hq-miss" placeholder="e.g. Baddi=01, Shimla=01"></div>
    </div>
    <button class="btn br" onclick="saveHQAcc()">💾 Save Accident Data</button>
    <div id="hq-acc-msg" style="display:none;margin-top:10px"></div>
  </div>
  <div class="card"><div class="ct">🗺️ District Status</div><div class="dg" id="dist-grid"></div></div>
  <div class="card">
    <div class="ct">📊 Consolidated Summary</div>
    <div class="tw">
      <table>
        <thead><tr><th>District</th><th>Officer</th><th>Veh In</th><th>Veh Out</th><th>Patrol Vehs</th><th>Motos</th><th>Total KMs</th><th>Challans</th><th>Volunteers</th><th>ITMS</th><th>Fatal</th></tr></thead>
        <tbody id="hq-tb"></tbody>
        <tfoot><tr style="background:#e8f0fb;font-weight:700;font-family:'Rajdhani',sans-serif">
          <td colspan="2">TOTAL</td>
          <td id="t-tvi">0</td><td id="t-tvo">0</td><td id="t-tpv">0</td><td id="t-tmo">0</td>
          <td id="t-tkm">0</td><td id="t-tch">0</td><td id="t-tvl">0</td><td id="t-tit">0</td><td id="t-tfa">0</td>
        </tr></tfoot>
      </table>
    </div>
  </div>
  <div class="card r">
    <div class="ct">🚨 Fatal Cases — All Districts</div>
    <div class="tw"><table><thead><tr><th>#</th><th>District</th><th>FIR No. &amp; Date</th><th>PS Name</th><th>Brief Facts</th></tr></thead><tbody id="hq-fat"></tbody></table></div>
  </div>
  <div class="card g">
    <div class="ct">⚠️ Non-Working ITMS — All Districts</div>
    <div class="tw"><table><thead><tr><th>#</th><th>District</th><th>Non-Working ITMS &amp; Reason</th></tr></thead><tbody id="hq-itms"></tbody></table></div>
  </div>
</main>
</div>
</div>

<!-- PDF REPORT -->
<div id="pg-pdf" class="pg">
<main>
  <div style="display:flex;gap:9px;margin-bottom:14px;align-items:flex-end;flex-wrap:wrap;background:#fff;padding:12px 16px;border-radius:8px;box-shadow:var(--sh)">
    <div class="fg" style="flex:1;min-width:130px"><label>Report Date</label><input type="date" id="pdf-dt"></div>
    <button class="btn bgn" onclick="loadPDF()">📥 Load &amp; Build PDF</button>
    <button class="btn bp" id="pdf-print" onclick="window.print()" style="display:none">🖨️ Print / Save PDF</button>
    <button class="btn bo" onclick="go('hq')">← Back</button>
  </div>
  <div id="pdf-msg" style="display:none;padding:12px 16px;background:#fff;border-radius:8px;box-shadow:var(--sh);margin-bottom:13px;font-size:13px"></div>
  <div class="pw" id="pdf-body" style="display:none">
    <div style="text-align:center;margin-bottom:12px">
      <h2>TRAFFIC DSI &nbsp;<span id="p-title-date">—</span></h2>
      <div class="subtitle">Himachal Pradesh Police &nbsp;|&nbsp; Traffic, Tourist &amp; Railways Wing</div>
      <div style="margin:10px auto;max-width:320px">
        <svg viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:auto;border:1px solid #ddd;border-radius:6px;background:#f0f7ff">
          <path d="M80,40 L130,15 L190,10 L250,20 L310,15 L360,45 L375,90 L365,130 L345,160 L320,190 L295,230 L260,268 L215,285 L170,278 L125,260 L90,230 L68,195 L55,155 L50,110 L58,75 Z" fill="#d4edda" stroke="#1a6b3a" stroke-width="2.5"/>
          <text x="105" y="50" font-size="10" fill="#0a1628" font-weight="700">Chamba</text>
          <text x="215" y="38" font-size="10" fill="#0a1628" font-weight="700">Lahaul &amp; Spiti</text>
          <text x="78" y="95" font-size="10" fill="#0a1628" font-weight="700">Nurpur</text>
          <text x="130" y="90" font-size="10" fill="#0a1628" font-weight="700">Kangra</text>
          <text x="205" y="95" font-size="10" fill="#0a1628" font-weight="700">Kullu</text>
          <text x="295" y="95" font-size="10" fill="#0a1628" font-weight="700">Kinnaur</text>
          <text x="72" y="140" font-size="10" fill="#0a1628" font-weight="700">Una</text>
          <text x="122" y="135" font-size="10" fill="#0a1628" font-weight="700">Hamirpur</text>
          <text x="178" y="135" font-size="10" fill="#0a1628" font-weight="700">Mandi</text>
          <text x="100" y="178" font-size="10" fill="#0a1628" font-weight="700">Bilaspur</text>
          <text x="160" y="185" font-size="10" fill="#0a1628" font-weight="700">Shimla</text>
          <text x="92" y="215" font-size="10" fill="#0a1628" font-weight="700">Baddi</text>
          <text x="138" y="222" font-size="10" fill="#0a1628" font-weight="700">Solan</text>
          <text x="188" y="245" font-size="10" fill="#0a1628" font-weight="700">Sirmour</text>
          <circle cx="87" cy="148" r="6" fill="#e2c46a" stroke="#c8a84b" stroke-width="2"/>
          <circle cx="112" cy="183" r="6" fill="#e2c46a" stroke="#c8a84b" stroke-width="2"/>
          <circle cx="148" cy="228" r="6" fill="#e2c46a" stroke="#c8a84b" stroke-width="2"/>
          <circle cx="162" cy="195" r="6" fill="#e2c46a" stroke="#c8a84b" stroke-width="2"/>
          <circle cx="205" cy="255" r="6" fill="#e2c46a" stroke="#c8a84b" stroke-width="2"/>
          <circle cx="45" cy="280" r="5" fill="#e2c46a" stroke="#c8a84b" stroke-width="1.5"/>
          <text x="55" y="284" font-size="8" fill="#555">ITMS Border Points</text>
        </svg>
      </div>
      <div style="font-size:10px;color:var(--muted);margin-top:4px">Ref: <span id="p-ref">—</span> &nbsp;|&nbsp; Generated: <span id="p-gen">—</span></div>
    </div>

    <table class="pt" style="margin-bottom:12px">
      <thead><tr><th></th><th>Title</th><th>Page No.</th></tr></thead>
      <tbody>
        <tr><td>1.</td><td>Vehicle entry/exit status and Status of ITMS (Non-working)</td><td>2-3</td></tr>
        <tr><td>2.</td><td>Status of Vehicle &amp; Motorcycle under World Bank project</td><td>3-7</td></tr>
        <tr><td>3.</td><td>Status of Traffic Volunteers Employed</td><td>7</td></tr>
        <tr><td>4.</td><td>Status of Accident Cases</td><td>7</td></tr>
        <tr><td>5.</td><td>Fatal Accident Cases</td><td>7</td></tr>
      </tbody>
    </table>

    <div class="ps">
      <h3>Section 1 — Vehicles Entry/Exit Status During Last 24 Hours</h3>
      <div class="veh-summary">
        <h4>Vehicles entry/exit status during last 24 hours</h4>
        <div class="veh-nums">
          <div class="veh-num"><div class="n" id="p-total-vi">—</div><div class="l">Vehicle Entered</div></div>
          <div class="veh-num"><div class="n" id="p-total-vo">—</div><div class="l">Vehicle Exited</div></div>
          <div class="veh-num"><div class="n" id="p-total-via">—</div><div class="l">Entered Monthly Avg</div></div>
          <div class="veh-num"><div class="n" id="p-total-voa">—</div><div class="l">Exited Monthly Avg</div></div>
        </div>
      </div>
      <table class="pt">
        <thead><tr><th>ITMS Point</th><th>Vehicles Entered (24 Hrs)</th><th>Incoming Avg/Day (2026)</th><th>Vehicles Exited (24 Hrs)</th><th>Outgoing Avg/Day (2026)</th></tr></thead>
        <tbody id="p-veh"></tbody>
      </table>
      <div style="font-size:10px;font-weight:700;color:var(--navy);text-transform:uppercase;margin:8px 0 5px">Status of Non-Working ITMS:</div>
      <table class="pt">
        <thead><tr><th>Sr.No.</th><th>District</th><th>Name/Locations of Non-Working ITMS Along With Reasons</th></tr></thead>
        <tbody id="p-itms"></tbody>
      </table>
    </div>

    <div class="ps">
      <h3>Section 2 — Status of Vehicle &amp; Motorcycle Distributed Under World Bank Project</h3>
      <table class="pt">
        <thead><tr><th>District</th><th>Vehicle/Motorcycle Reg. No.</th><th>Police Station &amp; Beat Deployed</th><th>Patrolling Done in Last 24 Hrs (KMs)</th><th>No. of Challans Done in Last 24 Hrs</th></tr></thead>
        <tbody id="p-veh2"></tbody>
      </table>
    </div>

    <div class="ps">
      <h3>Section 3 — Traffic Volunteers Employed</h3>
      <table class="pt">
        <thead><tr><th>District</th><th>No. of Traffic Volunteers Employed</th><th>Place of Deployment</th><th>Nature of Duty Assigned</th></tr></thead>
        <tbody id="p-vol"></tbody>
      </table>
    </div>

    <div class="ps">
      <h3>Section 4 — Status of Accident Cases</h3>
      <table class="pt" style="margin-bottom:8px">
        <thead><tr><th>No. of Accident Cases Entered in CCTNS</th><th>No. of Accident Cases Entered in e-DAR</th><th>Name of District Who Have Not Entered Accident Cases in e-DAR</th></tr></thead>
        <tbody><tr>
          <td style="font-weight:700;text-align:center;font-size:14px" id="p-cc">—</td>
          <td style="font-weight:700;text-align:center;font-size:14px" id="p-ed">—</td>
          <td contenteditable="true" id="p-ms">—</td>
        </tr></tbody>
      </table>
      <div style="font-size:10px;font-weight:700;color:var(--navy);text-transform:uppercase;margin-bottom:5px">Details of Fatal Accident Cases Reported in Last 24 Hours:</div>
      <table class="pt">
        <thead><tr><th>Sr. No.</th><th>FIR &amp; Date</th><th>PS Name</th><th>Brief Facts of Fatal Accident Cases</th></tr></thead>
        <tbody id="p-fat"></tbody>
      </table>
    </div>

    <div class="pf">
      <div><strong>HP Police — Traffic, Tourist &amp; Railways Wing</strong><br>DSI Report &nbsp;|&nbsp; For Official Use Only</div>
      <div><div class="sig" contenteditable="true">DSP/SP Traffic (PHQ)</div></div>
    </div>
  </div>
</main>
</div>

<footer style="background:var(--navy);color:rgba(255,255,255,.4);text-align:center;font-size:11px;padding:10px">
  HP Police — DSI Portal &nbsp;|&nbsp; Traffic, Tourist &amp; Railways Wing &nbsp;|&nbsp; For Official Use Only
</footer>

<script>
var API = 'https://script.google.com/macros/s/AKfycbzsLtqaw0LJ7j83k5DhtlXaCnIOqf4WbqBCG3vtpEGL5wSX-kfJTdwCgspJwv_VgZ4w/exec';
var HQ_PASS = 'hppolice@2026';

var ITMS_PTS = {
  'PD Dehra':'ITMS Dehra',
  'Una':'ITMS Una',
  'Bilaspur':'ITMS Bilaspur',
  'Solan':'ITMS Solan',
  'Sirmour':'ITMS Paonta Sahib'
};

var PATROL = {
  'Baddi (BBN)':[{n:'HP-63C-8751 (Interceptor)',b:'Baddi to Manpura'},{n:'HP07D-2398 (EV)',b:'Nalagarh to Joghon'},{n:'HP07D-2404 (EV)',b:'Manpura to Nalagarh'}],
  'Bilaspur':[{n:'HP07D-2428 (EV)',b:'Namhol to Bilaspur to Gagus'},{n:'HP63C-8774',b:'Kandraur to Targhel'}],
  'Chamba':[{n:'HP07D-2395 (EV)',b:'Banikhet to Chamba'},{n:'HP07D-2411 (EV)',b:'Draman to Dhamoti'}],
  'PD Dehra':[{n:'HP63C-8750 (Interceptor)',b:'Mangarh to Bagli'},{n:'HP07D-2432 (EV)',b:'Balugloa to Nadaun Bridge'},{n:'HP63C-8778 (Scorpio)',b:'Bathu Bridge to Balugloa'},{n:'HP07D-2435 (EV)',b:'Sansarpur Terrace to Dhaliyara'}],
  'Hamirpur':[{n:'HP63C-8747 (Interceptor)',b:'Anu to Awahdevi'},{n:'HP07D-2429 (EV)',b:'Anu to Awahdevi'},{n:'HP63C-8772 (Scorpio)',b:'Nadaun to Hamirpur'},{n:'HP07D-2385 (EV)',b:'Nadaun to Hamirpur'}],
  'Kangra':[{n:'Interceptor (PS D/SHALA)',b:'Yol to Chamunda to McLeodganj'},{n:'EV (PS M/GANJ)',b:'McLeodganj to Dharamshala'},{n:'EV (PS KANGRA)',b:'Ranital to Mataur Bridge'},{n:'EV (PS BAGWAN)',b:'Tanda to Paraur'},{n:'EV',b:'61 Miles to Bhawana'},{n:'HP07D-2392 (EV)',b:'Thakurdwara to Paprola'}],
  'Kullu':[{n:'HP07D-2416 (EV)',b:'Mohal to Gannon Bridge'},{n:'HP07D-2419 (EV)',b:'Jhiri to Jia'},{n:'HP07D-2403 (EV)',b:'Manali to Atal Tunnel'},{n:'HP07D-2409 (EV)',b:'Palchan to Rohtang'},{n:'HP7D-2412 (EV)',b:'Nehru Kund to 18 Mile'}],
  'Mandi':[{n:'HP07D-2420 (EV)',b:'Sundernagar to Nerchowk'},{n:'HP07D-2408 (EV)',b:'Dadour to Malori Tunnel'},{n:'HP63C-8779',b:'Malori to Hanogi Tunnel'},{n:'HP07D-2402 (EV)',b:'Banoha to Sarkaghat'}],
  'Sirmour':[{n:'HP63C-8757 (Interceptor)',b:'Kollar to Paonta Sahib'},{n:'HP07D-2417 (EV)',b:'Nahan to Prem Nagar'},{n:'HP63C-8742 (Interceptor)',b:'Kala Amb to Nahan'}],
  'Solan':[{n:'HP07D-2396 (EV)',b:'Solan to Waknaghat'},{n:'HP63C-8749 (Interceptor)',b:'Solan to Waknaghat'},{n:'HP07D-2283 (EV)',b:'Solan to Dharampur'}],
  'Una':[{n:'HP63C-8744 (Interceptor)',b:'Mehatpur to Ghanwal'},{n:'HP07D-2397 (EV)',b:'Dhussara to Mubarakpur'},{n:'HP07D-2399 (EV)',b:'Jhalera to Bankhandi'}],
  'PD Nurpur':[{n:'HP63C-8748 (Interceptor)',b:'Kandwa to Behar Khad'},{n:'HP63C-8776 (Scorpio)',b:'Bhadroya to Toki'},{n:'HP07D-2439 (EV)',b:'Kathgarh to Attara Road'}],
  'Shimla':[{n:'HP63C-8746 (Interceptor)',b:'Dhalli to Shilaru'},{n:'HP07D-2437 (EV)',b:'Baira Khadd to Jeori'},{n:'HP63A-8771 (Scorpio)',b:'Dhalli to Soghi'},{n:'HP07D-2390 (EV)',b:'Rohru to Khara Pathar'},{n:'HP07D-2434 (EV)',b:'Hulli to Khara Pathar'}],
  'TTPS Baghed':[{n:'HP63C-8745 (Interceptor)',b:'Garha Mora to Baloh Toll'},{n:'HP07D-2438 (EV)',b:'Garha Mora to Baloh Toll'}],
  'TTPS Nerchowk':[{n:'HP63C-8759 (Interceptor)',b:'Samlhau to Jhiri'},{n:'HP07D-2436 (EV)',b:'Samlhau to Jhiri'}],
  'TTPS Bhunter':[{n:'HP63C-8743 (Interceptor)',b:'Jia to Raison'},{n:'HP63C-8780 (Scorpio)',b:'Jia to Raison'}],
  'GRPS Kangra':[{n:'HP07D-2394 (EV)',b:'National Highway'}],
  'GRPS Shimla':[{n:'HP07D-2423',b:'National Highway'}],
  'OPGRP Una':[{n:'HP63C-8753 (Interceptor)',b:'National Highway'}]
};

var MOTOS = {
  'Baddi (BBN)':[{r:'HP63C-7692',p:'Traffic Wing Baddi'},{r:'HP63C-7723',p:'Traffic Wing Nalagarh'}],
  'Bilaspur':[{r:'HP63C-7693',p:'PS Sadar'}],
  'Chamba':[{r:'HP63C-7705',p:'Traffic Wing Chamba'}],
  'PD Dehra':[{r:'HP63C-7699',p:'PS Dehra'},{r:'HP63C-7701',p:'PS Jawalamukhi'}],
  'Hamirpur':[{r:'HP63C-7704',p:'Traffic Wing Hamirpur'},{r:'HP63C-7708',p:'PS Hamirpur'},{r:'HP63C-7709',p:'PS Hamirpur'}],
  'Kangra':[{r:'HP63C-7703',p:'PS Kangra'},{r:'HP63C-7706',p:'PS Dharamshala'},{r:'HP63C-7715',p:'PS Nagrota'},{r:'HP63C-7725',p:'PS Bhawarna'},{r:'HP63C-7727',p:'PS Palampur'}],
  'Kinnaur':[],'Kullu':[{r:'HP63C-7694',p:'Traffic Wing Manali'},{r:'HP63C-7695',p:'Traffic Wing Kullu'}],
  'Lahaul & Spiti':[],
  'Mandi':[{r:'HP63C-7696',p:'PS Sundernagar'},{r:'HP63C-7712',p:'PS Balh'},{r:'HP63C-7716',p:'PS Aut'},{r:'HP63C-7719',p:'PS Sadar Mandi'},{r:'HP63C-7720',p:'PS Paddar'}],
  'PD Nurpur':[{r:'HP63C-6177',p:'Kandwal to Nurpur'},{r:'HP63C-6178',p:'Rahan to Raja ka Talab'},{r:'HP63C-6180',p:'PS Damtal'},{r:'HP63C-6190',p:'Talara to Baroh'},{r:'HP63C-6194',p:'Nurpur to BhedKhad'},{r:'HP63C-6202',p:'Fatehpur to Dhameta'}],
  'Shimla':[{r:'HP63C-6172',p:'PP Baghi'},{r:'HP63C-6176',p:'PP Junga'},{r:'HP63C-6179',p:'PS Rampur'},{r:'HP63C-6181',p:'Traffic Wing Shimla'},{r:'HP63C-6184',p:'PP Tikkar'},{r:'HP63C-6185',p:'PP Taklech'},{r:'HP63C-6186',p:'PS Sanjauli'},{r:'HP63C-6187',p:'Traffic Wing Shimla'},{r:'HP63C-6188',p:'PP Chhaila'},{r:'HP63C-6189',p:'Traffic Wing Shimla'},{r:'HP63C-6191',p:'Traffic Wing Shimla'},{r:'HP63C-6192',p:'Traffic Wing Shimla'},{r:'HP63C-6193',p:'Traffic Wing Shimla'},{r:'HP63C-6195',p:'PP Dhami'},{r:'HP63C-6196',p:'Traffic Wing/PL Kaithu'},{r:'HP63C-6197',p:'Traffic Wing Shimla'},{r:'HP63C-6198',p:'Traffic Wing Shimla'},{r:'HP63C-6199',p:'Traffic Wing Shimla'}],
  'Sirmour':[{r:'HP63C-7698',p:'Traffic Wing Nahan'},{r:'HP63C-7718',p:'Traffic Wing Paonta Sahib'}],
  'Solan':[],'Una':[{r:'HP63C-7702',p:'Traffic Wing Una'},{r:'HP63C-7713',p:'PS Haroli'},{r:'HP63C-7714',p:'Highway Patrol'},{r:'HP63C-7726',p:'PS Chintpurni'}]
};

var ALL_DIST=['Baddi (BBN)','Bilaspur','Chamba','PD Dehra','Hamirpur','Kangra','Kinnaur','Kullu','Lahaul & Spiti','Mandi','PD Nurpur','Shimla','Sirmour','Solan','Una'];
var HD={summary:[],moto:[],patrol:[],vol:[],itms:[],fatal:[],hqaccidents:[]};
var hqUnlocked=false;

setInterval(function(){document.getElementById('clk').textContent=new Date().toLocaleString('en-IN',{weekday:'short',day:'2-digit',month:'short',year:'numeric',hour:'2-digit',minute:'2-digit',second:'2-digit'});},1000);
var T=new Date().toISOString().split('T')[0];
['f-date','hq-dt','pdf-dt'].forEach(function(id){document.getElementById(id).value=T;});

function go(p){
  document.querySelectorAll('.pg').forEach(function(x){x.classList.remove('on');});
  document.getElementById('pg-'+p).classList.add('on');
  document.querySelectorAll('.tab').forEach(function(b,i){b.classList.remove('on');if({'dist':0,'hq':1,'pdf':2}[p]===i)b.classList.add('on');});
  window.scrollTo({top:0,behavior:'smooth'});
}

function fmtD(d){
  if(!d) return d;
  var p=d.split('-');
  return p.length===3?p[2]+'-'+p[1]+'-'+p[0]:d;
}

function checkHQ(){
  if(document.getElementById('hq-pass').value===HQ_PASS){
    hqUnlocked=true;
    document.getElementById('hq-lock').style.display='none';
    document.getElementById('hq-con').style.display='block';
    loadHQ();
  } else {
    document.getElementById('hq-err').style.display='block';
    document.getElementById('hq-err').textContent='Incorrect password.';
  }
}

function hqLogout(){
  hqUnlocked=false;
  document.getElementById('hq-lock').style.display='block';
  document.getElementById('hq-con').style.display='none';
  document.getElementById('hq-pass').value='';
  document.getElementById('hq-err').style.display='none';
}

function onDistrictChange(){
  var dist=document.getElementById('f-dist').value;
  loadVehicles(dist);
  loadPatrolMoto(dist);
}

function loadVehicles(dist){
  var sec=document.getElementById('veh-sec');
  var na=document.getElementById('veh-na');
  var tb=document.getElementById('veh-tb');
  var lbl=document.getElementById('itms-lbl');
  if(!dist){sec.style.display='none';na.style.display='none';return;}
  if(ITMS_PTS[dist]){
    sec.style.display='block';na.style.display='none';
    lbl.textContent='ITMS Point: '+ITMS_PTS[dist];
    tb.innerHTML='<tr><td style="font-weight:600">'+ITMS_PTS[dist]+'</td>'+
      '<td><input type="number" id="f-vin" value="0" min="0" style="width:85px;font-size:13px;padding:5px;border:1.5px solid var(--accent);border-radius:4px;font-weight:600"></td>'+
      '<td><input type="number" id="f-via" value="0" min="0" style="width:85px;font-size:13px;padding:5px;border:1.5px solid var(--blue);border-radius:4px;font-weight:600"></td>'+
      '<td><input type="number" id="f-vout" value="0" min="0" style="width:85px;font-size:13px;padding:5px;border:1.5px solid var(--accent);border-radius:4px;font-weight:600"></td>'+
      '<td><input type="number" id="f-voa" value="0" min="0" style="width:85px;font-size:13px;padding:5px;border:1.5px solid var(--blue);border-radius:4px;font-weight:600"></td></tr>';
    ['f-vin','f-via','f-vout','f-voa'].forEach(function(id){
      var el=document.getElementById(id);
      if(el) el.addEventListener('input',updVehTotals);
    });
    updVehTotals();
  } else {
    sec.style.display='none';na.style.display='block';
  }
}

function updVehTotals(){
  document.getElementById('t-vi').textContent=document.getElementById('f-vin')?document.getElementById('f-vin').value:0;
  document.getElementById('t-via').textContent=document.getElementById('f-via')?document.getElementById('f-via').value:0;
  document.getElementById('t-vo').textContent=document.getElementById('f-vout')?document.getElementById('f-vout').value:0;
  document.getElementById('t-voa').textContent=document.getElementById('f-voa')?document.getElementById('f-voa').value:0;
}

function loadPatrolMoto(dist){
  var info=document.getElementById('veh2-info');
  var psec=document.getElementById('patrol-sec');
  var msec=document.getElementById('moto-sec');
  var ptb=document.getElementById('patrol-tb');
  var mtb=document.getElementById('moto-tb');
  if(!dist){info.style.display='block';psec.style.display='none';msec.style.display='none';return;}
  info.style.display='none';
  var pvs=PATROL[dist]||[];
  if(pvs.length){
    psec.style.display='block';
    ptb.innerHTML=pvs.map(function(v,i){
      return '<tr><td style="color:var(--muted)">'+(i+1)+'</td>'+
        '<td><input type="text" value="'+v.n+'" readonly style="width:160px;font-size:11.5px;padding:4px 6px;border:1px solid var(--border);border-radius:4px;background:#f0f4f8;font-weight:600"></td>'+
        '<td><input type="text" value="'+v.b+'" readonly style="width:100%;font-size:11.5px;padding:4px 6px;border:1px solid var(--border);border-radius:4px;background:#f0f4f8;font-weight:600"></td>'+
        '<td><input type="number" id="pkm'+i+'" value="0" min="0" style="width:75px;font-size:13px;padding:5px;border:1.5px solid var(--accent);border-radius:4px;font-weight:600"></td>'+
        '<td><input type="number" id="pch'+i+'" value="0" min="0" style="width:75px;font-size:13px;padding:5px;border:1.5px solid var(--accent);border-radius:4px;font-weight:600"></td></tr>';
    }).join('');
  } else { psec.style.display='none'; }
  var mos=MOTOS[dist]||[];
  if(mos.length){
    msec.style.display='block';
    mtb.innerHTML=mos.map(function(m,i){
      return '<tr><td style="color:var(--muted)">'+(i+1)+'</td>'+
        '<td><input type="text" value="'+m.r+'" readonly style="width:130px;font-size:11.5px;padding:4px 6px;border:1px solid var(--border);border-radius:4px;background:#f0f4f8;font-weight:600"></td>'+
        '<td><input type="text" value="'+m.p+'" readonly style="width:100%;font-size:11.5px;padding:4px 6px;border:1px solid var(--border);border-radius:4px;background:#f0f4f8;font-weight:600"></td>'+
        '<td><input type="number" id="mkm'+i+'" value="0" min="0" style="width:75px;font-size:13px;padding:5px;border:1.5px solid var(--accent);border-radius:4px;font-weight:600"></td>'+
        '<td><input type="number" id="mch'+i+'" value="0" min="0" style="width:75px;font-size:13px;padding:5px;border:1.5px solid var(--accent);border-radius:4px;font-weight:600"></td></tr>';
    }).join('');
  } else { msec.style.display='none'; }
  if(!pvs.length&&!mos.length){info.style.display='block';info.textContent=dist+' — No vehicles/motorcycles assigned.';}
}

function getPatrol(){
  var dist=document.getElementById('f-dist').value;
  return (PATROL[dist]||[]).map(function(v,i){
    return {veh:v.n,beat:v.b,km:document.getElementById('pkm'+i)?document.getElementById('pkm'+i).value:'0',ch:document.getElementById('pch'+i)?document.getElementById('pch'+i).value:'0'};
  });
}

function getMotos(){
  var dist=document.getElementById('f-dist').value;
  return (MOTOS[dist]||[]).map(function(m,i){
    return {reg:m.r,ps:m.p,km:document.getElementById('mkm'+i)?document.getElementById('mkm'+i).value:'0',ch:document.getElementById('mch'+i)?document.getElementById('mch'+i).value:'0'};
  });
}

var rn={itms:0,vol:0,fat:0};
function addRow(t){
  rn[t]++;
  var n=rn[t];
  var tb=document.getElementById(t+'-tb');
  var tr=document.createElement('tr');
  var h='<td style="color:var(--muted);font-size:11px">'+n+'</td>';
  if(t==='itms'){
    h+='<td><input type="text" id="id'+n+'" placeholder="District" style="width:100px;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
    h+='<td><input type="text" id="il'+n+'" placeholder="No. & Location/Reason" style="width:100%;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
  } else if(t==='vol'){
    h+='<td><input type="number" id="vn'+n+'" value="0" min="0" style="width:65px;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
    h+='<td><input type="text" id="vp'+n+'" placeholder="Place" style="width:100%;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
    h+='<td><input type="text" id="vd'+n+'" value="Traffic Duty" style="width:100%;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
  } else if(t==='fat'){
    h+='<td><input type="text" id="ff'+n+'" placeholder="FIR No. & Date" style="width:100%;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
    h+='<td><input type="text" id="fps'+n+'" placeholder="PS Name" style="width:100%;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></td>';
    h+='<td><textarea id="fb'+n+'" rows="2" style="width:100%;min-width:150px;font-size:12px;padding:4px 7px;border:1px solid var(--border);border-radius:4px"></textarea></td>';
  }
  h+='<td><button class="dr" onclick="this.closest(\'tr\').remove()">✕</button></td>';
  tr.innerHTML=h;
  tb.appendChild(tr);
}

function getRows(t){
  var rows=[];
  document.getElementById(t+'-tb').querySelectorAll('tr').forEach(function(tr){
    if(t==='itms'){var d=tr.querySelector('[id^="id"]'),l=tr.querySelector('[id^="il"]');if(l&&l.value)rows.push({dist:d?d.value:'',loc:l.value});}
    else if(t==='vol'){var n=tr.querySelector('[id^="vn"]'),p=tr.querySelector('[id^="vp"]'),d=tr.querySelector('[id^="vd"]');if(p&&p.value)rows.push({n:n?n.value:'0',p:p.value,d:d?d.value:'Traffic Duty'});}
    else if(t==='fat'){var f=tr.querySelector('[id^="ff"]'),ps=tr.querySelector('[id^="fps"]'),b=tr.querySelector('[id^="fb"]');if(f&&f.value)rows.push({fir:f.value,ps:ps?ps.value:'',facts:b?b.value:''});}
  });
  return rows;
}

function submitData(){
  var date=document.getElementById('f-date').value;
  var dist=document.getElementById('f-dist').value;
  var off=document.getElementById('f-off').value.trim();
  var rank=document.getElementById('f-rank').value;
  var decl=document.getElementById('f-decl').checked;
  if(!date||!dist||!off||!rank){alert('Date, District, Officer Name and Rank are required.');return;}
  if(!decl){alert('Please accept the declaration.');return;}
  var btn=document.getElementById('sub-btn');
  var msg=document.getElementById('sub-msg');
  btn.innerHTML='<span class="sp"></span>Submitting...';btn.disabled=true;msg.style.display='none';
  var payload={
    action:'submit',date:date,district:dist,officer:off,rank:rank,
    itms_point:ITMS_PTS[dist]||'',
    vin:+(document.getElementById('f-vin')?document.getElementById('f-vin').value:0)||0,
    vin_avg:+(document.getElementById('f-via')?document.getElementById('f-via').value:0)||0,
    vout:+(document.getElementById('f-vout')?document.getElementById('f-vout').value:0)||0,
    vout_avg:+(document.getElementById('f-voa')?document.getElementById('f-voa').value:0)||0,
    patrol:getPatrol(),moto:getMotos(),
    itms:getRows('itms'),vol:getRows('vol'),fatal:getRows('fat')
  };
  fetch(API,{method:'POST',headers:{'Content-Type':'text/plain'},body:JSON.stringify(payload)})
    .then(function(r){return r.json();})
    .then(function(d){
      msg.style.display='block';
      if(d.ok){msg.className='ok';msg.innerHTML='Data submitted successfully for <strong>'+dist+'</strong>!';}
      else{msg.className='er';msg.textContent='Error: '+(d.msg||'Unknown');}
    })
    .catch(function(e){msg.style.display='block';msg.className='er';msg.textContent='Network error: '+e.message;})
    .finally(function(){btn.innerHTML='Submit';btn.disabled=false;});
}

function saveHQAcc(){
  var date=document.getElementById('hq-dt').value;
  if(!date){alert('Select date first.');return;}
  var msg=document.getElementById('hq-acc-msg');
  fetch(API,{method:'POST',headers:{'Content-Type':'text/plain'},body:JSON.stringify({action:'saveHQAccidents',date:date,cctns:+document.getElementById('hq-cctns').value||0,edar:+document.getElementById('hq-edar').value||0,missing:document.getElementById('hq-miss').value||''})})
    .then(function(r){return r.json();})
    .then(function(d){msg.style.display='block';msg.className=d.ok?'ok':'er';msg.textContent=d.ok?'Accident data saved!':'Error: '+d.msg;})
    .catch(function(e){msg.style.display='block';msg.className='er';msg.textContent='Failed: '+e.message;});
}

function loadHQ(){
  var date=document.getElementById('hq-dt').value;
  fetch(API,{method:'POST',headers:{'Content-Type':'text/plain'},body:JSON.stringify({action:'fetch',date:fmtD(date)})})
    .then(function(r){return r.json();})
    .then(function(d){if(d.ok){HD=d;renderHQ(d);}else alert('Error: '+d.msg);})
    .catch(function(e){alert('Load failed: '+e.message);});
}

function renderHQ(d){
  var rows=d.summary||[];
  var subs=rows.map(function(r){return r.District;});
  var dg=document.getElementById('dist-grid');dg.innerHTML='';
  ALL_DIST.forEach(function(x){
    var s=rows.find(function(r){return r.District===x;});
    var div=document.createElement('div');div.className='dc '+(s?'s':'p');
    div.innerHTML='<div class="dn">'+x+'</div><div style="margin-top:3px">'+(s?'<span class="bx bg2">Done</span>':'<span class="bx by">Pending</span>')+'</div>'+(s?'<div style="font-size:9.5px;color:var(--muted);margin-top:2px">'+(s.Officer||'')+'</div>':'');
    dg.appendChild(div);
  });
  var tb=document.getElementById('hq-tb');tb.innerHTML='';
  var tvi=0,tvo=0,tpv=0,tmo=0,tkm=0,tch=0,tvl=0,tit=0,tfa=0;
  ALL_DIST.forEach(function(x){
    var s=rows.find(function(r){return r.District===x;});
    var tr=document.createElement('tr');
    if(s){
      var vi=+s.Veh_In||0,vo=+s.Veh_Out||0,pv=+s.Patrol_Vehs||0,mo=+s.Motos||0,km=+s.Total_KMs||0,ch=+s.Total_Challans||0,vl=+s.Volunteers||0,it=+s.ITMS||0,fa=+s.Fatal||0;
      tvi+=vi;tvo+=vo;tpv+=pv;tmo+=mo;tkm+=km;tch+=ch;tvl+=vl;tit+=it;tfa+=fa;
      tr.innerHTML='<td><strong>'+x+'</strong></td><td>'+(s.Officer||'')+'<br><span style="font-size:9.5px;color:var(--muted)">'+(s.Rank||'')+'</span></td><td style="text-align:center">'+vi+'</td><td style="text-align:center">'+vo+'</td><td style="text-align:center">'+pv+'</td><td style="text-align:center">'+mo+'</td><td style="text-align:center">'+km+'</td><td style="text-align:center">'+ch+'</td><td style="text-align:center">'+vl+'</td><td style="text-align:center">'+(it?'<span class="bx brd">'+it+'</span>':'<span class="bx bg2">NIL</span>')+'</td><td style="text-align:center">'+(fa?'<span class="bx brd">'+fa+'</span>':'NIL')+'</td>';
    } else {
      tr.innerHTML='<td><strong>'+x+'</strong></td><td colspan="9" style="color:var(--muted);font-style:italic">Pending</td><td><span class="bx by">⏳</span></td>';
    }
    tb.appendChild(tr);
  });
  ['t-tvi','t-tvo','t-tpv','t-tmo','t-tkm','t-tch','t-tvl','t-tit','t-tfa'].forEach(function(id,i){document.getElementById(id).textContent=[tvi,tvo,tpv,tmo,tkm,tch,tvl,tit,tfa][i];});
  document.getElementById('ss-sub').textContent=subs.length;
  document.getElementById('ss-pen').textContent=15-subs.length;
  document.getElementById('ss-veh').textContent=tvi;
  document.getElementById('ss-acc').textContent=(d.hqaccidents&&d.hqaccidents[0])?d.hqaccidents[0].CCTNS||0:0;
  document.getElementById('ss-fat').textContent=tfa;
  document.getElementById('ss-ch').textContent=tch;
  document.getElementById('ss-vol').textContent=tvl;
  document.getElementById('ss-itms').textContent=tit;
  if(d.hqaccidents&&d.hqaccidents.length){var ha=d.hqaccidents[0];document.getElementById('hq-cctns').value=ha.CCTNS||0;document.getElementById('hq-edar').value=ha.eDAR||0;document.getElementById('hq-miss').value=ha.Missing||'';}
  var fl=d.fatal||[];
  document.getElementById('hq-fat').innerHTML=fl.length?fl.map(function(f,i){return '<tr><td>'+(i+1)+'</td><td><strong>'+f.District+'</strong></td><td>'+f.FIR+'</td><td>'+f.PS+'</td><td>'+f.Facts+'</td></tr>';}).join(''):'<tr><td colspan="5" style="text-align:center;color:var(--muted);padding:12px">No fatal cases.</td></tr>';
  var il=d.itms||[];
  document.getElementById('hq-itms').innerHTML=il.length?il.map(function(it,i){return '<tr><td>'+(i+1)+'</td><td><strong>'+it.District+'</strong></td><td>'+it.Location+'</td></tr>';}).join(''):'<tr><td colspan="3" style="text-align:center;color:var(--muted);padding:12px">No ITMS issues.</td></tr>';
}

function goPDF(){
  go('pdf');
  document.getElementById('pdf-dt').value=document.getElementById('hq-dt').value;
  if(HD.summary&&HD.summary.length>0){buildPDF(HD);document.getElementById('pdf-body').style.display='block';document.getElementById('pdf-print').style.display='inline-flex';}
}

function loadPDF(){
  var date=document.getElementById('pdf-dt').value;
  if(!date){alert('Please select a date.');return;}
  var msg=document.getElementById('pdf-msg');
  msg.style.display='block';
  msg.innerHTML='<span class="sp" style="border-top-color:var(--blue);border-color:rgba(26,58,107,.2)"></span> Loading data...';
  document.getElementById('pdf-print').style.display='none';
  document.getElementById('pdf-body').style.display='none';
  fetch(API,{method:'POST',headers:{'Content-Type':'text/plain'},body:JSON.stringify({action:'fetch',date:fmtD(date)})})
    .then(function(r){return r.json();})
    .then(function(d){
      if(d.ok){HD=d;buildPDF(d);msg.innerHTML='PDF ready! Click Print to save.';document.getElementById('pdf-print').style.display='inline-flex';document.getElementById('pdf-body').style.display='block';}
      else{msg.innerHTML='Error: '+d.msg;}
    })
    .catch(function(e){msg.innerHTML='Failed: '+e.message;});
}

function buildPDF(d){
  var date=document.getElementById('pdf-dt').value||T;
  var months=['January','February','March','April','May','June','July','August','September','October','November','December'];
  var dp=date.split('-');
  var fmtDate=parseInt(dp[2])+' '+months[parseInt(dp[1])-1]+' '+dp[0];
  document.getElementById('p-title-date').textContent=fmtDate;
  document.getElementById('p-ref').textContent='DSI/'+date.replace(/-/g,'')+'/CONSOLIDATED';
  document.getElementById('p-gen').textContent=new Date().toLocaleString('en-IN');
  var rows=d.summary||[];
  var tvi=0,tvia=0,tvo=0,tvoa=0;
  rows.forEach(function(s){tvi+=+s.Veh_In||0;tvia+=+s.Veh_In_Avg||0;tvo+=+s.Veh_Out||0;tvoa+=+s.Veh_Out_Avg||0;});
  document.getElementById('p-total-vi').textContent=tvi.toLocaleString('en-IN');
  document.getElementById('p-total-vo').textContent=tvo.toLocaleString('en-IN');
  document.getElementById('p-total-via').textContent=tvia.toLocaleString('en-IN');
  document.getElementById('p-total-voa').textContent=tvoa.toLocaleString('en-IN');
  var itmsRows=rows.filter(function(s){return s.ITMS_Point&&s.ITMS_Point!='';});
  document.getElementById('p-veh').innerHTML=itmsRows.length?
    itmsRows.map(function(s){return '<tr><td><strong>'+s.ITMS_Point+'</strong></td><td style="text-align:center">'+(s.Veh_In||0)+'</td><td style="text-align:center">'+(s.Veh_In_Avg||0)+'</td><td style="text-align:center">'+(s.Veh_Out||0)+'</td><td style="text-align:center">'+(s.Veh_Out_Avg||0)+'</td></tr>';}).join('')+
    '<tr style="font-weight:700;background:#f4f7fb"><td>Total</td><td style="text-align:center">'+tvi+'</td><td style="text-align:center">'+tvia+'</td><td style="text-align:center">'+tvo+'</td><td style="text-align:center">'+tvoa+'</td></tr>'
    :'<tr><td colspan="5" style="text-align:center;color:var(--muted)">NIL</td></tr>';
  var il=d.itms||[];
  document.getElementById('p-itms').innerHTML=il.length?
    il.map(function(it,i){return '<tr><td>'+(i+1)+'</td><td>'+it.District+'</td><td>'+it.Location+'</td></tr>';}).join('')+
    '<tr style="font-weight:700;background:#f4f7fb"><td colspan="2">Total</td><td>'+il.length+'</td></tr>'
    :'<tr><td colspan="3" style="text-align:center;color:var(--muted)">NIL</td></tr>';
  var pt=d.patrol||[];var mt=d.moto||[];
  var allV2=pt.concat(mt);
  var s2html='';var lastDist='';var dkm=0,dch=0,gkm=0,gch=0;
  allV2.forEach(function(v){
    var dist=v.District||'';
    if(dist!==lastDist){
      if(lastDist) s2html+='<tr style="background:#f4f7fb;font-weight:700"><td colspan="3">Sub-total '+lastDist+'</td><td style="text-align:center">'+dkm+'</td><td style="text-align:center">'+dch+'</td></tr>';
      lastDist=dist;dkm=0;dch=0;
    }
    var km=+v.KMs||0;var ch=+v.Challans||0;
    dkm+=km;dch+=ch;gkm+=km;gch+=ch;
    var reg=v.Reg_No||v.Vehicle||'';
    var beat=v.PS_Beat||v.Beat||'';
    s2html+='<tr><td>'+dist+'</td><td>'+reg+'</td><td>'+beat+'</td><td style="text-align:center">'+km+'</td><td style="text-align:center">'+ch+'</td></tr>';
  });
  if(lastDist) s2html+='<tr style="background:#f4f7fb;font-weight:700"><td colspan="3">Sub-total '+lastDist+'</td><td style="text-align:center">'+dkm+'</td><td style="text-align:center">'+dch+'</td></tr>';
  if(allV2.length) s2html+='<tr style="background:#e8f0fb;font-weight:700"><td colspan="3">GRAND TOTAL</td><td style="text-align:center">'+gkm+'</td><td style="text-align:center">'+gch+'</td></tr>';
  document.getElementById('p-veh2').innerHTML=s2html||'<tr><td colspan="5" style="text-align:center;color:var(--muted)">NIL</td></tr>';
  var vl=d.vol||[];var tvol3=0;
  document.getElementById('p-vol').innerHTML=vl.length?
    vl.map(function(v){tvol3+=+v.Count||0;return '<tr><td>'+v.District+'</td><td style="text-align:center">'+v.Count+'</td><td>'+v.Place+'</td><td>'+v.Duty+'</td></tr>';}).join('')+
    '<tr style="font-weight:700;background:#f4f7fb"><td>Total</td><td style="text-align:center">'+tvol3+'</td><td colspan="2"></td></tr>'
    :'<tr><td colspan="4" style="text-align:center;color:var(--muted)">NIL</td></tr>';
  var ha=d.hqaccidents&&d.hqaccidents.length?d.hqaccidents[0]:null;
  document.getElementById('p-cc').textContent=ha?ha.CCTNS||0:'—';
  document.getElementById('p-ed').textContent=ha?ha.eDAR||0:'—';
  document.getElementById('p-ms').textContent=ha?ha.Missing||'NIL':'NIL';
  var fat=d.fatal||[];
  document.getElementById('p-fat').innerHTML=fat.length?
    fat.map(function(f,i){return '<tr><td>'+(i+1)+'</td><td contenteditable="true">'+f.FIR+'</td><td contenteditable="true">'+f.PS+'</td><td contenteditable="true">'+f.Facts+'</td></tr>';}).join('')
    :'<tr><td>1</td><td contenteditable="true"></td><td contenteditable="true"></td><td contenteditable="true"></td></tr>';
}

function resetForm(){
  document.getElementById('f-off').value='';
  document.getElementById('f-dist').value='';
  document.getElementById('f-rank').value='';
  document.getElementById('f-date').value=T;
  document.getElementById('f-decl').checked=false;
  ['itms-tb','vol-tb','fat-tb'].forEach(function(id){var e=document.getElementById(id);if(e)e.innerHTML='';});
  document.getElementById('veh-sec').style.display='none';
  document.getElementById('veh-na').style.display='none';
  document.getElementById('patrol-sec').style.display='none';
  document.getElementById('moto-sec').style.display='none';
  document.getElementById('veh2-info').style.display='block';
  document.getElementById('veh2-info').textContent='Select district — vehicles will load automatically.';
  rn={itms:0,vol:0,fat:0};
  document.getElementById('sub-msg').style.display='none';
}
</script>
</body>
</html>
