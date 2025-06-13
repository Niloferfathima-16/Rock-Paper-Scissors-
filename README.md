import random

def get_user_choice():
    choice = input("Enter your choice (rock, paper, or scissors): ").lower()
    while choice not in ['rock', 'paper', 'scissors']:
        choice = input("Invalid input. Please choose rock, paper, or scissors: ").lower()
    return choice

def get_computer_choice():
    return random.choice(['rock', 'paper', 'scissors'])

def decide_winner(user, computer):
    print(f"\nYou chose: {user}")
    print(f"Computer chose: {computer}")

    if user == computer:
        return "It's a tie!"
    elif (user == 'rock' and computer == 'scissors') or \
         (user == 'scissors' and computer == 'paper') or \
         (user == 'paper' and computer == 'rock'):
        return "🎉 You win!"
    else:
        return "💻 Computer wins!"

# --- Main Program ---
print("🪨📄✂️ Welcome to Rock Paper Scissors!")
play_again = 'yes'

while play_again == 'yes':
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()
    result = decide_winner(user_choice, computer_choice)
    print(result)

    play_again = input("\nDo you want to play again? (yes/no): ").lower()

print("Thanks for playing! 👋")
