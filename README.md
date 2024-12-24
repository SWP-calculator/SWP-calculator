<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WPS Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 0;
        }
        .container {
            max-width: 400px;
            margin: auto;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        input, button {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            font-size: 16px;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>WPS Calculator</h1>
        <label for="words">Number of Words:</label>
        <input type="number" id="words" placeholder="Enter the number of words" required>
        
        <label for="time">Time Taken (in seconds):</label>
        <input type="number" id="time" placeholder="Enter the time in seconds" required>
        
        <button onclick="calculateWPS()">Calculate WPS</button>
        
        <div id="result" class="result"></div>
    </div>

    <script>
        function calculateWPS() {
            const words = document.getElementById('words').value;
            const time = document.getElementById('time').value;
            
            if (words <= 0 || time <= 0) {
                document.getElementById('result').textContent = "Please enter positive numbers for both fields.";
                return;
            }

            const wps = words / time;
            document.getElementById('result').textContent = `Words Per Second: ${wps.toFixed(2)}`;
        }
    </script>
</body>
</html>
