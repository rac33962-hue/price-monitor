<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>가격 모니터링 대시보드</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root { --bg: #f8f9fa; --surface: #ffffff; --border: #e9ecef; --text: #212529; --text-muted: #6c757d; --primary: #1a73e8; --danger: #d93025; --danger-bg: #fce8e6; --success: #1e8e3e; --success-bg: #e6f4ea; --warning: #f29900; --warning-bg: #fef7e0; --radius: 12px; --radius-sm: 8px; }
  body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; }
  #login-screen { display: flex; align-items: center; justify-content: center; min-height: 100vh; }
  .login-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 48px 40px; width: 360px; text-align: center; }
  .login-logo { width: 48px; height: 48px; background: var(--primary); border-radius: 12px; display: inline-flex; align-items: center; justify-content: center; margin-bottom: 20px; }
  .login-logo svg { width: 24px; height: 24px; fill: white; }
  .login-card h1 { font-size: 20px; font-weight: 600; margin-bottom: 6px; }
  .login-card p { font-size: 14px; color: var(--text-muted); margin-bottom: 28px; }
  .login-card input { width: 100%; padding: 10px 14px; border: 1px solid var(--border); border-radius: var(--radius-sm); font-size: 14px; margin-bottom: 12px; outline: none; }
  .login-card input:focus { border-color: var(--primary); }
  .login-card button { width: 100%; padding: 10px; background: var(--primary); color: white; border: none; border-radius: var(--radius-sm); font-size: 14px; font-weight: 500; cursor: pointer; }
  .login-error { color: var(--danger); font-size: 13px; margin-top: 10px; display: none; }
  #app { display: none; }
  header { background: var(--surface); border-bottom: 1px solid var(--border); padding: 0 32px; height: 60px; display: flex; align-items: center; justify-content: space-between; position: sticky; top: 0; z-index: 100; }
  .header-left { display: flex; align-items: center; gap: 12px; }
  .header-logo { width: 32px; height: 32px; background: var(--primary); border-radius: 8px; display: flex; align-items: center; justify-content: center; }
  .header-logo svg { width: 16px; height: 16px; fill: white; }
  header h1 { font-size: 16px; font-weight: 600; }
  .header-right { display: flex; align-items: center; gap: 12px; }
  .last-updated { font-size: 13px; color: var(--text-muted); }
  .btn-refresh { padding: 7px 14px; background: var(--primary); color: white; border: none; border-radius: var(--radius-sm); font-size: 13px; font-weight: 500; cursor: pointer; display: flex; align-items: center; gap: 6px; }
  .btn-logout { padding: 7px 14px; background: transparent; color: var(--text-muted); border: 1px solid var(--border); border-radius: var(--radius-sm); font-size: 13px; cursor: pointer; }
  .tabs { display: flex; border-bottom: 1px solid var(--border); background: var(--surface); padding: 0 32px; }
  .tab { padding: 14px 20px; font-size: 14px; color: var(--text-muted); cursor: pointer; border-bottom: 2px solid transparent; font-weight: 500; }
  .tab.active { color: var(--primary); border-bottom-color: var(--primary); }
  .content { padding: 28px 32px; max-width: 1200px; margin: 0 auto; }
  .tab-content { display: none; }
  .tab-content.active { display: block; }
  .summary-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; margin-bottom: 28px; }
  .summary-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 20px; }
  .summary-card .label { font-size: 13px; color: var(--text-muted); margin-bottom: 8px; }
  .summary-card .value { font-size: 28px; font-weight: 600; }
  .summary-card.danger .value { color: var(--danger); }
  .section-title { font-size: 15px; font-weight: 600; margin-bottom: 14px; }
  .branch-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 14px; }
  .branch-card { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); padding: 20px; cursor: pointer; transition: all 0.15s; position: relative; }
  .branch-card:hover { border-color: var(--primary); transform: translateY(-1px); }
  .branch-card.has-violation { border-color: #f5c6c3; background: #fffafa; }
  .branch-name { font-size: 15px; font-weight: 600; margin-bottom: 10px; }
  .branch-stats { display: flex; gap: 6px; flex-wrap: wrap; }
  .branch-stat { font-size: 12px; padding: 3px 8px; border-radius: 20px; font-weight: 500; }
  .branch-stat.violation { background: var(--danger-bg); color: var(--danger); }
  .branch-stat.normal { background: var(--success-bg); color: var(--success); }
  .branch-stat.total { background: var(--bg); color: var(--text-muted); border: 1px solid var(--border); }
  .violation-dot { width: 8px; height: 8px; background: var(--danger); border-radius: 50%; position: absolute; top: 14px; right: 14px; animation: pulse 1.5s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }
  #detail-view { display: none; }
  .breadcrumb { display: flex; align-items: center; gap: 8px; margin-bottom: 20px; font-size: 14px; }
  .breadcrumb-back { display: flex; align-items: center; gap: 6px; color: var(--primary); cursor: pointer; font-weight: 500; }
  .breadcrumb-sep { color: var(--text-muted); }
  .breadcrumb-current { color: var(--text-muted); }
  .section { background: var(--surface); border: 1px solid var(--border); border-radius: var(--radius); margin-bottom: 20px; overflow: hidden; }
  .section-header { padding: 16px 20px; border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; }
  .section-header h2 { font-size: 15px; font-weight: 600; }
  .section-header .count { font-size: 13px; color: var(--text-muted); }
  table { width: 100%; border-collapse: collapse; }
  th { padding: 11px 16px; text-align: left; font-size: 12px; font-weight: 600; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.05em; border-bottom: 1px solid var(--border); background: #fafafa; }
  td { padding: 13px 16px; font-size: 14px; border-bottom: 1px solid var(--border); }
  tr:last-child td { border-bottom: none; }
  tr:hover td { background: var(--bg); }
  .badge { display: inline-flex; align-items: center; padding: 3px 10px; border-radius: 20px; font-size: 12px; font-weight: 500; }
  .badge-danger { background: var(--danger-bg); color: var(--danger); }
  .badge-success { background: var(--success-bg); color: var(--success); }
  .badge-warning { background: var(--warning-bg); color: var(--warning); }
  .contact-btn { padding: 5px 10px; border-radius: 6px; font-size: 12px; font-weight: 500; cursor: pointer; border: 1px solid var(--border); background: var(--surface); color: var(--text-muted); }
  .contact-btn:hover { background: var(--bg); }
  .filter-bar { display: flex; gap: 10px; margin-bottom: 20px; align-items: center; flex-wrap: wrap; }
  .filter-bar select, .filter-bar input { padding: 8px 12px; border: 1px solid var(--border); border-radius: var(--radius-sm); font-size: 13px; background: var(--surface); outline: none; }
  .filter-bar button { padding: 8px 12px; border: 1px solid var(--border); border-radius: var(--radius-sm); background: white; cursor: pointer; font-size: 13px; }
  .empty { text-align: center; padding: 48px 20px; color: var(--text-muted); font-size: 14px; }
  .loading { text-align: center; padding: 48px; color: var(--text-muted); font-size: 14px; }
  .spinner { display: inline-block; width: 20px; height: 20px; border: 2px solid var(--border); border-top-color: var(--primary); border-radius: 50%; animation: spin 0.8s linear infinite; margin-right: 8px; vertical-align: middle; }
  @keyframes spin { to { transform: rotate(360deg); } }
  .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.4); z-index: 1000; align-items: center; justify-content: center; }
  .modal-overlay.open { display: flex; }
  .modal { background: var(--surface); border-radius: var(--radius); padding: 28px; width: 440px; max-width: 90vw; }
  .modal h3 { font-size: 16px; font-weight: 600; margin-bottom: 6px; }
  .modal p { font-size: 13px; color: var(--text-muted); margin-bottom: 20px; }
  .modal-product { font-size: 14px; font-weight: 500; margin-bottom: 20px; }
  .contact-options { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; margin-bottom: 20px; }
  .contact-option { padding: 12px; border: 2px solid var(--border); border-radius: var(--radius-sm); text-align: center; cursor: pointer; font-size: 13px; font-weight: 500; }
  .contact-option.selected { border-color: var(--primary); background: #e8f0fe; color: var(--primary); }
  .contact-option .icon { font-size: 20px; margin-bottom: 6px; }
  .modal-note { width: 100%; padding: 10px 12px; border: 1px solid var(--border); border-radius: var(--radius-sm); font-size: 13px; resize: vertical; min-height: 80px; margin-bottom: 16px; font-family: inherit; outline: none; }
  .modal-actions { display: flex; gap: 10px; justify-content: flex-end; }
  .btn-cancel { padding: 9px 18px; border: 1px solid var(--border); background: transparent; border-radius: var(--radius-sm); font-size: 14px; cursor: pointer; }
  .btn-save { padding: 9px 18px; background: var(--primary); color: white; border: none; border-radius: var(--radius-sm); font-size: 14px; font-weight: 500; cursor: pointer; }
  .contact-log { display: flex; flex-wrap: wrap; gap: 4px; }
  .contact-log-item { font-size: 11px; padding: 2px 8px; border-radius: 12px; background: var(--bg); border: 1px solid var(--border); color: var(--text-muted); }
  a { color: var(--primary); text-decoration: none; }
  a:hover { text-decoration: underline; }
</style>
</head>
<body>

<div id="login-screen">
  <div class="login-card">
    <div class="login-logo"><svg viewBox="0 0 24 24"><path d="M3 13h8V3H3v10zm0 8h8v-6H3v6zm10 0h8V11h-8v10zm0-18v6h8V3h-8z"/></svg></div>
    <h1>가격 모니터링</h1>
    <p>관리자 계정으로 로그인하세요</p>
    <input type="text" id="login-id" placeholder="아이디" />
    <input type="password" id="login-pw" placeholder="비밀번호" onkeydown="if(event.key==='Enter') doLogin()" />
    <button onclick="doLogin()">로그인</button>
    <div class="login-error" id="login-error">아이디 또는 비밀번호가 올바르지 않습니다</div>
  </div>
</div>

<div id="app">
  <header>
    <div class="header-left">
      <div class="header-logo"><svg viewBox="0 0 24 24"><path d="M3 13h8V3H3v10zm0 8h8v-6H3v6zm10 0h8V11h-8v10zm0-18v6h8V3h-8z"/></svg></div>
      <h1>가격 모니터링 대시보드</h1>
    </div>
    <div class="header-right">
      <span class="last-updated" id="last-updated">-</span>
      <button class="btn-refresh" onclick="refreshAll()">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M17.65 6.35A7.958 7.958 0 0012 4c-4.42 0-7.99 3.58-7.99 8s3.57 8 7.99 8c3.73 0 6.84-2.55 7.73-6h-2.08A5.99 5.99 0 0112 18c-3.31 0-6-2.69-6-6s2.69-6 6-6c1.66 0 3.14.69 4.22 1.78L13 11h7V4l-2.35 2.35z"/></svg>
        새로고침
      </button>
      <button class="btn-logout" onclick="doLogout()">로그아웃</button>
    </div>
  </header>
  <div class="tabs">
    <div class="tab active" onclick="switchTab('dashboard',this)">대시보드</div>
    <div class="tab" onclick="switchTab('history',this)">가격 변동 이력</div>
    <div class="tab" onclick="switchTab('contact',this)">연락 이력</div>
  </div>
  <div class="content">

    <div class="tab-content active" id="tab-dashboard">
      <div class="summary-grid">
        <div class="summary-card"><div class="label">전체 지사</div><div class="value" id="stat-branches">-</div></div>
        <div class="summary-card danger"><div class="label">위반 발생 지사</div><div class="value" id="stat-violation-branches">-</div></div>
        <div class="summary-card danger"><div class="label">전체 위반 상품</div><div class="value" id="stat-violations">-</div></div>
        <div class="summary-card"><div class="label">전체 모니터링 상품</div><div class="value" id="stat-total">-</div></div>
      </div>
      <div id="branch-list-view">
        <div class="section-title">지사 현황 — 클릭하면 상세 보기</div>
        <div class="branch-grid" id="branch-grid"><div class="loading"><span class="spinner"></span>데이터 불러오는 중...</div></div>
      </div>
      <div id="detail-view">
        <div class="breadcrumb">
          <span class="breadcrumb-back" onclick="goBack()">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z"/></svg>
            전체 지사
          </span>
          <span class="breadcrumb-sep">›</span>
          <span class="breadcrumb-current" id="detail-branch-name"></span>
        </div>
        <div class="summary-grid" style="grid-template-columns:repeat(3,1fr);">
          <div class="summary-card"><div class="label">전체 상품</div><div class="value" id="detail-stat-total">-</div></div>
          <div class="summary-card danger"><div class="label">위반 상품</div><div class="value" id="detail-stat-violations">-</div></div>
          <div class="summary-card"><div class="label">마지막 점검</div><div class="value" style="font-size:15px;padding-top:6px;" id="detail-stat-checked">-</div></div>
        </div>
        <div class="section">
          <div class="section-header"><h2>상품 현황</h2><span class="count" id="detail-product-count"></span></div>
          <div id="detail-product-table"></div>
        </div>
      </div>
    </div>

    <div class="tab-content" id="tab-history">
      <div class="filter-bar">
        <select id="history-branch-filter" onchange="renderHistory()"><option value="">전체 지사</option></select>
        <select id="history-status-filter" onchange="renderHistory()">
          <option value="">전체 상태</option>
          <option value="위반">위반만</option>
          <option value="정상">정상만</option>
        </select>
        <input type="date" id="history-date-filter" onchange="renderHistory()" />
        <button onclick="clearHistoryFilter()">초기화</button>
      </div>
      <div class="section">
        <div class="section-header"><h2>가격 변동 이력</h2><span class="count" id="history-count"></span></div>
        <div id="history-table"><div class="loading"><span class="spinner"></span>불러오는 중...</div></div>
      </div>
    </div>

    <div class="tab-content" id="tab-contact">
      <div class="section">
        <div class="section-header"><h2>연락 이력</h2><span class="count" id="contact-count"></span></div>
        <div id="contact-table"></div>
      </div>
    </div>

  </div>
</div>

<div class="modal-overlay" id="contact-modal">
  <div class="modal">
    <h3>연락 기록 남기기</h3>
    <p>연락 방법을 선택하고 메모를 남겨주세요</p>
    <div class="modal-product" id="modal-product-name"></div>
    <div class="contact-options">
      <div class="contact-option" onclick="selectContact('톡톡')"><div class="icon">💬</div>네이버 톡톡</div>
      <div class="contact-option" onclick="selectContact('문자')"><div class="icon">📱</div>문자</div>
      <div class="contact-option" onclick="selectContact('전화')"><div class="icon">📞</div>전화</div>
    </div>
    <textarea class="modal-note" id="modal-note" placeholder="메모 (선택사항)"></textarea>
    <div class="modal-actions">
      <button class="btn-cancel" onclick="closeModal()">취소</button>
      <button class="btn-save" onclick="saveContact()">저장</button>
    </div>
  </div>
</div>

<script>
const BRANCHES = [
  { name: '베니몰', url: 'https://script.google.com/macros/s/AKfycbx29XQo9SIG-zdgwany9OSxIH8WZ3hT2PJqy7ZMUf5OhcADUu0sQIYne91K-OMLWPrx-g/exec' },
  // 지사 추가할 때 여기에 추가하세요:
  // { name: '지사이름', url: '앱스크립트 배포 URL' },
];
const USERS = { 'admin': '1234', 'manager': '5678' };
let allData = {}, contactLogs = JSON.parse(localStorage.getItem('contactLogs')||'[]'), selectedContactMethod = null, currentModalProduct = null, currentBranch = null;

function doLogin() {
  const id = document.getElementById('login-id').value.trim(), pw = document.getElementById('login-pw').value;
  if (USERS[id] && USERS[id] === pw) {
    document.getElementById('login-screen').style.display = 'none';
    document.getElementById('app').style.display = 'block';
    sessionStorage.setItem('loggedIn','1'); loadAllBranches();
  } else { document.getElementById('login-error').style.display = 'block'; }
}
function doLogout() { sessionStorage.removeItem('loggedIn'); location.reload(); }
if (sessionStorage.getItem('loggedIn')) { document.getElementById('login-screen').style.display='none'; document.getElementById('app').style.display='block'; loadAllBranches(); }

async function loadAllBranches() {
  document.getElementById('branch-grid').innerHTML = '<div class="loading"><span class="spinner"></span>데이터 불러오는 중...</div>';
  await Promise.all(BRANCHES.map(async b => {
    try { const r = await fetch(b.url+'?t='+Date.now()); allData[b.name] = await r.json(); }
    catch(e) { allData[b.name] = {error:true, shopName:b.name, products:[], history:[], violations:[]}; }
  }));
  renderDashboard(); renderHistoryFilters(); renderHistory(); renderContactTab();
  document.getElementById('last-updated').textContent = '마지막 새로고침: '+new Date().toLocaleTimeString('ko-KR');
}
function refreshAll() { loadAllBranches(); }

function switchTab(name, el) {
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  document.querySelectorAll('.tab-content').forEach(t=>t.classList.remove('active'));
  el.classList.add('active'); document.getElementById('tab-'+name).classList.add('active');
}

function renderDashboard() {
  let tp=0, tv=0, vb=0;
  const grid = document.getElementById('branch-grid'); grid.innerHTML = '';
  BRANCHES.forEach(b => {
    const data = allData[b.name]; if(!data) return;
    const products = data.products||[], violations = data.violations||[];
    tp += products.length; tv += violations.length; if(violations.length>0) vb++;
    const card = document.createElement('div');
    card.className = 'branch-card'+(violations.length>0?' has-violation':'');
    card.onclick = () => showBranchDetail(b.name);
    card.innerHTML = (violations.length>0?'<div class="violation-dot"></div>':'')+
      '<div class="branch-name">'+b.name+'</div>'+
      '<div class="branch-stats">'+
      '<span class="branch-stat total">전체 '+products.length+'개</span>'+
      (violations.length>0?'<span class="branch-stat violation">위반 '+violations.length+'건</span>':'<span class="branch-stat normal">정상</span>')+
      '</div>';
    grid.appendChild(card);
  });
  document.getElementById('stat-branches').textContent = BRANCHES.length;
  document.getElementById('stat-violation-branches').textContent = vb;
  document.getElementById('stat-violations').textContent = tv;
  document.getElementById('stat-total').textContent = tp;
}

function showBranchDetail(name) {
  currentBranch = name; const data = allData[name]; if(!data) return;
  document.getElementById('branch-list-view').style.display = 'none';
  document.getElementById('detail-view').style.display = 'block';
  document.getElementById('detail-branch-name').textContent = name;
  const products = data.products||[], violations = data.violations||[];
  document.getElementById('detail-stat-total').textContent = products.length;
  document.getElementById('detail-stat-violations').textContent = violations.length;
  const lc = products.find(p=>p.checkedAt);
  if(lc) document.getElementById('detail-stat-checked').textContent = new Date(lc.checkedAt).toLocaleString('ko-KR',{month:'numeric',day:'numeric',hour:'numeric',minute:'2-digit'});
  document.getElementById('detail-product-count').textContent = products.length+'개 상품';
  if(!products.length) { document.getElementById('detail-product-table').innerHTML='<div class="empty">상품 데이터가 없습니다</div>'; return; }
  let html = '<table><thead><tr><th>상품명</th><th>기준가</th><th>현재가</th><th>상태</th><th>마지막 점검</th><th>링크</th><th>연락</th></tr></thead><tbody>';
  products.forEach(p => {
    const iv = p.status==='위반', badge = iv?'<span class="badge badge-danger">위반</span>':'<span class="badge badge-success">정상</span>';
    const checked = p.checkedAt?new Date(p.checkedAt).toLocaleString('ko-KR',{month:'numeric',day:'numeric',hour:'numeric',minute:'2-digit'}):'-';
    const title = p.title?p.title.replace(/ : .+$/,''):'URL 확인 필요';
    html += '<tr style="'+(iv?'background:#fffafa;':'')+'"><td style="max-width:260px;word-break:break-word;">'+title+'</td><td style="font-weight:500;">'+(p.basePrice?p.basePrice.toLocaleString()+'원':'-')+'</td><td style="font-weight:500;'+(iv?'color:var(--danger);':'')+'">'+
    (p.currentPrice?p.currentPrice.toLocaleString()+'원':'-')+'</td><td>'+badge+'</td><td style="color:var(--text-muted);font-size:13px;">'+checked+'</td>'+
    '<td><a href="'+p.url+'" target="_blank" style="font-size:13px;">스토어 보기</a></td>'+
    '<td>'+(iv?'<button class="contact-btn" onclick=\'openModal('+JSON.stringify(p).replace(/'/g,"&#39;")+')\'>연락하기</button>':'')+'</td></tr>';
  });
  document.getElementById('detail-product-table').innerHTML = html+'</tbody></table>';
}

function goBack() { currentBranch=null; document.getElementById('branch-list-view').style.display='block'; document.getElementById('detail-view').style.display='none'; }

function renderHistoryFilters() {
  const sel = document.getElementById('history-branch-filter');
  sel.innerHTML = '<option value="">전체 지사</option>';
  BRANCHES.forEach(b => { const o=document.createElement('option'); o.value=b.name; o.textContent=b.name; sel.appendChild(o); });
}

function renderHistory() {
  const bf=document.getElementById('history-branch-filter')?.value||'', sf=document.getElementById('history-status-filter')?.value||'', df=document.getElementById('history-date-filter')?.value||'';
  let history = [];
  BRANCHES.forEach(b => { const data=allData[b.name]; if(data&&data.history) data.history.forEach(h=>history.push({...h,branchName:b.name})); });
  if(bf) history=history.filter(h=>h.shopName===bf||h.branchName===bf);
  if(sf) history=history.filter(h=>h.status===sf);
  if(df) history=history.filter(h=>h.checkedAt&&h.checkedAt.startsWith(df));
  history.sort((a,b)=>new Date(b.checkedAt)-new Date(a.checkedAt));
  document.getElementById('history-count').textContent = history.length+'건';
  if(!history.length) { document.getElementById('history-table').innerHTML='<div class="empty">가격 변동 이력이 없습니다</div>'; return; }
  let html='<table><thead><tr><th>변동 시각</th><th>지사</th><th>상품명</th><th>기준가</th><th>이전 가격</th><th>변동 후</th><th>상태</th></tr></thead><tbody>';
  history.forEach(h => {
    const badge=h.status==='위반'?'<span class="badge badge-danger">위반</span>':'<span class="badge badge-success">정상</span>';
    const diff=h.prevPrice&&h.currentPrice?h.currentPrice-h.prevPrice:null;
    const diffStr=diff!==null?(diff>0?'<span style="color:var(--success)">+'+diff.toLocaleString()+'원</span>':diff<0?'<span style="color:var(--danger)">'+diff.toLocaleString()+'원</span>':''):'';
    html+='<tr><td style="font-size:13px;color:var(--text-muted);white-space:nowrap;">'+(h.checkedAt?new Date(h.checkedAt).toLocaleString('ko-KR'):'-')+'</td><td style="font-size:13px;font-weight:500;">'+(h.shopName||h.branchName)+'</td><td style="max-width:200px;word-break:break-word;">'+(h.title?h.title.replace(/ : .+$/,''):'-')+'</td><td>'+(h.basePrice?h.basePrice.toLocaleString()+'원':'-')+'</td><td style="color:var(--text-muted);">'+(h.prevPrice?h.prevPrice.toLocaleString()+'원':'-')+'</td><td>'+(h.currentPrice?h.currentPrice.toLocaleString()+'원':'-')+' '+diffStr+'</td><td>'+badge+'</td></tr>';
  });
  document.getElementById('history-table').innerHTML=html+'</tbody></table>';
}

function clearHistoryFilter() { document.getElementById('history-branch-filter').value=''; document.getElementById('history-status-filter').value=''; document.getElementById('history-date-filter').value=''; renderHistory(); }

function getContactLog(url) { return contactLogs.filter(l=>l.url===url); }

function renderContactTab() {
  let ap=[];
  BRANCHES.forEach(b => { const data=allData[b.name]; if(data&&data.products) data.products.forEach(p=>ap.push({...p,branchName:b.name})); });
  const wl=ap.filter(p=>getContactLog(p.url).length>0);
  document.getElementById('contact-count').textContent=wl.length+'개 상품';
  if(!wl.length) { document.getElementById('contact-table').innerHTML='<div class="empty">아직 연락 이력이 없습니다</div>'; return; }
  let html='<table><thead><tr><th>지사</th><th>상품명</th><th>연락 횟수</th><th>연락 이력</th><th>마지막 연락</th></tr></thead><tbody>';
  wl.forEach(p => {
    const logs=getContactLog(p.url), ll=logs[logs.length-1];
    html+='<tr><td style="font-size:13px;font-weight:500;">'+p.branchName+'</td><td style="max-width:200px;word-break:break-word;">'+(p.title?p.title.replace(/ : .+$/,''):'URL 확인 필요')+'</td><td><span class="badge badge-warning">'+logs.length+'회</span></td><td><div class="contact-log">'+logs.map(l=>'<span class="contact-log-item">'+l.method+' '+formatDate(l.date)+'</span>').join('')+'</div></td><td style="font-size:13px;color:var(--text-muted);">'+formatDate(ll.date)+'<br><small>'+(ll.note||'')+'</small></td></tr>';
  });
  document.getElementById('contact-table').innerHTML=html+'</tbody></table>';
}

function openModal(p) {
  currentModalProduct=p; selectedContactMethod=null;
  document.getElementById('modal-product-name').textContent=p.title?p.title.replace(/ : .+$/,''):p.url;
  document.getElementById('modal-note').value='';
  document.querySelectorAll('.contact-option').forEach(el=>el.classList.remove('selected'));
  document.getElementById('contact-modal').classList.add('open');
}
function closeModal() { document.getElementById('contact-modal').classList.remove('open'); }
function selectContact(m) { selectedContactMethod=m; document.querySelectorAll('.contact-option').forEach(el=>el.classList.toggle('selected',el.textContent.includes(m))); }
function saveContact() {
  if(!selectedContactMethod) { alert('연락 방법을 선택해주세요'); return; }
  contactLogs.push({url:currentModalProduct.url,method:selectedContactMethod,note:document.getElementById('modal-note').value.trim(),date:new Date().toISOString(),productTitle:currentModalProduct.title});
  localStorage.setItem('contactLogs',JSON.stringify(contactLogs));
  closeModal(); renderContactTab(); if(currentBranch) showBranchDetail(currentBranch);
}
function formatDate(iso) { if(!iso) return '-'; return new Date(iso).toLocaleString('ko-KR',{month:'numeric',day:'numeric',hour:'numeric',minute:'2-digit'}); }
</script>
</body>
</html>
