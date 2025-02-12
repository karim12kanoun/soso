#soso

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
            margin: 0;
        }

        .container {
            width: 80vw; /* Zone où le bouton peut apparaître */
            height: 80vh;
            background-color: white;
            border: 2px solid #007BFF;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
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

    <div class="container">
        <button class="magic-button" onclick="moveButton()">Clique-moi !</button>
    </div>

    <script>
        function moveButton() {
            const button = document.querySelector('.magic-button');
            const container = document.querySelector('.container');

            button.style.opacity = '0'; // Disparition

            setTimeout(() => {
                // Obtenir la taille du conteneur et du bouton
                const containerRect = container.getBoundingClientRect();
                const buttonWidth = button.offsetWidth;
                const buttonHeight = button.offsetHeight;

                // Calculer une nouvelle position aléatoire à l'intérieur du conteneur
                const maxX = containerRect.width - buttonWidth;
                const maxY = containerRect.height - buttonHeight;
                const newX = Math.random() * maxX;
                const newY = Math.random() * maxY;

                // Appliquer la nouvelle position dans les limites du conteneur
                button.style.transform = `translate(${newX}px, ${newY}px)`;
                button.style.opacity = '1'; // Réapparition
            }, 500);
        }
    </script>

</body>
</html>
