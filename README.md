# For-you-ibu
<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8">
  <title>Selamat Hari Ibu!</title>
  <style>
    body {
      background: linear-gradient(to bottom, #fff0f5, #ffe6f0);
      text-align: center;
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden;
      padding: 50px 20px;
    }
    h1 {
      color: #e60073;
      font-size: 3em;
      animation: fadeInDown 2s ease;
    }
    p {
      font-size: 1.4em;
      color: #4d004d;
      margin-top: 20px;
    }
    #quote {
      font-style: italic;
      margin-top: 30px;
      font-size: 1.2em;
      color: #660033;
      min-height: 40px;
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
    @keyframes float {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-100vh) scale(1.5); opacity: 0; }
    }
    @keyframes fadeInDown {
      from { opacity: 0; transform: translateY(-30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .floating-heart {
      position: absolute;
      color: #ff4d88;
      animation: float 6s linear infinite;
      opacity: 0.9;
      font-size: 2em;
    }
    button {
      margin-top: 30px;
      padding: 10px 20px;
      font-size: 1em;
      background-color: #ff66b3;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 2px 2px 10px rgba(0,0,0,0.2);
    }
    button:hover {
      background-color: #ff3385;
    }
  </style>
</head>
<body>

  <h1>Selamat Hari Ibu!</h1>
  <div class="heart">♥</div>
  <p>Ibu, kasihmu tiada tandingan. Terima kasih kerana sentiasa ada.</p>
  <button onclick="ucapan()">Tekan untuk Ucapan Istimewa</button>
  <p id="quote"></p>

  <!-- Muzik autoplay -->
  <audio autoplay loop>
    <source src="https://archive.org/download/IwanFals_ibu/Iwan%20Fals%20-%20Ibu.mp3" type="audio/mpeg">
    Browser anda tidak menyokong audio.
  </audio>

  <script>
    function ucapan() {
      alert("Ibu, terima kasih atas segalanya. Saya sayang Ibu!");
    }

    const quotes = [
      "Ibu adalah cinta yang pertama dan terakhir.",
      "Di dalam pelukan ibu, segalanya terasa tenang.",
      "Doa ibu adalah pelita hidup anaknya.",
      "Syurga itu di bawah telapak kaki ibu.",
      "Ibu tak pernah lelah mencintai, meskipun letih tak pernah habis menghampirinya.",
      "Kasih ibu sepanjang masa, kasih anak sepanjang galah.",
      "Ibu adalah guru pertama, sahabat sejati, dan malaikat di dunia nyata.",
      "Terima kasih ibu, untuk cinta yang tiada syarat dan doa yang tiada henti.",
      "Walau dunia menolak, ibu tetap menerima.",
      "Ibu, engkaulah wanita terkuat dalam hidupku."
    ];

    let current = 0;
    const quoteEl = document.getElementById("quote");
    function showQuote() {
      quoteEl.innerText = quotes[current];
      current = (current + 1) % quotes.length;
    }
    showQuote();
    setInterval(showQuote, 5000);

    // Floating hearts
    setInterval(() => {
      const heart = document.createElement('div');
      heart.classList.add('floating-heart');
      heart.innerText = '♥';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.fontSize = (Math.random() * 24 + 16) + 'px';
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 6000);
    }, 250);
  </script>
</body>
</html>
