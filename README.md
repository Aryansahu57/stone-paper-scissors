import random

# Choices list
choices = ["rock", "scissor", "paper"]

while True:
    print('''\n
    Welcome to Rock-Paper-Scissors Game
    1. Start Game
    2. Exit
    ''')
    
    uc = int(input("Enter your choice: "))
    
    if uc == 1:
        ucount = 0
        ccount = 0

        # 5 rounds
        for a in range(1, 6):
            print(f"\nRound {a}")
            print("1. Rock")
            print("2. Scissor")
            print("3. Paper")
            
            user_choice = int(input("Enter your choice (1-3): "))
            
            if user_choice == 1:
                uchoice = "rock"
            elif user_choice == 2:
                uchoice = "scissor"
            elif user_choice == 3:
                uchoice = "paper"
            else:
                print("Invalid input, try again!")
                continue

            cchoice = random.choice(choices)

            print("Computer value:", cchoice)
            print("User value:", uchoice)

            # Draw condition
            if uchoice == cchoice:
                print("Round Draw!")
                ucount += 1
                ccount += 1

            # User wins conditions
            elif (uchoice == "rock" and cchoice == "scissor") or \
                 (uchoice == "paper" and cchoice == "rock") or \
                 (uchoice == "scissor" and cchoice == "paper"):
                print("You win this round!")
                ucount += 1

            else:
                print("Computer wins this round!")
                ccount += 1

        # Final results
        print("\n---- Final Result ----")
        print("Your Score:", ucount)
        print("Computer Score:", ccount)

        if ucount == ccount:
            print("Match Draw!")
        elif ucount > ccount:
            print("Congratulations! You win the game 🎉")
        else:
            print("Computer wins the game 😅")

    elif uc == 2:
        print("Game Closed. Bye!")
        break
    else:
        print("Invalid choice, try again.")
