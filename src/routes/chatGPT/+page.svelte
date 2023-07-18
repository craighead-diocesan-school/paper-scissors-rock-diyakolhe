<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
    <style>
      body {
        text-align: center;
        font-family: Arial, sans-serif;
      }
    </style>
  </head>
  <body>
    <h1>Rock Paper Scissors</h1>
    <p>Select your move:</p>
    <button onclick="play('rock')">Rock</button>
    <button onclick="play('paper')">Paper</button>
    <button onclick="play('scissors')">Scissors</button>
    <p id="result" />

    <script>
      function play(userChoice) {
        // Generate computer's move
        const moves = ["rock", "paper", "scissors"]
        const computerChoice = moves[Math.floor(Math.random() * moves.length)]

        // Determine the winner
        let result = ""
        if (userChoice === computerChoice) {
          result = "It's a tie!"
        } else if ((userChoice === "rock" && computerChoice === "scissors") || (userChoice === "paper" && computerChoice === "rock") || (userChoice === "scissors" && computerChoice === "paper")) {
          result = "You win!"
        } else {
          result = "Computer wins!"
        }

        // Display the result
        document.getElementById("result").innerHTML = `You chose ${userChoice}. The computer chose ${computerChoice}. ${result}`
      }
    </script>
  </body>
</html>
