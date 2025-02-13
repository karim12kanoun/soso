
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
            position: relative;
        }

        /* Carrousel */
        .carousel {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .carousel img {
            position: absolute;
            width: 80%;  /* Réduction de la taille */
            height: 80%;
            object-fit: cover;
            opacity: 0;
            animation: carousel 16s infinite;
        }

        .carousel img:nth-child(1) { animation-delay: 0s; }
        .carousel img:nth-child(2) { animation-delay: 4s; }
        .carousel img:nth-child(3) { animation-delay: 8s; }
        .carousel img:nth-child(4) { animation-delay: 12s; }

        @keyframes carousel {
            0% { opacity: 0; }
            10% { opacity: 1; }
            25% { opacity: 1; }
            35% { opacity: 0; }
            100% { opacity: 0; }
        }

        /* Cadre blanc avec plus de transparence */
        .container {
            background: rgba(255, 255, 255, 0.75); /* Plus transparent */
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
            position: relative;
            backdrop-filter: blur(5px); /* Effet flou pour une meilleure lisibilité */
            z-index: 1;
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

        .countdown {
            font-size: 20px;
            color: #ff1493;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <audio autoplay loop>
        <source src="votre-musique.mp3" type="audio/mpeg">
        Votre navigateur ne supporte pas l'élément audio.
    </audio>

    <!-- Carrousel en arrière-plan -->
    <div class="carousel">
        <img src="photo1.jpg.jpg" alt="Photo 1">
        <img src="photo2.jpg.jpg" alt="Photo 2">
        <img src="photo3.jpg.jpg" alt="Photo 3">
        <img src="photo4.jpg.jpg" alt="Photo 4">
    </div>

    <div class="container">
        <h2>Man chat tu veux bien être ma Valentine ? 💖</h2>
        <div class="buttons">
            <button class="yes" onclick="showLove()">Oui</button>
            <button class="no" onclick="moveButton(this)">Non</button>
        </div>
        <div class="love-message">Bebou, tu es mon plus beau cadeau, mon bonheur quotidien, ma plus belle histoire. Je t’aime infiniment ! 💕</div>
        <div class="hidden-message">Tu es la plus belle, mon amour éternel 😘</div>
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
