# Turtle-race
A simple Python turtle racing game.
from turtle import Turtle, Screen
import random  

window = Screen()
window.title("octocode turtle race")
window.setup(600, 400)
colors = ("red", "blue", "green")
y_pos = (70, 0, -70)
turtles = []

user_bet = window.textinput("make your bet", "guess the winner:")

for i in range(3):
    new_turtle = Turtle(shape="turtle")
    new_turtle.color(colors[i])
    new_turtle.penup()
    new_turtle.goto(-280, y_pos[i])
    turtles.append(new_turtle)

def race():
    is_race = True
    while is_race: 
        for turtle in turtles:
             if turtle.xcor() > 280:
                is_race = False
                winning_color = turtle.pencolor()
                the_winner(winning_color)
             else:
               p=random.randint(1,5)
               turtle.forward(p)
               
def the_winner(winning_color):
              
      
      result_turtle=Turtle()   
      result_turtle.hideturtle()    
      result_turtle.penup() 
      result_turtle.goto(0,0)
      result_turtle.pendown()
      
      if user_bet==winning_color:
             window.bgcolor("dark green")
             result_turtle.write("you win")
      else:
               window.bgcolor("white")
               result_turtle.write("you lose")   
                   
                      
               
race()
the_winner()
window.exitonclick()


