# codsoft-project-task-4
Rock, Paper, Scissors Game.

import random

def get_computer_choice():
    return random.choice(['rock', 'paper', 'scissors'])

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It is tie!"
    elif (user_choice == 'rock' and computer_choice == 'scissors') or \
         (user_choice == 'scissors' and computer_choice == 'paper') or \
         (user_choice == 'paper' and computer_choice == 'rock'):
        return " Great! You win!"
    else:
        return " Better luck next time!You lose!"

def play_game():
    user_score = 0
    computer_score = 0

    while True:
        print("\nwelcome to Rock, Paper, Scissors!")
        print("choose: rock, paper, or scissors.")

        user_choice = input("Your choice: ").lower()
        if user_choice not in ['rock', 'paper', 'scissors']:
            print("wrong choice. Please enter again.")
            continue

        computer_choice = get_computer_choice()
        print(f"Computer chose: {computer_choice}")

        result = determine_winner(user_choice, computer_choice)
        print(result)
        if result == "You win!":
            user_score += 1
        elif result == "You lose!":
            computer_score += 1

        print(f"Score - You: {user_score}, Computer: {computer_score}")

        play_again = input("Want to play once more? (yes/no): ").lower()
        if play_again != 'yes':
            print("Thank you for the fun! Wishing you all the best!")
            break

if __name__ == "__main__":
    play_game()
