# Number-Guessing-Game
"""
Python Web Development Techdegree
Project 1 - Number Guessing Game
--------------------------------

For this first project we will be using Workspaces.

NOTE: If you strongly prefer to work locally on your own computer, you can totally do that by clicking: File -> Download Workspace in the file menu after you fork the snapshot of this workspace.

"""

import random


def start_game():
   """Psuedo-code Hints

   When the program starts, we want to:
   ------------------------------------
   1. Display an intro/welcome message to the player.
   2. Store a random number as the answer/solution.
   3. Continuously prompt the player for a guess.
     a. If the guess greater than the solution, display to the player "It's lower".
     b. If the guess is less than the solution, display to the player "It's higher".

   4. Once the guess is correct, stop looping, inform the user they "Got it"
        and show how many attempts it took them to get the correct number.
   5. Let the player know the game is ending, or something that indicates the game is over.

   ( You can add more features/enhancements if you'd like to. )
   """
   # write your code inside this function.
   print("************************************")
   print("Welcome to the number guessing game!")
   print("************************************")
   answer = random.randint(1, 10)
   guess_number = 0
   while True:
       guess_number += 1
       try:
           guess = input("Choose a number between 1 and 10: ")
           guess = int(guess)
           if guess > 10 or guess < 1:
               print("Please pick a number between 1 and 10")
               continue
       except ValueError:
           print("Only a number will do. Please pick a number between 1 and 10.")
           continue
       if guess > answer:
           print("It's lower")
           continue
       elif guess < answer:
           print("It's higher")
           continue
       elif guess == answer:
           if guess_number == 1:
               print("Got it!")
               print("It took you just one try!")
               print("Thanks for playing!")
           elif guess_number > 1:
               print("Got it!")
               print("It took you {} tries!".format(guess_number))
       play_again = input("Play again? (Y/N): ")
       if play_again.lower() == "y":
           start_game()
       else:
           print("Thanks for playing!")
           exit()
       










# Kick off the program by calling the start_game function.
start_game()
