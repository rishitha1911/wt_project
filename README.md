# wt_project
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f3f3f3;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: #222;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0px 6px 15px rgba(0,0,0,0.3);
      width: 300px;
    }
    #display {
      width: 100%;
      height: 60px;
      background: #111;
      color: #fff;
      text-align: right;
      font-size: 28px;
      padding: 10px;
      border-radius: 10px;
      border: none;
      margin-bottom: 15px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      height: 60px;
      font-size: 20px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      opacity: 0.8;
    }
    .number {
      background: #333;
      color: #fff;
    }
    .operator {
      background: #f39c12;
      color: #fff;
    }
    .equal {
      background: #27ae60;
      color: #fff;
      grid-column: span 2;
    }
    .clear {
      background: #e74c3c;
      color: #fff;
    }
    .backspace {
      background: #3498db;
      color: #fff;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">C</button>
      <button class="backspace" onclick="backspace()">⌫</button>
      <button class="operator" onclick="appendValue('/')">÷</button>
      <button class="operator" onclick="appendValue('*')">×</button>
      
      <button class="number" onclick="appendValue('7')">7</button>
      <button class="number" onclick="appendValue('8')">8</button>
      <button class="number" onclick="appendValue('9')">9</button>
      <button class="operator" onclick="appendValue('-')">-</button>
      
      <button class="number" onclick="appendValue('4')">4</button>
      <button class="number" onclick="appendValue('5')">5</button>
      <button class="number" onclick="appendValue('6')">6</button>
      <button class="operator" onclick="appendValue('+')">+</button>
      
      <button class="number" onclick="appendValue('1')">1</button>
      <button class="number" onclick="appendValue('2')">2</button>
      <button class="number" onclick="appendValue('3')">3</button>
      <button class="equal" onclick="calculate()">=</button>
      
      <button class="number" onclick="appendValue('0')">0</button>
      <button class="number" onclick="appendValue('.')">.</button>
    </div>
  </div>

  <script>
    let display = document.getElementById("display");

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = "";
    }

    function backspace() {
      display.value = display.value.slice(0, -1);
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>
  </body>
  </html>
