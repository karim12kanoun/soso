
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour Toi, Mon Amour 💖</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe4e1;
            margin: 0;
            font-family: Arial, sans-serif;
            text-align: center;
            overflow: hidden;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }
        .yes {
            background-color: #ff1493;
            color: white;
        }
        .no {
            background-color: #ff4d4d;
            color: white;
            position: absolute;
        }
        .love-message {
            display: none;
            font-size: 30px;
            color: #ff1493;
            font-weight: bold;
            opacity: 0;
            transform: scale(0.5);
            animation: loveAnimation 2s forwards;
        }
        @keyframes loveAnimation {
            0% { opacity: 0; transform: scale(0.5); }
            50% { opacity: 1; transform: scale(1.2); }
            100% { opacity: 1; transform: scale(1); }
        }
        .hidden-message {
            display: none;
            font-size: 20px;
            color: #d63384;
            margin-top: 10px;
        }
        .hearts {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: red;
            clip-path: polygon(50% 0%, 100% 35%, 80% 100%, 50% 80%, 20% 100%, 0% 35%);
            animation: float 4s infinite;
        }
        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }
        .gallery img {
            width: 200px;
            height: auto;
            border-radius: 10px;
            display: none;
        }
        .countdown {
            font-size: 20px;
            color: #ff1493;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <audio autoplay loop>
        <source src="romantic-music.mp3" type="audio/mpeg">
    </audio>
    <div class="container">
        <h2>Veux-tu être ma Valentine ? 💖</h2>
        <div class="buttons">
            <button class="yes" onclick="showLove()">Oui</button>
            <button class="no" onclick="moveButton(this)">Non</button>
        </div>
        <div class="love-message">Je t'aime ! 💕</div>
        <div class="hidden-message">Tu es la plus belle 😘</div>
        <div class="gallery">
            <img src="photo1.jpg" class="photo">
            <img src="photo2.jpg" class="photo">
            <img src="photo3.jpg" class="photo">
        </div>
        <div class="countdown">Surprise dans <span id="timer">10</span> secondes...</div>
    </div>
    <script>
        function showLove() {
            document.querySelector('.love-message').style.display = 'block';
            for (let i = 0; i < 10; i++) {
                let heart = document.createElement('div');
                heart.classList.add('hearts');
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = (Math.random() * 2 + 2) + 's';
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 4000);
            }
            let photos = document.querySelectorAll('.photo');
            let index = 0;
            function showNextPhoto() {
                photos.forEach(photo => photo.style.display = 'none');
                photos[index].style.display = 'block';
                index = (index + 1) % photos.length;
                setTimeout(showNextPhoto, 3000);
            }
            showNextPhoto();
            let countdown = 10;
            let timerInterval = setInterval(() => {
                document.getElementById('timer').textContent = countdown;
                countdown--;
                if (countdown < 0) {
                    clearInterval(timerInterval);
                    document.querySelector('.hidden-message').style.display = 'block';
                }
            }, 1000);
        }
        function moveButton(button) {
            const maxX = window.innerWidth - button.offsetWidth;
            const maxY = window.innerHeight - button.offsetHeight;
            const newX = Math.random() * maxX;
            const newY = Math.random() * maxY;
            button.style.left = `${newX}px`;
            button.style.top = `${newY}px`;
        }
    </script>
</body>
</html>
