<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Profil Saya — CV Web</title>
  <meta name="description" content="Halaman data diri / CV sederhana yang bisa diedit dan diunduh." />
  <style>
    :root{
      --bg:#f7f9fb; --card:#ffffff; --muted:#6b7280; --accent:#0b84ff;
    }
    *{box-sizing:border-box}
    body{font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; margin:0; background:var(--bg); color:#0f172a}
    .container{max-width:900px;margin:28px auto;padding:20px}
    .card{background:var(--card);border-radius:12px;box-shadow:0 6px 18px rgba(12,15,20,0.06);padding:22px}
    header{display:flex;gap:18px;align-items:center}
    .avatar{width:96px;height:96px;border-radius:12px;background:linear-gradient(135deg,#e6f0ff,#f0f7ff);display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--accent);font-size:28px}
    h1{margin:0;font-size:20px}
    .role{color:var(--muted);margin-top:6px}
    .links a{display:inline-block;margin-right:8px;text-decoration:underline;color:var(--accent)}
    .grid{display:grid;grid-template-columns:1fr 320px;gap:18px;margin-top:18px}
    .section{margin-bottom:14px}
    h2{font-size:14px;margin:0 0 8px 0}
    p{margin:0;color:#111827}
    .muted{color:var(--muted);font-size:14px}
    .skill{display:inline-block;background:#eef6ff;border-radius:999px;padding:6px 10px;margin:6px 6px 0 0;font-size:13px}
    .contact-list{list-style:none;padding:0;margin:0}
    .contact-list li{margin-bottom:8px}
    .edit-btns{display:flex;gap:8px;margin-top:12px}
    button{cursor:pointer;border:1px solid rgba(15,23,42,0.06);background:#fff;padding:8px 12px;border-radius:8px}
    .primary{background:var(--accent);color:#fff;border:none}
    textarea,input[type="text"]{width:100%;padding:10px;border-radius:8px;border:1px solid #e6eef8;font-size:14px}
    .share-note{font-size:13px;color:var(--muted);margin-top:8px}
    footer{margin-top:16px;text-align:center;color:var(--muted);font-size:13px}
    @media(max-width:820px){.grid{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <div class="container">
    <div class="card" id="cvCard">
      <header>
        <div class="avatar" id="avatar">PK</div>
        <div style="flex:1">
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div>
              <h1 id="fullName">Nama Lengkap</h1>
              <div class="role" id="role">Posisi / Job Title</div>
            </div>
            <div class="links">
              <!-- clickable blue links -->
              <a id="websiteLink" href="#" target="_blank">website</a>
              <a id="linkedinLink" href="#" target="_blank">linkedin</a>
            </div>
          </div>
          <p class="muted" id="summary">Ringkasan singkat tentang diri Anda. Contoh: "Pengembang web berpengalaman, suka membangun UI yang bersih dan responsif."</p>
        </div>
      </header>

      <div class="grid">
        <main>
          <section class="section">
            <h2>Pengalaman</h2>
            <div id="experience">
              <p class="muted">(Klik "Edit" untuk menambah atau mengubah pengalaman.)</p>
            </div>
          </section>

          <section class="section">
            <h2>Pendidikan</h2>
            <div id="education">
              <p class="muted">(Contoh: S1 Teknik Informatika — Universitas Contoh — 2018–2022)</p>
            </div>
          </section>

          <section class="section">
            <h2>Kemampuan</h2>
            <div id="skills">
              <span class="skill">HTML</span>
              <span class="skill">CSS</span>
              <span class="skill">JavaScript</span>
            </div>
          </section>
        </main>

        <aside>
          <section class="section">
            <h2>Kontak</h2>
            <ul class="contact-list">
              <li>Email: <a id="emailLink" href="mailto:you@example.com">you@example.com</a></li>
              <li>Telepon: <a id="phoneLink" href="tel:+628123456789">+62 812-3456-789</a></li>
              <li>Lokasi: <span id="location">Kota, Negara</span></li>
            </ul>
          </section>

          <section class="section">
            <h2>Unduh / Bagikan</h2>
            <div class="edit-btns">
              <button id="downloadBtn" class="primary">Unduh HTML</button>
              <button id="copyBtn">Salin HTML</button>
            </div>
            <div class="share-note">Link yang Anda bagikan akan tampil berwarna biru (clickable) — sudah otomatis diatur.</div>
          </section>

          <section class="section">
            <h2>Ubah Konten</h2>
            <div>
              <label>Nama</label>
              <input id="inputName" type="text" placeholder="Nama Lengkap" />
            </div>
            <div style="margin-top:8px">
              <label>Posisi</label>
              <input id="inputRole" type="text" placeholder="Job Title" />
            </div>
            <div style="margin-top:8px">
              <label>Ringkasan</label>
              <textarea id="inputSummary" rows="3" placeholder="Tulis ringkasan singkat..."></textarea>
            </div>
            <div class="edit-btns">
              <button id="applyBtn" class="primary">Terapkan</button>
              <button id="resetBtn">Reset</button>
            </div>
          </section>
        </aside>
      </div>

      <footer>Generated with simple CV web template • Bisa disimpan / dibagikan</footer>
    </div>
  </div>

  <script>
    // Simple interactivity & export
    const defaultData = {
      name: 'Prayoga Kurnia',
      role: 'Web Developer',
      summary: 'Pengembang web yang fokus pada front-end. Suka membuat UI yang bersih dan cepat.',
      email: 'prayoga@example.com',
      phone: '+628123456789',
      location: 'Jakarta, Indonesia',
      website: 'https://example.com',
      linkedin: 'https://linkedin.com/in/yourprofile'
    };

    // Elements
    const fullName = document.getElementById('fullName');
    const roleEl = document.getElementById('role');
    const summaryEl = document.getElementById('summary');
    const emailLink = document.getElementById('emailLink');
    const phoneLink = document.getElementById('phoneLink');
    const locationEl = document.getElementById('location');
    const websiteLink = document.getElementById('websiteLink');
    const linkedinLink = document.getElementById('linkedinLink');
    const avatar = document.getElementById('avatar');

    // Inputs
    const inputName = document.getElementById('inputName');
    const inputRole = document.getElementById('inputRole');
    const inputSummary = document.getElementById('inputSummary');
    const applyBtn = document.getElementById('applyBtn');
    const resetBtn = document.getElementById('resetBtn');
    const downloadBtn = document.getElementById('downloadBtn');
    const copyBtn = document.getElementById('copyBtn');

    function initials(name){
      return name.split(' ').map(s=>s[0]||'').slice(0,2).join('').toUpperCase();
    }

    function loadData(){
      const saved = localStorage.getItem('cvData');
      const data = saved ? JSON.parse(saved) : defaultData;
      fullName.textContent = data.name;
      roleEl.textContent = data.role;
      summaryEl.textContent = data.summary;
      emailLink.href = 'mailto:'+data.email; emailLink.textContent = data.email;
      phoneLink.href = 'tel:'+data.phone; phoneLink.textContent = data.phone;
      locationEl.textContent = data.location;
      websiteLink.href = data.website; websiteLink.textContent = 'website';
      linkedinLink.href = data.linkedin; linkedinLink.textContent = 'linkedin';
      avatar.textContent = initials(data.name);

      // fill inputs
      inputName.value = data.name; inputRole.value = data.role; inputSummary.value = data.summary;
    }

    function applyChanges(){
      const data = {
        name: inputName.value || defaultData.name,
        role: inputRole.value || defaultData.role,
        summary: inputSummary.value || defaultData.summary,
        email: defaultData.email,
        phone: defaultData.phone,
        location: defaultData.location,
        website: defaultData.website,
        linkedin: defaultData.linkedin
      };
      localStorage.setItem('cvData', JSON.stringify(data));
      loadData();
      alert('Perubahan tersimpan di penyimpanan browser (localStorage).');
    }

    function resetToDefault(){
      if(confirm('Reset ke data default?')){
        localStorage.removeItem('cvData');
        loadData();
      }
    }

    function downloadHTML(){
      // download the current page HTML as a file
      const docHtml = `<!doctype html>` + document.documentElement.outerHTML;
      const blob = new Blob([docHtml],{type:'text/html'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url; a.download = (fullName.textContent || 'profile') + '.html';
      document.body.appendChild(a); a.click(); a.remove();
      URL.revokeObjectURL(url);
    }

    function copyHTMLToClipboard(){
      const docHtml = `<!doctype html>` + document.documentElement.outerHTML;
      navigator.clipboard.writeText(docHtml).then(()=>{
        alert('HTML halaman disalin ke clipboard. Anda bisa paste ke editor / hosting.');
      }).catch(()=>{alert('Tidak bisa menyalin otomatis. Silakan coba browser lain atau gunakan tombol unduh.');});
    }

    applyBtn.addEventListener('click', applyChanges);
    resetBtn.addEventListener('click', resetToDefault);
    downloadBtn.addEventListener('click', downloadHTML);
    copyBtn.addEventListener('click', copyHTMLToClipboard);

    // initialize
    loadData();
  </script>
</body>
</html>
