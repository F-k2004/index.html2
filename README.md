<!-- index.html -->
<!OCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>سنگ ✊ کاغذ ✋ قیچی ✌️</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #ffecd2, #fcb69f);
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    h1 {
      color: #333;
    }
    .choices {
      margin: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 18px;
      margin: 5px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      transform: scale(1.1);
    }
    .result {
      font-size: 20px;
      margin-top: 20px;
      font-weight: bold;
      color: #444;
    }
    .score {
      margin-top: 30px;
      font-size: 18px;
      background: #fff3;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>
  <h1>🎮 سنگ، کاغذ، قیچی</h1>
  <div class="choices">
    <button onclick="play('سنگ')">✊ سنگ</button>
    <button onclick="play('کاغذ')">✋ کاغذ</button>
    <button onclick="play('قیچی')">✌️ قیچی</button>
  </div>
  <div class="result" id="result">انتخاب کنید 👆</div>

  <div class="score">
    <p>✅ بردها: <span id="wins">0</span></p>
    <p>❌ باخت‌ها: <span id="losses">0</span></p>
    <p>😐 مساوی‌ها: <span id="draws">0</span></p>
  </div>

  <script>
    const choices = ["سنگ", "کاغذ", "قیچی"];
    let wins = 0, losses = 0, draws = 0;

    function play(userChoice) {
      const computerChoice = choices[Math.floor(Math.random() * choices.length)];
      let result = `شما: ${userChoice} | کامپیوتر: ${computerChoice} <br>`;

      if (userChoice === computerChoice) {
        result += "😐 مساوی شد!";
        draws++;
      } else if (
        (userChoice === "سنگ" && computerChoice === "قیچی") ||
        (userChoice === "کاغذ" && computerChoice === "سنگ") ||
        (userChoice === "قیچی" && computerChoice === "کاغذ")
      ) {
        result += "✅ شما برنده شدید!";
        wins++;
      } else {
        result += "❌ کامپیوتر برنده شد!";
        losses++;
      }

      document.getElementById("result").innerHTML = result;
      document.getElementById("wins").textContent = wins;
      document.getElementById("losses").textContent = losses;
      document.getElementById("draws").textContent = draws;
    }
  </script>
</body>
</html>
