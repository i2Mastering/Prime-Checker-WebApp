# Prime Checker Web Application

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [How It Works](#how-it-works)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Example](#example)
7. [Notes](#notes)
8. [License](#license)

## Overview
This project is a **Prime Checker** web application built using HTML and JavaScript. Users can enter a number (from 2 to 9999) into a text field and click a button to check if the number is a prime number.

This simple app demonstrates fundamental HTML structure and JavaScript functionality, including:
- DOM manipulation
- Event handling
- Basic mathematical algorithms

## Features
- Checks if a number is prime using a simple algorithm.
- User-friendly interface with input field and button.
- Instant feedback showing whether the number is prime or not.
- No exception handling as per project instructions.

## How It Works
1. The user enters a number into the input box.
2. Upon clicking the **Submit** button, the `isPrime()` function is invoked.
3. The function:
   - Retrieves and parses the user's input.
   - Checks if the number is a prime using standard division tests.
   - Displays the result in a paragraph below the button.

## Installation
No installation is required. Simply open the HTML file in any modern web browser.

## Usage
1. Open the `index.html` file in your preferred web browser.
2. Enter a number between 2 and 9999 in the provided input field.
3. Click the **Submit** button.
4. The application will display whether the entered number is a prime or not.

## Example
- Enter: `7`
- Click **Submit**
- Output: `7 is a prime number.`

- Enter: `8`
- Click **Submit**
- Output: `8 is not a prime number.`

## Notes
- There is **no input validation** beyond the browser's default behavior.
- Strings or invalid input may produce unexpected results (e.g., strings are parsed as numbers and treated as prime).
- Only numbers from 2 to 9999 are expected, as per class instructions.

## License
This project is for educational purposes. No additional licensing terms apply.

---

## Source Code

```html
<!-- Ike Iloegbu CSC 6303 PROJECT 4 -->

<!DOCTYPE html>
<html>
<head>
  <title>Prime Checker</title>
  <script>
    function isPrime() {
        var number = parseInt(document.getElementById("nbr").value);
        var prime = true;

        if (number === 2) {
            prime = true;
        } else if (number < 2 || number % 2 === 0) {
            prime = false;
        } else {
            for (var i = 3; i * i <= number; i += 2) {
                if (number % i === 0) {
                    prime = false;
                    break;
                }
            }
        }

        if (prime) {
            document.getElementById("outputName").textContent = number + " is a prime number.";
        } else {
            document.getElementById("outputName").textContent = number + " is not a prime number.";
        }
    }
  </script>
</head>
<body>
    <h1 style="color:rgb(0, 42, 255)">Prime Checker</h1>
    <label>Enter a number from 2 to 9999</label>
    <input type="number" id="nbr"> <br>
    <button onclick="isPrime()">Submit</button>
    <p id="outputName">I'm waiting...</p>
</body>
</html>
```
