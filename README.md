# my-game
 <!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>لعبة النقر السريع</title>

<style>
body {
  font-family: Arial;
  text-align: center;
  background: #f2f2f2;
}

#box {
  width: 80px;
  height: 80px;
  background: red;
  position: absolute;
  display: none;
  cursor: pointer;
}
</style>
</head>

<body>

<h1>🎮 العب فورًا</h1>
<p id="score">النقاط: 0</p>
<button onclick="startGame()">ابدأ اللعبة</button>

<div id="box"></div>

<script>
let score = 0;
let speed = 1000;
let box = document.getElementById("box");

function startGame() {
  score = 0;
  speed = 1000;
  document.getElementById("score").innerText = "النقاط: 0";
  showBox();
}

function showBox() {
  let x = Math.random() * (window.innerWidth - 100);
  let y = Math.random() * (window.innerHeight - 100);

  box.style.left = x + "px";
  box.style.top = y + "px";
  box.style.display = "block";

  setTimeout(() => {
    box.style.display = "none";
    speed -= 50;
    if (speed < 300) speed = 300;
    showBox();
  }, speed);
}

box.onclick = function () {
  score++;
  document.getElementById("score").innerText = "النقاط: " + score;
};
</script>

</body>
</html>
