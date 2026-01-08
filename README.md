# birthday-surprise

<!DOCTYPE html><!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Bannu! 🎉</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(120deg, #fbc2eb, #a6c1ee);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
      text-align: center;
      position: relative;
    }

    h1 {
      position: absolute;
      top: 30px;
      width: 100%;
      font-size: 3em;
      color: #fff;
      text-shadow: 2px 2px #ff6f91;
      animation: bounce 1s infinite alternate;
      z-index: 2;
    }

    @keyframes bounce {
      from { transform: translateY(0); }
      to { transform: translateY(-20px); }
    }

    #slideshow {
      width: 90%;
      max-width: 500px;
      height: 300px;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(0,0,0,0.3);
      z-index: 1;
    }

    #slideshow img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }

    #slideshow img.active {
      opacity: 1;
    }

    #confetti-canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
    }

    #surprise-note {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0.5);
      background: rgba(255, 255, 255, 0.9);
      padding: 30px;
      border-radius: 20px;
      font-size: 1.5em;
      color: #ff3366;
      text-shadow: 1px 1px #fff;
      display: none;
      z-index: 3;
      box-shadow: 0 0 20px rgba(0,0,0,0.4);
      opacity: 0;
      transition: opacity 1.5s ease, transform 1.5s ease;
    }

    #surprise-note.show {
      display: block;
      opacity: 1;
      transform: translate(-50%, -50%) scale(1);
    }
  </style>
</head>
<body>
  <canvas id="confetti-canvas"></canvas>
  <h1>Happy Birthday, Bannu! 🫂🎂</h1>

  <div id="slideshow">
    <img src="photo1.jpg" class="active" alt="Birthday Photo 1">
    <img src="photo2.jpg" alt="Birthday Photo 2">
    <img src="photo3.jpg" alt="Birthday Photo 3">
    <!-- Add more photos here -->
  </div>

  <div id="surprise-note">
    🎉 Happy Birthday to you Bawa! <br>
    Love you so much ❤️‍🩹
  </div>

  <audio id="birthday-music" autoplay loop>
    <source src="happy_birthday.mp3" type="audio/mpeg">
  </audio>

  <script>
    // Confetti animation
    const canvas = document.getElementById('confetti-canvas');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const confettiCount = 150;
    const confetti = [];

    for (let i = 0; i < confettiCount; i++) {
      confetti.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height - canvas.height,
        r: Math.random() * 6 + 4,
        d: Math.random() * confettiCount,
        color: `hsl(${Math.random() * 360}, 100%, 50%)`,
        tilt: Math.random() * 10 - 10,
        tiltAngleIncremental: Math.random() * 0.07 + 0.05,
        tiltAngle: 0
      });
    }

    function drawConfetti() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      confetti.forEach((c) => {
        ctx.beginPath();
        ctx.lineWidth = c.r / 2;
        ctx.strokeStyle = c.color;
        ctx.moveTo(c.x + c.tilt + c.r / 4, c.y);
        ctx.lineTo(c.x + c.tilt, c.y + c.tilt + c.r / 4);
        ctx.stroke();
      });
      updateConfetti();
    }

    function updateConfetti() {
      confetti.forEach((c, i) => {
        c.tiltAngle += c.tiltAngleIncremental;
        c.y += (Math.cos(c.d) + 3 + c.r / 2) / 2;
        c.x += Math.sin(c.d);
        c.tilt = Math.sin(c.tiltAngle) * 15;

        if (c.y > canvas.height) {
          confetti[i] = { 
            x: Math.random() * canvas.width,
            y: -20,
            r: c.r,
            d: c.d,
            color: c.color,
            tilt: c.tilt,
            tiltAngleIncremental: c.tiltAngleIncremental,
            tiltAngle: c.tiltAngle
          };
        }
      });
    }

    setInterval(drawConfetti, 20);

    // Surprise note popup with animation
    window.onload = () => {
      setTimeout(() => {
        const note = document.getElementById('surprise-note');
        note.classList.add('show');
      }, 1000); // Show after 1 second
    };

    // Slideshow
    const slides = document.querySelectorAll('#slideshow img');
    let currentSlide = 0;

    setInterval(() => {
      slides[currentSlide].classList.remove('active');
      currentSlide = (currentSlide + 1) % slides.length;
      slides[currentSlide].classList.add('active');
    }, 3000); // Change slide every 3 seconds
  </script>
