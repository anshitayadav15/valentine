index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine 💖</title>
<style>
body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    font-family: 'Comic Sans MS', cursive;
}

.card {
    background: #fff0f6;
    padding: 40px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 20px 40px rgba(0,0,0,0.2);
    width: 350px;
}

h1 {
    color: #e60073;
}

.buttons {
    margin-top: 30px;
    position: relative;
    height: 80px;
}

button {
    padding: 12px 25px;
    font-size: 18px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
}

#yes {
    background: #ff4d88;
    color: white;
}

#no {
    background: #ffd6e8;
    color: #e60073;
    position: absolute;
    left: 120px;
}

</style>
</head>
<body>

<div class="card">
    <h1>Siddhartha Paul,<br>will you be my Valentine? 💘</h1>

    <div class="buttons">
        <button id="yes">YES 💖</button>
        <button id="no">NO 🙈</button>
    </div>
</div>

<script>
const noBtn = document.getElementById("no");

noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * 200;
    const y = Math.random() * 60;
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

document.getElementById("yes").addEventListener("click", () => {
    document.querySelector(".card").innerHTML = `
        <h1>YAY!!! 💕</h1>
        <p style="color:#e60073;font-size:20px;">
        Wuhu, you just made me the happiest person ❤️<br><br>
        – Anshita 💖
        </p>
    `;
});
</script>

</body>
</html>
