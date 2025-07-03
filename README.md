# Python_Number_Guess_Game
# perfect guess game 

import random
def guess_the_number_game():
    
    print("Welcome to the Game!!")
    while True:
        level = input("Choose the difficulty level: 😊 easy / 👿 Medium / ☠️ Hard / ⚔️ GOD : ").lower()
        if level not in ["easy", "medium", "hard" , "god"]:
            print("❌ Invalid difficulty! Please enter easy, Medium, Hard or god .")
            return
        user_desire = int(input("Enter how many attempts you want "))
        if level == "easy":
                max_num = 20
        elif level == "medium":
                max_num = 50
        elif level == "hard":
                max_num = 100
        elif level == "god":
               max_num = 1000
        random_number = random.randint(1 ,max_num)
        # print(f"[Dev Mode] The number is: {random_number}") 

        attempt = 0
        highscore = 0
        # print("\033[91mWrong guess!\033[0m")  # Red text
        # print("\033[92mCorrect guess!\033[0m")  # Green text
        
        while attempt < user_desire:
            try:
                guess = int(input(f"Enter a number from 1 to {max_num}: "))
                attempt += 1 
                highscore +=1
                if(guess == random_number):
                        print(f"You gussed the number right in {attempt} attempts \nThe number was {random_number} Congrats")
                        print(f"Your highscore is {highscore}")
                        break
      
                elif guess < random_number:
                        print("Your guess is lower then guessed number!!")
                else:
                        print("Your guess is higher then guessed number")
                difference = abs(guess - random_number)

                if difference == 0:
                        print("🎯 Perfect guess!")
                elif difference <= 3:
                        print("🔥 You're super close!")
                elif difference <= 10:
                        print("🌡️ you're getting closer.")
                elif difference <= 20:
                        print("🧊  a bit far.")
                else:
                        print("❄️ You're way off.")      
            except ValueError:
                        print("Try again")
        else:
                print(f"\n💀 Game Over! You've used all your attempts.")
                print(f"The correct number was {random_number}.")
        play_again = input("Do you want to play again ? (yes/no):").lower()
        if play_again not in ["yes" , "no"]:
               print("Enter valid option !!!")
               return
               
        if play_again != "yes":  
               print("Thanks for playing! ")
               break
                
        

guess_the_number_game()
  
