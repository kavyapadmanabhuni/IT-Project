<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>timetrix — Complete</title>
<link rel="preconnect" href="https://fonts.gstatic.com">
<style>
  body.light-theme {
    --bg-1: #f5f6fa;
    --bg-2: #e9ecef;
    --panel: #f8f9fa;
    --card: #f3f4f8;
    --glass: rgba(0,0,0,0.04);
    --accent: #0056d6;
    --accent-2: #00c6fb;
    --accent-3: #ffd166;
    --muted: #6c757d;
    --success: #06d6a0;
    --danger: #ff7b7b;
    color: #222;
    text-shadow: none;
  }
  body.dark-theme {
    --bg-1: #181c2f;
    --bg-2: #232946;
    --panel: #232946;
    --card: #181c2f;
    --glass: rgba(0,198,251,0.10);
    --accent: #00c6fb;
    --accent-2: #ffd166;
    --accent-3: #06d6a0;
    --muted: #b0b8c1;
    --success: #06d6a0;
    --danger: #ff7b7b;
    color: #f5faff;
    text-shadow: 0 2px 16px rgba(0,198,251,0.18), 0 1px 0 #000;
  }
  h1, h2, h3, h4, h5, h6 {
    color: #00eaff;
    font-weight: 700;
    letter-spacing: 0.5px;
    text-shadow:
      0 0 12px #00eaff,
      0 2px 24px #00eaff,
      0 1px 0 #000;
    transition: color 0.2s;
  }
  p, li, td, th, .btn, .field {
    color: #f5faff;
    text-shadow:
      0 0 8px #00eaff,
      0 1px 0 #000;
    transition: color 0.2s;
  }
  /* ========= THEME & LAYOUT ========= */
  :root {
    --radius: 20px;
    font-family: "Inter", "Segoe UI", Roboto, Arial, sans-serif;
  }
  body.light-theme {
    --bg-1: #f5f7fa;
    --bg-2: #e3f0ff;
    --panel: #fff;
    --card: #eaf6ff;
    --glass: rgba(0,180,216,0.10);
    --accent: #0056d6;
    --accent-2: #00c6fb;
    --accent-3: #ffd166;
    --muted: #6c757d;
    --success: #06d6a0;
    --danger: #ff7b7b;
    color: #222;
  }
  body.dark-theme {
    --bg-1: #0a2540;
    --bg-2: #102542;
    --panel: #16213e;
    --card: #1b2a49;
    --glass: rgba(0,198,251,0.10);
    --accent: #00c6fb;
    --accent-2: #ffd166;
    --accent-3: #06d6a0;
    --muted: #b0b8c1;
    --success: #06d6a0;
    --danger: #ff7b7b;
    color: #f5faff;
  }
  *{box-sizing:border-box}
  html,body{
    height:100%;
    margin:0;
    background: #f5f7fa !important;
    color:#222;
    font-family: "Inter", "Segoe UI", Roboto, Arial, sans-serif;
  }
  a{color:var(--accent);text-decoration:none;font-weight:500;transition:color 0.2s;}
  a:hover{color:var(--accent-2);}
  .container{max-width:1100px;margin:48px auto;padding:0 32px;}
  h1, h2, h3, h4, h5, h6 {
    color: var(--accent);
    font-weight: 700;
    letter-spacing: 0.5px;
    text-shadow: 0 2px 8px rgba(0,198,251,0.18);
  }
  p, li, td, th, .btn, .field {
    color: #f5faff;
    text-shadow: 0 1px 4px rgba(0,0,0,0.18);
  }

  /* LOGIN / AUTH MODALS */
