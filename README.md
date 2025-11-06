# practical-8-b-
<!DOCTYPE html>
<html>
<head>
  <title>Conditional Statements and Functions in JavaScript</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
      background-color: #f9f9f9;
    }
    h2 {
      color: #333;
    }
    input, button {
      padding: 10px;
      margin: 5px 0;
      font-size: 16px;
    }
    button {
      background-color: #0078d7;
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: #005fa3;
    }
    #result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>Grade Calculator</h2>

  <label for="name">Student Name:</label><br>
  <input type="text" id="name" placeholder="Enter your name"><br>

  <label for="score">Score (0–100):</label><br>
  <input type="number" id="score" placeholder="Enter your score"><br>

  <button onclick="displayResult()">Check Grade</button>

  <div id="result"></div>

  <script>
    // Function to calculate grade using conditional statements
    function calculateGrade(score) {
      if (score >= 90) {
        return "A (Excellent)";
      } else if (score >= 80) {
        return "B (Very Good)";
      } else if (score >= 70) {
        return "C (Good)";
      } else if (score >= 60) {
        return "D (Pass)";
      } else {
        return "F (Fail)";
      }
    }

    // Function to display the result
    function displayResult() {
      let name = document.getElementById("name").value;
      let score = parseFloat(document.getElementById("score").value);
      let resultDiv = document.getElementById("result");

      if (name === "" || isNaN(score)) {
        resultDiv.innerHTML = "⚠️ Please enter both your name and a valid score!";
        resultDiv.style.color = "red";
        return;
      }

      let grade = calculateGrade(score);

      resultDiv.innerHTML = `<p>Hello, <strong>${name}</strong>!<br>
      Your score is <strong>${score}</strong>.<br>
      Your grade is <strong>${grade}</strong>.</p>`;
      resultDiv.style.color = "#333";
    }
  </script>

</body>
</html>

