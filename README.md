<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Life Choices</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin: 20px; }
        .question { font-size: 1.5em; margin: 20px; }
        .option { padding: 10px 20px; margin: 10px; background: #007BFF; color: white; border: none; cursor: pointer; }
        .option:hover { background: #0056b3; }
    </style>
</head>
<body>
    <h1>Life Choices</h1>
    <div class="question">What will you do today?</div>
    <button class="option" onclick="choiceMade('Go for a walk')">Go for a walk</button>
    <button class="option" onclick="choiceMade('Watch TV')">Watch TV</button>
    <script>
        function choiceMade(choice) {
            alert(`You chose to ${choice}!`);
            // Add more logic here for outcomes
        }
    </script>
</body>
</html>
