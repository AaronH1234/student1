---
toc: true
comments: false
layout: post
title: Guess the number
type: hacks
courses: { compsci: {week: 3} }
---


<head>
    <meta charset="UTF-8">
    <title>Simple JavaScript Game</title>
</head>
<body>
    <h1>Simple JavaScript Game</h1>
    <p>Guess the random number between 1 and 100.</p>
    <input type="text" id="guessField">
    <input type="submit" value="Submit Guess" onclick="checkGuess()">
    <p id="message"></p>

    <script>
        // Generate a random number between 1 and 100
        const randomNumber = Math.floor(Math.random() * 100) + 1;

        // Get references to HTML elements
        const guessField = document.getElementById("guessField");
        const message = document.getElementById("message");

        // Initialize attempts
        let attempts = 0;

        function checkGuess() {
            const userGuess = parseInt(guessField.value);

            if (isNaN(userGuess) || userGuess < 1 || userGuess > 100) {
                message.textContent = "Please enter a valid number between 1 and 100.";
            } else {
                attempts++;

                if (userGuess === randomNumber) {
                    message.textContent = `Congratulations! You guessed the correct number ${randomNumber} in ${attempts} attempts!`;
                    message.style.color = "green";
                    guessField.disabled = true;
                } else {
                    const hint = userGuess < randomNumber ? "higher" : "lower";
                    message.textContent = `Wrong guess! Try a ${hint} number. (Attempts: ${attempts})`;
                    message.style.color = "red";
                }

                guessField.value = "";
                guessField.focus();
            }
        }
    </script>
</body>
