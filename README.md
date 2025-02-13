<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour Toi, Mon Amour ❤️</title>
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
            background: #ffe6f2;
        }

        /* Animation des fleurs */
        .flower {
            position: absolute;
            top: -10vh;
            width: 40px;
            height: 40px;
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Sakura_icon.svg/1024px-Sakura_icon.svg.png');
            background-size: cover;
            opacity: 0.8;
            animation: fall 5s linear infinite;
        }

        @keyframes fall {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Man chat, tu veux bien être ma Valentine ? ❤️</h2>
        <div id="typewriter"></div>
        <div class="buttons">
            <button class="yes" onclick="showLove()">Oui</button>
            <button class="no" onclick="moveButton(this)">Non</button>
        </div>
    </div>

    <script>
        function showLove() {
            alert("Bebou, tu es mon plus beau cadeau, mon bonheur quotidien, ma plus belle histoire NHABEEEEK ❤️");
            startFlowerAnimation();
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

        function startFlowerAnimation() {
            for (let i = 0; i < 10; i++) {
                let flower = document.createElement("div");
                flower.classList.add("flower");
                flower.style.left = Math.random() * 100 + "vw";
                flower.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.body.appendChild(flower);
                setTimeout(() => { flower.remove(); }, 5000);
            }
        }
    </script>
</body>
</html>
