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


# CSS

     body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.calculator {
    width: 350px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    overflow: hidden;
}

.display {
    background-color: #383741dc;
    color: #fff;
    text-align: right;
    padding: 20px;
    font-size: 2em;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background-color: #ccc;
}

button {
    background-color: #fff;
    border: none;
    font-size: 1.5em;
    padding: 20px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
}

button:hover {
    background-color: #f0f0f0;
}

button:active {
    background-color: #ddd;
}

button.zero {
    grid-column: span 2;
}

button:nth-child(4n) {
    background-color: #4699f9;
    color: #fff;
}

button:nth-child(4n):hover {
    background-color: #1a17e7;
}


# JavaScript
let display = document.getElementById('display');

function appendNumber(number) {
    if (display.innerText === '0') {
        display.innerText = number;
    } else {
        display.innerText += number;
    }
}

function appendOperator(operator) {
    const lastChar = display.innerText.slice(-1);
    if (!['+', '-', '*', '/', '%'].includes(lastChar)) {
        display.innerText += operator;
    }
}

function clearDisplay() {
    display.innerText = '0';
}

function deleteLast() {
    display.innerText = display.innerText.length > 1 ? display.innerText.slice(0, -1) : '0';
}

function calculateResult() {
    try {
        display.innerText = eval(display.innerText.replace('÷', '/').replace('×', '*'));
    } catch {
        display.innerText = 'Error';
    }
}
