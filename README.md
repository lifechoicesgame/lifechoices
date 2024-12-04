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
            color: #333;
        }
        .question-container {
            background-color: white;
            padding: 50px;
            margin: 80px auto;
            width: 70%;
            border-radius: 10px;
            box-shadow: 0 2px 15px rgba(0,0,0,0.1);
            text-align: center;
            margin-bottom: 80px;
        }
        .question {
            font-size: 32px;
            margin-bottom: 60px;
        }
        .question-image {
            margin: 40px 0;
            max-width: 80%;
            height: auto;
        }
        .options {
            display: flex;
            justify-content: space-evenly;
            margin-top: 60px;
        }
        .option-button {
            background-color: white;
            color: black;
            border: 2px solid black;
            padding: 30px 60px;
            font-size: 24px;
            border-radius: 10px;
            cursor: pointer;
            width: 45%;
            transition: background-color 0.3s, color 0.3s;
        }
        .option-button:hover {
            background-color: black;
            color: white;
        }
    </style>
</head>
<body>

<div id="questions-container"></div>

<script>
    const questions = [
        { 
            question: "Do you prefer coffee or tea?", 
            options: ["Coffee", "Tea"], 
            image: "https://via.placeholder.com/600x400.png?text=Coffee+or+Tea" 
        },
        { 
            question: "Do you like cats or dogs?", 
            options: ["Cats", "Dogs"], 
            image: "https://via.placeholder.com/600x400.png?text=Cats+or+Dogs" 
        },
        { 
            question: "Do you prefer summer or winter?", 
            options: ["Summer", "Winter"], 
            image: "https://via.placeholder.com/600x400.png?text=Summer+or+Winter" 
        },
        { 
            question: "Would you rather read a book or watch a movie?", 
            options: ["Read a book", "Watch a movie"], 
            image: "https://via.placeholder.com/600x400.png?text=Book+or+Movie" 
        },
        { 
            question: "Do you prefer chocolate or vanilla?", 
            options: ["Chocolate", "Vanilla"], 
            image: "https://via.placeholder.com/600x400.png?text=Chocolate+or+Vanilla" 
        },
        { 
            question: "Would you prefer to live in space or underwater?", 
            options: ["Space", "Underwater"], 
            image: "https://via.placeholder.com/600x400.png?text=Space+or+Underwater" 
        },
        { 
            question: "Do you like playing video games or board games?", 
            options: ["Video games", "Board games"], 
            image: "https://via.placeholder.com/600x400.png?text=Video+or+Board+Games" 
        },
        { 
            question: "Do you prefer morning or night?", 
            options: ["Morning", "Night"], 
            image: "https://via.placeholder.com/600x400.png?text=Morning+or+Night" 
        },
        { 
            question: "Would you rather be able to fly or be invisible?", 
            options: ["Fly", "Invisible"], 
            image: "https://via.placeholder.com/600x400.png?text=Fly+or+Invisible" 
        },
        { 
            question: "Do you like going to the beach or hiking in the mountains?", 
            options: ["Beach", "Hiking"], 
            image: "https://via.placeholder.com/600x400.png?text=Beach+or+Hiking" 
        }
    ];

    function generateRandomQuestions() {
        const randomQuestions = [];
        for (let i = 0; i < 10; i++) {
            const randomIndex = Math.floor(Math.random() * questions.length);
            randomQuestions.push(questions[randomIndex]);
            questions.splice(randomIndex, 1);
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
                <img src="${questionObj.image}" alt="Question Image" class="question-image">
                <div class="options">
                    <button class="option-button" onclick="answerQuestion(${index}, 0)">${questionObj.options[0]}</button>
                    <button class="option-button" onclick="answerQuestion(${index}, 1)">${questionObj.options[1]}</button>
                </div>
            `;
            container.appendChild(questionDiv);
        });
    }

    function answerQuestion(questionIndex, optionIndex) {
        alert(`You chose: ${questions[questionIndex].options[optionIndex]}`);
    }

    window.onload = displayQuestions;
</script>

</body>
</html>

