<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday 🎉</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    text-align: center;
    background: linear-gradient(270deg, #ff9a9e, #fad0c4, #fbc2eb);
    background-size: 600% 600%;
    animation: gradientBG 10s ease infinite;
    color: white;
    overflow: hidden;
}

/* Background animation */
@keyframes gradientBG {
    0% { background-position: 0% }
    50% { background-position: 100% }
    100% { background-position: 0% }
}

/* Title animation */
h1 {
    margin-top: 50px;
    font-size: 3em;
    animation: glow 2s ease-in-out infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px #fff; }
    to { text-shadow: 0 0 30px #ff4da6; }
}

/* Message */
p {
    font-size: 1.5em;
}

/* Button */
button {
    padding: 12px 25px;
    font-size: 1.2em;
    background: white;
    color: #ff4da6;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: transform 0.3s;
}

button:hover {
    transform: scale(1.2);
}

/* Photo */
img {
    width: 200px;
    border-radius: 50%;
    margin-top: 20px;
    border: 5px solid white;
    animation: float 3s ease-in-out infinite;
}

@keyframes float {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

/* Balloons */
.balloon {
    position: absolute;
    bottom: -150px;
    width: 60px;
    height: 80px;
    border-radius: 50%;
    animation: rise 10s linear infinite;
}

@keyframes rise {
    from { transform: translateY(0); }
    to { transform: translateY(-120vh); }
}

/* Confetti */
.confetti {
    position: absolute;
    width: 10px;
    height: 10px;
    animation: fall 3s linear forwards;
}

@keyframes fall {
    to {
        transform: translateY(100vh) rotate(360deg);
        opacity: 0;
    }
}
</style>

</head>

<body>

<h1>🎂 Happy Birthday!</h1>

<p id="message">Wishing you a day full of joy and happiness 💖</p>

<!-- Replace this with your own photo -->
<img src="myphoto.jpg" alt="My Photo">

<br><br>

<button onclick="surprise()">Click for Surprise 🎁</button>

<!-- Balloons -->
<div class="balloon" style="left:10%; background:red; animation-duration:8s;"></div>
<div class="balloon" style="left:30%; background:blue; animation-duration:10s;"></div>
<div class="balloon" style="left:50%; background:yellow; animation-duration:9s;"></div>
<div class="balloon" style="left:70%; background:green; animation-duration:11s;"></div>
<div class="balloon" style="left:90%; background:purple; animation-duration:7s;"></div>

<script>
function surprise() {
    document.getElementById("message").innerText =
        "🎉 May all your dreams come true! 💕";

    createConfetti();
}

function createConfetti() {
    for (let i = 0; i < 80; i++) {
        let c = document.createElement("div");
        c.className = "confetti";
        c.style.left = Math.random() * 100 + "vw";
        c.style.backgroundColor =
            "hsl(" + Math.random() * 360 + ",100%,50%)";

        document.body.appendChild(c);

        setTimeout(() => c.remove(), 3000);
    }
}
</script>

</body>
</html>
