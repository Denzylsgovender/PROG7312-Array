# 🎮 C# Guessing Game – Build Your Own!

## 🧠 Overview
Welcome to the **Guessing Game Project**! In this project, you'll build a fun guessing game using **C#** in **Visual Studio**. *(You are not restricted to a console app—so make your app look nice!)* This activity is designed to help you understand core programming concepts like **arrays**, **loops**, **conditionals**, and **user input**. 

---

## 🎯 Learning Goals

By the end of this activity, you will be able to:

- Use **1D and 2D arrays** to store and retrieve data  
- Apply **loops** and **conditionals** to control program flow  
- Work with **random values** and **user input**  
- Use **variables** to track scores and limits  
- Store **top scores** using **arrays or lists**  
- Work with **DateTime** to track performance  

---

## 🚀 Project Features

Below are the features your game should include (**Choose any 3**), along with the concepts they are designed to teach:

| 🌟 Feature        | 💡 Learning Concept     | 🛠️ Implementation Idea                                           |
|------------------|-------------------------|------------------------------------------------------------------|
| **Score System** | Variables & logic       | Award **+10** for every correct guess, **-1** for wrong guesses |
| **Guess Limit**  | Loops + conditionals    | Limit the user to **5 total guesses**                           |
| **Hint System**  | Conditionals + strings  | After a wrong guess, display: *"Hint: it starts with X"*       |
| **Timer**        | Time management         | Track how long the user takes using `DateTime`                  |
| **Leaderboard**  | Arrays or Lists         | Store top 5 scores and display them after each round            |

---
## Submission Instructions
Complete your guessing game using Visual Studio.

Make sure you implement at least 3 features from the project list above.

Submit your code to the following GitHub Classroom Repo:
🔗 https://classroom.github.com/a/J-524X85

Then submit your GitHub link to Arc under ICE Task 1.
---
## 🧩 Sample Starter Code

Here’s a simple base to help you get started:

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        string[] words = { "apple", "banana", "cherry", "grape", "lemon" };
        Random rand = new Random();
        string secret = words[rand.Next(words.Length)];

        int score = 0;
        int attempts = 0;
        int maxAttempts = 5;
        DateTime startTime = DateTime.Now;

        while (attempts < maxAttempts)
        {
            Console.Write("Guess the word: ");
            string guess = Console.ReadLine();
            attempts++;

            if (guess == secret)
            {
                score += 10;
                Console.WriteLine("Correct! 🎉");
                break;
            }
            else
            {
                score -= 1;
                Console.WriteLine($"Wrong! Hint: It starts with '{secret[0]}'");
            }
        }

        TimeSpan duration = DateTime.Now - startTime;
        Console.WriteLine($"Game Over. Your score: {score}. Time: {duration.Seconds} seconds.");

        // Add the rest of your features
    }
}
