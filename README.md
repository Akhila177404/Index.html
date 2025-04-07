<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Age Calculator</h1>
        <div class="form">
            <label for="dob">Date of Birth:</label>
            <input type="date" id="dob">
            <button onclick="calculateAge()">Calculate Age</button>
        </div>
        <div class="result">
            <p>Your age is:</p>
            <p id="ageResult">0 years, 0 months, 0 days</p>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
