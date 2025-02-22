<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }

        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
        }

        .display {
            width: 220px;
            height: 50px;
            font-size: 24px;
            text-align: right;
            padding: 10px;
            margin-bottom: 20px;
            border: 2px solid #ccc;
            border-radius: 5px;
            background-color: #f8f8f8;
        }

        .button-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }

        .button {
            width: 50px;
            height: 50px;
            font-size: 18px;
            background-color: #f0f0f0;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .button:hover {
            background-color: #e0e0e0;
        }

        .button:active {
            background-color: #ccc;
        }

        .button-equal {
            background-color: #4CAF50;
            color: white;
        }

        .button-clear {
            background-color: #FF6347;
            color: white;
        }
    </style>
</head>
<body>

    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        
        <div class="button-row">
            <button class="button" onclick="appendToDisplay('7')">7</button>
            <button class="button" onclick="appendToDisplay('8')">8</button>
            <button class="button" onclick="appendToDisplay('9')">9</button>
            <button class="button" onclick="appendToDisplay('/')">/</button>
        </div>

        <div class="button-row">
            <button class="button" onclick="appendToDisplay('4')">4</button>
            <button class="button" onclick="appendToDisplay('5')">5</button>
            <button class="button" onclick="appendToDisplay('6')">6</button>
            <button class="button" onclick="appendToDisplay('*')">*</button>
        </div>

        <div class="button-row">
            <button class="button" onclick="appendToDisplay('1')">1</button>
            <button class="button" onclick="appendToDisplay('2')">2</button>
            <button class="button" onclick="appendToDisplay('3')">3</button>
            <button class="button" onclick="appendToDisplay('-')">-</button>
        </div>

        <div class="button-row">
            <button class="button" onclick="appendToDisplay('0')">0</button>
            <button class="button" onclick="appendToDisplay('.')">.</button>
            <button class="button button-equal" onclick="calculateResult()">=</button>
            <button class="button" onclick="appendToDisplay('+')">+</button>
        </div>

        <div class="button-row">
            <button class="button button-clear" onclick="clearDisplay()">C</button>
        </div>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculateResult() {
            const display = document.getElementById('display');
            try {
                display.value = eval(display.value); // Use eval to calculate the result
            } catch (e) {
                display.value = "Error"; // If there's an error in calculation
            }
        }
    </script>

</body>
</html>
