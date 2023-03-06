# Quiz

```html
<button id="submit">Submit</button>

<div id="result"></div>

<script src="//code.jquery.com/jquery-3.6.0.min.js"></script>
<script>
$(document).ready(function() {
  // Set up an object to store the correct answers
  const correctAnswers = {
    q1: "Paris",
    q2: "Tokyo",
    q3: "Mars",
    q4: "HTML",
    q5: "JavaScript"
  };

  // Set up variables to store the user's answers and score
  let userAnswers = {};
  let score = 0;

  // Set up an event listener for the submit button
  $("#submit").click(function() {
    // Loop through each question and store the user's answer
    for (let i = 1; i <= 5; i++) {
      const name = "q" + i;
      const value = $('input[name="' + name + '"]:checked').val();
      userAnswers[name] = value;
    }

    // Calculate the user's score
    for (const name in correctAnswers) {
      if (userAnswers[name] === correctAnswers[name]) {
        score++;
      }
    }

    // Display the user's score and each question's answer
    let resultHTML = "";
    resultHTML += "<h2>Your Score: " + score + "/5</h2>";
    resultHTML += "<ul>";
    for (const name in correctAnswers) {
      resultHTML += "<li>";
      resultHTML += "Question " + name.substr(1) + ": ";
      resultHTML += "Your Answer: " + userAnswers[name] + ", ";
      resultHTML += "Correct Answer: " + correctAnswers[name];
      resultHTML += "</li>";
    }
    resultHTML += "</ul>";
    $("#result").html(resultHTML);
  });
});
</script>
```