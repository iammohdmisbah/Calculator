# Calculator
Creating a calculator using HTML, CSS, and JavaScript is a great project to enhance your front-end development skills. Here's an overview of how these technologies work together to build a functional and visually appealing calculator.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendOperator('%')">%</button>
            <button onclick="appendOperator('/')">÷</button>
            <button onclick="appendNumber('7')">7</button>
            <button onclick="appendNumber('8')">8</button>
            <button onclick="appendNumber('9')">9</button>
            <button onclick="appendOperator('*')">×</button>
            <button onclick="appendNumber('4')">4</button>
            <button onclick="appendNumber('5')">5</button>
            <button onclick="appendNumber('6')">6</button>
            <button onclick="appendOperator('-')">−</button>
            <button onclick="appendNumber('1')">1</button>
            <button onclick="appendNumber('2')">2</button>
            <button onclick="appendNumber('3')">3</button>
            <button onclick="appendOperator('+')">+</button>
            <button onclick="appendNumber('0')" class="zero">0</button>
            <button onclick="appendNumber('.')">.</button>
            <button onclick="calculateResult()">=</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
