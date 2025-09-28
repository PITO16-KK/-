<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Blog - Profile & Post Folders</title>
  <style>
    :root{
      --pink:#ff8fb1;
      --ungu:#8b5cf6;
      --abu:#8d7792;
      --hitam:#0b0b0b;
      --biru:#4da6ff;
      --glass: rgba(255,255,255,0.6);
      --card-shadow: 0 8px 24px rgba(11,11,11,0.12);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#8268ac,#000000);color:var(--hitam)}

    .container{max-width:980px;margin:28px auto;padding:20px}

    header{
      display:flex;align-items:center;gap:18px;padding:18px;border-radius:18px;background:linear-gradient(90deg,rgba(238, 230, 255, 0.829),rgba(144, 89, 154, 0.708));box-shadow:var(--card-shadow)
    }

    .avatar{
      width:100px;height:100px;border-radius:18px;overflow:hidden;flex:0 0 100px;background:linear-gradient(135deg,var(--pink),var(--ungu));display:grid;place-items:center;border:4px solid rgba(255,255,255,0.6);
    }
    .avatar img{width:100%;height:100%;object-fit:cover;display:block}
    .profile-info h1{margin:0;font-size:1.25rem;color:#371b5e}
    .profile-info p{margin:6px 0 0;color:#371b5e}
    .badges{margin-top:8px;display:flex;gap:8px;color:#371b5e}
    .badge{background:#e6e6e9;padding:6px 10px;border-radius:999px;font-size:12px}

    main{display:grid;grid-template-columns:1fr;gap:20px;margin-top:18px}

    .folders{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:18px}
    .folder{
      background:linear-gradient(180deg,rgba(255, 255, 255, 0.8),rgba(208, 195, 220, 0.7));padding:16px;border-radius:14px;box-shadow:var(--card-shadow);position:relative;overflow:hidden;min-height:180px;display:flex;flex-direction:column;gap:10px
    }
    .cover{
      height:96px;border-radius:10px;position:relative; overflow:hidden;}
    .folder-img {width: 100%;height: 96px;object-fit: cover;border-radius: 8px;position:absolute; inset:0; object-fit:cover;}    
    .cover .sticker{position:absolute;right:8px;top:8px;font-size:20px;filter:drop-shadow(0 4px 8px rgba(0,0,0,0.15))}
    .folder h3{margin:0; color:#8a36ff}
    .folder p{flex:1;margin:0;color:#444}
    .open-btn{align-self:flex-end;padding:8px 12px;border-radius:10px;border:0;background:linear-gradient(90deg,var(--ungu),var(--biru));color:white;cursor:pointer}

    .cute{font-size:22px}

    .modal-backdrop{position:fixed;inset:0;background:rgba(11,11,11,0.45);display:none;align-items:center;justify-content:center;padding:20px}
    .modal{background:white;border-radius:12px;max-width:760px;width:100%;padding:18px;box-shadow:0 20px 40px rgba(11,11,11,0.25);max-height:84vh;overflow:auto}
    .modal header{display:flex;align-items:center;justify-content:space-between}
    .close{background:var(--abu);border-radius:10px;padding:6px 10px;border:0;cursor:pointer}

    @media (max-width:520px){
      header{flex-direction:column;align-items:flex-start}
      .avatar{width:88px;height:88px}
    }

    .sticker-emoji{position:absolute;font-size:34px;opacity:0.95}
    .s1{left:-18px;top:12px;transform:rotate(-18deg)}
    .s2{right:-18px;bottom:14px;transform:rotate(10deg)}

    footer{margin-top:20px;text-align:center;color:#666;font-size:13px}

    .muted{color:#666;font-size:13px}
    a.link{color:var(--ungu);text-decoration:none}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="avatar" id="avatar">
        <div class="avatar" id="avatar">
        <img src="foto1.jpg" alt="Foto Profil" class="profile-img">
      </div>
    </div>
      <div class="profile-info">
          <h1>KAISHA KAMILA PUSPITO</h1>
          <p>Teknik Informatika UBP Karawang</p>
          <div class="badges">
            <span class="badge">NIM : 24416255201028</span>
            <span class="badge">if24.kaishapuspito@mhs.ubpkarawang.ac.id</span>
            <span class="badge">Basis Data</span>
          </div>
      </div>
    </header>

    <main>
      <section>
        <div class="folders">
          <article class="folder" data-folder="1">
            <div class="cover" style="text-align:center">
              <img src="foto5.jpg" alt="Cover Harapan MK" class="folder-img">
              <div class="sticker">✨</div>
            </div>
            <h3>Harapan</h3>
            <p>Harapan saya di Mata Kuliah Basis Data</p>
            <button class="open-btn" data-open="1">Buka</button>
          </article>

          <article class="folder" data-folder="2">
            <div class="cover" style="background:linear-gradient(135deg,var(--biru),var(--ungu))">
              <img src="foto2.jpg" alt="Cover Harapan MK" class="folder-img">
              <div class="sticker">📚</div>
            </div>
            <h3>Basis Data</h3>
            <p>Apa itu Basis Data?</p>
            <button class="open-btn" data-open="2">Buka</button>
          </article>

          <article class="folder" data-folder="3">
            <div class="cover" style="background:linear-gradient(135deg,var(--pink),var(--biru))">
              <img src="foto3.jpg" alt="Cover Harapan MK" class="folder-img">
              <div class="sticker">🧩</div>
            </div>
            <h3>Conceptual DB</h3>
            <p>Apa itu Conceptual DB?</p>
            <button class="open-btn" data-open="3">Buka</button>
          </article>

          <article class="folder" data-folder="4">
            <div class="cover" style="background:linear-gradient(135deg,var(--abu),#c9b7ff)">
              <img src="foto4.jpg" alt="Cover Harapan MK" class="folder-img">
              <div class="sticker">🛠️</div>
            </div>
            <h3>Physical Model</h3>
            <p>Apa itu Physical Model?</p>
            <button class="open-btn" data-open="4">Buka</button>
          </article>

        </div>
      </section>
    </main>

    <footer>
      <section style="margin-top:18px">
        <div id="preview" style="margin-top:10px;padding:12px;border-radius:12px;background:var(--glass);box-shadow:var(--card-shadow)">
          © 2025 Blog Basis Data | Kaisha | <a href="https://www.ubpkarawang.ac.id" target="_blank">UBP Karawang</a>
        </div>
      </section>
    </footer>
  </div>

  <div id="modalBackdrop" class="modal-backdrop" role="dialog" aria-hidden>
    <div class="modal" role="document">
      <header>
        <strong id="modalTitle">Judul Folder</strong>
        <div>
          <button class="close" id="modalClose">Tutup</button>
        </div>
      </header>
      <div id="modalContent" style="margin-top:12px;line-height:1.6;color:#222">
      </div>
    </div>
  </div>

  <script>
    const dbAnswers = {
      1: {
        title: 'Harapan saya di Mata Kuliah Basis Data',
        body: `Sebagai mahasiswa semester 3, saya berharap dari mata kuliah Basis Data dapat memahami bagaimana cara merancang, mengelola, dan mengoptimalkan database yang baik. Selain itu, saya ingin menguasai praktik penggunaan DBMS seperti MySQL agar bisa menerapkannya dalam pembuatan aplikasi, serta memahami konsep normalisasi, relasi antar tabel, dan keamanan data.`
      },
      2: {
        title: 'Apa itu Basis Data',
        body: `Basis data adalah kumpulan data yang terorganisir dan saling berhubungan, yang disimpan secara sistematis di komputer sehingga mudah diakses, dikelola, dan diperbarui. Basis data membantu menyimpan informasi dalam jumlah besar secara efisien dan mengurangi redundansi data.`
      },
      3: {
        title: 'Apa itu Conceptual Database?',
        body: `Conceptual database adalah gambaran umum dari struktur data secara logis yang menunjukkan bagaimana data saling berhubungan tanpa memperhatikan aspek teknis penyimpanan. Biasanya divisualisasikan dengan ERD (Entity Relationship Diagram) yang menampilkan entitas, atribut, dan relasinya.`
      },
      4: {
        title: 'Apa itu Physical Model?',
        body: `Physical model adalah representasi basis data yang lebih teknis dan detail, yang menunjukkan bagaimana data akan disimpan di dalam DBMS tertentu. Model ini sudah mencakup tipe data, struktur tabel, primary key, foreign key, serta indeks yang digunakan agar database berjalan secara optimal.`
      }
    };

    const openButtons = document.querySelectorAll('[data-open]');
    const modal = document.getElementById('modalBackdrop');
    const modalTitle = document.getElementById('modalTitle');
    const modalContent = document.getElementById('modalContent');
    const preview = document.getElementById('preview');
    const modalClose = document.getElementById('modalClose');

    function openFolder(id){
      const d = dbAnswers[id];
      if(!d) return;
      modalTitle.textContent = d.title;
      modalContent.innerHTML = '<p>' + d.body.replace(/\\n/g,'<br><br>') + '</p>' +
        '<div style="margin-top:12px;color:#555;font-size:13px">Kaisha - Basis Data</div>';
      modal.style.display = 'flex';
      modal.setAttribute('aria-hidden','false');

      preview.innerHTML = '<h3>' + d.title + '</h3><p style="white-space:pre-wrap">' + d.body + '</p>';
    }

    openButtons.forEach(btn => btn.addEventListener('click', ()=>{
      const id = btn.getAttribute('data-open');
      openFolder(id);
    }));

    modalClose.addEventListener('click', ()=>{
      modal.style.display = 'none';
      modal.setAttribute('aria-hidden','true');
    });

    modal.addEventListener('click', (e)=>{
      if(e.target === modal) { modal.style.display='none'; modal.setAttribute('aria-hidden','true'); }
    });

    window.addEventListener('keydown', (e)=>{
      if(e.key >= '1' && e.key <= '4'){
        openFolder(e.key);
      }
      if(e.key === 'Escape'){
        modal.style.display='none'; modal.setAttribute('aria-hidden','true');
      }
    });
  </script>
</body>
</html>
