<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Thư 20/10 💌</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ffe6f2, #fff0f5);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Poppins', sans-serif;
      overflow: hidden;
    }

    .envelope {
      position: relative;
      width: 260px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    .envelope img {
      width: 100%;
      border-radius: 14px;
      box-shadow: 0 6px 14px rgba(0,0,0,0.15);
      transition: transform 0.4s ease;
    }

    .envelope:hover {
      transform: scale(1.05);
    }

    .letter {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 250px;
      min-height: 180px;
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 6px 16px rgba(0,0,0,0.15);
      transform: translate(-50%, -50%) scale(0);
      opacity: 0;
      transition: all 0.7s ease;
      z-index: 2;
      padding: 20px;
      text-align: center;
      line-height: 1.6;
      color: #d63384;
      font-weight: 500;
    }

    .letter.open {
      transform: translate(-50%, -130%) scale(1);
      opacity: 1;
    }

    .bounce {
      animation: bounce 0.4s;
    }

    @keyframes bounce {
      0% { transform: scale(1); }
      50% { transform: scale(1.08); }
      100% { transform: scale(1); }
    }

    .heart {
      position: absolute;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 24px;
      opacity: 0;
      transition: opacity 0.6s ease;
    }

    .letter.open .heart {
      opacity: 1;
    }
  </style>
</head>
<body>
  <div class="envelope" id="envelope">
    <img src="6dc1c2ca-c347-44a3-b25c-d88b99412408.png" alt="Love Envelope">
    <div class="letter" id="letter">
      💌 <br>
      Gửi đến những người phụ nữ tuyệt vời nhất,  
      chúc bạn luôn xinh đẹp, hạnh phúc và rạng rỡ như những bông hoa! 🌸  
      <br><br>
      Chúc mừng ngày 20/10! 💖
      <div class="heart">💗</div>
    </div>
  </div>

  <!-- Hiệu ứng âm thanh mở thư -->
  <audio id="openSound" preload="auto">
    <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_2b1fbe3b38.mp3" type="audio/mpeg">
  </audio>

  <script>
    const envelope = document.getElementById('envelope');
    const letter = document.getElementById('letter');
    const sound = document.getElementById('openSound');

    envelope.addEventListener('click', () => {
      envelope.classList.add('bounce');
      setTimeout(() => envelope.classList.remove('bounce'), 400);
      const opening = !letter.classList.contains('open');
      letter.classList.toggle('open');
      if (opening) sound.play();
    });
  </script>
</body>
</html>
