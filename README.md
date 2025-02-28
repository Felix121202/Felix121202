<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>How are u doing, Pipian</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #ffdde1;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            animation: fadeIn 2s ease-in-out;
        }
        h1 {
            color: #ff4b5c;
        }
        p {
            color: #444;
        }
        button {
            background: #ff4b5c;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
            transition: transform 0.2s ease-in-out;
        }
        button:hover {
            background: #e63b4a;
            transform: scale(1.1);
        }
        .popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            display: none;
            text-align: center;
        }
        .character {
            width: 100px;
            height: 100px;
            background: orange;
            border-radius: 50%;
            position: relative;
            animation: bounce 1s infinite alternate;
        }
        .eyes {
            position: absolute;
            top: 30%;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            justify-content: space-between;
            width: 60%;
        }
        .eye {
            width: 20px;
            height: 25px;
            background: black;
            border-radius: 50%;
            position: relative;
        }
        .eye::after {
            content: '';
            position: absolute;
            top: 30%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 10px;
            height: 10px;
            background: white;
            border-radius: 50%;
        }
        .mouth {
            position: absolute;
            bottom: 20%;
            left: 50%;
            transform: translateX(-50%);
            width: 30px;
            height: 15px;
            background: black;
            border-radius: 50%;
        }
        .mouth::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 25px;
            height: 10px;
            background: orange;
            border-radius: 50%;
        }
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-10px); }
        }
        #special-image {
            display: none;
            width: 100%;
            max-width: 300px;
            border-radius: 10px;
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>How are u doing Pipian? </h1>
        <p id="message">Hi Pipian. Do u still feel tired?</p>
        <button onclick="showPopup()">Click here 🤏</button>
    </div>

    <div class="popup" id="popup">
        <div class="character" id="character">
            <div class="eyes">
                <div class="eye"></div>
                <div class="eye"></div>
            </div>
            <div class="mouth"></div>
        </div>
        <p id="popup-message">I'm really sorry! 🥺</p>
        <button onclick="changePopupMessage()" id="nextButton">Next</button>
        <button onclick="showSpecialImage()" id="specialButton" style="display:none;">See Something Special</button>
        <button onclick="hidePopup()" id="closeButton">Close</button>
        <img id="special-image" src="foto bunga.jpeg" alt="Special Image">
    </div>

    <script>
        let messages = [
            "I'm really sorry! 🥺",
            "I promise to be less spamming 😢",
            "and annoying",
            "Hope u can feel better really soon 😊"
        ];
        let msgIndex = 0;

        function showPopup() {
            document.getElementById("popup").style.display = "block";
        }

        function hidePopup() {
            document.getElementById("popup").style.display = "none";
        }

        function changePopupMessage() {
            msgIndex++;
            if (msgIndex < messages.length) {
                document.getElementById("popup-message").innerHTML = messages[msgIndex];
            } else {
                document.getElementById("popup-message").innerHTML = "Here something for you";
                document.getElementById("nextButton").style.display = "none";
                document.getElementById("specialButton").style.display = "inline-block";
                document.getElementById("closeButton").style.display = "none";
                document.getElementById("character").style.display = "none";
            }
        }

        function showSpecialImage() {
            document.getElementById("special-image").style.display = "block";
            document.getElementById("specialButton").style.display = "none";
        }
    </script>
</body>
</html>
