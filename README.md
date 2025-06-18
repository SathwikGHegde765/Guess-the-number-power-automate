# Guess-the-number-power-automate
# Guessing Random Number Game (Power Automate Desktop)

This repository contains a Microsoft Power Automate Desktop flow that implements a simple "Guessing Random Number Game".

## Table of Contents

* [About the Game](#about-the-game)
* [Features](#features)
* [Prerequisites](#prerequisites)
* [How to Play](#how-to-play)
* [Flow Details](#flow-details)
* [Variables Used](#variables-used)
* [Contributing](#contributing)
* [License](#license)

## About the Game

The "Guessing Random Number Game" is a classic interactive game where the user attempts to guess a secret number generated randomly by the Power Automate flow. The flow provides hints (too high or too low) after each guess until the correct number is identified. Once guessed, it congratulates the user and reveals the number of attempts taken.

## Features

* Generates a random number between 1 and 100.
* Prompts the user for guesses.
* Provides feedback: "Too low" or "Too high".
* Tracks and displays the number of attempts.
* Congratulatory message upon correct guess.

## Prerequisites

To run this Power Automate flow, you need:

* **Microsoft Power Automate Desktop** installed on your Windows machine.

## How to Play

1.  **Download/Clone:** Get the Power Automate flow file (e.g., `.pad` file) from this repository.
2.  **Open in Power Automate:** Open Power Automate Desktop and import/open the downloaded flow.
3.  **Run the Flow:** Click the "Run" button (the play icon) in the Power Automate Desktop interface.
4.  **Start Guessing:** A dialog box will appear prompting you to enter a number between 1 and 100.
5.  **Follow Feedback:** Based on your guess, the flow will tell you if your guess was "Too low" or "Too high". Continue guessing.
6.  **Win!** Once you guess the correct number, a final message will congratulate you and show you how many attempts it took.

## Flow Details

The Power Automate flow is structured as follows:

1.  **Generate Random Number:** A random integer between 1 and 100 is generated and stored in the `RandomNumber` variable.
2.  **Initialize Counter:** A variable `Counter` is initialized to `1` to count the guesses.
3.  **Loop for Guessing:** A `Loop condition` (While loop) continues as long as the user's `UserInput` does not match the `RandomNumber`.
    * **Input Dialog:** Inside the loop, a `Display input dialog` action asks the user for their guess.
    * **Conditional Checks:**
        * `If UserInput < RandomNumber`: Displays "Too low" message and increments `Counter`.
        * `If UserInput > RandomNumber`: Displays "Too high" message and increments `Counter`.
4.  **Success Message:** Once the loop terminates (meaning the `UserInput` matches `RandomNumber`), a `Display message` action shows the final congratulatory message, including the `RandomNumber` and the `Counter` value.

## Variables Used

| Variable Name  | Description                                                         |
| :------------- | :------------------------------------------------------------------ |
| `RandomNumber` | Stores the randomly generated secret number (1-100).                |
| `Counter`      | Keeps track of the number of attempts/guesses made by the user.     |
| `UserInput`    | Stores the number entered by the user in the input dialog.          |
| `ButtonPressed`| Stores the result of the input dialog button press (e.g., "OK").    |

## Contributing

Feel free to fork this repository, make improvements, or suggest new features. Pull requests are welcome!

## License

This project is open-source and available under the [MIT License](LICENSE).
