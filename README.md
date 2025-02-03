<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Financial Literacy Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }
        h1 {
            color: #333;
        }
        .question {
            background-color: #fff;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        .question label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        .question input {
            margin-right: 10px;
        }
        .submit-btn {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        .submit-btn:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 20px;
            font-size: 1.2em;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Financial Literacy Quiz</h1>
    <form id="quizForm">
        <div class="question">
            <label>1. What is a credit score?</label>
            <input type="radio" name="q1" value="a"> A score that determines how much you can borrow<br>
            <input type="radio" name="q1" value="b"> A score showing how much debt you have<br>
            <input type="radio" name="q1" value="c"> A score indicating your income<br>
            <input type="radio" name="q1" value="d"> A score used to calculate your taxes<br>
        </div>

        <div class="question">
            <label>2. What is the purpose of a budget?</label>
            <input type="radio" name="q2" value="a"> To track your expenses<br>
            <input type="radio" name="q2" value="b"> To determine how much money you can spend<br>
            <input type="radio" name="q2" value="c"> Both A and B<br>
            <input type="radio" name="q2" value="d"> To make sure you save money<br>
        </div>

        <div class="question">
            <label>3. What is compound interest?</label>
            <input type="radio" name="q3" value="a"> Interest calculated only on the initial principal<br>
            <input type="radio" name="q3" value="b"> Interest calculated on both the initial principal and the accumulated interest<br>
            <input type="radio" name="q3" value="c"> Interest earned from stocks<br>
            <input type="radio" name="q3" value="d"> A form of saving<br>
        </div>

        <div class="question">
            <label>4. What does diversification mean in investing?</label>
            <input type="radio" name="q4" value="a"> Investing in a variety of different assets to reduce risk<br>
            <input type="radio" name="q4" value="b"> Putting all your money into one stock<br>
            <input type="radio" name="q4" value="c"> Focusing only on high-risk investments<br>
            <input type="radio" name="q4" value="d"> Investing only in real estate<br>
        </div>

        <button type="button" class="submit-btn" onclick="submitQuiz()">Submit</button>
    </form>

    <div class="result" id="result"></div>

    <script>
        function submitQuiz() {
            var correctAnswers = {
                q1: 'a',
                q2: 'c',
                q3: 'b',
                q4: 'a'
            };

            var form = document.getElementById('quizForm');
            var result = document.getElementById('result');
            var score = 0;

            for (var question in correctAnswers) {
                var answer = form.querySelector('input[name="' + question + '"]:checked');
                if (answer && answer.value === correctAnswers[question]) {
                    score++;
                }
            }

            result.textContent = 'Your score: ' + score + ' out of 4';
        }
    </script>
</body>
</html>
