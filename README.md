<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Brain War</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f3f3f3;
      margin: 0;
      padding: 0;
    }
    .game-container {
      max-width: 600px;
      margin: 50px auto;
      padding: 20px;
      background: #ffffff;
      border: 2px solid #ccc;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }
    .question {
      font-size: 24px;
      margin-bottom: 20px;
    }
    .input-field {
      margin: 10px 0;
    }
    .input-field input {
      font-size: 18px;
      padding: 10px;
      width: 80%;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .submit-btn {
      padding: 10px 20px;
      font-size: 18px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .submit-btn:hover {
      background-color: #218838;
    }
    .feedback {
      font-size: 20px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <div class="game-container">
    <div class="question" id="question">Loading...</div>
    <div class="input-field">
      <input type="text" id="answer" placeholder="Enter your answer here">
    </div>
    <button class="submit-btn" onclick="checkAnswer()">Submit</button>
    <div class="feedback" id="feedback"></div>
  </div>

  <script>
    // Array of questions and answers
    const questions = [
      { question: "What is 5 + 3?", answer: "8" },
      { question: "How many sides does a hexagon have?", answer: "6" },
      { question: "What is the capital of France?", answer: "Paris" },
      { question: "What comes after 'E' in the English alphabet?", answer: "F" },
      { question: "How many legs do spiders have?", answer: "8" },
      { question: "What is the square root of 64?", answer: "8" },
      { question: "What is 12 x 12?", answer: "144" },
      { question: "Which planet is known as the Red Planet?", answer: "Mars" },
      { question: "What is 15 - 7?", answer: "8" },
      { question: "Which gas do plants use for photosynthesis?", answer: "Carbon dioxide" },
      { question: "What is the boiling point of water in Celsius?", answer: "100" },
      { question: "How many continents are there on Earth?", answer: "7" },
      { question: "What is the largest mammal on Earth?", answer: "Blue whale" },
      { question: "What is 20% of 50?", answer: "10" },
      { question: "Which month has 28 days?", answer: "All months" },
      { question: "What is the largest planet in our solar system?", answer: "Jupiter" },
      { question: "What color is a polar bear’s fur?", answer: "Transparent" },
      { question: "What is the first element on the periodic table?", answer: "Hydrogen" },
      { question: "What is the chemical formula for water?", answer: "H2O" },
      { question: "How many hours are in two days?", answer: "48" },
      { question: "What is 3 squared?", answer: "9" },
      { question: "Which country is known as the Land of the Rising Sun?", answer: "Japan" },
      { question: "What is the opposite of 'minimum'?", answer: "Maximum" },
      { question: "What is the capital of Italy?", answer: "Rome" },
      { question: "Which animal is known as the King of the Jungle?", answer: "Lion" },
      { question: "What is the freezing point of water in Celsius?", answer: "0" },
      { question: "What is 7 x 6?", answer: "42" },
      { question: "What is the currency of the United States?", answer: "Dollar" },
      // Add more questions up to 100
    ];

    let currentQuestionIndex = 0;

    // Load a random question
    function loadQuestion() {
      currentQuestionIndex = Math.floor(Math.random() * questions.length);
      document.getElementById('question').textContent = questions[currentQuestionIndex].question;
      document.getElementById('answer').value = ""; // Clear input field
      document.getElementById('feedback').textContent = ""; // Clear feedback
    }

    // Check the player's answer
    function checkAnswer() {
      const playerAnswer = document.getElementById('answer').value.trim();
      const correctAnswer = questions[currentQuestionIndex].answer;

      const feedback = document.getElementById('feedback');
      if (playerAnswer.toLowerCase() === correctAnswer.toLowerCase()) {
        feedback.textContent = "Correct! Well done!";
        feedback.style.color = "green";
        setTimeout(loadQuestion, 2000); // Load next question after 2 seconds
      } else {
        feedback.textContent = "Wrong answer! Try again!";
        feedback.style.color = "red";
      }
    }

    // Initialize the game
    window.onload = loadQuestion;
  </script>
</body>
</html>
