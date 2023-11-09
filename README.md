# PyAutoGui-Game
#A simple choice-based game created with the Python library PyAutoGUI

import pyautogui
import time

def introduction():
    pyautogui.alert("Welcome! Your choices will be important in this game!", "WELCOME")
    print("You are in a dark and mysterious forest.")
    print("You can choose between two paths: the left one or the right one.")

def choose_path():
    choice = pyautogui.confirm("Left or Right?", buttons=["Left", "Right"])
    print(choice)
    if choice == "Right":
        right_path()
    elif choice == "Left":
        left_cave()
    else:
        print("Invalid choice. Try again.")

def right_path():
    print("You safely crossed the river.")
    print("As you walk along the riverbank, you come across an abandoned cabin.")
    print("Do you want to enter the cabin (yes/no)?")
    choice = pyautogui.confirm("Do you want to enter the cabin (yes/no)?", buttons=["Yes", "No"])
    if choice == "Yes":
        pyautogui.alert("There was a Bear inside! You lost!")
        print("There was a Bear inside! You lost!")
    elif choice == "No":
        print("You decide to continue exploring the forest.")
        continue_game()
    else:
        print("Invalid choice. Try again.")

def left_cave():
    print("You passed through a thicket of trees, and everything is fine.")
    print("You found a chest in the middle of nowhere. Do you want to open it?")
    choice = pyautogui.confirm("What would you like to do (open/keep walking)?", buttons=["Open", "Keep walking"])
    if choice == "Open":
        print("Inside the chest was a venomous snake! You lost.")
        pyautogui.alert("Inside the chest was a venomous snake! You lost.")
    elif choice == "Keep walking":
        print("You leave the tree-filled area and decide to continue exploring the forest.")
        continue_game()
    else:
        print("Invalid choice. Try again.")

def continue_game():
    print("You continue your journey in the forest...")
    print("You found a letter!")
    pyautogui.alert("You found a Letter")
    time.sleep(2)
    pyautogui.press("win")
    time.sleep(4)
    pyautogui.typewrite("notepad")
    time.sleep(2)
    pyautogui.press("enter")
    time.sleep(2)
    pyautogui.typewrite("HELP ME, THEY ARE AFTER ME. FIND ME IN THE ABANDONED HOUSE. When you arrive, knock on the door and say your name is banana!")
    time.sleep(5)
    pyautogui.alert("You noticed there was another paper along with the letter, showing a map to the house.")
    choice = pyautogui.confirm("What do you want to do now?", buttons=["Open the other paper and follow the clue", "I don't want to die, I'll follow it"])
    if choice == "Open the other paper and follow the clue":
        follow_clue()
    else:
        pyautogui.alert("You followed the trail!")
        ending2()

def follow_clue():
    time.sleep(2)
    pyautogui.press("win")
    time.sleep(4)
    pyautogui.typewrite("paint")
    time.sleep(3)
    pyautogui.press("enter")
    time.sleep(2)
    pyautogui.moveTo(500, 300, 3)
    pyautogui.mouseDown()
    pyautogui.moveTo(530, 280, 3)
    pyautogui.moveTo(400, 200, 3)
    pyautogui.moveTo(360, 170, 3)
    pyautogui.mouseUp()
    abandoned_house()

def abandoned_house():
    time.sleep(6)
    pyautogui.alert("Arriving there, you knock on the door, and a voice asks?")
    print("Arriving there, you knock on the door, and a voice asks?")
    name = pyautogui.prompt("Who is it?")
    pyautogui.alert(f'Your name is {name}.')
    if name == "banana":
        pyautogui.alert("He opened the door for you.")
        print("He explained that he was being followed by hunters because he shouldn't be walking in the forest, and therefore, YOU shouldn't be in the forest either.")
        ending1()
    else:
        pyautogui.alert("YOU WERE SUPPOSED TO SAY BANANA. YOU GOT SHOT AND LOST.")

def ending1():
    pyautogui.alert("You both decided to leave the house, each with a weapon.")
    pyautogui.alert("After 5 minutes of walking, you encountered a hunter!")
    choice2 = pyautogui.confirm("Choose a number (1 or 2). If you choose the right number, you will survive.",
                                buttons=["1", "2"])
    if choice2 == "1":
        pyautogui.alert("You took 1 second to shoot and killed the hunter!")
        pyautogui.alert("After that, you both managed to leave the forest alive. Congratulations!", "THE END")

    else:
        pyautogui.alert("You took 2 seconds to shoot and died!")

def ending2():
    pyautogui.alert("After a while of walking, you encounter a man with an unfriendly look.")
    pyautogui.alert("You run into the forest, but soon realize you are surrounded by hunters.")
    choice3 = pyautogui.confirm("Choose a number (1, 2, or 3) to try to escape.", buttons=["1", "2", "3"])

    if choice3 == "1":
        pyautogui.alert("You run swiftly through the forest, escaping from the hunters!")
        pyautogui.alert("Finally, you find a safe refuge and survive. Congratulations, you won the game!", "THE END")
    elif choice3 == "2":
        pyautogui.alert("You try to fight the hunters, but they are too strong.")
        pyautogui.alert("A hunter approached from behind and stabbed you. You lost.")
    elif choice3 == "3":
        pyautogui.alert("You try to negotiate with the hunters, offering something in exchange for your freedom.")
        pyautogui.alert("The hunters accept your offer and let you go. You survive and win the game!", "THE END")
    else:
        pyautogui.alert("Invalid choice. Try again.")

def adventure_game():
    introduction()
    choose_path()

adventure_game()

