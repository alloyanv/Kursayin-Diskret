# Kursayin-Diskret
import turtle

joe=turtle.Turtle()
joe.up()
joe.goto(-300,300)
joe.down()
joe.speed(0)

lab=turtle.Turtle()
lab.speed(0)
dom=turtle.Turtle()
dom.color("red")
dom.pensize(5)


x=-300
y=300

def sq(): #qarakusi
    for i in range(4):
        joe.forward(50)
        joe.right(90)
    joe.forward(50)

def sq_blue(): #qar kapuyt
    joe.begin_fill()
    joe.color("blue")
    sq()
    joe.end_fill()

def sq_black(): #qar sev
    joe.begin_fill()
    joe.color("black")
    sq()
    joe.end_fill()


def chakboxin(n,k):
    t=1
    
    for i in range(n):
        
        joe.up()
        joe.goto(x,y-k)
        joe.down()
        for j in range(n//2):
            if t%2==0:
                sq_blue()
                sq_black()
            else:
                sq_black()
                sq_blue()

        if n%2!=0:
                if t%2!=0:
                    sq_black()
                else:
                    sq_blue()
            
    
        t=t+1    
        k=k+50

def labirint(n):
    lab.pensize(7)
    lab.color("green")
    lab.up()
    lab.goto(-300,300)
    lab.down()
    for i in range(4):
        lab.forward(n*50)
        lab.right(90)
    lab.up()
    lab.goto(-250,300-(n-1)*50)
    lab.down()

    lab.left(90)
    #for i in range((n//2)-1):
          
    lab.forward((n-2)*50)
    lab.right(90)
    lab.forward((n-2)*50)
    lab.right(90)
    lab.forward((n-2)*50)

    lab.up()
    lab.goto(-200,300-n*50)
    lab.left(180)
    lab.down()
    
    for i in range((n-2)//2):
        lab.forward((n-2)*50)
        lab.backward((n-2)*50)
        lab.right(90)
        lab.forward(100)
        lab.left(90)

    lab.up()
    lab.goto(-150,250)
    lab.left(180)
    lab.down()
    for  i in range((n-2)//2-1):
         lab.forward((n-2)*50)
         lab.backward((n-2)*50)
         lab.left(90)
         lab.forward(100)
         lab.right(90)
    if n%2!=0:
        lab.forward((n-2)*50)
        

def domino_vertikal():
    joe.color("red")
    joe.pensize(5)
    joe.begin_fill()
    joe.color("red")
    for i in range(4):
        joe.forward(40)
        joe.left(90)
    joe.end_fill()

    joe.begin_fill()
    joe.color("yellow")
    joe.right(90)
    for i in range(2):
        joe.forward(40)
        joe.left(90)
    joe.forward(40)
    joe.end_fill()

def domino_horizontal():
    joe.color("red")
    joe.pensize(5)
    joe.begin_fill()
    joe.color("red")
    for i in range(5):
        joe.forward(25)
        joe.left(90)
    joe.end_fill()

    joe.begin_fill()
    joe.color("yellow")
    joe.right(90)
    for i in range(2):
        joe.forward(25)
        joe.left(90)
    joe.forward(25)
    joe.end_fill()    

def linia(x,y,n,k):
    t=1
   
    
    for i in range(2):
        joe.up()
        joe.goto(x,y-k)
        joe.down()
        for j in range(n*n//4):
            if t%2==0:
                sq_blue()
                sq_black()
            else:
                sq_black()
                sq_blue()

    
        t=t+1    
        k=k+50

    if n%2!=0:
            if t%2!=0:
               sq_black()
            else:
               sq_blue()

def linia_lab(n,x,y):

    joe.color("green")
    joe.pensize(5)
    joe.up()
    joe.goto(x,y)
    joe.down()
    for i in range(2):
        joe.forward((n*n//2)*50)
        joe.right(90)
        joe.forward(100)
        joe.right(90)
    joe.right(90)
    joe.forward(50)
    joe.left(90)
    joe.forward(((n*n//2)-1)*50)
    

#####main#####
xd=-275
yd=260
n=int(input("N ="))
chakboxin(n,0)

labirint(n)
joe.goto(-700,-300)
linia(-750,-250,n,0)
linia_lab(n,-750,-250)    
