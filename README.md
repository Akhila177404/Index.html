<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        .age-calculator {
            width: 300px;
            margin: 40px auto;
            background-color: #f0f0f0;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        label {
            display: block;
            margin-bottom: 10px;
        }

        input[type="date"] {
            width: 100%;
            height: 30px;
            margin-bottom: 20px;
            padding: 10px;
            border: 1px solid #ccc;
        }

        button {
            width: 100%;
            height: 30px;
            background-color: #4CAF50;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #3e8e41;
        }

        #result {
            font-size: 24px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="age-calculator">
        <h1>Age Calculator</h1>
        <form>
            <label for="birth-date">Birth Date:</label>
            <input type="date" id="birth-date" required>
            <button id="calculate-btn">Calculate Age</button>
        </form>
        <p id="result"></p>
    </div>

    <script>
        const birthDateInput = document.getElementById('birth-date');
        const calculateButton = document.getElementById('calculate-btn');
        const resultElement = document.getElementById('result');

        calculateButton.addEventListener('click', (e) => {
            e.preventDefault();
            const birthDate = new Date(birthDateInput.value);
            const today = new Date();
            const age = calculateAge(birthDate, today);
            resultElement.textContent = `You are ${age.years} years, ${age.months} months, and ${age.days} days old.`;
        });

        function calculateAge(birthDate, today) {
            let years = today.getFullYear() - birthDate.getFullYear();
            let months = today.getMonth() - birthDate.getMonth();
            let days = today.getDate() - birthDate.getDate();

            if (months < 0) {
                years--;
                months += 12;
            }

            if (days < 0) {
                months--;
                days += getDaysInMonth(today.getFullYear(), today.getMonth() - 1);
            }

            return { years, months, days };
        }

        function getDaysInMonth(year, month) {
            return new Date(year, month + 1, 0).getDate();
        }
    </script>
</body>
</html>
