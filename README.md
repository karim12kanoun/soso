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

        .container {
            background: rgba(255, 255, 255, 0.7);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
            position: relative;
            backdrop-filter: blur(8px);
            z-index: 1;
        }

        .buttons {
            margin-top: 20px;
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

        .yes {
            background-color: #ff1493;
            color: white;
        }

        .no {
            background-color: #ff4d4d;
            color: white;
        }

        /* Animation de pétales */
        .flower {
            position: absolute;
            width: 30px;
            height: 30px;
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Cherry_Blossom_Flower.svg/1024px-Cherry_Blossom_Flower.svg.png');
            background-size: cover;
            opacity: 0.8;
            animation: fall 5s linear infinite;
        }

        @keyframes fall {
            from {
                transform: translateY(-10vh) rotate(0deg);
                opacity: 1;
            }
            to {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Man chat, tu veux bien être ma Valentine ? ❤️</h2>
        <div class="buttons">
            <button class="yes" onclick="showLove()">Oui</button>
            <button class="no" onclick="moveButton(this)">Non</button>
        </div>
    </div>

    <script>
        function showLove() {
            alert("Bebou, tu es mon plus beau cadeau, mon bonheur quotidien, ma plus belle histoire NHABEEEEK ❤️");
            createFlowers();
        }

        function createFlowers() {
            for (let i = 0; i < 20; i++) {
                let flower = document.createElement("div");
                flower.classList.add("flower");
                flower.style.left = Math.random() * 100 + "vw";
                flower.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.body.appendChild(flower);
                setTimeout(() => {
                    flower.remove();
                }, 5000);
            }
        }

        function moveButton(button) {
            const container = document.querySelector('.container');
            const maxX = container.offsetWidth - button.offsetWidth;
            const maxY = container.offsetHeight - button.offsetHeight;
            const newX = Math.random() * maxX;
            const newY = Math.random() * maxY;
            button.style.position = "absolute";
            button.style.left = `${newX}px`;
            button.style.top = `${newY}px`;
        }
    </script>
</body>
</html>
