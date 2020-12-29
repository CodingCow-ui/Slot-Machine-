# Slot-Machine-
#Python Slot Machine
#2020

import random
from turtle import *
import time
setup(width = 500, height = 200, startx = -200, starty = -600)



bank = 1500



shape1 = Turtle()
shape2 = Turtle()
shape3 = Turtle()

shape1.setheading(90)
shape2.setheading(90)
shape3.setheading(90)


shape1.up()
shape2.up()
shape3.up()


shape1.goto(-100,0)
shape3.goto(100,0)


shapelist = ["square", "circle", "triangle"]

print("───────────────────────────────────────────────────────────────────────────────────")
print("─██████████████─██████─────────██████████████─██████████████─██████████████─██████─")
print("─██░░░░░░░░░░██─██░░██─────────██░░░░░░░░░░██─██░░░░░░░░░░██─██░░░░░░░░░░██─██░░██─")
print("─██░░██████████─██░░██─────────██░░██████░░██─██████░░██████─██░░██████████─██░░██─")
print("─██░░██─────────██░░██─────────██░░██──██░░██─────██░░██─────██░░██─────────██░░██─")
print("─██░░██████████─██░░██─────────██░░██──██░░██─────██░░██─────██░░██████████─██░░██─")
print("─██░░░░░░░░░░██─██░░██─────────██░░██──██░░██─────██░░██─────██░░░░░░░░░░██─██░░██─")
print("─██████████░░██─██░░██─────────██░░██──██░░██─────██░░██─────██████████░░██─██████─")
print("─────────██░░██─██░░██─────────██░░██──██░░██─────██░░██─────────────██░░██────────")
print("─██████████░░██─██░░██████████─██░░██████░░██─────██░░██─────██████████░░██─██████─")
print("─██░░░░░░░░░░██─██░░░░░░░░░░██─██░░░░░░░░░░██─────██░░██─────██░░░░░░░░░░██─██░░██─")
print("─██████████████─██████████████─██████████████─────██████─────██████████████─██████─")
print("───────────────────────────────────────────────────────────────────────────────────")



keep_playing = "true"


while keep_playing == "true":
    
    print ("You have",bank,"points to wager.")
    
    wager = int(input("What is your wager?"))
    
    if wager > bank:
        continue
        
    bank = bank - wager
    for i in range(3):
        shape1.shape(shapelist[i])
        time.sleep(0.1)
        shape2.shape(shapelist[i])
        time.sleep(0.1)
        shape3.shape(shapelist[i])
        time.sleep(0.1)
       
    result1 = random.choice(shapelist)
    shape1.shape(result1)
    result2 = random.choice(shapelist)
    shape2.shape(result2)
    result3 = random.choice(shapelist)
    
    shape3.shape(result3)
    
    if result1 == result2 and result2 == result3:
        
        if result1 == "square":    
            print ("WINNER 3 SQUARES!")  
            wager = wager * 5          
            bank = bank + wager
        elif result1 == "circle":
            print ("WINNER 3 CIRCLES!")
            wager = wager * 15
            bank = bank + wager
        elif result1 == "triangle":
            print ("WINNER 3 TRIANGLES!")
            wager = wager * 25
            bank = bank + wager
            
    if bank <= 0: 
        print ("GAME OVER!!! Sorry, you have no money left to bet! Restart the game to play again.")
        break
        
    prompt = input("Would you like to keep playing?")
   
    if prompt == "no" or prompt == "NO" or prompt == "No":
        print("Thank you for playing. Restart the game to reset your wager.")
        keep_playing == "false"
        break

    if prompt == "yes" or prompt == "YES" or prompt == "Yes": 
        keep_playing == "true"
    
