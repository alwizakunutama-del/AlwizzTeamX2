
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>(AlwizzTeamX)</title>
  <style>
    :root{
      --bg1: #0b0710;
      --bg2: #1b0520;
      --card: rgba(16,8,28,0.95);
      --neon: #9b59ff;
      --muted: #b6c6e0;
      --glass: rgba(255,255,255,0.03);
      --accent: #7a4bff;
      --success: #2ecc71;
      --warn: #ffb86b;
      --danger: #ff6b6b;
      font-family: "Courier New", Courier, monospace;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(140,18,150,0.18), transparent),
                  radial-gradient(900px 400px at 90% 90%, rgba(10,10,40,0.6), transparent),
                  linear-gradient(180deg, var(--bg1), var(--bg2));
      color:var(--muted);
      display:flex;
      align-items:center;
      justify-content:center;
      padding:20px;
    }

    .frame{
      width:380px;
      max-width:95%;
      border-radius:22px;
      padding:20px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(0,0,0,0.2));
      border: 1px solid rgba(155,89,255,0.12);
      box-shadow: 0 10px 40px rgba(0,0,0,0.6), 0 0 40px rgba(139,0,255,0.06) inset;
      position:relative;
      overflow:hidden;
    }

    .inner{
      border-radius:16px;
      padding:18px;
      background: linear-gradient(180deg, rgba(0,0,0,0.28), rgba(0,0,0,0.45));
      border: 1px solid rgba(255,255,255,0.02);
    }

    .title{
      text-align:center;
      color:var(--neon);
      font-size:40px;
      letter-spacing:2px;
      margin:6px 0 10px;
      text-shadow: 0 6px 30px rgba(122,75,255,0.22);
    }
    .subtitle{
      text-align:left;
      font-size:13px;
      color:rgba(180,200,235,0.6);
      margin-bottom:10px;
      padding-left:6px;
    }

    .input-wrap{
      display:flex;
      gap:10px;
      flex-direction:column;
      margin-bottom:16px;
    }
    input[type="text"]{
      width:100%;
      padding:14px 16px;
      border-radius:14px;
      background: rgba(255,255,255,0.02);
      border: 1px solid rgba(155,89,255,0.14);
      color:var(--muted);
      font-size:16px;
      outline:none;
      letter-spacing:2px;
      text-align:center;
    }
    input::placeholder{color:rgba(180,200,235,0.25)}

    .btns{
      display:flex;
      flex-direction:column;
      gap:12px;
    }
    .btn{
      padding:16px;
      border-radius:16px;
      border: none;
      background: linear-gradient(90deg, rgba(122,75,255,1), rgba(134,73,255,0.9));
      color:white;
      font-weight:700;
      font-size:16px;
      cursor:pointer;
      box-shadow: 0 8px 30px rgba(122,75,255,0.18), 0 0 40px rgba(122,75,255,0.06) inset;
      transition: transform .12s ease, box-shadow .12s ease;
    }
    .btn:active{transform: translateY(2px)}
    .btn.secondary{
      background: linear-gradient(90deg, rgba(120,120,150,0.12), rgba(80,40,120,0.12));
      color:var(--muted);
      border:1px solid rgba(155,89,255,0.06);
      box-shadow:none;
    }

    .info{
      margin-top:14px;
      border-radius:12px;
      padding:12px;
      background: linear-gradient(180deg, rgba(20,8,40,0.65), rgba(10,4,30,0.55));
      border:1px solid rgba(155,89,255,0.06);
      color:rgba(180,220,255,0.9);
      font-size:14px;
      line-height:1.5;
    }
    .status{color:#40e0a0;font-weight:700}

    .credit{
      margin-top:18px;
      text-align:center;
      font-size:12px;
      color:rgba(180,200,235,0.45);
    }
    .developer{
      margin-top:6px;
      color:rgba(200,220,255,0.5);
      font-size:13px;
      text-align:center;
      letter-spacing:1px;
    }

    /* Tombol ke channel */
    .channel-btn {
      display:block;
      width:100%;
      margin-top:14px;
      text-align:center;
      background: linear-gradient(90deg, #25d366, #128c7e);
      color:white;
      font-weight:bold;
      border:none;
      border-radius:14px;
      padding:14px;
      font-size:16px;
      cursor:pointer;
      text-decoration:none;
      box-shadow: 0 8px 25px rgba(37, 211, 102, 0.3);
      transition: transform 0.15s ease, box-shadow 0.15s ease;
    }
    .channel-btn:hover{
      transform:scale(1.03);
      box-shadow: 0 10px 30px rgba(37,211,102,0.4);
    }

    .modal-backdrop{
      position:fixed;
      inset:0;
      background:rgba(0,0,0,0.45);
      display:none;
      align-items:center;
      justify-content:center;
      z-index:40;
      padding:18px;
    }
    .modal{
      width:100%;
      max-width:420px;
      background:white;
      color:#222;
      border-radius:12px;
      padding:26px;
      box-shadow: 0 14px 50px rgba(0,0,0,0.6);
      text-align:center;
      font-family: "Times New Roman", serif;
    }
    .modal h2{font-size:36px;margin:6px 0;color:#444}
    .modal p{color:#666;margin:6px 0 14px}
    .modal .ok-btn{
      padding:10px 20px;border-radius:8px;border:none;background:linear-gradient(90deg,#7a4bff,#5b3cff);
      color:white;font-weight:700;cursor:pointer;
    }

    .loader{
      width:66px;height:66px;border-radius:50%;
      border:6px solid rgba(150,150,150,0.12);
      border-top-color:var(--accent);
      margin:18px auto;
      animation:spin 1s linear infinite;
    }
    @keyframes spin{from{transform:rotate(0)}to{transform:rotate(360deg)}}

    .icon-success{
      width:76px;height:76px;border-radius:50%;
      border:6px solid rgba(46,204,113,0.12);
      display:inline-grid;place-items:center;margin:6px auto 8px;
    }
    .icon-success svg{width:48px;height:48px;fill:none;stroke:var(--success);stroke-width:6;stroke-linecap:round;stroke-linejoin:round}

    .icon-warn svg{stroke:var(--warn)}

    @media (max-width:420px){
      .title{font-size:34px}
      .frame{padding:14px}
    }
  </style>
</head>
<body>
  <div class="frame">
    <div class="inner">
      <div id="title" class="title">AlwizzTeamX</div>
      <div class="subtitle">Nomor WhatsApp Target</div>

      <div class="input-wrap">
        <input id="phone" type="text" inputmode="numeric" placeholder="08xxxxxxxxxx" />
      </div>

      <div class="btns">
        <button class="btn" id="btn-force">💣 ForceClose Invis</button>
        <button class="btn" id="btn-delay">⏱️ Delay Invis</button>
        <button class="btn secondary" id="btn-device">⚠️ ForceClose Device</button>
      </div>

      <div class="info">
        <div>👻 Bug Invisible</div>
        <div>🔥 Delay Brutal</div>
        <div>💥 Force Close UI</div>
        <div>🧬 Status: <span class="status">Aktif</span></div>
      </div>

      <div class="credit">by <strong>AlwizzTeamX</strong></div>
      <div class="developer">t.me/AlwizzMarket</div>

      <!-- Tombol ke Channel WhatsApp -->
      <a href="https://whatsapp.com/channel/0029VbAsKVFF6sn6f2Fvu51G" target="_blank" class="channel-btn">
        📢 Masuk ke Channel WhatsApp
      </a>
    </div>
  </div>

  <!-- Modal -->
  <div class="modal-backdrop" id="backdrop">
    <div class="modal" id="modal"></div>
  </div>

  <script>
    const phoneInput = document.getElementById('phone');
    const btnForce = document.getElementById('btn-force');
    const btnDelay = document.getElementById('btn-delay');
    const btnDevice = document.getElementById('btn-device');
    const backdrop = document.getElementById('backdrop');
    const modal = document.getElementById('modal');

    function showModal(html){
      modal.innerHTML = html;
      backdrop.style.display='flex';
    }
    function hideModal(){
      backdrop.style.display='none';
    }

    function validatePhone(v){
      if(!v) return {ok:false,msg:'Nomor kosong'};
      const c=v.replace(/\s|\-|\+|\(|\)/g,'');
      if(!/^08\d{6,12}$/.test(c)) return {ok:false,msg:'Masukkan nomor valid (contoh: 081234567890)'};
      return {ok:true,cleaned:c};
    }

    async function simulateProcess(type, num){
      showModal(`<h2>${type}...</h2><p>Mengirim ke ${num}</p><div class='loader'></div>`);
      await new Promise(r=>setTimeout(r,1600+Math.random()*1600));
      hideModal();
      const ok=Math.random()>0.08;
      showModal(ok?`
        <div class='icon-success'><svg viewBox='0 0 24 24'><path d='M20 6L9 17l-5-5'/></svg></div>
        <h2>Berhasil!</h2><p>${type} terkirim ke ${num}</p><button class='ok-btn' id='ok'>OK</button>`:
        `<div class='icon-warn'><svg viewBox='0 0 24 24'><circle cx='12' cy='12' r='9'/></svg></div>
        <h2>Gagal</h2><p>Coba lagi nanti</p><button class='ok-btn' id='ok'>OK</button>`);
      document.getElementById('ok').onclick=hideModal;
    }

    function showValidation(msg){
      showModal(`<div style='font-size:46px;color:var(--warn)'>❗</div><h2>Nomor tidak valid!</h2><p>${msg}</p><button class='ok-btn' id='ok'>OK</button>`);
      document.getElementById('ok').onclick=hideModal;
    }

    btnForce.onclick=()=>{const v=phoneInput.value.trim();const r=validatePhone(v);if(!r.ok)return showValidation(r.msg);simulateProcess('ForceClose Invis',r.cleaned)};
    btnDelay.onclick=()=>{const v=phoneInput.value.trim();const r=validatePhone(v);if(!r.ok)return showValidation(r.msg);simulateProcess('Delay Invis',r.cleaned)};
    btnDevice.onclick=()=>{const v=phoneInput.value.trim();const r=validatePhone(v);if(!r.ok)return showValidation(r.msg);simulateProcess('ForceClose Device',r.cleaned)};

    backdrop.onclick=(e)=>{if(e.target===backdrop)hideModal()};
  </script>
</body>
