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
function destroySession(){ sessionSto