</body>
</html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Bannu! 🎉</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(120deg, #fbc2eb, #a6c1ee);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
      text-align: center;
      position: relative;
    }

    h1 {
      position: absolute;
      top: 30px;
      width: 100%;
      font-size: 3em;
      color: #fff;
      text-shadow: 2px 2px #ff6f91;
      animation: bounce 1s infinite alternate;
      z-index: 2;
    }

    @keyframes bounce {
      from { transform: translateY(0); }
      to { transform: translateY(-20px); }
    }

    #slideshow {
      width: 90%;
      max-width: 500px;
      height: 300px;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(0,0,0,0.3);
      z-index: 1;
    }

    #slideshow img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }

    #slideshow img.active {
      opacity: 1;
    }

    #confetti-canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
    }

    #surprise-note {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0.5);
      background: rgba(255, 255, 255, 0.9);
      padding: 30px;
      border-radius: 20px;
      font-size: 1.5em;
      color: #ff3366;
      text-shadow: 1px 1px #fff;
      display: none;
      z-index: 3;
      box-shadow: 0 0 20px rgba(0,0,0,0.4);
      opacity: 0;
      transition: opacity 1.5s ease, transform 1.5s ease;
    }

    #surprise-note.show {
      display: block;
      opacity: 1;
      transform: translate(-50%, -50%) scale(1);
    }
  </style>
</head>
<body>
  <canvas id="confetti-canvas"></canvas>
  <h1>Happy Birthday, Bannu! 🫂🎂</h1>

  <div id="slideshow">
    <img src="photo1.jpg" class="active" alt="Birthday Photo 1">
    <img src="photo2.jpg" alt="Birthday Photo 2">
    <img src="photo3.jpg" alt="Birthday Photo 3">
    <!-- Add more photos here -->
  </div>

  <div id="surprise-note">
    🎉 Happy Birthday to you Bawa! <br>
    Love you so much ❤️‍🩹
  </div>

  <audio id="birthday-music" autoplay loop>
    <source src="happy_birthday.mp3" type="audio/mpeg">
  </audio>

  <script>
    // Confetti animation
    const canvas = document.getElementById('confetti-canvas');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const confettiCount = 150;
    const confetti = [];

    for (let i = 0; i < confettiCount; i++) {
      confetti.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height - canvas.height,
        r: Math.random() * 6 + 4,
        d: Math.random() * confettiCount,
        color: `hsl(${Math.random() * 360}, 100%, 50%)`,
        tilt: Math.random() * 10 - 10,
        tiltAngleIncremental: Math.random() * 0.07 + 0.05,
        tiltAngle: 0
      });
    }

    function drawConfetti() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      confetti.forEach((c) => {
        ctx.beginPath();
        ctx.lineWidth = c.r / 2;
        ctx.strokeStyle = c.color;
        ctx.moveTo(c.x + c.tilt + c.r / 4, c.y);
        ctx.lineTo(c.x + c.tilt, c.y + c.tilt + c.r / 4);
        ctx.stroke();
      });
      updateConfetti();
    }

    function updateConfetti() {
      confetti.forEach((c, i) => {
        c.tiltAngle += c.tiltAngleIncremental;
        c.y += (Math.cos(c.d) + 3 + c.r / 2) / 2;
        c.x += Math.sin(c.d);
        c.tilt = Math.sin(c.tiltAngle) * 15;

        if (c.y > canvas.height) {
          confetti[i] = { 
            x: Math.random() * canvas.width,
            y: -20,
            r: c.r,
            d: c.d,
            color: c.color,
            tilt: c.tilt,
            tiltAngleIncremental: c.tiltAngleIncremental,
            tiltAngle: c.tiltAngle
          };
        }
      });
    }

    setInterval(drawConfetti, 20);

    // Surprise note popup with animation
    window.onload = () => {
      setTimeout(() => {
        const note = document.getElementById('surprise-note');
        note.classList.add('show');
      }, 1000); // Show after 1 second
    };

    // Slideshow
    const slides = document.querySelectorAll('#slideshow img');
    let currentSlide = 0;

    setInterval(() => {
      slides[currentSlide].classList.remove('active');
      currentSlide = (currentSlide + 1) % slides.length;
      slides[currentSlide].classList.add('active');
    }, 3000); // Change slide every 3 seconds
  </script>
</body>
</html>
