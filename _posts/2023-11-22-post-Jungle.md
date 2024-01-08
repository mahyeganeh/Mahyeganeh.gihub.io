---
layout: posts
title: Jungle(python)
---

```python
import random
import time
import turtle

def Tree(d, a):
    color = turtle.pencolor()
    
    if d < 8:
        return
    colors = ['red','orange','yellow']

    if d < 10 and a != 45:
        turtle.pencolor(random.choice(colors))
        a = 45
    if d < 4:
        turtle.circle(2)
        


    turtle.pendown()
    turtle.pensize(3.5)
    turtle.forward(d)
    turtle.left(a)
    Tree(d * (random.random() / 2 + 0.5),
         a * (random.random() / 2 + 0.8),
        )
    turtle.right(2 * a)
    Tree(d * (random.random() / 2 + 0.5),
         a * (random.random() / 2 + 0.8),
         )
    turtle.left(a)
    turtle.penup()
    turtle.backward(d)
    turtle.pencolor(color)

def setup_screen(width, height):
    turtle.left(90)
    turtle.pencolor("chocolate4")
    turtle.tracer(0)
    turtle.hideturtle()
    turtle.screensize(width, height)

width, height = 900, 400
x = -width/2 + 80
y = -height/2
setup_screen(width, height)
tree_count = 9

for _ in range(tree_count):
    x += random.randint(50, 100)
    y = random.randint(-350, 150)
    turtle.penup()
    turtle.setpos(x, y)
    turtle.pendown()
    Tree(
        random.randint(38, 80),
        random.randint(9, 20),)
    turtle.update()
turtle.circle(2)

turtle.mainloop()

```


![Alt text](../assets/images/jungle-pic.png "picture of jungle")