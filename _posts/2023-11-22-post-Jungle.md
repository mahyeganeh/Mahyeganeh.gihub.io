---
layout: posts
title: Jungle (python)
---


<html>
<head>
    <h1 style=" color:green; text-align:center;">توضیحات کد جنگل</h1>
    <body>
    <img src="" alt="درخت" width="400" border-radius="10" >
    <br>
    <div >
    <p dir="rtl" style="text-align: right;">

    این کد یک برنامه پایتون است که از کتابخانه turtle برای رسم درختانی با شاخه‌های فرکتالی استفاده می‌کند. بیایید آن را مرحله به مرحله توضیح دهیم:

1. وارد کردن کتابخانه‌ها: 
   کتابخانه‌های random, time و turtle وارد شده‌اند. random برای انتخاب تصادفی مقادیر، time برای عملکردهای مرتبط با زمان و turtle برای رسم گرافیکی استفاده می‌شوند.

2. تعریف تابع `Tree`:
   این تابع برای رسم شاخه‌های درخت با استفاده از روش بازگشتی تعریف شده است. دو پارامتر دارد: d که طول شاخه درخت را تعیین می‌کند و a که زاویه شاخه‌های فرعی را مشخص می‌کند.

3. شرط پایان بازگشت:
   اگر طول شاخه (`d`) کمتر از 8 باشد، تابع بدون انجام هیچ کاری برمی‌گردد. این شرط مانع از رسم شاخه‌های خیلی کوچک می‌شود.

4. تغییر رنگ و زاویه:
   اگر طول شاخه کمتر از 10 باشد و زاویه متفاوت از 45 درجه باشد، رنگ قلم به یکی از رنگ‌های تصادفی (`red`, orange, `yellow`) تغییر می‌کند و زاویه به 45 درجه تنظیم می‌شود.

5. رسم شاخه‌های فرعی:
   تابع به صورت بازگشتی خودش را با طول و زاویه‌های تصادفی جدید فراخوانی می‌کند تا شاخه‌های فرعی رسم شوند.

6. تنظیمات اولیه `turtle` و رسم درختان:
   تابع setup_screen برای تنظیمات اولیه پنجره turtle استفاده می‌شود. سپس با استفاده از یک حلقه for, چندین درخت در موقعیت‌های تصادفی رسم می‌شوند.

7. نمایش نهایی:
   turtle.mainloop() پنجره را باز نگه می‌دارد تا کاربر بتواند درختان رسم شده را مشاهده کند.

        
    </p>
    <h2 style=" color:green; text-align:center;">کد درخت</h2>
    <pre>
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
            
    </pre>
    <a href="triangle.html">کد مثلث</a>
    </div>
    </body>
</head>
</html>
---
**Test**: This is atest
