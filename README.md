import random

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (
        (user_choice == "rock" and computer_choice == "scissors") or
        (user_choice == "scissors" and computer_choice == "paper") or
        (user_choice == "paper" and computer_choice == "rock")
    ):
        return "You win!"
    else:
        return "You lose!"

def display_choices(user_choice, computer_choice):
    print(f"Your choice: {user_choice}")
    print(f"Computer's choice: {computer_choice}")


user_score = 0
computer_score = 0

while True:
    print("\nWelcome to Rock, Paper, Scissors!")
    
    
    user_choice = input("Choose rock, paper, or scissors: ").lower()
    
   
    if user_choice not in ["rock", "paper", "scissors"]:
        print("Invalid choice. Please choose rock, paper, or scissors.")
        continue
    
    
    computer_choice = random.choice(["rock", "paper", "scissors"])
    
    
    display_choices(user_choice, computer_choice)
    
    
    result = determine_winner(user_choice, computer_choice)
    print(result)
    
    
    if "win" in result:
        user_score += 1
    elif "lose" in result:
        computer_score += 1
    
   
    print(f"\nScores - You: {user_score} | Computer: {computer_score}")
    
    # Ask if the user wants to play again
    play_again = input("Do you want to play again? (yes/no): ").lower()
    if play_again != "yes":
        print("Thanks for playing! Goodbye!")
        break
