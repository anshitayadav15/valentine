<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine 💖</title>

<style>
body {
    margin: 0;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff4f9a, #ffc1d9);
    font-family: 'Comic Sans MS', cursive;
}

/* Card */
.card {
    background: #fff0f6;
    padding: 35px;
    border-radius: 25px;
    text-align: center;
    box-shadow: 0 25px 50px rgba(0,0,0,0.25);
    width: 90%;
    max-width: 350px;
    z-index: 2;
}

h1 {
    color: #e60073;
}

/* Buttons */
.buttons {
    margin-top: 30px;
    position: relative;
    height: 120px;
}

button {
    padding: 14px 30px;
    font-size: 18px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
}

#yes {
    background: #ff2f92;
    color: white;
}

#no {
    background: #ffd6e8;
    color: #e60073;
    position: fixed;
    left: 60%;
    top: 65%;
    z-index: 999;
}

/* Floating hearts */
.heart {
    position: fixed;
    bottom: -20px;
    font-size: 20px;
    animation: floatUp 6s linear infinite;
    color: rgba(255, 0, 102, 0.6);
}

@keyframes floatUp {
    from {
        transform: translateY(0);
        opacity: 1;
    }
    to {
        transform: translateY(-120vh);
        opacity: 0;
    }
}

/* Confetti */
.confetti {
    position: fixed;
    width: 10px;
    height: 10px;
    background-color: red;
    animation: fall 3s linear forwards;
}

@keyframes fall {
    to {
        transform: translateY(120vh) rotate(720deg);
        opacity: 0;
    }
}
</style>
</head>

<body>

<!-- Background Music -->
<audio autoplay loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div class="card">
    <h1>Siddhartha Paul,<br>will you be my Valentine? 💘</h1>

    <div class="buttons">
        <button id="yes">YES 💖</button>
    </div>
</div>

<button id="no">NO 🙈</button>

<script>
/* NO button escape logic */
const noBtn = document.getElementById("no");

function escapeNo() {
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 60);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}

["mouseover", "click", "touchstart"].forEach(event => {
    noBtn.addEventListener(event, escapeNo);
});

/* YES click logic with confetti */
document.getElementById("yes").addEventListener("click", () => {
    document.querySelector(".card").innerHTML = `
        <h1>YAAYYYY!💕🥰</h1>
        <p style="color:#e60073;font-size:20px;">
        Wuhuuu, thank you made me the happiest person. I'm so grateful for you! ❤️<br><br>
        Happy Valentine’s Day 💖<br><br>
        – Anshi 💕
        </p>
    `;
    launchConfetti();
});

/* Confetti generator */
function launchConfetti() {
    for (let i = 0; i < 120; i++) {
        const confetti = document.createElement("div");
        confetti.classList.add("confetti");
        confetti.style.left = Math.random() * window.innerWidth + "px";
        confetti.style.top = "-10px";
        confetti.style.backgroundColor = 
            ["#ff2f92", "#ffcc00", "#ff4f9a", "#e60073"][Math.floor(Math.random()*4)];
        confetti.style.transform = `rotate(${Math.random()*360}deg)`;
        confetti.style.animationDuration = Math.random() * 2 + 2 + "s";
        document.body.appendChild(confetti);

        setTimeout(() => confetti.remove(), 3000);
    }
}

/* Floating hearts */
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    heart.style.animationDuration = Math.random() * 3 + 4 + "s";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
}

setInterval(createHeart, 350);
</script>

</body>
</html>
