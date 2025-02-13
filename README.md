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
            transition: width 3s linear;
        }

        .main-content {
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }

        /* Carrousel */
        .carousel {
            position: absolute;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .carousel img {
            width: 100vw;
            height: 100vh;
            object-fit: cover;
            object-position: center center;
            opacity: 0;
            position: absolute;
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

        /* Cadre blanc transparent */
        .container {
            background: rgba(255, 255, 255, 0.7);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
            position: relative;
            backdrop-filter: blur(8px);
            z-index: 1;
        }

        /* Texte défilant */
        #typewriter {
            font-size: 22px;
            color: #ff1493;
            font-weight: bold;
            white-space: nowrap;
            overflow: hidden;
            border-right: 2px solid #ff1493;
            display: inline-block;
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

        /* Pétales de rose */
        .petal {
            position: absolute;
            width: 15px;
            height: 15px;
            background-color: pink;
            opacity: 0.8;
            border-radius: 50%;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        /* Lumières scintillantes */
        .light {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: white;
            border-radius: 50%;
            box-shadow: 0 0 10px white;
            opacity: 0.7;
            animation: twinkle infinite alternate;
        }

        @keyframes twinkle {
            0% { opacity: 0.2; }
            100% { opacity: 1; }
        }

    </style>
</head>
<body>
    <div class="loading-screen">
        <div class="loading-text">Chargement en cours...</div>
        <div class="progress-bar">
            <div class="progress"></div>
        </div>
    </div>

    <div class="main-content">
        <audio autoplay loop>
            <source src="votre-musique.mp3" type="audio/mpeg">
            Votre navigateur ne supporte pas l'élément audio.
        </audio>

        <div class="carousel">
            <img src="photo1.jpg.jpg" alt="Photo 1">
            <img src="photo2.jpg.jpg" alt="Photo 2">
            <img src="photo3.jpg.jpg" alt="Photo 3">
            <img src="photo4.jpg.jpg" alt="Photo 4">
        </div>

        <div class="container">
            <h2>Man chat, tu veux bien être ma Valentine ? ❤️</h2>
            <div id="typewriter"></div>
            <div class="buttons">
                <button class="yes" onclick="showLove()">Oui</button>
                <button class="no" onclick="moveButton(this)">Non</button>
            </div>
        </div>
    </div>

    <script>
        const text = "T'es la personne la plus importante de ma vie. Je t'aime plus que tout mon bébé ! ❤️";
        let index = 0;
        function typeWriter() {
            if (index < text.length) {
                document.getElementById('typewriter').innerHTML += text.charAt(index);
                index++;
                setTimeout(typeWriter, 100);
            }
        }

        window.onload = function() {
            let progress = document.querySelector('.progress');
            let loadingScreen = document.querySelector('.loading-screen');
            let mainContent = document.querySelector('.main-content');

            progress.style.width = "100%";

            setTimeout(() => {
                loadingScreen.style.opacity = "0";
                setTimeout(() => {
                    loadingScreen.style.display = "none";
                    mainContent.style.opacity = "1";
                    typeWriter();

                    for (let i = 0; i < 50; i++) {
                        let petal = document.createElement('div');
                        petal.classList.add('petal');
                        petal.style.left = Math.random() * 100 + 'vw';
                        petal.style.animationDuration = (Math.random() * 5 + 5) + 's';
                        document.body.appendChild(petal);
                    }

                    for (let i = 0; i < 100; i++) {
                        let light = document.createElement('div');
                        light.classList.add('light');
                        light.style.left = Math.random() * 100 + 'vw';
                        light.style.top = Math.random() * 100 + 'vh';
                        light.style.animationDuration = (Math.random() * 2 + 1) + 's';
                        document.body.appendChild(light);
                    }

                }, 1000);
            }, 3000);
        };
    </script>
</body>
</html>
