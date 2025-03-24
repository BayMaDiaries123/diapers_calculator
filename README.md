<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diaper Calculator - BayMa Diaries</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f9f9f9;
            text-align: center;
            padding: 20px;
        }
        .calculator-container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: auto;
        }
        input, select, button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            border: 1px solid #ddd;
        }
        button {
            background-color: #ff8c8c;
            color: white;
            font-size: 16px;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #ff6b6b;
        }
        .result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="calculator-container">
        <h2>Diaper Calculator</h2>
        <label for="age">Select Baby's Age:</label>
        <select id="age">
            <option value="12">0-3 months</option>
            <option value="10">3-6 months</option>
            <option value="8">6-12 months</option>
            <option value="6">12-24 months</option>
            <option value="4">2+ years</option>
        </select>

        <label for="weight">Enter Baby's Weight (kg):</label>
        <input type="number" id="weight" placeholder="Enter weight in kg">

        <button onclick="calculateDiapers()">Calculate</button>

        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateDiapers() {
            var age = document.getElementById("age").value;
            var weight = document.getElementById("weight").value;

            if (weight === "" || weight <= 0) {
                alert("Please enter a valid baby weight.");
                return;
            }

            var diapersPerDay = parseInt(age);
            var monthlyDiapers = diapersPerDay * 30;

            var diaperSize = "Newborn";
            if (weight > 5) diaperSize = "Small";
            if (weight > 8) diaperSize = "Medium";
            if (weight > 12) diaperSize = "Large";
            if (weight > 15) diaperSize = "Extra Large";

            document.getElementById("result").innerHTML =
                "Estimated Diapers per Month: <b>" + monthlyDiapers + "</b><br>" +
                "Recommended Diaper Size: <b>" + diaperSize + "</b><br><br>" +
                "<button onclick='subscribeNow()'>Subscribe Now</button>";
        }

        function subscribeNow() {
            alert("Redirecting to BayMa Diaries Subscription Page...");
            window.location.href = "https://yourwebsite.com/subscribe"; // Replace with actual link
        }
    </script>

</body>
</html>
