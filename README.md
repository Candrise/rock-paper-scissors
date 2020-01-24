# rock-paper-scissors

import random

user_wins = 0
comp_wins = 0

def playing():
  global user_choice
  global comp_choice
  user_choice = user_chooses()
  comp_choice = comp_chooses()
  is_rock()
  is_paper()
  is_scissors()
  play_again()

#user chooses rock, paper, or scissors
def user_chooses():
  user_choice = input("Choose Rock, Paper, or Scissors:  ")
  if user_choice in ["Rock", "rock", "R", "r"]:
   user_choice = "r"
  elif user_choice in ["Paper", "paper", "P", "p"]:
   user_choice = "p"
  elif user_choice in ["Scissors", "scissors", "S", "s"]:
   user_choice = "s"
  else:
    print("That is not an option; please try again.")
    user_chooses()
  return user_choice

#computer chooses rock, paper, or scissors
def comp_chooses():
  choices = ["r", "p", "s"]
  comp_choice = random.choice(choices)
  return comp_choice

#asking whether or not they want to play again
def play_again():
  user_play_again = input("Do you wish to play again? Y/N:  ")
  if user_play_again in ["Y", "y", "Yes", "yes"]:
    playing()
  elif user_play_again in ["N", "n", "No", "no"]:
    print("Goodbye.")
  else: 
    print("I do not understand; try again.")
    play_again()

#user chose rock
def is_rock():
  global user_wins
  global user_choice
  if user_choice == "r" and comp_choice == "r":
    print("You chose rock, and the computer chose rock. You tie.")
  elif user_choice == "r" and comp_choice == "p":
    print("You chose rock, and the computer chose paper. You lose.")
    comp_wins =+ 1
    print("Your score is " + str(user_wins) + ". " "The computer's score is " + str(comp_wins) + ".")
  elif user_choice == "r" and comp_choice == "s":
    print("You chose rock, and the computer chose scissors. You win.")
    user_wins =+ 1 
    print("Your score is " + str(user_wins) + ". " "The computer's score is " + str(comp_wins) + ".")

#user chose paper
def is_paper():
  if user_choice == "p" and comp_choice == "p":
    print("You chose paper, and the computer chose paper. You tie.")
  if user_choice == "p" and comp_choice == "s":
    print("You chose paper, and the computer chose scissors. You lose.")
    comp_wins =+ 1
    print("Your score is " + str(user_wins) + ". " "The computer's score is " + str(comp_wins) + ".")
  print("You chose rock, and the computer chose paper. You lose.")
  if user_choice == "p" and comp_choice == "r":
    print("You chose paper, and the computer chose rock. You win.")
    user_wins =+ 1 
    print("Your score is " + str(user_wins) + ". " "The computer's score is " + str(comp_wins) + ".")

#user chose scissors
def is_scissors():
  if user_choice == "s" and comp_choice == "s":
    print("You chose scissors, and the computer chose scissors. You tie.")
  if user_choice == "s" and comp_choice == "r":
    print("You chose scissors, and the computer chose rock. You lose.")
    comp_wins =+ 1
    print("Your score is " + str(user_wins) + ". " "The computer's score is " + str(comp_wins) + ".")
  if user_choice == "s" and comp_choice == "p":
    print("You chose scissors, and the computer chose paper. You win.")
    user_wins =+ 1 
    print("Your score is " + str(user_wins) + ". " "The computer's score is " + str(comp_wins) + ".")


playing()