.center-screen {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background: #a7c7e7 !important; /* pastel blue */
}


  .auth-card{width:360px;padding:26px;border-radius:var(--radius);background:var(--card);box-shadow:0 4px 24px rgba(60,60,60,0.10);color:#222;}
  .auth-card * { color: #000 !important; }
  .auth-card h2{margin:0 0 12px;color:var(--accent)}
  .auth-card p{color:var(--muted);margin:8px 0 14px}

  input, select, textarea, button {font:inherit}
  .field{width:100%;padding:12px 14px;border-radius:10px;border:1px solid #e0e3ea;background:#f8f9fa;color:#222;outline:none;margin-bottom:12px;box-shadow:0 2px 8px rgba(60,60,60,0.06);transition:border-color 0.2s, box-shadow 0.2s;}
  .field:focus{border-color:var(--accent);box-shadow:0 6px 18px rgba(0,86,214,0.08)}

  .btn {
    display: inline-block;
    padding: 12px 24px;
    border-radius: 24px;
    border: none;
    cursor: pointer;
    font-weight: 600;
    background: linear-gradient(135deg, #5eb6e6 0%, #3a8edb 100%);
    color: #fff;
    box-shadow: 0 4px 16px rgba(60, 120, 180, 0.18), 0 1.5px 0 #fff inset;
    transition: background 0.2s, box-shadow 0.2s, transform 0.1s;
    outline: none;
    border: 1.5px solid #5eb6e6;
  }
  .btn:active {
    transform: translateY(2px) scale(0.98);
    box-shadow: 0 2px 8px rgba(60, 120, 180, 0.12);
  }
  .btn-primary {
    background: linear-gradient(135deg, #5eb6e6 0%, #3a8edb 100%);
    color: #fff;
    box-shadow: 0 4px 16px rgba(60, 120, 180, 0.18), 0 1.5px 0 #fff inset;
    border: 1.5px solid #5eb6e6;
  }
  .btn-primary:hover {
    background: linear-gradient(135deg, #3a8edb 0%, #5eb6e6 100%);
    box-shadow: 0 6px 24px rgba(60, 120, 180, 0.22);
  }
  .btn-ghost {
    background: transparent;
    border: 1.5px solid #5eb6e6;
    color: #3a8edb;
    box-shadow: none;
  }
  .link{color:var(--muted);cursor:pointer;font-size:14px}

  /* APP */
  .app-header{display:flex;justify-content:space-between;align-items:center;padding:14px;border-radius:12px;background:var(--card);box-shadow:0 8px 30px rgba(0,0,0,0.6)}
  .brand{display:flex;gap:12px;align-items:center}
  .brand .logo-box{width:46px;height:46px;border-radius:10px;background:linear-gradient(135deg,var(--accent),var(--accent-2))}
  .brand h1{font-size:18px;margin:0}
  .nav{display:flex;gap:8px}
  .nav button {
    background: linear-gradient(135deg, #5eb6e6 0%, #3a8edb 100%);
    border: 1.5px solid #5eb6e6;
    padding: 12px 24px;
    border-radius: 24px;
    color: #fff;
    cursor: pointer;
    font-weight: 600;
    box-shadow: 0 4px 16px rgba(60, 120, 180, 0.18), 0 1.5px 0 #fff inset;
    margin-right: 6px;
    transition: background 0.2s, box-shadow 0.2s, transform 0.1s;
  }
  .nav button.active {
    background: linear-gradient(135deg, #3a8edb 0%, #5eb6e6 100%);
    color: #ffd166;
    font-weight: 700;
    box-shadow: 0 6px 24px rgba(60, 120, 180, 0.22);
    border: 1.5px solid #3a8edb;
  }

  .layout{display:grid;grid-template-columns:320px 1fr;gap:40px;margin-top:40px;min-height:70vh;}
  .sidebar{background:var(--card);padding:32px;border-radius:var(--radius);min-height:520px;box-shadow:0 2px 12px rgba(0,198,251,0.18);margin-bottom:40px;}
  .main{padding:40px;background:var(--panel);border-radius:var(--radius);box-shadow:0 2px 12px rgba(0,198,251,0.18);margin-bottom:40px;}
  .panel{background:var(--panel);padding:18px 20px;border-radius:16px;margin-bottom:18px;box-shadow:0 4px 24px rgba(60,60,60,0.10);}
  .small{font-size:13px;color:var(--muted)}

  /* department list */
  .dept-list{display:flex;flex-direction:column;gap:8px;margin-top:10px}
  .dept-item{display:flex;justify-content:space-between;align-items:center;padding:10px;border-radius:10px;background:var(--card)}
  .dept-item .meta{color:var(--muted);font-size:13px}

  /* tables */
  table{width:100%;border-collapse:collapse;margin-top:8px}
  th,td{padding:8px;border:1px solid rgba(255,255,255,0.05);text-align:left}
  th{background:rgba(255,255,255,0.03);font-weight:700}

  /* rooms grid */
  .rooms-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
  .room-card{padding:12px;border-radius:10px;background:var(--card)}
  .device-row{display:flex;justify-content:space-between;align-items:center;padding:8px;border-radius:8px;background:rgba(255,255,255,0.02);margin-top:8px}

  /* timetable */
  .tt-wrap{overflow:auto}
  .subject-pill{display:inline-block;padding:6px 8px;border-radius:8px;background:rgba(255,255,255,0.03);font-weight:700}

  /* modal */
  .modal-backdrop{position:fixed;inset:0;background:rgba(0,0,0,0.5);display:none;align-items:center;justify-content:center;z-index:60}
  .modal{background:linear-gradient(180deg,#071021,#0b1220);padding:18px;border-radius:10px;min-width:320px;box-shadow:0 12px 40px rgba(0,0,0,0.8)}
  .modal h3{margin:0 0 12px}

  /* responsive */
  @media (max-width:980px){
    .layout{grid-template-columns:1fr}
    .rooms-grid{grid-template-columns:1fr}
  }
</style>
</head>
<body>

<!-- ========== AUTH SCREENS ========== -->
<div id="authRoot" class="center-screen">
  <div class="auth-card" id="signInCard">
    <h2>TIMETRIX</h2>
    <p class="small">Schedule smarter shine brighter.</p>
    <input id="authEmail" class="field" placeholder="Email" type="email" value="">
    <input id="authPassword" class="field" placeholder="Password" type="password" value="">
    <button class="btn btn-primary" id="authSignIn">Sign in</button>
    <div style="display:flex;justify-content:space-between;margin-top:10px">
      <div class="link" id="showForgot">Forgot password?</div>
      <div class="link" id="openRegister">Register</div>
    </div>
    <p id="authMsg" class="small" style="margin-top:10px;color:var(--danger)"></p>
  </div>
</div>

<!-- OTP modal (used in forgot password) -->
<div class="modal-backdrop" id="otpModal">
  <div class="modal">
    <h3>Email Verification (OTP)</h3>
    <p class="small">We sent an OTP to your email (demo: shown in-site). Enter it to reset your password.</p>
    <input id="otpInput" class="field" placeholder="Enter OTP">
    <div style="display:flex;gap:8px;justify-content:flex-end">
      <button class="btn btn-ghost" id="otpCancel">Cancel</button>
      <button class="btn btn-primary" id="otpVerify">Verify</button>
    </div>
    <p id="otpNote" class="small" style="margin-top:8px;color:var(--muted)"></p>
  </div>
</div>

<!-- Reset modal -->
<div class="modal-backdrop" id="resetModal">
  <div class="modal">
    <h3>Reset Password</h3>
    <input id="resetNewPass" class="field" placeholder="New password">
    <div style="display:flex;gap:8px;justify-content:flex-end">
      <button class="btn btn-ghost" id="resetCancel">Cancel</button>
      <button class="btn btn-primary" id="resetSubmit">Set Password</button>
    </div>
    <p id="resetNote" class="small" style="margin-top:8px;color:var(--muted)"></p>
  </div>
</div>

<!-- Register modal -->
<div class="modal-backdrop" id="registerModal">
  <div class="modal">
    <h3>Register</h3>
    <input id="regEmail" class="field" placeholder="Email">
    <input id="regPass" class="field" placeholder="Password" type="password">
    <div style="display:flex;gap:8px;justify-content:flex-end">
      <button class="btn btn-ghost" id="regCancel">Cancel</button>
      <button class="btn btn-primary" id="regSubmit">Create Account</button>
    </div>
    <p id="regNote" class="small" style="margin-top:8px;color:var(--muted)"></p>
  </div>
</div>

<!-- ========== APPLICATION ROOT ========= -->
<div class="container" id="appRoot" style="display:none">

  <!-- Header removed: navigation and info are now in the sidebar only -->

  <!-- Layout -->
  <div class="layout">

    <!-- Sidebar -->
    <aside class="sidebar" style="height:calc(100vh - 80px);display:flex;flex-direction:column;justify-content:flex-start;align-items:stretch;">
      <div class="panel" style="flex:1;display:flex;flex-direction:column;justify-content:flex-start;align-items:stretch;min-height:600px;">
        <strong style="margin-bottom:18px;font-size:20px;">Main Menu</strong>
        <div class="nav" role="navigation" style="flex-direction:column;gap:18px;margin-bottom:32px;">
          <button data-view="dashboard" class="active">Dashboard</button>
          <button data-view="departments">Departments</button>
          <button data-view="timetable">Timetable</button>
          <button data-view="classrooms">Smart Classrooms</button>
          <button data-view="settings">Settings</button>
        </div>
        <button class="btn btn-primary" id="btnQuickGen" style="margin-bottom:24px;">Generate Now</button>
        <button class="btn btn-ghost" id="signOutBtn" style="margin-top:auto;">Sign out</button>
        <div style="margin-top:24px;">
          <div class="small" id="sessionInfo" style="margin-bottom:8px;font-weight:600;">Not signed in</div>
          <div class="small" id="statSummary" style="margin-bottom:8px;">Loading...</div>
          <div class="small" style="margin-bottom:8px;">Email: <span id="acctEmail">—</span></div>
          <div class="small" style="margin-bottom:0;color:#888;font-size:12px;">Local-only demo: use a server for real auth & email</div>
        </div>
        <div style="margin-top:12px;text-align:center;">
          <button class="btn btn-ghost" id="exportAll">Export All Timetables (CSV)</button>
        </div>
      </div>
    </aside>

    <!-- Main -->
    <main class="main">

      <!-- Dashboard -->
  <section class="panel" data-screen="dashboard" style="background:#000;box-shadow:0 2px 16px rgba(0,0,0,0.18);border-radius:var(--radius);">
        <h2 style="color:#00c6fb;text-shadow:0 2px 16px rgba(0,198,251,0.18)">Dashboard</h2>
        <div class="small" style="color:#ffd166">Overview of your scheduler</div>
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:18px;margin-top:18px">
          <div class="panel" style="background:#232946;color:#fff;box-shadow:0 2px 8px rgba(0,198,251,0.10);">
            <div class="small" style="color:#ffd166">Departments</div>
            <div id="statDeptCount" style="font-weight:800;font-size:20px;color:#00c6fb;">0</div>
          </div>
          <div class="panel" style="background:#232946;color:#fff;box-shadow:0 2px 8px rgba(0,198,251,0.10);">
            <div class="small" style="color:#ffd166">Smart Classrooms</div>
            <div id="statRoomCount" style="font-weight:800;font-size:20px;color:#00c6fb;">0</div>
          </div>
          <div class="panel" style="background:#232946;color:#fff;box-shadow:0 2px 8px rgba(0,198,251,0.10);">
            <div class="small" style="color:#ffd166">Timetables Generated</div>
            <div id="statTTCount" style="font-weight:800;font-size:20px;color:#00c6fb;">0</div>
          </div>
        </div>
      </section>

      <!-- Departments -->
      <section class="panel" data-screen="departments" style="display:none;background:#000;box-shadow:0 2px 16px rgba(0,0,0,0.18);border-radius:var(--radius);color:#f5faff;">
        <h2 style="color:#00eaff;text-shadow:0 2px 16px #00eaff">Departments</h2>
        <div style="display:flex;gap:12px;align-items:center">
          <input id="newDeptName" class="field" placeholder="New department name">
          <button class="btn btn-primary" id="addDeptBtn">Add Dept</button>
        </div>

        <div style="display:flex;gap:14px;margin-top:12px">
          <div style="flex:1">
            <div class="panel" style="background:#181818;color:#f5faff;">
              <h3 class="small">Departments list</h3>
              <div class="dept-list" id="deptList"></div>
            </div>
          </div>

          <div style="flex:1.4">
            <div id="deptConfigPanel" class="panel" style="background:#181818;color:#f5faff;">
              <h3 id="deptConfigTitle">Select a department to configure</h3>

              <div id="deptConfigArea" style="display:none">
                <div style="display:flex;gap:8px">
                  <div style="flex:1"><label class="small">Sections</label><input id="cfgSections" class="field" type="number" min="1" value="1"></div>
                  <div style="flex:1"><label class="small">Days</label><input id="cfgDays" class="field" type="number" min="1" value="5"></div>
                  <div style="flex:1"><label class="small">Periods</label><input id="cfgPeriods" class="field" type="number" min="1" value="6"></div>
                </div>

                <div style="margin-top:8px"><label class="small">Subjects (comma separated)</label><input id="cfgSubjects" class="field" placeholder="Math,Physics,DSA"></div>

                <div style="margin-top:10px"><h4 class="small">Faculty</h4>
                  <div style="display:flex;gap:8px">
                    <input id="facName" class="field" placeholder="Faculty name">
                    <input id="facSubject" class="field" placeholder="Subject">
                    <button class="btn btn-primary" id="addFacultyBtn">Add</button>
                  </div>
                  <table id="facultyTable"><thead><tr><th>Name</th><th>Subject</th><th>Action</th></tr></thead><tbody></tbody></table>
                </div>

                <div style="display:flex;justify-content:flex-end;gap:8px;margin-top:12px">
                  <button class="btn btn-ghost" id="cfgCancel">Cancel</button>
                  <button class="btn btn-primary" id="cfgSave">Save & Generate Timetables</button>
                </div>
              </div>

            </div>
          </div>
        </div>
      </section>

      <!-- Timetable viewer -->
      <section class="panel" data-screen="timetable" style="display:none;background:#000;box-shadow:0 2px 16px rgba(0,0,0,0.18);border-radius:var(--radius);color:#f5faff;">
        <h2 style="color:#00eaff;text-shadow:0 2px 16px #00eaff">Timetable Viewer</h2>
        <div style="display:flex;gap:8px;align-items:center">
          <select id="ttDeptSelect" class="field" style="width:260px"></select>
          <select id="ttSectionSelect" class="field" style="width:200px"></select>
          <select id="ttRoomSelect" class="field" style="width:220px">
            <option value="">— (don't assign room) —</option>
          </select>
          <button class="btn btn-primary" id="ttRefresh">Show</button>
          <button class="btn btn-ghost" id="ttExport">Export CSV</button>
        </div>
        <div class="tt-wrap" id="timetableContainer" style="margin-top:12px"></div>
      </section>

      <!-- Smart Classrooms -->
      <section class="panel" data-screen="classrooms" style="display:none;background:#000;box-shadow:0 2px 16px rgba(0,0,0,0.18);border-radius:var(--radius);color:#f5faff;">
        <h2 style="color:#00eaff;text-shadow:0 2px 16px #00eaff">Smart Classrooms</h2>
        <div style="display:flex;gap:8px;align-items:center">
          <input id="newRoomInput" class="field" placeholder="Room name (e.g. R101)">
          <button class="btn btn-primary" id="addRoomBtn">Add Room</button>
        </div>

        <div class="rooms-grid" id="roomList" style="margin-top:12px"></div>
      </section>

      <!-- Settings -->
      <section class="panel" data-screen="settings" style="display:none;background:#000;box-shadow:0 2px 16px rgba(0,0,0,0.18);border-radius:var(--radius);color:#f5faff;">
        <h2 style="color:#00eaff;text-shadow:0 2px 16px #00eaff">Settings & Security</h2>
        <div class="small">This demo stores data in your browser (localStorage). For a production system, use a backend to store users, send real OTP emails, and hash passwords (bcrypt).</div>

        <div style="margin-top:12px">
          <label class="small">Change demo admin password</label>
          <input id="chgPass" class="field" placeholder="New password">
          <button class="btn btn-primary" id="chgPassBtn">Change Password</button>
        </div>

        <div style="margin-top:12px">
          <button class="btn btn-ghost" id="clearAll">Reset demo data (clear localStorage)</button>
        </div>
      </section>

    </main>

  </div>
</div>

<script>
/*
  Smart Scheduler Pro (single-file demo)
  - Local-only demo: localStorage stores data, sessionStorage stores session token
  - OTP is simulated; comments show where to integrate real backend/email service
  - Timetable generator avoids teacher clashes across sections for same slot
*/

/* ======= Utilities & Storage ======= */

const STORAGE_KEY = 'ss_pro_data_v1';
const USER_KEY = 'ss_pro_users_v1';
const SESSION_KEY = 'ss_pro_session_v1';

function nowStr(){ return new Date().toISOString(); }

function loadData(){
  try{
    const raw = localStorage.getItem(STORAGE_KEY);
    if(!raw) return { departments: {}, classrooms:{}, stats:{ttGenerated:0} };
    return JSON.parse(raw);
  }catch(e){ return { departments: {}, classrooms:{}, stats:{ttGenerated:0} };}
}
function saveData(data){ localStorage.setItem(STORAGE_KEY, JSON.stringify(data)); }

function loadUsers(){
  try{ const raw = localStorage.getItem(USER_KEY); if(!raw) return {}; return JSON.parse(raw);}catch(e){return {}}
}
function saveUsers(users){ localStorage.setItem(USER_KEY, JSON.stringify(users)); }

function createSession(email){
  const token = `${email}::${Date.now()}`;
  sessionStorage.setItem(SESSION_KEY, token);
}
function destroySession(){ sessionStorage.removeItem(SESSION_KEY);}
function getSession(){
  const t = sessionStorage.getItem(SESSION_KEY);
  if(!t) return null;
  const email = t.split('::')[0]; return { email };
}

function requireAuth(fn){
  return (...args) => {
    if(!getSession()){ alert('Please sign in to perform this action.'); return; }
    return fn(...args);
  }
}

/* ======= Demo setup: default admin user & seed data ======= */

let DATA = loadData();
let USERS = loadUsers();

// Create demo admin user if none
if(Object.keys(USERS).length === 0){
  // NOTE: For production, DO NOT store plaintext passwords. Use server + hashed passwords.
  USERS['admin@demo.com'] = { email:'admin@demo.com', password:'1234', created: nowStr() };
  saveUsers(USERS);
}

/* ======= AUTH UI & Flows (email+password, forgot->OTP->reset) ======= */

const authRoot = document.getElementById('authRoot');
const signInCard = document.getElementById('signInCard');
const authEmail = document.getElementById('authEmail');
const authPassword = document.getElementById('authPassword');
const authSignIn = document.getElementById('authSignIn');
const authMsg = document.getElementById('authMsg');
const showForgotBtn = document.getElementById('showForgot');
const otpModal = document.getElementById('otpModal');
const otpInput = document.getElementById('otpInput');
const otpVerifyBtn = document.getElementById('otpVerify');
const otpCancelBtn = document.getElementById('otpCancel');
const otpNote = document.getElementById('otpNote');
const resetModal = document.getElementById('resetModal');
const resetNewPass = document.getElementById('resetNewPass');
const resetSubmit = document.getElementById('resetSubmit');
const resetCancel = document.getElementById('resetCancel');
const registerModal = document.getElementById('registerModal');
const openRegister = document.getElementById('openRegister');
const regEmail = document.getElementById('regEmail');
const regPass = document.getElementById('regPass');
const regSubmit = document.getElementById('regSubmit');
const regCancel = document.getElementById('regCancel');

let otpForEmail = null;
let otpValue = null;

function openAppAs(email){
  // mark session, show app, hide auth
  createSession(email);
  document.getElementById('appRoot').style.display = 'block';
  authRoot.style.display = 'none';
  document.getElementById('userEmailDisplay').textContent = email;
  document.getElementById('acctEmail').textContent = email;
  document.getElementById('sessionInfo').textContent = `Signed in as ${email}`;
  refreshAllUI();
}

authSignIn.addEventListener('click', ()=>{
  const e = authEmail.value.trim().toLowerCase();
  const p = authPassword.value;
  if(!e || !p){ authMsg.textContent = 'Enter email & password'; return; }
  const user = USERS[e];
  if(!user || user.password !== p){ authMsg.textContent = 'Invalid credentials'; return; }
  authMsg.textContent = '';
  openAppAs(e);
});

// Register (demo)
openRegister.addEventListener('click', ()=> {
  showModal(registerModal);
});
regCancel.addEventListener('click', ()=> hideModal(registerModal));
regSubmit.addEventListener('click', ()=>{
  const e = regEmail.value.trim().toLowerCase();
  const p = regPass.value;
  if(!e || !p){ document.getElementById('regNote').textContent = 'Enter email & password'; return; }
  if(USERS[e]){ document.getElementById('regNote').textContent = 'Account exists'; return; }
  USERS[e] = { email:e, password:p, created: nowStr() };
  saveUsers(USERS);
  document.getElementById('regNote').textContent = 'Account created — you can sign in now';
  setTimeout(()=> { hideModal(registerModal); authEmail.value = e; }, 900);
});

// Forgot flow: show OTP modal and simulate sending
showForgotBtn.addEventListener('click', ()=>{
  const e = document.getElementById('authEmail').value.trim().toLowerCase();
  if(!e){ authMsg.textContent = 'Enter email to reset'; return; }
  if(!USERS[e]){ authMsg.textContent = 'No account with that email'; return; }
  // Generate OTP and "send" — in demo show note; in real app call backend to email OTP
  otpValue = (Math.floor(100000 + Math.random()*900000)).toString();
  otpForEmail = e;
  // DEMO: show OTP in note (you should remove this in production)
  otpNote.textContent = `Demo OTP: ${otpValue} (In production, this would be emailed)`;
  otpInput.value = '';
  showModal(otpModal);
  // Real integration (server): make a POST to your backend endpoint that sends an email with the OTP
  // fetch('/api/send-otp', {method:'POST', body: JSON.stringify({email:e})})
});

otpCancelBtn.addEventListener('click', ()=> hideModal(otpModal));

otpVerifyBtn.addEventListener('click', ()=>{
  const v = otpInput.value.trim();
  if(!v){ document.getElementById('otpNote').textContent = 'Enter the OTP'; return; }
  if(v !== otpValue){ document.getElementById('otpNote').textContent = 'Invalid OTP'; return; }
  // OTP valid — open reset modal
  hideModal(otpModal);
  showModal(resetModal);
  document.getElementById('resetNote').textContent = `Reset password for ${otpForEmail}`;
});

resetCancel.addEventListener('click', ()=> hideModal(resetModal));

resetSubmit.addEventListener('click', ()=>{
  const np = resetNewPass.value;
  if(!np || np.length < 4){ document.getElementById('resetNote').textContent = 'Password too short'; return; }
  // Update password for otpForEmail
  if(otpForEmail && USERS[otpForEmail]){
    USERS[otpForEmail].password = np;
    saveUsers(USERS);
    hideModal(resetModal);
    alert('Password updated. Please sign in.');
    // Reset variables
    otpForEmail = null; otpValue = null;
  } else {
    document.getElementById('resetNote').textContent = 'Unexpected error';
  }
});

/* sign out */
document.getElementById('signOutBtn').addEventListener('click', ()=>{
  destroySession();
  document.getElementById('appRoot').style.display = 'none';
  authRoot.style.display = 'flex';
  authEmail.value = '';
  authPassword.value = '';
});

/* ======= Modal helpers ======= */
function showModal(el){ el.style.display = 'flex'; el.style.alignItems='center'; el.style.justifyContent='center'; }
function hideModal(el){ el.style.display = 'none'; }

/* ======= Core app: data model and UI glue ======= */

DATA = loadData(); // ensure in-memory

// UI elements
const navButtons = document.querySelectorAll('.nav button');
navButtons.forEach(btn => btn.addEventListener('click', ()=>{
  navButtons.forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('[data-screen]').forEach(s => s.style.display = s.dataset.screen === btn.dataset.view ? '' : 'none');
}));

// initial screen: dashboard
document.querySelector('.nav button[data-view="dashboard"]').click();

// Stats UI
function refreshStats(){
  document.getElementById('statDeptCount').textContent = Object.keys(DATA.departments || {}).length;
  document.getElementById('statRoomCount').textContent = Object.keys(DATA.classrooms || {}).length;
  document.getElementById('statTTCount').textContent = (DATA.stats && DATA.stats.ttGenerated) ? DATA.stats.ttGenerated : 0;
  document.getElementById('statSummary').textContent = `${Object.keys(DATA.departments||{}).length} depts • ${Object.keys(DATA.classrooms||{}).length} rooms • ${DATA.stats?DATA.stats.ttGenerated:0} timetables`;
}

// Department CRUD
const deptListEl = document.getElementById('deptList');
const addDeptBtn = document.getElementById('addDeptBtn');
const newDeptName = document.getElementById('newDeptName');

addDeptBtn.addEventListener('click', requireAuth(()=> {
  const name = newDeptName.value.trim();
  if(!name) return alert('Enter a department name');
  if(DATA.departments[name]) return alert('Department exists');
  DATA.departments[name] = { subjects: [], faculty: [], numSections:1, days:5, periods:6, timetables:{} };
  saveData(DATA);
  newDeptName.value = '';
  renderDeptList();
}));

function renderDeptList(){
  deptListEl.innerHTML = '';
  const names = Object.keys(DATA.departments);
  if(names.length===0){
    deptListEl.innerHTML = '<div class="small">No departments yet</div>';
  } else {
    names.forEach(name=>{
      const d = DATA.departments[name];
      const item = document.createElement('div'); item.className='dept-item';
      item.innerHTML = `<div>
                          <div style="font-weight:700">${escapeHtml(name)}</div>
                          <div class="meta">${d.faculty.length} faculty • ${d.subjects.length} subjects • ${d.numSections||0} sections</div>
                        </div>
                        <div style="display:flex;gap:8px">
                          <button class="btn btn-ghost" data-action="open">Open</button>
                          <button class="btn btn-ghost" data-action="delete">Delete</button>
                        </div>`;
      item.querySelector('[data-action="open"]').addEventListener('click', ()=> openDeptConfig(name));
      item.querySelector('[data-action="delete"]').addEventListener('click', requireAuth(()=> {
        if(!confirm(`Delete department "${name}" and its timetables?`)) return;
        delete DATA.departments[name];
        saveData(DATA);
        renderDeptList();
        refreshAllUI();
      }));
      deptListEl.appendChild(item);
    });
  }
  refreshStats();
}
renderDeptList();

/* Dept config area */
const deptConfigTitle = document.getElementById('deptConfigTitle');
const deptConfigArea = document.getElementById('deptConfigArea');
const cfgSections = document.getElementById('cfgSections');
const cfgDays = document.getElementById('cfgDays');
const cfgPeriods = document.getElementById('cfgPeriods');
const cfgSubjects = document.getElementById('cfgSubjects');
const facName = document.getElementById('facName');
const facSubject = document.getElementById('facSubject');
const addFacultyBtn = document.getElementById('addFacultyBtn');
const facultyTbody = document.querySelector('#facultyTable tbody');
const cfgCancel = document.getElementById('cfgCancel');
const cfgSave = document.getElementById('cfgSave');

let activeDept = null;

function openDeptConfig(name){
  activeDept = name;
  const dept = DATA.departments[name];
  deptConfigTitle.textContent = `Configure: ${name}`;
  deptConfigArea.style.display = '';
  cfgSections.value = dept.numSections || 1;
  cfgDays.value = dept.days || 5;
  cfgPeriods.value = dept.periods || 6;
  cfgSubjects.value = (dept.subjects || []).join(', ');
  renderFacultyTable();
  // switch to Departments screen
  document.querySelector('.nav button[data-view="departments"]').click();
}

function closeDeptConfig(){
  activeDept = null;
  deptConfigTitle.textContent = 'Select a department to configure';
  deptConfigArea.style.display = 'none';
}

function renderFacultyTable(){
  facultyTbody.innerHTML = '';
  if(!activeDept) return;
  const list = DATA.departments[activeDept].faculty || [];
  if(!list.length){
    facultyTbody.innerHTML = '<tr><td colspan="3" class="small">No faculty added</td></tr>';
    return;
  }
  list.forEach((f,i)=>{
    const tr = document.createElement('tr');
    tr.innerHTML = `<td>${escapeHtml(f.name)}</td><td>${escapeHtml(f.subject)}</td><td><button class="btn btn-ghost" data-i="${i}">Delete</button></td>`;
    tr.querySelector('button').addEventListener('click', requireAuth(()=> {
      DATA.departments[activeDept].faculty.splice(i,1);
      saveData(DATA);
      renderFacultyTable();
    }));
    facultyTbody.appendChild(tr);
  });
}

addFacultyBtn.addEventListener('click', requireAuth(()=> {
  if(!activeDept) return alert('Open a department first');
  const n = facName.value.trim(), s = facSubject.value.trim();
  if(!n || !s) return alert('Enter both name and subject');
  DATA.departments[activeDept].faculty.push({name:n, subject:s});
  saveData(DATA);
  facName.value = facSubject.value = '';
  renderFacultyTable();
}));

cfgCancel.addEventListener('click', ()=> closeDeptConfig());

cfgSave.addEventListener('click', requireAuth(()=> {
  if(!activeDept) return alert('Open a department first');
  const subjects = cfgSubjects.value.split(',').map(x=>x.trim()).filter(Boolean);
  const numSections = Math.max(1, parseInt(cfgSections.value) || 1);
  const days = Math.max(1, parseInt(cfgDays.value) || 5);
  const periods = Math.max(1, parseInt(cfgPeriods.value) || 6);
  if(subjects.length === 0) return alert('Add at least one subject');
  if((DATA.departments[activeDept].faculty || []).length === 0) return alert('Add faculty first');
  const dept = DATA.departments[activeDept];
  dept.subjects = subjects;
  dept.numSections = numSections;
  dept.days = days;
  dept.periods = periods;
  // Generate timetables with clash-free algorithm
  dept.timetables = generateClashFreeTimetablesForDept(dept);
  DATA.stats = DATA.stats || {};
  DATA.stats.ttGenerated = (DATA.stats.ttGenerated || 0) + Object.keys(dept.timetables).length;
  saveData(DATA);
  alert('Timetables generated successfully.');
  populateTimetableSelectors();
  renderDeptList();
  refreshAllUI();
}));

/* ====== Timetable generator (clash-free across teachers & rooms) ====== */

/*
 Algorithm approach (greedy, round-robin + conflict checks):
 - For each department:
   - Build mapping subject -> list of teachers able to teach it
   - For each section s (1..numSections):
     - Initialize empty table [days][periods]
 - Use slot-by-slot assignment across sections:
   For day in 0..days-1:
     For period in 0..periods-1:
       For each section in 1..numSections:
         Attempt to assign a subject + teacher such that:
           - The teacher is not already assigned to any *other section* in the same (day,period)
           - Prefer to balance subject frequency (round-robin list)
       If couldn't find any teacher for a subject (rare), mark "TBA"
 This ensures no teacher is scheduled to more than one section at same slot.
*/
function generateClashFreeTimetablesForDept(dept){
  const subjects = dept.subjects.slice();
  const days = dept.days;
  const periods = dept.periods;
  const numSections = dept.numSections;
  const faculty = dept.faculty || [];
  // build map subject -> teachers
  const subjMap = {};
  for(const f of faculty){
    if(!subjMap[f.subject]) subjMap[f.subject] = [];
    subjMap[f.subject].push(f.name);
  }
  // fallback: if some subject has no teacher, it will be TBA
  const timetables = {};
  for(let s=1;s<=numSections;s++){
    timetables[`Section ${s}`] = Array.from({length:days}, ()=> Array.from({length:periods}, ()=> ({subject:'', teacher:''})));
  }

  // track (day,period) -> set of teachers assigned (to avoid duplicates)
  const slotAssignedTeachers = {}; // key: `${d}-${p}` -> Set()

  // for some subject ordering, create a queue per section to rotate subjects
  const subjQueues = {};
  for(let s=1;s<=numSections;s++){
    // start offset so sections don't all pick same subject in same order
    const offset = (s-1) % subjects.length;
    subjQueues[s] = subjects.slice(offset).concat(subjects.slice(0, offset));
  }

  // iterate day & period, then assign each section
  for(let d=0; d<days; d++){
    for(let p=0; p<periods; p++){
      const slotKey = `${d}-${p}`;
      slotAssignedTeachers[slotKey] = new Set();
      for(let s=1; s<=numSections; s++){
        let assigned = false;
        // try all subjects in rotation order for this section
        const q = subjQueues[s];
        for(let qidx=0; qidx<q.length; qidx++){
          const subj = q[(p + qidx) % q.length]; // some deterministic variation
          const teachers = subjMap[subj] || [];
          // try to pick a teacher not used in this slot
          let chosenTeacher = null;
          for(const t of teachers){
            if(!slotAssignedTeachers[slotKey].has(t)){
              chosenTeacher = t;
              break;
            }
          }
          if(chosenTeacher){
            timetables[`Section ${s}`][d][p] = { subject: subj, teacher: chosenTeacher };
            slotAssignedTeachers[slotKey].add(chosenTeacher);
            assigned = true;
            break;
          }
        }
        if(!assigned){
          // no teacher available for chosen subjects -> assign subject but teacher TBA
          const subjFallback = subjects[(p + s -1) % subjects.length];
          timetables[`Section ${s}`][d][p] = { subject: subjFallback, teacher: 'TBA' };
        }
      }
    }
  }
  return timetables;
}

/* ======= Timetable UI: selectors & rendering ======= */

const ttDeptSelect = document.getElementById('ttDeptSelect');
const ttSectionSelect = document.getElementById('ttSectionSelect');
const ttRoomSelect = document.getElementById('ttRoomSelect');
const ttRefresh = document.getElementById('ttRefresh');
const timetableContainer = document.getElementById('timetableContainer');
const ttExport = document.getElementById('ttExport');

function populateTimetableSelectors(){
  ttDeptSelect.innerHTML = '';
  const depts = Object.keys(DATA.departments);
  if(depts.length === 0){
    ttDeptSelect.innerHTML = '<option value="">No departments</option>';
    ttSectionSelect.innerHTML = '<option value="">-</option>';
    return;
  }
  depts.forEach(name=>{
    const opt = document.createElement('option'); opt.value = name; opt.textContent = name;
    ttDeptSelect.appendChild(opt);
  });
  ttDeptSelect.dispatchEvent(new Event('change'));
  populateRoomSelect();
}

ttDeptSelect.addEventListener('change', ()=>{
  const dname = ttDeptSelect.value;
  ttSectionSelect.innerHTML = '';
  if(!dname) return;
  const tt = DATA.departments[dname].timetables || {};
  Object.keys(tt).forEach(sec=>{
    const opt = document.createElement('option'); opt.value = sec; opt.textContent = sec;
    ttSectionSelect.appendChild(opt);
  });
});

ttRefresh.addEventListener('click', ()=> {
  const d = ttDeptSelect.value, s = ttSectionSelect.value;
  if(!d || !s) return alert('Select dept & section');
  renderTimetable(d, s);
});

ttExport.addEventListener('click', ()=> {
  const d = ttDeptSelect.value, s = ttSectionSelect.value;
  if(!d || !s) return alert('Select dept & section');
  exportTimetableCSV(d, s);
});

function renderTimetable(deptName, sectionName){
  const dept = DATA.departments[deptName];
  if(!dept || !dept.timetables || !dept.timetables[sectionName]){ timetableContainer.innerHTML = '<div class="small">No timetable available</div>'; return; }
  const table = dept.timetables[sectionName];
  const days = dept.days; const periods = dept.periods;
  let html = `<table><thead><tr><th>Day / Period</th>`;
  for(let p=1;p<=periods;p++) html += `<th>P${p}</th>`;
  html += `</tr></thead><tbody>`;
  table.forEach((row,di)=>{
    html += `<tr><td style="font-weight:700">Day ${di+1}</td>`;
    row.forEach(cell=>{
      html += `<td><div class="subject-pill">${escapeHtml(cell.subject)}</div><div class="small">${escapeHtml(cell.teacher)}</div></td>`;
    });
    html += `</tr>`;
  });
  html += `</tbody></table>`;
  timetableContainer.innerHTML = html;
}

function exportTimetableCSV(deptName, sectionName){
  const dept = DATA.departments[deptName];
  const tt = dept.timetables[sectionName];
  if(!tt) return alert('No timetable');
  const rows = [];
  const header = ['Day'].concat(Array.from({length:dept.periods}, (_,i)=>`P${i+1}`));
  rows.push(header.join(','));
  tt.forEach((r,di)=>{
    const cols = [`Day ${di+1}`].concat(r.map(c=>`${c.subject} (${c.teacher})`));
    rows.push(cols.map(v=>`"${v.replace(/"/g,'""')}"`).join(','));
  });
  const csv = rows.join('\n');
  const blob = new Blob([csv], {type:'text/csv'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a'); a.href = url; a.download = `${deptName}_${sectionName}.csv`; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
}

/* ======= Smart Classrooms CRUD ======= */

const roomListEl = document.getElementById('roomList');
const addRoomBtn = document.getElementById('addRoomBtn');
const newRoomInput = document.getElementById('newRoomInput');

addRoomBtn.addEventListener('click', requireAuth(()=> {
  const name = newRoomInput.value.trim(); if(!name) return alert('Enter room name');
  if(DATA.classrooms[name]) return alert('Room exists');
  DATA.classrooms[name] = { devices:{projector:true,ac:false,smartboard:true}, assigned:null }; saveData(DATA); newRoomInput.value=''; renderRooms();
}));

function renderRooms(){
  roomListEl.innerHTML = '';
  const names = Object.keys(DATA.classrooms);
  if(names.length===0){ roomListEl.innerHTML = '<div class="small">No smart classrooms</div>'; refreshStats(); return; }
  names.forEach(n=>{
    const r = DATA.classrooms[n];
    const card = document.createElement('div'); card.className = 'room-card';
    card.innerHTML = `<div style="display:flex;justify-content:space-between;align-items:center">
                        <div><strong>${escapeHtml(n)}</strong><div class="small">${r.assigned? 'Assigned to '+r.assigned : 'Unassigned'}</div></div>
                        <div style="display:flex;gap:6px"><button class="btn btn-ghost" data-action="assign">Assign</button><button class="btn btn-ghost" data-action="del">Delete</button></div>
                      </div>
                      <div class="device-row"><div class="small">Projector</div><input type="checkbox" data-device="projector" ${r.devices.projector? 'checked':''}></div>
                      <div class="device-row"><div class="small">Aircon</div><input type="checkbox" data-device="ac" ${r.devices.ac? 'checked':''}></div>
                      <div class="device-row"><div class="small">Smartboard</div><input type="checkbox" data-device="smartboard" ${r.devices.smartboard? 'checked':''}></div>`;
    card.querySelector('[data-action="assign"]').addEventListener('click', requireAuth(()=> {
      // quick assign UI: list available dept-section combos
      const chooser = document.createElement('div');
      const sel = document.createElement('select'); sel.className='field';
      const optEmpty = document.createElement('option'); optEmpty.value=''; optEmpty.textContent='Unassign'; sel.appendChild(optEmpty);
      for(const dn of Object.keys(DATA.departments || {})){
        const tt = DATA.departments[dn].timetables || {};
        for(const sec of Object.keys(tt)){
          const o = document.createElement('option'); o.value = `${dn} • ${sec}`; o.textContent = `${dn} • ${sec}`; sel.appendChild(o);
        }
      }
      chooser.appendChild(sel);
      showCustomModal(`Assign ${n}`, chooser, ()=> {
        const val = sel.value;
        DATA.classrooms[n].assigned = val || null; saveData(DATA); renderRooms(); populateRoomSelect();
      });
    }));
    card.querySelector('[data-action="del"]').addEventListener('click', requireAuth(()=> {
      if(!confirm(`Delete room ${n}?`)) return;
      delete DATA.classrooms[n]; saveData(DATA); renderRooms(); populateRoomSelect();
    }));
    // device toggles
    card.querySelectorAll('input[type="checkbox"]').forEach(cb=>{
      cb.addEventListener('change', requireAuth((ev)=> {
        const dev = ev.target.dataset.device;
        DATA.classrooms[n].devices[dev] = ev.target.checked; saveData(DATA);
      }));
    });
    roomListEl.appendChild(card);
  });
  refreshStats();
}
renderRooms();

/* populate room select for timetable assignment (if desired) */
function populateRoomSelect(){
  ttRoomSelect.innerHTML = '<option value="">— (no room assigned) —</option>';
  for(const r of Object.keys(DATA.classrooms || {})){
    const o = document.createElement('option'); o.value = r; o.textContent = r; ttRoomSelect.appendChild(o);
  }
}

/* ======= Quick generate action (sidebar) ======= */
document.getElementById('btnQuickGen').addEventListener('click', requireAuth(()=> {
  // generate timetables for all departments that have faculty & subjects
  let count=0;
  for(const dn of Object.keys(DATA.departments || {})){
    const dept = DATA.departments[dn];
    if((dept.subjects||[]).length && (dept.faculty||[]).length){
      dept.timetables = generateClashFreeTimetablesForDept(dept);
      count += Object.keys(dept.timetables).length;
    }
  }
  DATA.stats = DATA.stats || {}; DATA.stats.ttGenerated = (DATA.stats.ttGenerated || 0) + count;
  saveData(DATA); refreshAllUI(); alert(`Generated timetables for ${count} sections across departments.`);
}));

/* ======= Export all CSV ======= */
document.getElementById('exportAll').addEventListener('click', requireAuth(()=> {
  // prepare zip-like combined CSV content - for demo we export multiple CSVs sequentially as downloads (user will get multiple files)
  for(const dn of Object.keys(DATA.departments || {})){
    const dept = DATA.departments[dn];
    for(const sec of Object.keys(dept.timetables || {})){
      exportTimetableCSV(dn, sec);
    }
  }
}));

/* ======= Settings: change demo password / reset data ======= */
document.getElementById('chgPassBtn').addEventListener('click', requireAuth(()=> {
  const np = document.getElementById('chgPass').value;
  const session = getSession();
  if(!session) return alert('Not signed in');
  if(!np || np.length < 4) return alert('Use at least 4 characters');
  USERS[session.email].password = np; saveUsers(USERS); alert('Password changed for current account');
}));

document.getElementById('clearAll').addEventListener('click', requireAuth(()=> {
  if(!confirm('Clear all demo data (localStorage)?')) return;
  localStorage.removeItem(STORAGE_KEY);
  localStorage.removeItem(USER_KEY);
  location.reload();
}));

/* ======= Helpers & boot ======= */

function refreshAllUI(){
  DATA = loadData();
  USERS = loadUsers();
  refreshStats();
  renderDeptList();
  renderRooms();
  populateTimetableSelectors();
  populateRoomSelect();
  document.getElementById('acctEmail').textContent = getSession()? getSession().email : '—';
  document.getElementById('userEmailDisplay').textContent = getSession()? getSession().email : '';
}

/* escape HTML utility */
function escapeHtml(s){
  if(s==null) return '';
  return String(s).replace(/[&<>"'`]/g, c=>({ '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;','`':'&#96;' }[c]));
}

/* Custom modal for assign actions */
const customModalBackdrop = document.createElement('div'); customModalBackdrop.className='modal-backdrop'; customModalBackdrop.style.display='none';
const customModal = document.createElement('div'); customModal.className='modal'; customModal.style.minWidth='420px';
customModalBackdrop.appendChild(customModal); document.body.appendChild(customModalBackdrop);

function showCustomModal(title, contentNode, onOk){
  customModal.innerHTML = `<h3>${escapeHtml(title)}</h3>`;
  if(typeof contentNode === 'string') customModal.innerHTML += contentNode; else customModal.appendChild(contentNode);
  const actions = document.createElement('div'); actions.style.display='flex'; actions.style.justifyContent='flex-end'; actions.style.gap='8px'; actions.style.marginTop='12px';
  const cancelBtn = document.createElement('button'); cancelBtn.className='btn btn-ghost'; cancelBtn.textContent='Cancel';
  const okBtn = document.createElement('button'); okBtn.className='btn btn-primary'; okBtn.textContent='OK';
  actions.appendChild(cancelBtn); actions.appendChild(okBtn);
  customModal.appendChild(actions);
  customModalBackdrop.style.display='flex';
  cancelBtn.onclick = ()=> { customModalBackdrop.style.display='none'; };
  okBtn.onclick = ()=> { customModalBackdrop.style.display='none'; if(onOk) onOk(); };
}

/* small generic modal (reusing simple show/hide) */
function showModal(el){ el.style.display = 'flex'; }
function hideModal(el){ el.style.display = 'none'; }

/* small helper to show modals built in DOM */
function showModalById(id){ document.getElementById(id).style.display = 'flex'; }
function hideModalById(id){ document.getElementById(id).style.display = 'none'; }

/* ======= Initialize UI on page load if session exists ======= */

(function init(){
  const session = getSession();
  if(session){
    // signed in — show app
    authRoot.style.display = 'none';
    document.getElementById('appRoot').style.display = 'block';
    document.getElementById('userEmailDisplay').textContent = session.email;
    document.getElementById('acctEmail').textContent = session.email;
    refreshAllUI();
  } else {
    // show sign-in form
    authRoot.style.display = 'flex';
    document.getElementById('appRoot').style.display = 'none';
    authMsg.textContent = '';
    // prefill authEmail with admin for convenience
    authEmail.value = 'admin@demo.com';
  }
})();

/* ======= Small UI wiring for built-in modals ======= */
document.getElementById('otpVerify').addEventListener('click', ()=> {
  const v = otpInput.value.trim();
  if(!v) { document.getElementById('otpNote').textContent = 'Enter OTP'; return; }
  if(v !== otpValue){ document.getElementById('otpNote').textContent = 'Invalid OTP'; return; }
  // Open reset modal
  hideModal(otpModal);
  showModal(resetModal);
});
document.getElementById('otpCancel').addEventListener('click', ()=> hideModal(otpModal));
document.getElementById('resetCancel').addEventListener('click', ()=> hideModal(resetModal));

/* open modals: we used showModal/hideModal above; connect those DOM elements */
document.getElementById('showForgot').addEventListener('click', ()=> {
  const e = authEmail.value.trim().toLowerCase();
  if(!e){ authMsg.textContent = 'Enter email before requesting password reset.'; return; }
  if(!USERS[e]){ authMsg.textContent = 'No account with that email.'; return; }
  // generate OTP
  otpValue = (Math.floor(100000 + Math.random()*900000)).toString();
  otpForEmail = e;
  // DEMO: display OTP in modal note. Replace this with server-side email in production.
  document.getElementById('otpNote').textContent = `Demo OTP: ${otpValue} (In production, OTP will be emailed)`;
  document.getElementById('otpInput').value = '';
  showModal(otpModal);
});

/* register modal wiring */
document.getElementById('regSubmit').addEventListener('click', ()=> {
  const e = document.getElementById('regEmail').value.trim().toLowerCase();
  const p = document.getElementById('regPass').value;
  if(!e || !p){ document.getElementById('regNote').textContent = 'Enter email & password'; return; }
  if(USERS[e]){ document.getElementById('regNote').textContent = 'Account exists'; return; }
  USERS[e] = { email:e, password:p, created: nowStr() }; saveUsers(USERS);
  document.getElementById('regNote').textContent = 'Account created — sign in now';
  setTimeout(()=> { hideModal(registerModal); authEmail.value = e; }, 800);
});
document.getElementById('regCancel').addEventListener('click', ()=> hideModal(registerModal));

/* show/hide helper wrappers for built-in modals */
function showModal(el){ el.style.display = 'flex'; }
function hideModal(el){ el.style.display = 'none'; }

/* ======= Utility for quick CSV export used earlier ======= */
/* exportTimetableCSV already defined above */

/* ======= Helper: escapeHtml (used earlier) ======= */
/* defined above */

/* ======= Final UI refresh function call ======= */
refreshAllUI();

</script>

</body>
</html>
