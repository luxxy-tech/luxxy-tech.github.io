#  kelas7bssa.xo.je
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Website Kelas</title>
<style>
  :root{
    --primary:#4f46e5; --primary-dark:#4338ca; --accent:#ec4899;
    --bg:#f4f6fb; --card:#ffffff; --text:#1f2937; --muted:#6b7280;
    --border:#e5e7eb; --radius:16px; --shadow:0 4px 20px rgba(17,24,39,.08);
  }
  *{box-sizing:border-box}
  html,body{margin:0;padding:0}
  body{
    font-family:system-ui,-apple-system,"Segoe UI",Roboto,Arial,sans-serif;
    background:var(--bg); color:var(--text); line-height:1.55;
    -webkit-font-smoothing:antialiased;
  }
  img{max-width:100%;display:block}
  button{font-family:inherit}

  /* ---------- HERO ---------- */
  .hero{
    background:linear-gradient(135deg,#4f46e5 0%,#7c3aed 50%,#ec4899 100%);
    color:#fff; padding:28px 20px 62px; position:relative; overflow:hidden;
  }
  .hero::after{
    content:""; position:absolute; right:-60px; bottom:-90px; width:280px; height:280px;
    background:rgba(255,255,255,.12); border-radius:50%;
  }
  .hero-inner{
    max-width:1000px; margin:0 auto; display:flex; align-items:center; gap:18px;
    position:relative; z-index:2; flex-wrap:wrap;
  }
  .logo{
    width:76px; height:76px; border-radius:20px; object-fit:cover; overflow:hidden;
    background:rgba(255,255,255,.25); border:2px solid rgba(255,255,255,.6);
    display:flex; align-items:center; justify-content:center; font-size:32px;
    flex:0 0 auto;
  }
  .logo img{width:100%; height:100%; object-fit:cover}
  .hero h1{margin:0; font-size:clamp(20px,4vw,30px); letter-spacing:-.5px}
  .hero p{margin:4px 0 0; opacity:.92; font-size:14px}
  .hero-actions{margin-left:auto; display:flex; gap:8px; flex-wrap:wrap; align-items:center}

  .btn{
    border:0; border-radius:10px; padding:10px 16px; font-size:14px; font-weight:600;
    cursor:pointer; display:inline-flex; align-items:center; gap:6px;
    transition:.18s transform,.18s box-shadow,.18s background;
  }
  .btn:active{transform:scale(.97)}
  .btn-glass{background:rgba(255,255,255,.2); color:#fff; border:1px solid rgba(255,255,255,.45)}
  .btn-glass:hover{background:rgba(255,255,255,.32)}
  .btn-primary{background:var(--primary); color:#fff}
  .btn-primary:hover{background:var(--primary-dark)}
  .btn-ghost{background:#f3f4f6; color:var(--text)}
  .btn-ghost:hover{background:#e5e7eb}
  .btn-danger{background:#fee2e2; color:#b91c1c}
  .btn-danger:hover{background:#fecaca}
  .btn-sm{padding:7px 11px; font-size:13px; border-radius:9px}

  /* ---------- TABS ---------- */
  .tabs-wrap{max-width:1000px; margin:-36px auto 0; padding:0 20px; position:relative; z-index:3}
  .tabs{
    background:var(--card); border-radius:var(--radius); box-shadow:var(--shadow);
    padding:8px; display:flex; gap:4px; overflow-x:auto;
  }
  .tab{
    border:0; background:transparent; padding:10px 16px; border-radius:10px;
    font-size:14px; font-weight:600; color:var(--muted); cursor:pointer;
    white-space:nowrap; transition:.15s;
  }
  .tab:hover{background:#f3f4f6; color:var(--text)}
  .tab.active{background:var(--primary); color:#fff}

  /* ---------- LAYOUT ---------- */
  main{max-width:1000px; margin:0 auto; padding:24px 20px 60px}
  .view{display:none; animation:fade .25s ease}
  .view.active{display:block}
  @keyframes fade{from{opacity:0; transform:translateY(6px)} to{opacity:1; transform:none}}

  .panel{
    background:var(--card); border-radius:var(--radius); box-shadow:var(--shadow);
    padding:22px; margin-bottom:20px;
  }
  .panel-head{display:flex; align-items:center; gap:12px; margin-bottom:16px; flex-wrap:wrap}
  .panel-head h2{margin:0; font-size:18px}
  .spacer{margin-left:auto}
  .muted{color:var(--muted); font-size:13px}

  .info-grid{display:grid; grid-template-columns:repeat(auto-fit,minmax(170px,1fr)); gap:14px}
  .info-item{background:#f9fafb; border:1px solid var(--border); border-radius:12px; padding:12px 14px}
  .info-item span{display:block; font-size:11px; color:var(--muted); text-transform:uppercase; letter-spacing:.6px}
  .info-item strong{font-size:15px; font-weight:600}

  /* ---------- CARDS ---------- */
  .grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(155px,1fr)); gap:14px}
  .person{
    background:#f9fafb; border:1px solid var(--border); border-radius:14px; padding:14px;
    text-align:center; position:relative; transition:.18s;
  }
  .person:hover{transform:translateY(-3px); box-shadow:0 8px 20px rgba(17,24,39,.08)}
  .avatar{
    width:64px; height:64px; border-radius:50%; margin:0 auto 10px; overflow:hidden;
    background:linear-gradient(135deg,#c7d2fe,#fbcfe8); display:flex; align-items:center;
    justify-content:center; font-size:22px; font-weight:700; color:#4338ca;
  }
  .avatar img{width:100%; height:100%; object-fit:cover}
  .person .nama{font-weight:600; font-size:14px; word-break:break-word}
  .person .sub{font-size:12px; color:var(--muted)}
  .badge{
    display:inline-block; background:#eef2ff; color:#4338ca; border-radius:999px;
    padding:2px 9px; font-size:11px; font-weight:700; margin-bottom:8px;
  }
  .icon-btn{
    position:absolute; top:6px; border:0; width:26px; height:26px; border-radius:8px;
    cursor:pointer; font-size:12px; line-height:1; display:flex; align-items:center;
    justify-content:center; transition:.15s;
  }
  .icon-btn.edit{left:6px; background:#e0e7ff; color:#4338ca}
  .icon-btn.edit:hover{background:#c7d2fe}
  .icon-btn.del{right:6px; background:#fee2e2; color:#b91c1c}
  .icon-btn.del:hover{background:#fecaca}

  /* ---------- GALLERY ---------- */
  .dropzone{
    border:2px dashed #c7d2fe; border-radius:14px; padding:26px; text-align:center;
    color:var(--muted); background:#f8faff; transition:.18s; cursor:pointer; font-size:14px;
  }
  .dropzone.hover{background:#eef2ff; border-color:var(--primary)}
  .gallery{display:grid; grid-template-columns:repeat(auto-fill,minmax(165px,1fr)); gap:12px; margin-top:16px}
  .media{
    position:relative; border-radius:14px; overflow:hidden; background:#111827;
    aspect-ratio:4/3; box-shadow:var(--shadow); cursor:pointer;
  }
  .media img,.media video{width:100%; height:100%; object-fit:cover; display:block}
  .media .cap{
    position:absolute; left:0; right:0; bottom:0; padding:18px 10px 8px; color:#fff;
    font-size:12px; background:linear-gradient(transparent,rgba(0,0,0,.78)); pointer-events:none;
    white-space:nowrap; overflow:hidden; text-overflow:ellipsis;
  }
  .media .del{
    position:absolute; top:8px; right:8px; background:rgba(0,0,0,.6); color:#fff; border:0;
    width:28px; height:28px; border-radius:50%; cursor:pointer; font-size:13px;
    display:flex; align-items:center; justify-content:center;
  }
  .media .del:hover{background:#dc2626}

  /* ---------- MODAL ---------- */
  .overlay{
    position:fixed; inset:0; background:rgba(17,24,39,.55);
    display:none; align-items:center; justify-content:center; padding:18px; z-index:100;
  }
  .overlay.show{display:flex}
  .modal{
    background:#fff; border-radius:18px; padding:22px; width:100%; max-width:440px;
    max-height:90vh; overflow:auto; box-shadow:0 20px 50px rgba(0,0,0,.3);
    animation:pop .2s ease;
  }
  @keyframes pop{from{transform:scale(.94); opacity:0} to{transform:none; opacity:1}}
  .modal h3{margin:0 0 16px; font-size:18px}
  .field{margin-bottom:14px}
  .field label{display:block; font-size:13px; font-weight:600; margin-bottom:6px}
  .field input[type=text],.field input[type=password],.field input[type=number]{
    width:100%; padding:10px 12px; border:1px solid var(--border); border-radius:10px;
    font-size:14px; font-family:inherit; outline:none; transition:.15s; background:#fff;
  }
  .field input:focus{border-color:var(--primary); box-shadow:0 0 0 3px rgba(79,70,229,.15)}
  .modal-actions{display:flex; gap:8px; justify-content:flex-end; margin-top:10px}
  .foto-row{display:flex; gap:12px; align-items:center}
  .foto-preview{
    width:72px; height:72px; border-radius:12px; overflow:hidden; background:#f3f4f6;
    display:flex; align-items:center; justify-content:center; color:var(--muted);
    font-size:11px; flex:0 0 auto; border:1px solid var(--border);
  }
  .foto-preview img{width:100%; height:100%; object-fit:cover}

  /* ---------- LIGHTBOX ---------- */
  .lightbox{
    position:fixed; inset:0; background:rgba(0,0,0,.93); display:none;
    align-items:center; justify-content:center; z-index:200; padding:20px;
  }
  .lightbox.show{display:flex}
  .lightbox img,.lightbox video{max-width:92vw; max-height:82vh; border-radius:12px}
  .lightbox .close{
    position:absolute; top:18px; right:22px; background:rgba(255,255,255,.15);
    color:#fff; border:0; width:42px; height:42px; border-radius:50%; font-size:22px; cursor:pointer;
  }
  .lightbox .caption{position:absolute; bottom:26px; color:#fff; font-size:14px; opacity:.85; text-align:center; padding:0 20px}

  /* ---------- MISC ---------- */
  .empty{text-align:center; padding:34px 10px; color:var(--muted); font-size:14px}
  body:not(.is-dev) .dev-only{display:none !important}
  .dev-badge{
    background:rgba(255,255,255,.25); border:1px solid rgba(255,255,255,.5);
    border-radius:999px; padding:4px 12px; font-size:12px; font-weight:700; color:#fff;
  }
  .toolbar{display:flex; gap:8px; flex-wrap:wrap; margin-bottom:14px}
  .toolbar input[type=search]{
    flex:1; min-width:160px; padding:10px 12px; border:1px solid var(--border);
    border-radius:10px; font-size:14px; outline:none; font-family:inherit;
  }
  .toolbar input[type=search]:focus{border-color:var(--primary)}
  #toast{
    position:fixed; bottom:24px; left:50%; transform:translateX(-50%) translateY(80px);
    background:#111827; color:#fff; padding:12px 20px; border-radius:12px; font-size:14px;
    opacity:0; transition:.3s; z-index:300; pointer-events:none; max-width:90vw; text-align:center;
  }
  #toast.show{opacity:1; transform:translateX(-50%) translateY(0)}
  footer{text-align:center; padding:8px 20px 30px; color:var(--muted); font-size:13px}
  .setting-row{
    display:flex; gap:10px; align-items:center; justify-content:space-between;
    padding:14px; border:1px solid var(--border); border-radius:12px; margin-bottom:10px;
    flex-wrap:wrap;
  }
  .setting-row .txt{font-size:14px}
  .setting-row .txt small{display:block; color:var(--muted); font-size:12px}
</style>
</head>
<body>

<!-- ================= HERO ================= -->
<header class="hero">
  <div class="hero-inner">
    <div class="logo" id="logoBox">🎓</div>
    <div>
      <h1 id="judulKelas">Website Kelas</h1>
      <p id="subKelas">Sekolah • Tahun Ajaran</p>
    </div>
    <div class="hero-actions">
      <span class="dev-badge dev-only">🔓 Mode Developer</span>
      <button class="btn btn-glass" id="btnLogin">🔒 Login Developer</button>
      <button class="btn btn-glass dev-only" id="btnLogout">Logout</button>
    </div>
  </div>
</header>

<!-- ================= TABS ================= -->
<div class="tabs-wrap">
  <nav class="tabs" id="tabs">
    <button class="tab active" data-view="beranda">🏠 Beranda</button>
    <button class="tab" data-view="guru">👨‍🏫 Guru</button>
    <button class="tab" data-view="murid">🧑‍🎓 Murid</button>
    <button class="tab" data-view="galeri">📸 Galeri</button>
    <button class="tab" data-view="pengaturan">⚙️ Pengaturan</button>
  </nav>
</div>

<!-- ================= MAIN ================= -->
<main>

  <!-- BERANDA -->
  <section class="view active" id="view-beranda">
    <div class="panel">
      <div class="panel-head">
        <h2>Profil Kelas</h2>
        <div class="spacer"></div>
        <button class="btn btn-primary btn-sm dev-only" id="btnEditProfil">✏️ Edit Profil</button>
      </div>
      <div class="info-grid" id="infoProfil"></div>
      <div id="mottoBox" style="margin-top:14px"></div>
    </div>
    <div class="panel">
      <div class="panel-head"><h2>Statistik</h2></div>
      <div class="info-grid" id="statistik"></div>
    </div>
  </section>

  <!-- GURU -->
  <section class="view" id="view-guru">
    <div class="panel">
      <div class="panel-head">
        <h2>Daftar Guru</h2>
        <div class="spacer"></div>
        <button class="btn btn-primary btn-sm dev-only" id="btnTambahGuru">➕ Tambah Guru</button>
      </div>
      <div class="grid" id="gridGuru"></div>
    </div>
  </section>

  <!-- MURID -->
  <section class="view" id="view-murid">
    <div class="panel">
      <div class="panel-head">
        <h2>Daftar Murid</h2>
        <div class="spacer"></div>
        <button class="btn btn-primary btn-sm dev-only" id="btnTambahMurid">➕ Tambah Murid</button>
      </div>
      <div class="toolbar">
        <input type="search" id="cariMurid" placeholder="🔍 Cari nama murid..." />
      </div>
      <div class="grid" id="gridMurid"></div>
    </div>
  </section>

  <!-- GALERI -->
  <section class="view" id="view-galeri">
    <div class="panel">
      <div class="panel-head">
        <h2>Galeri Foto &amp; Video</h2>
        <div class="spacer"></div>
        <span class="muted" id="galeriInfo"></span>
      </div>
      <div class="dropzone dev-only" id="dropzone">
        📤 <strong>Klik untuk pilih</strong> atau tarik file ke sini<br />
        <span class="muted">Mendukung foto (JPG/PNG/WebP) &amp; video (MP4/WebM)</span>
      </div>
      <input type="file" id="inputMedia" accept="image/*,video/*" multiple hidden />
      <div class="gallery" id="galleryGrid"></div>
    </div>
  </section>

  <!-- PENGATURAN -->
  <section class="view" id="view-pengaturan">
    <div class="panel">
      <div class="panel-head"><h2>Pengaturan Developer</h2></div>

      <div class="setting-row">
        <div class="txt"><strong>Ganti Password Developer</strong><small>Password untuk membuka mode edit</small></div>
        <button class="btn btn-primary btn-sm" id="btnGantiPass">🔑 Ganti Password</button>
      </div>

      <div class="setting-row">
        <div class="txt"><strong>Backup Data (.json)</strong><small>Simpan profil, guru, dan murid ke file</small></div>
        <button class="btn btn-ghost btn-sm" id="btnExport">💾 Unduh Backup</button>
      </div>

      <div class="setting-row">
        <div class="txt"><strong>Restore Data (.json)</strong><small>Pulihkan data dari file backup</small></div>
        <button class="btn btn-ghost btn-sm" id="btnImport">📂 Pilih File</button>
        <input type="file" id="inputImport" accept=".json,application/json" hidden />
      </div>

      <div class="setting-row">
        <div class="txt"><strong>Unduh File index.html</strong><small>Simpan halaman ini sebagai file</small></div>
        <button class="btn btn-ghost btn-sm" id="btnUnduhHtml">⬇️ Unduh index.html</button>
      </div>

      <div class="setting-row">
        <div class="txt"><strong style="color:#b91c1c">Reset Semua Data</strong><small>Hapus profil, guru, murid, dan galeri</small></div>
        <button class="btn btn-danger btn-sm" id="btnReset">🗑️ Reset</button>
      </div>

      <p class="muted" style="margin-top:16px">
        ℹ️ Data disimpan di browser ini (localStorage &amp; IndexedDB). Jika website di-host online,
        setiap pengunjung punya datanya masing-masing. Untuk website kelas bersama, gunakan backup/restore
        atau hosting dengan database.
      </p>
    </div>
  </section>

</main>

<footer>© <span id="tahunFooter"></span> Website Kelas · Dibuat dengan ❤️</footer>

<!-- ================= MODAL ================= -->
<div class="overlay" id="modalOverlay">
  <div class="modal">
    <h3 id="modalTitle">Judul</h3>
    <div id="modalBody"></div>
    <div class="modal-actions">
      <button class="btn btn-ghost" id="modalCancel">Batal</button>
      <button class="btn btn-primary" id="modalSave">Simpan</button>
    </div>
  </div>
</div>

<!-- ================= LIGHTBOX ================= -->
<div class="lightbox" id="lightbox">
  <button class="close" id="lightboxClose">✕</button>
  <div id="lightboxContent"></div>
  <div class="caption" id="lightboxCaption"></div>
</div>

<div id="toast"></div>

<script>
/* =========================================================
   UTILITAS
   ========================================================= */
const $  = (s, r = document) => r.querySelector(s);
const $$ = (s, r = document) => Array.from(r.querySelectorAll(s));
const uid = () => Date.now().toString(36) + Math.random().toString(36).slice(2, 7);
const esc = s => String(s ?? '').replace(/[&<>"']/g, c =>
  ({ '&':'&amp;', '<':'&lt;', '>':'&gt;', '"':'&quot;', "'":'&#39;' }[c]));

function toast(msg) {
  const t = $('#toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(t._t);
  t._t = setTimeout(() => t.classList.remove('show'), 2200);
}

/* =========================================================
   DATA (localStorage)
   ========================================================= */
const LS_KEY = 'kelasData_v1';
const DEFAULT_PASSWORD = 'admin123';
let isDev = false;

function defaultData() {
  return {
    profil: {
      namaKelas: 'Kelas XI IPA 1',
      sekolah: 'SMA Negeri 1',
      tahun: '2025/2026',
      waliKelas: 'Nama Wali Kelas',
      motto: 'Belajar, Berkarya, Berprestasi',
      logo: ''
    },
    guru: [],
    murid: [],
    password: DEFAULT_PASSWORD
  };
}

let data = (() => {
  try {
    const raw = localStorage.getItem(LS_KEY);
    if (raw) return Object.assign(defaultData(), JSON.parse(raw));
  } catch (e) { console.warn('Gagal memuat data', e); }
  return defaultData();
})();

function save() {
  try {
    localStorage.setItem(LS_KEY, JSON.stringify(data));
  } catch (e) {
    toast('⚠️ Penyimpanan penuh. Hapus beberapa data.');
  }
}

/* =========================================================
   INDEXEDDB (media)
   ========================================================= */
const DB_NAME = 'kelasMediaDB';
const STORE = 'media';

function idbOpen() {
  return new Promise((res, rej) => {
    const r = indexedDB.open(DB_NAME, 1);
    r.onupgradeneeded = () => {
      const db = r.result;
      if (!db.objectStoreNames.contains(STORE)) db.createObjectStore(STORE, { keyPath: 'id' });
    };
    r.onsuccess = () => res(r.result);
    r.onerror = () => rej(r.error);
  });
}
async function mediaAll() {
  const db = await idbOpen();
  return new Promise((res, rej) => {
    const tx = db.transaction(STORE, 'readonly');
    const req = tx.objectStore(STORE).getAll();
    req.onsuccess = () => res(req.result || []);
    req.onerror = () => rej(req.error);
  });
}
async function mediaPut(item) {
  const db = await idbOpen();
  return new Promise((res, rej) => {
    const tx = db.transaction(STORE, 'readwrite');
    tx.objectStore(STORE).put(item);
    tx.oncomplete = () => res();
    tx.onerror = () => rej(tx.error);
  });
}
async function mediaDel(id) {
  const db = await idbOpen();
  return new Promise((res, rej) => {
    const tx = db.transaction(STORE, 'readwrite');
    tx.objectStore(STORE).delete(id);
    tx.oncomplete = () => res();
    tx.onerror = () => rej(tx.error);
  });
}

let mediaCache = [];
let objectUrls = [];

/* =========================================================
   HELPER FOTO (resize → dataURL)
   ========================================================= */
function resizeImage(file, max = 320) {
  return new Promise(resolve => {
    const reader = new FileReader();
    reader.onload = e => {
      const img = new Image();
      img.onload = () => {
        const canvas = document.createElement('canvas');
        const scale = Math.min(1, max / Math.max(img.width, img.height));
        canvas.width  = Math.round(img.width  * scale);
        canvas.height = Math.round(img.height * scale);
        canvas.getContext('2d').drawImage(img, 0, 0, canvas.width, canvas.height);
        resolve(canvas.toDataURL('image/jpeg', 0.82));
      };
      img.onerror = () => resolve('');
      img.src = e.target.result;
    };
    reader.onerror = () => resolve('');
    reader.readAsDataURL(file);
  });
}
