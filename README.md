
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
            height: 80vh;
            margin: 0;
            font-family: 'Poppins', sans-serif;
            text-align: center;
            overflow: hidden;
            flex-direction: column;
            position: relative;
            background: #ffe6f2; /* Fond rose pastel doux */
        }

        /* Écran de chargement */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #ff1493; /* Rose vif */
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

        /* Masquer la page au début */
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
        .carousel img:nth-child(5) { animation-delay: 0s; }
        .carousel img:nth-child(6) { animation-delay: 4s; }
        .carousel img:nth-child(7) { animation-delay: 8s; }
        .carousel img:nth-child(8) { animation-delay: 12s; }
        

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
            backdrop-filter: blur(2px);
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

        /* Animation de fleurs */
        .flower {
            position: absolute;
            width: 50px;
            height: 50px;
            animation: fall 4s linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }
        .letter-container {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
}

.envelope {
    width: 120px;
    height: 100px;
    background: #ff1493;
    position: relative;
    border-radius: 10px;
    cursor: pointer;
    transition: transform 0.5s;
}

.envelope .flap {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 50%;
    background: #ff66b2;
    border-radius: 10px 10px 0 0;
    transform-origin: top;
    transition: transform 0.5s ease-in-out;
}

.letter {
    width: 100px;
    height: 80px;
    background: white;
    position: absolute;
    top: 0;
    opacity: 0;
    padding: 10px;
    border-radius: 5px;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
    transition: opacity 0.5s, transform 0.5s;
}

.open-letter-btn {
    margin-top: 15px;
    padding: 5px 10px;
    font-size: 25px;
    border: none;
    background-color: #ff1493;
    color: white;
    border-radius: 20px;
    cursor: pointer;
    transition: 0.3s;
}

.open-letter-btn:hover {
    background-color: #e60073;
}

/* Animation quand la lettre s'ouvre */
.letter.open {
    opacity: 1;
    transform: translateY(20px);
}

.envelope.open .flap {
    transform: rotateX(180deg);
}

/* Ajustements pour les tablettes et petits écrans */
@media screen and (max-width: 1024px) {
    .container {
        width: 80%;
        padding: 20px;
    }

    .carousel img {
        width: 95vw;
        height: auto;
        max-height: 80vh;
    }

    button {
        padding: 12px 24px;
        font-size: 16px;
    }
}

/* Ajustements pour les mobiles */
@media screen and (max-width: 768px) {
    body {
        flex-direction: column;
        align-items: center;
        text-align: center;
        height: auto;
        padding: 20px;
    }

    .container {
        width: 90%;
        padding: 15px;
    }

    .carousel img {
        width: 100%;
        height: auto;
        max-height: 70vh;
        border-radius: 15px;
    }

    .buttons {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    button {
        width: 80%;
        font-size: 16px;
    }

    .no {
        position: relative;
    }

    .letter-container {
        margin-top: 30px;
    }
}

/* Pour éviter le débordement sur les très petits écrans */
@media screen and (max-width: 480px) {
    h2 {
        font-size: 20px;
    }

    .carousel img {
        max-height: 60vh;
    }

    .container {
        width: 95%;
    }

    button {
        font-size: 14px;
        padding: 10px 20px;
    }
}
/* Correction du flou sur Safari (Mac & iPhone) */
@supports (-webkit-backdrop-filter: none) {
    .container {
        background: rgba(255, 255, 255, 0.8);
        -webkit-backdrop-filter: blur(10px);
        backdrop-filter: blur(10px);
    }
}

/* Éviter les bugs de scaling sur les écrans Retina */
img {
    image-rendering: -webkit-optimize-contrast;
}

/* Fix du bouton "Non" qui bouge trop vite sur Mac */
button.no {
    transition: transform 0.3s ease-in-out, left 0.3s ease-in-out, top 0.3s ease-in-out;
}

    </style>
</head>
<body>
    <!-- Écran de chargement -->
    <div class="loading-screen">
        <div class="loading-text">Chargement en cours...</div>
        <div class="progress-bar">
            <div class="progress"></div>
        </div>
    </div>

   

        <div class="carousel">
            <img src="photo1.jpg.jpg" alt="Photo 1">
            <img src="photo2.jpg.jpg" alt="Photo 2">
            <img src="photo3.jpg.jpg" alt="Photo 3">
            <img src="photo4.jpg.jpg" alt="Photo 4">
            <img src="photo5.jpg.jpg" alt="Photo 1">
            <img src="photo6.jpg.jpg" alt="Photo 2">
            <img src="photo7.jpg.jpg" alt="Photo 3">
            <img src="photo8.jpg.jpg" alt="Photo 4">
        </div>

        <div class="container">
            <h2>Man chat, tu veux bien être ma Valentine ? ❤️</h2>
            <div id="typewriter"></div>
            <div class="buttons">
                <button class="yes" onclick="showLove()">Oui</button>
                <button class="no" onclick="moveButton(this)">Non</button>
            </div>
        </div>
       <div class="letter-container">
    <div class="envelope" onclick="openLetter()">
        <div class="flap"></div>
    </div>
    <div class="letter">
        <p>Mon amour, je t'aime ❤️</p>
    </div>
</div>
<button class="open-letter-btn" onclick="openLetter()"> ❤️</button>

        
    </div>

    <script>
      document.addEventListener("DOMContentLoaded", function () {
        const text = "T'es la personne la plus importante de ma vie. Je t'aime plus que tout mon bébé ! ❤️";
        let index = 0;
        let typewriterElement = document.getElementById('typewriter');
        
        function typeWriter() {
            if (index === 0) typewriterElement.innerHTML = ""; // Réinitialiser le texte
            
            if (index < text.length) {
                typewriterElement.innerHTML += text.charAt(index);
                index++;
                setTimeout(typeWriter, 100);
            }
        }

        // Démarrer l'effet une fois que la page est chargée
        typeWriter();
    });
        // Barre de chargement
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
                }, 1000);
            }, 3000);
        };

        // Animation de fleurs
        function showLove() {
            for (let i = 0; i < 30; i++) {
                let flower = document.createElement("div");
                flower.className = "flower";
                flower.style.left = Math.random() * 100 + "vw";
                flower.style.animationDuration = Math.random() * 2 + 3 + "s";
                flower.innerHTML = "🌸";
                document.body.appendChild(flower);
                setTimeout(() => { flower.remove(); }, 4000);
            }
            alert("Bebou, NHABEEEEK ❤️");
        }

        function moveButton(button) {
            button.style.left = `${Math.random() * 200}px`;
            button.style.top = `${Math.random() * 100}px`;
        }
        function openLetter() {
    let envelope = document.querySelector(".envelope");
    let letter = document.querySelector(".letter");

    console.log(envelope, letter); // Vérifie si les éléments existent

    if (envelope && letter) {
        envelope.classList.add("open");
        letter.classList.add("open");
    } else {
        console.error("L'enveloppe ou la lettre n'a pas été trouvée !");
    }
}
    </script>
</body>
</html>
