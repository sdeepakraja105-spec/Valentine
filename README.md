<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Varshini 💖</title>

<!-- Bootstrap -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">

<style>
body {
    margin: 0;
    padding: 0;
    font-family: monospace;
    overflow: hidden;

    /* Romantic gradient */
    background: linear-gradient(-45deg, #ff758c, #ff7eb3, #ff4d6d, #ff99ac);
    background-size: 400% 400%;
    animation: gradientBG 8s ease infinite;

    color: #fff0f5;
}

/* Background animation */
@keyframes gradientBG {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

/* Glass card */
.glass {
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(12px);
    box-shadow: 0 0 25px rgba(0,0,0,0.3);
}

/* Text styling */
#text {
    font-size: 24px;
    white-space: pre-line;
    color: #ffffff;
    text-shadow: 0 0 10px rgba(255, 105, 135, 0.8);
}

/* Yes button glow */
#yesBtn {
    box-shadow: 0 0 10px #00ff9d, 0 0 20px #00ff9d;
}

/* Floating hearts */
.heart {
    position: absolute;
    font-size: 20px;
    animation: float 5s linear infinite;
}

@keyframes float {
    0% {
        transform: translateY(100vh);
        opacity: 1;
    }
    100% {
        transform: translateY(-10vh);
        opacity: 0;
    }
}
</style>

</head>

<body>

<div class="container d-flex flex-column justify-content-center align-items-center vh-100 text-center">

    <div class="glass p-4 rounded-4">
        <h1 id="text" class="mb-4"></h1>

        <div id="buttons" class="d-none">
            <button id="yesBtn" class="btn btn-success btn-lg me-2">Yes 😍</button>
            <button id="noBtn" class="btn btn-danger btn-lg position-absolute">No 😅</button>
        </div>
    </div>

</div>

<script>
const message = "Hey Varshini... I have something to tell you 💖\n\nWill you be my Valentine? 🥺";
let i = 0;

const textElement = document.getElementById("text");
const buttons = document.getElementById("buttons");
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");

// Typewriter effect
function typeEffect() {
    if (i < message.length) {
        textElement.innerHTML += message.charAt(i);
        i++;
        setTimeout(typeEffect, 50);
    } else {
        buttons.classList.remove("d-none");
    }
}

typeEffect();

// Move "No" button
noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * window.innerWidth - 100;
    const y = Math.random() * window.innerHeight - 50;

    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

// Yes button click
yesBtn.addEventListener("click", () => {
    document.body.innerHTML = `
        <div class="d-flex flex-column justify-content-center align-items-center vh-100 text-center text-white">
            <h1 style="text-shadow:0 0 15px pink;">Yayyyy Varshini!!! 💖😍</h1>
            <p>You just made me the happiest person ever 🥹</p>
            <h2>I love you ❤️</h2>
        </div>
    `;
});

// Floating hearts
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerText = "❤️";

    heart.style.left = Math.random() * window.innerWidth + "px";
    heart.style.fontSize = (Math.random() * 20 + 10) + "px";

    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 5000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>