# Guess the Number Game

Welcome to the **Guess the Number Game**! This is a simple and fun game where the player tries to guess a randomly chosen number within a certain range and number of attempts. The game was created by **Onyedika Joel Chukwuka**.

## Game Overview

In this game, the computer randomly selects a number between 1 and 100, and the player has to guess what that number is. The player can choose between two difficulty levels:

- **Easy**: 10 attempts to guess the number.
- **Hard**: 5 attempts to guess the number.

After each guess, the game provides feedback indicating whether the guess was too high, too low, or correct. If the player guesses the number within the allowed attempts, they win. If they run out of attempts, they lose.

## How to Play

1. **Run the Game**: Start the game by running the `game()` function.
2. **Choose Difficulty**: Select a difficulty level by typing `easy` or `hard`.
3. **Make Guesses**: Enter your guesses when prompted. The game will guide you if your guess is too high or too low.
4. **Win or Lose**: Keep guessing until you either find the correct number or run out of attempts.

## Code Explanation

### Constants

- `EASY_LEVEL_TURNS`: Number of attempts in easy mode (10).
- `HARD_LEVEL_TURNS`: Number of attempts in hard mode (5).

### Functions

1. **check_answer(guess, answer, turns)**: 
   - Compares the player's guess to the correct answer.
   - Returns the number of remaining attempts.
   - Provides feedback if the guess is too high, too low, or correct.

2. **set_difficulty()**: 
   - Prompts the player to choose a difficulty level.
   - Returns the corresponding number of attempts.

3. **game()**: 
   - Initializes the game, including choosing a random number and setting the difficulty.
   - Manages the game loop, prompting the player for guesses and checking the answers.
   - Ends the game when the player guesses correctly or runs out of attempts.

### Sample Code

```python
from random import randint

EASY_LEVEL_TURNS = 10
HARD_LEVEL_TURNS = 5

def check_answer(guess, answer, turns):
    """Checks answer against guess. Returns the number of returns remaining.""" 
    if guess > answer:
        print("Too high.")
        return turns - 1
    elif guess < answer:
        print("Too low.")
        return turns - 1
    else:
        print(f"You got it! The answer was {answer}.")

def set_difficulty():
    level = input("Choose a difficulty. Type 'easy' or 'hard': ")
    if level == "easy":
        return EASY_LEVEL_TURNS
    else:
        return HARD_LEVEL_TURNS  

def game():
    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")
    answer = randint(1, 100)
    print(f"Psst, the correct answer is {answer}")

    turns = set_difficulty()
  
    guess = 0
    while guess != answer:
        print(f"You have {turns} attempts remaining to guess the number.")
        guess = int(input("Make a guess:"))

        turns = check_answer(guess, answer, turns)
        if turns == 0: 
            print("You've run out of guesses, you lose.")
            return
        elif guess != answer:
            print("Guess again.")

game()
```

## Getting Started

1. **Install Python**: Ensure you have Python installed on your system. You can download it from [python.org](https://www.python.org/).
2. **Run the Game**: Copy the sample code into a Python file (e.g., `guess_the_number.py`) and run it using a Python interpreter.

## Author

**Onyedika Joel Chukwuka**

Enjoy the game and happy guessing!
