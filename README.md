<!DOCTYPE html>
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
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
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
    </style>
</head>
<body>
    <div class="container">
        <h2>Veux-tu être ma Valentine ? 💖</h2>
        <div class="buttons">
            <button class="yes" onclick="showLove()">Oui</button>
            <button class="no" onclick="moveButton(this)">Non</button>
        </div>
        <div class="love-message">Je t'aime ! 💕</div>
    </div>

    <script>
        function showLove() {
            document.querySelector('.love-message').style.display = 'block';
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
