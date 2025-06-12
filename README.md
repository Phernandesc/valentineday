<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Feliz Dia dos Namorados</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to top right, #ff9aa2, #ffb7b2);
      overflow: hidden;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
    }

    h1 {
      font-size: 3em;
      animation: fadeIn 2s ease-in-out;
    }

    .heart {
      position: absolute;
      width: 50px;
      height: 50px;
      background-color: red;
      transform: rotate(45deg);
      animation: pulse 1s infinite;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 50px;
      height: 50px;
      background-color: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -25px;
      left: 0;
    }

    .heart::after {
      left: -25px;
      top: 0;
    }

    @keyframes pulse {
      0% {
        transform: scale(1) rotate(45deg);
      }
      50% {
        transform: scale(1.2) rotate(45deg);
      }
      100% {
        transform: scale(1) rotate(45deg);
      }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <h1> ❤️</h1>
  <script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.top = Math.random() * 100 + "vh";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 4000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>
