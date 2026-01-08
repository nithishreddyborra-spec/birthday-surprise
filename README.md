# birthday-surprise
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Bannu! 🎉</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <audio id="birthdayMusic" src="music.mp3" autoplay loop></audio>

  <div class="container">
    <h1>🎂 Happy Birthday Bannu! 🎉</h1>
    <p>Wishing you a day full of love, laughter, and joy! ❤️</p>

    <div class="gallery">
      <img src="https://placekitten.com/300/200" alt="Bannu Photo 1">
      <img src="https://placekitten.com/301/200" alt="Bannu Photo 2">
      <img src="https://placekitten.com/302/200" alt="Bannu Photo 3">
    </div>

    <button id="popupBtn">Click for Surprise 🎁</button>
  </div>

  <div id="popup" class="popup">
    <div class="popup-content">
      <h2>Surprise! 🎈</h2>
      <p>Hope your birthday is as amazing as you are, Bannu! 💖</p>
      <button id="closePopup">Close</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
