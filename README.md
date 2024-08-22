<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SDG 12 Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f4f4;
        }
        .quiz-container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 5px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
        }
        .question {
            margin-bottom: 20px;
        }
        .question h3 {
            margin-bottom: 10px;
        }
        .question label {
            display: block;
            margin-bottom: 5px;
        }
        .submit-btn {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .submit-btn:hover {
            background-color: #218838;
        }
        .result {
            margin-top: 20px;
            padding: 10px;
            background-color: #d4edda;
            border: 1px solid #c3e6cb;
            color: #155724;
            border-radius: 5px;
            display: none;
        }
        .wrong {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <h1>SDG 12 Quiz</h1>
        <form id="quizForm">
            <!-- Question 1 -->
            <div class="question">
                <h3>Question 1: By 2030, what is SDG 12's target concerning the management of chemicals and wastes?</h3>
                <label><input type="radio" name="q1" value="1"> 1) To eliminate all hazardous chemicals from consumer products</label>
                <label><input type="radio" name="q1" value="2"> 2) To significantly reduce the release of chemicals and wastes to minimize their adverse impacts</label>
                <label><input type="radio" name="q1" value="3"> 3) To ban all single-use plastics globally</label>
                <label><input type="radio" name="q1" value="4"> 4) To achieve zero industrial waste production</label>
            </div>

            <!-- Question 2 -->
            <div class="question">
                <h3>Question 2: What does SDG 12 aim to do regarding sustainable practices by 2030?</h3>
                <label><input type="radio" name="q2" value="1"> 1) To mandate sustainable practices for all companies</label>
                <label><input type="radio" name="q2" value="2"> 2) To encourage companies to adopt sustainable practices and integrate sustainability information into their reporting cycle</label>
                <label><input type="radio" name="q2" value="3"> 3) To make sustainability certification compulsory for all products</label>
                <label><input type="radio" name="q2" value="4"> 4) To ensure that all government policies enforce sustainable practices</label>
            </div>

            <!-- Question 3 -->
            <div class="question">
                <h3>Question 3: What is one of the key targets of SDG 12 related to food waste by 2030?</h3>
                <label><input type="radio" name="q3" value="1"> 1) To reduce global food waste at the retail and consumer levels by 75%</label>
                <label><input type="radio" name="q3" value="2"> 2) To halve per capita global food waste at the retail and consumer levels and reduce food losses along production and supply chains</label>
                <label><input type="radio" name="q3" value="3"> 3) To eliminate food waste entirely in developed countries</label>
                <label><input type="radio" name="q3" value="4"> 4) To ensure that all food waste is composted</label>
            </div>

            <button type="submit" class="submit-btn">Submit Quiz</button>
        </form>

        <div id="result1" class="result"></div>
        <div id="result2" class="result"></div>
        <div id="result3" class="result"></div>
    </div>

    <script>
        document.getElementById('quizForm').onsubmit = function(event) {
            event.preventDefault(); // Prevent form submission

            // Correct answers
            const correctAnswers = {
                q1: '2',
                q2: '2',
                q3: '2'
            };

            for (let i = 1; i <= 3; i++) {
                const userAnswer = document.querySelector(`input[name="q${i}"]:checked`);
                const resultDiv = document.getElementById('result' + i);

                if (userAnswer && userAnswer.value === correctAnswers['q' + i]) {
                    resultDiv.textContent = `Question ${i}: Correct!`;
                    resultDiv.className = 'result';
                } else {
                    resultDiv.textContent = `Question ${i}: Wrong.`;
                    resultDiv.className = 'result wrong';
                }

                resultDiv.style.display = 'block';
            }
        }
    </script>
</body>
</html>
