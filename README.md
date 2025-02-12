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
            margin: 0;
        }

        .container {
            width: 80vw; /* Zone du bouton */
            height: 80vh;
            background-color: white;
            border: 2px solid #007BFF;
            position: relative; /* Important pour positionner le bouton en absolu */
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .magic-button {
            position: absolute; /* Position absolue pour rester dans le cadre */
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 15px 30px;
            font-size: 18px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: opacity 0.3s, left 0.5s ease-in-out, top 0.5s ease-in-out;
        }
    </style>
</head>
<body>

    <div class="container">
        <button class="magic-button" onclick="moveButton()">Clique-moi !</button>
    </div>

    <script>
        function moveButton() {
            const button = document.querySelector('.magic-button');
            const container = document.querySelector('.container');

            button.style.opacity = '0'; // Disparition

            setTimeout(() => {
                // Obtenir les dimensions du conteneur et du bouton
                const containerRect = container.getBoundingClientRect();
                const buttonWidth = button.offsetWidth;
                const buttonHeight = button.offsetHeight;

                // Calculer des nouvelles positions aléatoires DANS le conteneur
                const minX = 0;
                const minY = 0;
                const maxX = containerRect.width - buttonWidth;
                const maxY = containerRect.height - buttonHeight;
                const newX = Math.random() * (maxX - minX) + minX;
                const newY = Math.random() * (maxY - minY) + minY;

                // Appliquer la nouvelle position
                button.style.left = `${newX}px`;
                button.style.top = `${newY}px`;

                button.style.opacity = '1'; // Réapparition
            }, 500);
        }
    </script>

</body>
</html>
