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

        /* Écran de chargement */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #ff1493;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            z-index: 1000;
            transition: opacity 1s ease-out;
        }

        .loading-text {
            color: white;
            font-size: 24px;
            margin-bottom: 20px;
            font-weight: bold;
        }

        .progress-bar {
            width: 60%;
            height: 10px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 5px;
            overflow: hidden;
        }

        .progress {
            height: 100%;
            width: 0;
            background: white;
        }

        .main-content {
            opacity: 0;
            transition: opacity 1s ease-in-out;
            pointer-events: none;
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

        .yes {
            background-color: #ff1493;
            color: white;
        }

        .no {
            background-color: #ff4d4d;
            color: white;
            position: absolute;
        }
    </style>
</head>
<body>
    <!-- Écran de chargement -->
    <div class="loading-screen">
        <div class="loading-text">Bonne Saint-Valentin à distance mon cœur 💕 <br> Chargement en cours...</div>
        <div class="progress-bar">
            <div class="progress"></div>
        </div>
    </div>

    <!-- Contenu principal -->
    <div class="main-content">
        <div class="container">
            <h2>Mon chat, tu veux bien être ma Valentine ? ❤️</h2>
            <div id="typewriter"></div>
            <div class="buttons">
                <button class="yes" onclick="showLove()">Oui</button>
                <button class="no" onclick="moveButton(this)">Non</button>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener("DOMContentLoaded", function () {
            let progress = document.querySelector('.progress');
            let loadingScreen = document.querySelector('.loading-screen');
            let mainContent = document.querySelector('.main-content');

            let width = 0;
            let interval = setInterval(() => {
                width += 1;
                progress.style.width = width + "%";

                if (width >= 100) {
                    clearInterval(interval);
                    setTimeout(() => {
                        loadingScreen.style.opacity = "0";
                        setTimeout(() => {
                            loadingScreen.style.display = "none";
                            mainContent.style.opacity = "1";
                            mainContent.style.pointerEvents = "auto";
                            typeWriter();
                        }, 1000);
                    }, 500);
                }
            }, 30); // Animation fluide de la barre de chargement
        });

        function typeWriter() {
            const text = "T'es la personne la plus importante de ma vie. Je t'aime plus que tout mon bébé ! ❤️";
            let index = 0;
            function write() {
                if (index < text.length) {
                    document.getElementById('typewriter').innerHTML += text.charAt(index);
                    index++;
                    setTimeout(write, 100);
                }
            }
            write();
        }

        function showLove() {
            alert("YOUHOUUUUU !!! Bebou t'es le plus beau cadeau que la vie m'ait donné, mon bonheur quotidien, ma plus belle histoire NHABEEEEK mon chatooon ❤️❤️❤️❤️❤️❤️❤️❤️");
        }

        function moveButton(button) {
            let x = Math.random() * (window.innerWidth - button.offsetWidth - 50);
            let y = Math.random() * (window.innerHeight - button.offsetHeight - 50);
            button.style.transform = `translate(${x}px, ${y}px)`;
        }
    </script>
</body>
</html>
