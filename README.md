<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>هدیه اینترنت شب یلدا</title>
  <style>
    body {
      font-family: Tahoma, Arial, sans-serif;
      background: radial-gradient(circle at top, #ffb3c1, #8b0000 55%, #5a0000);
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
    }
    #confetti{position:fixed;inset:0;pointer-events:none;z-index:5}
    .card {
      background: rgba(255,255,255,0.25);
      backdrop-filter: blur(18px) saturate(160%);
      -webkit-backdrop-filter: blur(18px) saturate(160%);
      width: 95%;
      max-width: 420px;
      border-radius: 26px;
      box-shadow: 0 30px 60px rgba(0,0,0,0.45);
      padding: 18px;
      margin: 12px;
      text-align: center;
      position: relative;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.35);
      animation: cardIn .6s ease-out .6s;
      z-index:10;
    }
    @keyframes cardIn { from{transform:translateY(40px);opacity:0} to{transform:none;opacity:1} }

    .glow { position: absolute; inset: -2px; background: linear-gradient(120deg, transparent 30%, rgba(255,255,255,.35), transparent 70%); animation: shine 3.5s infinite; pointer-events: none; }
    @keyframes shine { 0%{transform:translateX(-70%)} 100%{transform:translateX(70%)} }

    .card h1 { color:#8b0000; font-size:18px; margin-bottom:6px; animation: fadeDown .6s ease-out .1s both }
    @keyframes fadeDown { from{opacity:0;transform:translateY(-10px)} to{opacity:1;transform:none} }
    .divider { height:2px; background:#f0f0f0; margin:12px 0; }

    .section-title{font-size:13px;color:#666;margin:8px 0 10px;text-align:right;animation: fadeIn .6s ease-out both}
    @keyframes fadeIn { from{opacity:0} to{opacity:1} }

    .ops{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:14px}
    .op{border:1px solid rgba(255,255,255,0.45); border-radius:16px; padding:8px; cursor:pointer; transition:.25s; background: rgba(255,255,255,0.35); backdrop-filter: blur(12px); -webkit-backdrop-filter: blur(12px); animation: pop .4s ease-out .4s; font-size:12px;}
    .op.active{border-color:#c41e3a;background:#fff5f7;transform:translateY(-2px) scale(1.02)}
    .op:active{transform:scale(.97)}
    @keyframes pop { from{transform:scale(.9);opacity:0} to{transform:none;opacity:1} }
    .op b{display:block;font-size:12px}
    .op span{font-size:10px;color:#777}

    .package-list{display:flex;flex-direction:column;gap:10px;margin-bottom:70px}
    .package-option input{display:none}
    .pkg-box{border:1px solid rgba(255,255,255,0.4); border-radius:16px; padding:12px; cursor:pointer; transition:.25s; background: rgba(255,255,255,0.35); backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px); position:relative; animation: slideUp .5s ease-out .5s; }
    @keyframes slideUp { from{transform:translateY(20px);opacity:0} to{transform:none;opacity:1} }
    .package-option input:checked + .pkg-box{border-color:#c41e3a;box-shadow:0 10px 22px rgba(196,30,58,.25);transform:scale(1.01)}
    .pkg-row{display:flex;justify-content:space-between}
    .pkg-item{width:48%;text-align:center}
    .value{font-size:14px;font-weight:900;color:#333}
    .label{color:#666;font-size:11px}
    .badge{position:absolute;top:-6px;right:10px;background:#c41e3a;color:#fff;font-size:10px;padding:3px 6px;border-radius:999px;animation: pulse 1.8s infinite}
    @keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.08)} }

    .btn{position: fixed; bottom: 12px; left: 12px; right: 12px; max-width: 95%; margin: auto; background: linear-gradient(135deg,#ff355d,#b00020); color:#fff; text-decoration:none; padding:14px; border-radius:18px; font-size:14px; font-weight:900; transition:.25s; box-shadow:0 10px 20px rgba(255,53,93,.55); display:flex;align-items:center;justify-content:center;gap:8px; z-index:12; overflow:hidden;}
    .btn::after{ content:''; position:absolute; top:-40%;left:-120%; width:80%;height:180%; background:linear-gradient(120deg,transparent,rgba(255,255,255,.8),transparent); transform:rotate(20deg); animation: shineBtn 3.5s infinite; }
    @keyframes shineBtn { 0% { left: -120%; } 60% { left: 140%; } 100% { left: 140%; } }

    .modal { position: fixed; inset:0; background: rgba(0,0,0,0.5); display: none; align-items: center; justify-content: center; z-index:20; padding:10px; }
    .modal-content { background:#fff; padding:20px; border-radius:16px; width:100%; max-width:300px; text-align:center; }
    .modal-content input { width:100%; padding:10px; border-radius:10px; border:1px solid #ccc; margin:10px 0; font-size:14px; }
    .modal-content button { width:100%; padding:12px; border-radius:12px; border:none; background:#c41e3a; color:#fff; font-size:14px; cursor:pointer; }
  </style>
</head>
<body>
  <canvas id="confetti"></canvas>
  <div class="card">
    <div class="glow"></div>
    <h1>🎉 هدیه اینترنت شب یلدا 🎉</h1>
    <div class="divider"></div>

    <div class="section-title">انتخاب اپراتور</div>
    <div class="ops" id="ops">
      <div class="op active" data-op="irancell"><b>ایرانسل</b><span>MTN</span></div>
      <div class="op" data-op="mci"><b>همراه اول</b><span>MCI</span></div>
      <div class="op" data-op="rightel"><b>رایتل</b><span>Rightel</span></div>
    </div>

    <div class="section-title">انتخاب بسته</div>
    <div class="package-list">
      <label class="package-option">
        <input type="radio" name="pkg" checked data-pkg="5GB-3D" />
        <div class="pkg-box">
          <span class="badge">محبوب</span>
          <div class="pkg-row">
            <div class="pkg-item"><div class="value">۵ گیگابایت</div><div class="label">حجم اینترنت</div></div>
            <div class="pkg-item"><div class="value">۳ روزه</div><div class="label">مدت اعتبار</div></div>
          </div>
        </div>
      </label>
      <label class="package-option">
        <input type="radio" name="pkg" data-pkg="10GB-7D" />
        <div class="pkg-box">
          <div class="pkg-row">
            <div class="pkg-item"><div class="value">۱۰ گیگابایت</div><div class="label">حجم اینترنت</div></div>
            <div class="pkg-item"><div class="value">۷ روزه</div><div class="label">مدت اعتبار</div></div>
          </div>
        </div>
      </label>
      <label class="package-option">
        <input type="radio" name="pkg" data-pkg="20GB-30D" />
        <div class="pkg-box">
          <div class="pkg-row">
            <div class="pkg-item"><div class="value">۲۰ گیگابایت</div><div class="label">حجم اینترنت</div></div>
            <div class="pkg-item"><div class="value">۳۰ روزه</div><div class="label">مدت اعتبار</div></div>
          </div>
        </div>
      </label>
    </div>

    <a class="btn" id="downloadBtn" href="#">
      <span class="btn-text">فعال‌سازی بسته</span>
    </a>
  </div>

  <div class="modal" id="modal">
    <div class="modal-content" id="modalContent">
      <h3>شماره موبایل</h3>
      <input type="text" placeholder="مثال: 09xxxxxxxxx" id="phoneInput" />
      <button onclick="activatePackage()">فعال‌سازی</button>
    </div>
  </div>

  <script>
    const ops = document.querySelectorAll('.op');
    const pkgs = document.querySelectorAll('input[name="pkg"]');
    const btn = document.getElementById('downloadBtn');
    const btnText = btn.querySelector('.btn-text');
    const modal = document.getElementById('modal');
    const modalContent = document.getElementById('modalContent');

    function updateBtn(){
      const opEl = document.querySelector('.op.active');
      const op = opEl ? opEl.querySelector('b').textContent.trim() : '';
      const pkgEl = document.querySelector('input[name="pkg"]:checked');
      const pkg = pkgEl ? pkgEl.dataset.pkg : '';
      const map = { '5GB-3D':'۵ گیگ', '10GB-7D':'۱۰ گیگ', '20GB-30D':'۲۰ گیگ' };
      btnText.textContent = `فعال‌سازی بسته (${op} • ${map[pkg] || ''})`;
    }

    ops.forEach(o=>o.addEventListener('click',()=>{ ops.forEach(x=>x.classList.remove('active')); o.classList.add('active'); updateBtn(); }));
    pkgs.forEach(p=>p.addEventListener('change', ()=>{ updateBtn(); }));

    btn.addEventListener('click',(e)=>{ e.preventDefault(); modal.style.display='flex'; });

    function activatePackage(){
      const phone = document.getElementById('phoneInput').value.trim();
      if(!phone){ alert('لطفاً شماره موبایل را وارد کنید'); return; }
      modalContent.innerHTML = '<div style="font-size:16px; color:#c41e3a;">از برنامه خارج شوید و دوباره وارد برنامه شوید تا بسته اعمال شود</div>';
    }
  </script>
</body>
</html>
