<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Thư dành cho bạn</title>
  <!-- Open Graph: Facebook sẽ lấy ảnh preview từ og:image nếu bạn share -->
  <meta property="og:title" content="Một lá thư cho bạn" />
  <meta property="og:description" content="Bấm vào phong bì để mở thư" />
  <meta property="og:image" content="https://yourdomain.com/preview-envelope.jpg" />
  <style>
    :root{--bg:#f6f3ef}
    body{margin:0;height:100vh;display:flex;align-items:center;justify-content:center;background:var(--bg);font-family:system-ui,Segoe UI,Roboto}
    .stage{width:320px;max-width:90vw;perspective:1000px}
    .envelope{width:100%;position:relative;cursor:pointer;transform-style:preserve-3d;transition:transform .9s cubic-bezier(.2,.9,.2,1)}
    .front, .back{position:relative;background:#fff;border-radius:8px;box-shadow:0 8px 20px rgba(0,0,0,.12);overflow:hidden}
    .front{padding:18px;height:200px;display:flex;align-items:center;justify-content:center}
    .seal{width:72px;height:72px;border-radius:50%;background:linear-gradient(180deg,#b24a37,#8f2f2f);display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700;box-shadow:0 6px 12px rgba(0,0,0,.12)}
    .back{position:absolute;inset:0;padding:18px;transform:rotateX(-180deg);backface-visibility:hidden;display:flex;align-items:center;justify-content:center}
    .letter{width:calc(100% - 40px);height:180px;background:#fff;padding:20px;border-radius:6px;box-shadow:0 6px 20px rgba(0,0,0,.08);overflow:auto}
    .open .front{transform:rotateX(180deg)}
    .open .back{transform:rotateX(0deg)}
    .hint{margin-top:16px;text-align:center;color:#666;font-size:14px}
    /* small */
    @media (max-width:420px){.seal{width:60px;height:60px}}
  </style>
</head>
<body>
  <div class="stage">
    <div id="env" class="envelope" aria-label="Phong bì, bấm để mở">
      <div class="front">
        <div class="seal">Thư</div>
      </div>
      <div class="back">
        <div class="letter" id="letter">
          <h3 style="margin-top:0">Gửi đến bạn những lời chúc ngọt ngào nhất nhân ngày 20/10,</h3>
          <p>Chúc bạn luôn xinh đẹp, mạnh mẽ và hạnh phúc — không chỉ hôm nay mà là mỗi ngày sau này.Cảm ơn vì bạn đã xuất hiện, mang đến nụ cười và ánh sáng cho những người xung quanh.🌷Mong mọi điều tốt đẹp nhất sẽ luôn đến với bạn — bởi bạn xứng đáng với điều đó 💐✨.</p>
          <p>— Thân mến</p>
        </div>
      </div>
    </div>
    <div class="hint">Bấm vào phong bì để mở thư</div>
  </div>

  <script>
    const env = document.getElementById('env');
    let open=false;
    env.addEventListener('click', ()=> {
      open = !open;
      if(open) env.classList.add('open'); else env.classList.remove('open');
    });
    // optional: close when click outside
    document.addEventListener('click', (e)=>{
      if(!env.contains(e.target) && open){ open=false; env.classList.remove('open'); }
    });
  </script>
</body>
</html>
