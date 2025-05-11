# For-you-ibu
<html lang="ms">
<head>
  <meta charset="UTF-8">
  <title>Selamat Hari Ibu!</title>
  <style>
    body {
      background: #ffe6f0;
      text-align: center;
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden;
      padding-top: 50px;
    }
    h1 {
      color: #e60073;
      font-size: 3em;
    }
    p {
      font-size: 1.5em;
      color: #4d004d;
      margin-top: 20px;
    }
    .heart {
      color: red;
      font-size: 3em;
      animation: pulse 1s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
    button {
      margin-top: 30px;
      padding: 10px 20px;
      font-size: 1em;
      background-color: #ff66b3;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    button:hover {
      background-color: #ff3385;
    }

    /* Floating hearts animation */
    .floating-heart {
      position: absolute;
      color: #ff3366;
      animation: float 6s linear infinite;
      font-size: 2em;
      opacity: 0.8;
    }

    @keyframes float {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-100vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <h1>Selamat Hari Ibu!</h1>
  <div class="heart">♥</div>
  <p>Ibu, kasihmu tiada tandingan. Terima kasih kerana sentiasa ada.</p>
  <button onclick="ucapan()">Tekan untuk Ucapan Istimewa</button>

  <!-- Autoplay lagu -->
  <audio autoplay loop>
    <source src="https://archive.org/download/IwanFals_ibu/Iwan%20Fals%20-%20Ibu.mp3" type="audio/mpeg">
    Browser anda tidak menyokong audio.
  </audio>

  <!-- Floating hearts -->
  <script>
    function ucapan() {
      alert("Ibu, terima kasih atas segalanya. Saya sayang Ibu!");
    }

    // Create floating hearts
    setInterval(() => {
      const heart = document.createElement('div');
      heart.classList.add('floating-heart');
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (Math.random() * 20 + 10) + "px";
      heart.innerText = '♥';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }, 300);
  </script>
</body>
</html>
