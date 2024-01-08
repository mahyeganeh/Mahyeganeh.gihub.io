---
layout: posts
title: کد درخت
---

## توضیحات کد درخت 

<html>
<head>
    <h1 style=" color:green; text-align:center;">توضیحات کد درخت</h1>
    <body>
    <img src="C:\git\personal_website_template\assets\images\tree.png" alt="درخت" width="400" border-radius="10" >
    <br>
    <div >
    <p dir="rtl" style="text-align: right;">

        این کد برای رسم یک درخت ساده با استفاده از کتابخانه گرافیکی Turtle در پایتون است.
تابع TREE  : این تابع یک درخت را رسم می‌کند. دو شاخه اصلی در هر مرحله بازگشتی رسم می‌شوند، یکی به سمت چپ و دیگری به سمت راست.
در قسمت پارامتر ها d ظول شاخه های اصلی درخت را رسم میکند .r زاویه‌ای که شاخه‌ها در هر مرحله بازگشتی نسبت به هم قرار می‌گیرند را رسم میکند ، n نیز برای ضخامت خطی است که برای رسم شاخه‌ها استفاده می‌شود .
با هر دور بازگشت، طول و ضخامت شاخه‌ها کاهش می‌یابد. این باعث می‌شود شاخه‌های فرعی نازک‌تر و کوتاه‌تر باشند.
وقتی طول شاخه کمتر از یک حد معین شود، برگ‌هایی به شکل دایره‌های کوچک رسم می‌شوند.
سرعت رسم، رنگ پس‌زمینه و موقعیت اولیه قلم نیز به صورتی که نیاز داریم تنظیم می‌شوند و در نهایت، تابع TREE با پارامترهای اولیه فراخوانی می‌شود تا رسم درخت آغاز شود.

        
    </p>
    <h2 style=" color:green; text-align:center;">کد درخت</h2>
    <pre>import turtle
        def tree(d, r, n):
    if d < 20 or r < 6:
        return 
    turtle.pensize(n)
    turtle.pencolor("black")
    turtle.forward(d)
    turtle.left(r)
    tree(d * 0.75,r, n * 0.6)
    
    if d < 65:
        turtle.pencolor("white")
        turtle.fillcolor("white")
        turtle.begin_fill()
        turtle.left(45)
        leaf(d / 6)
        turtle.right(90)
        leaf(d / 6)
        turtle.left(45)
        turtle.pencolor("black")
        turtle.end_fill()
    
    turtle.right(2 * r)
    tree(d * 0.75,r, n * 0.6)
    turtle.left(r)
    turtle.backward(d)

def leaf(radius):
    turtle.begin_fill()
    turtle.circle(6)
    turtle.end_fill()

turtle.speed(0)
turtle.bgcolor("grey")
turtle.penup()
turtle.setpos(0, -200)
turtle.pendown()
turtle.left(90)

tree(100, 38, 18)

turtle.mainloop()
            
    </pre>
    <a href="triangle.html">کد مثلث</a>
    </div>
    </body>
</head>
</html>
---
**Test**: This is atest
