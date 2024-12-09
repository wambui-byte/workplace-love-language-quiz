<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Workplace Love Language Quiz</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            margin: 20px;
            line-height: 1.6;
            background-color: #f3f4f6;
            color: #333;
        }
        h1 {
            text-align: center;
            color: #4CAF50;
            font-size: 2.5em;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .question {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            cursor: pointer;
        }
        .submit-btn {
            display: block;
            margin: 20px auto;
            padding: 15px 30px;
            background-color: #4CAF50;
            color: white;
            font-size: 1.2em;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        .submit-btn:hover {
            background-color: #45a049;
        }
        .result {
            text-align: center;
            font-weight: bold;
            margin-top: 30px;
            font-size: 1.5em;
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <h1>💼 Workplace Love Language Quiz 💖</h1>
    <div class="container">
        <form id="quizForm">
            <div class="question">
                <p>1. When I achieve something at work, I feel most appreciated when:</p>
                <label><input type="radio" name="q1" value="A"> A) My manager or colleagues praise me with kind words.</label>
                <label><input type="radio" name="q1" value="B"> B) My team celebrates with a small gathering or activity.</label>
                <label><input type="radio" name="q1" value="C"> C) Someone offers to help me with my workload.</label>
                <label><input type="radio" name="q1" value="D"> D) I receive a thoughtful gift to commemorate the occasion.</label>
                <label><input type="radio" name="q1" value="E"> E) I get a firm handshake or a congratulatory high-five.</label>
            </div>
            <!-- Add more questions here following the same format as above -->
            <div class="question">
                <p>2. On a typical day at work, what makes you feel most valued?</p>
                <label><input type="radio" name="q2" value="A"> A) Hearing, "You did a fantastic job!"</label>
                <label><input type="radio" name="q2" value="B"> B) Having a colleague spend time with me to brainstorm or connect.</label>
                <label><input type="radio" name="q2" value="C"> C) Receiving assistance on a task I'm struggling with.</label>
                <label><input type="radio" name="q2" value="D"> D) A surprise coffee, snack, or token of appreciation.</label>
                <label><input type="radio" name="q2" value="E"> E) A friendly pat on the back or supportive physical gesture.</label>
            </div>
            <!-- Repeat for all 7 questions -->
            <button type="button" class="submit-btn" onclick="calculateResults()">Submit</button>
        </form>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateResults() {
            const form = document.getElementById('quizForm');
            const results = { A: 0, B: 0, C: 0, D: 0, E: 0 };

            // Tally up the answers
            for (let i = 1; i <= 7; i++) {
                const answer = form[`q${i}`]?.value;
                if (answer) {
                    results[answer]++;
                }
            }

            // Determine the highest score
            const highest = Object.keys(results).reduce((a, b) => results[a] > results[b] ? a : b);

            // Map to love languages
            const loveLanguages = {
                A: "Words of Affirmation",
                B: "Quality Time",
                C: "Acts of Service",
                D: "Gifts",
                E: "Physical Touch"
            };

            // Display the result
            const resultDiv = document.getElementById('result');
            if (results[highest] > 0) {
                resultDiv.innerHTML = `🎉 Your primary workplace love language is: <span style="color: #4CAF50;">${loveLanguages[highest]}</span>!`;
            } else {
                resultDiv.innerHTML = "⚠️ Please answer all the questions before submitting.";
            }
        }
    </script>
</body>
</html>
