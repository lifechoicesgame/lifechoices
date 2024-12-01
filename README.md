<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Question Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }
        .question-container {
            background-color: white;
            padding: 20px;
            margin: 10px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .question {
            font-size: 20px;
            margin-bottom: 10px;
        }
        .options {
            display: flex;
            gap: 10px;
            justify-content: space-between;
        }
        .option-button {
            background-color: #4CAF50;
            border: none;
            padding: 10px 20px;
            color: white;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
        }
        .option-button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

<div id="questions-container"></div>

<script>
    const questions = [
        { question: "Do you prefer coffee or tea?", options: ["Coffee", "Tea"] },
        { question: "Do you like cats or dogs?", options: ["Cats", "Dogs"] },
        { question: "Do you prefer summer or winter?", options: ["Summer", "Winter"] },
        { question: "Would you rather read a book or watch a movie?", options: ["Read a book", "Watch a movie"] },
        { question: "Do you prefer chocolate or vanilla?", options: ["Chocolate", "Vanilla"] },
        { question: "Would you prefer to live in space or underwater?", options: ["Space", "Underwater"] },
        { question: "Do you like playing video games or board games?", options: ["Video games", "Board games"] },
        { question: "Do you prefer morning or night?", options: ["Morning", "Night"] },
        { question: "Would you rather be able to fly or be invisible?", options: ["Fly", "Invisible"] },
        { question: "Do you like going to the beach or hiking in the mountains?", options: ["Beach", "Hiking"] },
        { question: "Do you prefer city life or countryside life?", options: ["City life", "Countryside life"] },
        { question: "Would you rather be super strong or super smart?", options: ["Super strong", "Super smart"] },
        { question: "Do you like sweet or savory foods?", options: ["Sweet", "Savory"] },
        { question: "Would you prefer to be rich or famous?", options: ["Rich", "Famous"] }
    ];

    function generateRandomQuestions() {
        const randomQuestions = [];
        for (let i = 0; i < 10; i++) {
            const randomIndex = Math.floor(Math.random() * questions.length);
            randomQuestions.push(questions[randomIndex]);
            questions.splice(randomIndex, 1); // Remove the selected question to avoid duplicates
        }
        return randomQuestions;
    }

    function displayQuestions() {
        const randomQuestions = generateRandomQuestions();
        const container = document.getElementById("questions-container");
        randomQuestions.forEach((questionObj, index) => {
            const questionDiv = document.createElement("div");
            questionDiv.classList.add("question-container");
            questionDiv.innerHTML = `
                <div class="question">${questionObj.question}</div>
                <div class="options">
                    <button class="option-button" onclick="answerQuestion(${index}, 0)">${questionObj.options[0]}</button>
                    <button class="option-button" onclick="answerQuestion(${index}, 1)">${questionObj.options[1]}</button>
                </div>
            `;
            container.appendChild(questionDiv);
        });
    }

    function answerQuestion(questionIndex, optionIndex) {
        // You can handle answers here if you want to track them
        alert(`You chose: ${questions[questionIndex].options[optionIndex]}`);
    }

    // Load and display the random questions on page load
    window.onload = displayQuestions;
</script>

</body>
</html>
