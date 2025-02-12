#soso

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bouton Magique</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            overflow: hidden;
            position: relative;
            margin: 0;
        }

        .magic-button {
            position: absolute;
            padding: 15px 30px;
            font-size: 18px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: transform 0.5s ease-in-out, opacity 0.3s;
        }
    </style>
</head>
<body>

    <button class="magic-button" onclick="moveButton()">Clique-moi !</button>

    <script>
        function moveButton() {
            const button = document.querySelector('.magic-button');
            button.style.opacity = '0'; // Disparition

            setTimeout(() => {
                // Calculer une nouvelle position aléatoire
                const maxX = window.innerWidth - button.offsetWidth;
                const maxY = window.innerHeight - button.offsetHeight;
                const newX = Math.random() * maxX;
                const newY = Math.random() * maxY;

                button.style.transform = `translate(${newX}px, ${newY}px)`;
                button.style.opacity = '1'; // Réapparition
            }, 500);
        }
    </script>

</body>
</html>

