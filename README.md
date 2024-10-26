<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jumpscare Horror</title>
    <style>
        body {
            font-family: 'Courier New', Courier, monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #111;
            color: #f00;
            overflow: hidden;
            text-shadow: 2px 2px 8px black;
        }
        #message {
            font-size: 28px;
            text-align: center;
            cursor: pointer;
            color: #f00;
            transition: color 0.5s ease;
        }
        #message:hover {
            color: #a00;
        }
        #jumpscare {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: black url('https://i.imgur.com/your-scary-image.jpg') no-repeat center center;
            background-size: cover;
            z-index: 9999;
            transition: opacity 0.1s ease-in-out;
            opacity: 0;
        }
    </style>
</head>
<body>

<div id="message">Klik di sini jika kamu berani...</div>
<div id="jumpscare"></div>

<!-- Suara scream untuk jumpscare -->
<audio id="scream" src="https://www.mywebsite.com/scream-sound.mp3"></audio>
<!-- Suara latar menyeramkan -->
<audio id="background-sound" src="https://www.mywebsite.com/creepy-background-music.mp3" loop autoplay></audio>

<script>
    const message = document.getElementById("message");
    const jumpscare = document.getElementById("jumpscare");
    const scream = document.getElementById("scream");
    const backgroundSound = document.getElementById("background-sound");

    message.addEventListener("click", () => {
        jumpscare.style.display = "block";
        setTimeout(() => { jumpscare.style.opacity = 1; }, 50);
        scream.play();
        backgroundSound.pause();
        setTimeout(() => {
            jumpscare.style.opacity = 0;
            setTimeout(() => { jumpscare.style.display = "none"; }, 500);
            backgroundSound.play();
        }, 4000); // Durasi jumpscare selama 4 detik
    });
</script>

</body>
</html>
