# -*- coding: utf-8 -*-
"""
Created on Sun Mar 17 04:00:03 2019

@author: enitee9
"""
import random
from PIL import Image
end=100
def show_board():
    img=Image.open(r'C:\Users\enite\Downloads\snakee.jpg')
    img.show()
def check_ladder(points):
    if points ==8:
        print("ladder")
        return 26
    elif points==21:
         print("ladder")
         return 82
    elif points ==43:
          print("ladder")
          return 77
    elif points ==50:
           print("ladder")
           return 91
    elif points ==54:
         print("ladder")
         return 93
    elif points ==62:
         print("ladder")
         return 96
    elif points == 66:
         print("ladder")
         return 87
    elif points == 80:
         print("ladder")
         return 100
    else:
        #it is not ladder
        return points
def check_snake(points):
    if points ==44:
         print("snake")
         return 22
    elif points ==46:
         print("snake")
         return 5
    elif points == 48:
         print("snake")
         return 5
    elif points == 55:
         print("snake")
         return 7
    elif points == 59:
         print("snake")
         return 17
    elif points ==64:
         print("snake")
         return 36
    elif points == 69:
         print("snake")
         return 33
    elif points == 73:
         print("snake")
         return 1
    elif points ==83:
         print("snake")
         return 19
    elif points ==92:
         print("snake")
         return 52
    elif points ==95:
         print("snake")
         return 24
    elif points ==98:
         print("snake")
         return 28
    else:
        #it's not snake bite
        return points
        
def reached_end(points):
    if points == end:
        return True
    else:
        return False
    
def play():
    p1_name= input('player 1,please enter the player name')
    #input plyer 1 nmae
    p2_name= input('player 2,please enter the player name')
    #input player 2
    pp1=0
    #intial point of player 1
    pp2=0
    #intial point of player 2
    turn = 0
    while(1):
        if turn % 2==0:
            #player 1 turn 
            print(p1_name,"your turn")
            #ask player's choice to continue
            choice = input('press 1 to continue , 0 to quit')
            if choice==0:
                print(p1_name,'scored',pp1)
                print(p2_name,'scored',ppp2)
                print('quiting the game ,Thanks for playing')
                break
            #generate the random number from 1 to 6
            dice = random.randint(1,6)
            print("Diced showed",dice)
            pp1 +=dice
            #add the point 
            pp1=check_ladder(pp1)
            pp1=check_snake(pp1)
            #check if player goes beyond the board
            if pp1 > end:
                pp1=end
            print(p1_name,'Your score:',pp1)
            if reached_end(pp1):
                print(p1_name,'won')
                break
        else:
            
            print(p2_name,"your turn")
            #ask player's choice to continue
            choice = input('press 1 to continue , 0 to quit')
            if choice==0:
                print(p1_name,'scored',pp1)
                print(p2_name,'scored',ppp2)
                print('quiting the game ,Thanks for playing')
                break
            #generate the random number from 1 to 6
            dice = random.randint(1,6)
            print("Diced showed",dice)
            pp2 +=dice
            #add the point 
            pp2=check_ladder(pp2)
            pp2=check_snake(pp2)
            #check if player goes beyond the board
            if pp2 > end:
                pp2=end
            print(p2_name,'Your score:',pp2)
            if reached_end(pp2):
                print(p2_name,'won')
                break
        turn = turn + 1   
show_board()
play()

