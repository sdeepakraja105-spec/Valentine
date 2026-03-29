<!DOCTYPE html>
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

    background: linear-gradient(-45deg, #ff758c, #ff7eb3, #ff4d6d, #ff99ac);
    background-size: 400% 400%;
    animation: gradientBG 8s ease infinite;

    color: #fff0f5;
}

@keyframes gradientBG {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

.glass {
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(12px);
    box-shadow: 0 0 25px rgba(0,0,0,0.3);
}

#text {
    font-size: 24px;
    white-space: pre-line;
    color: #ffffff;
    text-shadow: 0 0 10px rgba(255, 105, 135, 0.8);
}

#yesBtn {
    box-shadow: 0 0 10px #00ff9d, 0 0 20px #00ff9d;
}

.heart {
    position: absolute;
    font-size: 20px;
    animation: float 5s linear infinite;
}

@keyframes float {
    0% { transform: translateY(100vh); opacity: 1; }
    100% { transform: translateY(-10vh); opacity: 0; }
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

// Typewriter
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

// No button move
noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * window.innerWidth - 100;
    const y = Math.random() * window.innerHeight - 50;
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

// YES CLICK (🔥 MAIN MAGIC)
yesBtn.addEventListener("click", () => {
    document.body.innerHTML = `
        <style>
            body {
                margin: 0;
                height: 100vh;
                overflow: hidden;
                display: flex;
                justify-content: center;
                align-items: center;
                text-align: center;
                font-family: cursive;
                color: white;

                background: linear-gradient(-45deg, #ff758c, #ff7eb3, #ff4d6d, #ff99ac);
                background-size: 400% 400%;
                animation: gradientBG 8s ease infinite;
            }

            @keyframes gradientBG {
                0% { background-position: 0% 50%; }
                50% { background-position: 100% 50%; }
                100% { background-position: 0% 50%; }
            }

            .content {
                opacity: 0;
                transition: 1s;
            }

            .show {
                opacity: 1;
            }

            img {
                width: 230px;
                border-radius: 20px;
                margin-top: 20px;
                box-shadow: 0 0 20px pink;
            }

            .heart {
                position: absolute;
                font-size: 20px;
                animation: explode 1s ease-out forwards;
            }

            @keyframes explode {
                0% { transform: scale(0); opacity: 1; }
                100% { transform: scale(1.5) translate(var(--x), var(--y)); opacity: 0; }
            }
        </style>

        <div class="content" id="content">
            <h1>Yayyyy Varshini!!! 💖😍</h1>
            <p>You just made me the happiest person ever 🥹</p>
            <h2>I love you ❤️</h2>
            <img src="Snapchat-1023048052.jpg">
        </div>
    `;

    // 💥 Heart explosion
    for (let i = 0; i < 40; i++) {
        let heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerText = "❤️";

        let x = (Math.random() - 0.5) * 600 + "px";
        let y = (Math.random() - 0.5) * 600 + "px";

        heart.style.setProperty('--x', x);
        heart.style.setProperty('--y', y);

        heart.style.left = "50%";
        heart.style.top = "50%";

        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 1000);
    }

    // Show content after explosion
    setTimeout(() => {
        document.getElementById("content").classList.add("show");
    }, 1000);
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