<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Рефлексатор: Тест на скорость реакции</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f0f8ff;
    }
    h1 {
      color: #333;
    }
    #gameArea {
      margin-top: 50px;
    }
    #reactionButton {
      background-color: red;
      color: white;
      padding: 20px 40px;
      font-size: 24px;
      border: none;
      cursor: pointer;
      border-radius: 8px;
    }
    #reactionButton.green {
      background-color: green;
    }
    #result {
      margin-top: 20px;
      font-size: 24px;
    }
  </style>
</head>
<body>
  <h1>Тест на скорость реакции</h1>
  <p>Нажмите на кнопку, как только она станет зелёной!</p>

  <div id="gameArea">
    <button id="reactionButton" disabled>Подождите...</button>
    <p id="result"></p>
  </div>

  <script>
    let button = document.getElementById('reactionButton');
    let result = document.getElementById('result');
    let startTime;
    let timeout;

    function startGame() {
      button.disabled = true;
      button.classList.remove('green');
      button.textContent = 'Подождите...';

      // Случайная задержка перед зелёным сигналом
      let delay = Math.random() * 3000 + 1000;

      timeout = setTimeout(() => {
        button.classList.add('green');
        button.textContent = 'ЖМИ!';
        button.disabled = false;
        startTime = Date.now();
      }, delay);
    }

    button.addEventListener('click', () => {
      if (button.classList.contains('green')) {
        let reactionTime = Date.now() - startTime;
        result.textContent = `Ваше время реакции: ${reactionTime} мс`;
        button.disabled = true;
        button.classList.remove('green');
        button.textContent = 'Подождите...';
        setTimeout(startGame, 2000);
      } else {
        result.textContent = 'Слишком рано! Подождите зелёного сигнала.';
        clearTimeout(timeout);
        setTimeout(startGame, 2000);
      }
    });

    // Запуск игры
    startGame();
  </script>
</body>
</html>
