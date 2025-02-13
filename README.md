
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour Toi, Mon Amour 💖</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Poppins', sans-serif;
            text-align: center;
            overflow: hidden;
            flex-direction: column;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            animation: gradientBG 10s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
            position: relative;
            backdrop-filter: blur(10px);
        }

        .buttons {
            margin-top: 20px;
            position: relative;
        }

        button {
            padding: 15px 30px;
            font-size: 18px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            margin: 10px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
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
            animation: float 4s infinite ease-in-out;
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }

        .gallery {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 20px;
        }

        .gallery img {
            width: 200px;
            height: auto;
            border-radius: 10px;
            display: none;
            transition: transform 0.3s ease;
        }

        .gallery img:hover {
            transform: scale(1.1);
        }

        .countdown {
            font-size: 20px;
            color: #ff1493;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Man chat tu veux bien être ma Valentine ? 💖</h2>
        <div class="buttons">
            <button class="yes" onclick="showLove()">Oui</button>
            <button class="no" onclick="moveButton(this)">Non</button>
        </div>
        <div class="love-message">Bebou, tu es mon plus beau cadeau, mon bonheur quotidien, ma plus belle histoire. Je t’aime infiniment ! 💕</div>
        <div class="hidden-message">Tu es la plus belle, mon amour éternel 😘</div>
        <div class="gallery">
            <img src="photo1.jpg.jpg" class="photo">
            <img src="photo2.jpg.jpg" class="photo">
            <img src="photo3.jpg.jpg" class="photo">
            <img src="photo4.jpg.jpg" class="photo">
        </div>
        <div class="countdown">Surprise dans <span id="timer">10</span> secondes...</div>
    </div>
    <script>
        function showLove() {
            document.querySelector('.love-message').style.display = 'block';
            document.querySelector('.love-message').style.opacity = '1';
            for (let i = 0; i < 20; i++) {
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
            const container = document.querySelector('.container');
            const maxX = container.offsetWidth - button.offsetWidth;
            const maxY = container.offsetHeight - button.offsetHeight;
            const newX = Math.random() * maxX;
            const newY = Math.random() * maxY;
            button.style.left = `${newX}px`;
            button.style.top = `${newY}px`;
        }
    </script>
</body>
</html>
