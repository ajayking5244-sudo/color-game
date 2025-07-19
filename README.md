# color-game<!DOCTYPE html>
<html>
<head>
  <title>Color Production Game</title>
  <style>
    body { font-family: Arial; text-align: center; margin-top: 100px; }
    .hidden { display: none; }
  </style>
</head>
<body>
  <h1>🎨 Color Production Game 🎮</h1>
  <div id="pinScreen">
    <p>Enter PIN to start:</p>
    <input type="password" id="pinInput" />
    <button onclick="checkPIN()">Start</button>
  </div>

  <div id="gameScreen" class="hidden">
    <p>Click the button to produce a color!</p>
    <button onclick="generateColor()">🎨 Generate</button>
    <div id="colorBox" style="width:100px;height:100px;margin:20px auto;"></div>
  </div>

  <script>
    const correctPIN = "1234"; // PIN yahi hai
    function checkPIN() {
      const pin = document.getElementById("pinInput").value;
      if (pin === correctPIN) {
        document.getElementById("pinScreen").style.display = "none";
        document.getElementById("gameScreen").style.display = "block";
      } else {
        alert("❌ Wrong PIN!");
      }
    }

    function generateColor() {
      const color = "#" + Math.floor(Math.random()*16777215).toString(16);
      document.getElementById("colorBox").style.background = color;
    }
  </script>
</body>
</html>
