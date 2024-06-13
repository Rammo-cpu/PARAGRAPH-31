<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Geheimcode</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

        body {
            font-family: 'Bebas Neue', cursive;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: black;
            margin: 0;
            color: white;
        }
        .container {
            text-align: center;
            background-color: #333;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        }
        input {
            padding: 10px;
            font-size: 16px;
            margin-bottom: 10px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            background-color: #555;
            color: white;
            border: none;
            border-radius: 4px;
        }
        button:hover {
            background-color: #777;
        }
        .hidden {
            display: none;
        }
        #geheimwort {
            color: red;
            font-size: 24px;
            font-weight: bold;
        }
        .heading {
            font-size: 48px;
            margin-bottom: 20px;
        }
        #loading {
            display: none;
            text-align: center;
        }
        #loading .dot {
            display: inline-block;
            width: 10px;
            height: 10px;
            margin: 0 5px;
            background-color: white;
            border-radius: 50%;
            animation: blink 1s infinite;
        }
        @keyframes blink {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0;
            }
        }
        #errorMessage {
            font-size: 32px;
            color: red;
            display: none;
        }
        #instagramLink {
            position: absolute;
            bottom: 20px;
            right: 20px;
            color: white;
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        #instagramLink img {
            width: 24px;
            height: 24px;
            margin-right: 8px;
        }
        #instagramLink:hover {
            color: #ddd;
        }
    </style>
</head>
<body>
    <div id="codePage" class="container">
        <h1 class="heading">PARAGRAPH 31</h1>
        <h2>Gib den Geheimcode ein</h2>
        <input type="text" id="codeInput" placeholder="Geheimcode">
        <button onclick="checkCode()">Absenden</button>
        <p id="errorMessage">ERROR: Falscher Code, bitte versuche es erneut.</p>
    </div>

    <div id="loading" class="container">
        <h1 class="heading">PARAGRAPH 31</h1>
        <p>Wird geladen</p>
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
    </div>

    <div id="wordPage" class="container hidden">
        <h1 class="heading">PARAGRAPH 31</h1>
        <h2>Dein Geheimwort ist:</h2>
        <p id="geheimwort"></p>
        <p>Schick dieses Geheimwort an den Instagram-Account (PARAGRAPH 31) und gewinne die Chance, Teil der Crew zu sein und um im 2 Teil mitzumachen.</p>
        <a id="instagramLink" href="https://www.instagram.com/paragraphes_31?igsh=MWM1dnRpczRzeWk1OQ==" target="_blank">
            <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
            Instagram
        </a>
    </div>

    <script>
        function checkCode() {
            const correctCode = "0689";
            const userInput = document.getElementById('codeInput').value;
            if (userInput === correctCode) {
                showLoading();
            } else {
                document.getElementById('errorMessage').style.display = 'block';
            }
        }

        function showLoading() {
            document.getElementById('codePage').classList.add('hidden');
            document.getElementById('loading').style.display = 'block';

            setTimeout(showWordPage, 2000); // 2 Sekunden Animation
        }

        function showWordPage() {
            const words = ["Verräter", "Angst", "Strap", "Bruder", "Niederlande", "Belgien", "Nrw", "Deutschland", "Neuss", "Kreuzberger", "Die Jungs", "Schlägerei", "Geld", "Haps", "Rücken"];
            const randomWord = words[Math.floor(Math.random() * words.length)];
            document.getElementById('geheimwort').innerText = randomWord;

            document.getElementById('loading').style.display = 'none';
            document.getElementById('wordPage').classList.remove('hidden');
        }
    </script>
</body>
</html>
