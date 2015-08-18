# random-rectangle
## HCI574 HW8 - 2015
## 14  pts (+ 12 optional pts)
## this file is your main program file for this exercise, it will use
## the class definitions imported from your MyClasses module (i.e. the code contained in MyClasses.py). 
## Read MyClasses.py before starting.

import math

## Hint: After you changed/added something in MyClasses.py, make sure that you have 
## saved if before running the code in main file so it knows about your changes. 
## WingIDE is usually pretty good about this but other IDE's may not notice this
## change automatically!


# Much of these classes is already defined (in MyClasses.py) but needs to be further enhanced
#from MyClasses import Point   
#from MyClasses import Polygon  
#from MyClasses import Square  

# you will have to define the following two classes yourself in MyClasses.py 
# Once you have, comment in those two lines to import these 2 classes, too:
#from MyClasses import Rectangle 
#from MyClasses import RandomRectangle 


## Problems 1-7 are in the MyClasses.py file! In this main file, problems with 0 points (like this:)
##
##            [ 0 pt ] see  MyClasses.py
##
## mean that you should have put code in the class definition file and that
## you're just running/testing this method, etc. from here! (Also, it I've already given you
## this test code, you won't get points for it, hence the [0 pt ]  )


"""
Problem 8

In MyClasses.py file, the definition for Point already has 2 access methods:
   set_x() and get_xy().  
In MyClasses.py add four more additional access methods:
   set_y(), set_xy(), get_x, and get_y() methods.
The code below uses those new methods, so make sure you add them in your class definition 
file BEFORE stepping through the code.

[ 0 pt ] see  MyClasses.py 
"""
from MyClasses import Point

# make a Point object p1  
p1 = Point()
p1.set_xy(50, 35)
print "p1 has xy coordinates", p1.get_x(), p1.get_y() 
p1.draw()

# make a Point object p2  
p2 = Point() 
p2.set_xy(-100, -80)
print "p2 has xy coordinates", p2.get_x(), p2.get_y() 
p2.draw()

p3 = p1 + p2  # making a new point by adding two points -  uses __add__() as + has been overloaded
print "p3 has xy coordinates", p3.get_x(), p3.get_y()
p3.draw()
  

"""
Problem 9

After overloading the subtraction operator in MyCLasses.py, make a new point p4 by subtracting p2 from p1.
[ 0 pt ] see  MyClasses.py

"""

#p4 =  p2 - p1
p4_x = abs(p2.x - p1.x)
p4_y = abs(p2.y - p1.y)
p4 = Point()
p4.set_xy(p4_x, p4_y)

print "p4 has xy coordinates", p4.get_x(), p4.get_y() 
p4.draw()


"""
Problem 10

Optional: In MyClasses.py overload the equal operator (__eq__) of the Point
    class and use it here to check if p5 and p1 are equal, in the sense that
    their content(!) is the same, i.e. their x and and their y coordinates are
    the same.  
[ 0 pt ] see  MyClasses.py
"""
p5 = Point(10,5)
if p1 == p5 : 
    print "p5 has the same content as p1 (shallow equality)" # uncomment this to test your overloaded equal operator 




"""
Problem 11

After creating access methods for Point in MyClasses.py,
use getX() and getY() to calculate the 2D distance between p1 and p2
Hint: use the Pythagorean Theorem (http://www.purplemath.com/modules/distform.htm)
Note: Implement this right here, even if you late do the optional dist() method in MyCLasses.py (you can of course re-use the code ...)    
[ 4 pts ] Calc 2D distance between 2 points
"""
#dxy= p2 - p1 #y get distance in x
dx = abs(p1.x-p2.x)
dy = abs(p1.y-p2.y)# get distance in y
dxy_pow_sum = (dx*dx + dy*dy)
dst = math.sqrt(dxy_pow_sum) # calc 2D distance
print "distance between", p1, "and", p2, "is", dst





"""
Problem 12

Optional: In addition to calculating the distance in this file under 3, 
create a dist() method on the Point class in MyClasses.py and use it to
get the the distance between p1 and p3.
[ 0 pt ] see  MyClasses.py
"""

dst2 = abs(p1.x-p3.x) , abs(p1.y-p3.y)#??? (something with p1 and p3 ....)
print"distance between p1 and p3 is", dst2



from MyClasses import Polygon

# instantiate 4 points, make a Polygon from it and draw it 
pl = [Point(30, -110), Point(200, -80), Point(120, 40), Point(-100,150)]       
poly = Polygon(pl)
poly.draw()



"""
Problem 13

Optional: 
Define a length() method for the Polygon class in MyClasses.py that returns the 
length of the polygon's outline by summing up the distances from each point to 
the next, including the distance from the last point back to first point.
For example for a 3 point polygon poly = Poly(p1, p2, p3), poly.length()
should return distance from p1 to p2 plus the distance from  p2 to p3 plus the
distance from p3 to p1.  
[ 0 pt ] see  MyClasses.py
"""
poly_len = poly.length()
print "polygon length is", poly_len



"""
Problem 14

Rectangle class: in MyClasses.py, define a new Rectangle class:

Its __init__() arguments need to be  
    a) the rectangle's lower left corner Point (must be a Point object!)
    b) the rectangle's width 
    c) the rectangle's height 
    
e.g. rt = Rectangle(Point(-10, -10), 20, 8) would create a rectangle with
the lower-left corner at x -10 and y -10, a width of 20 and a height of 8
[ 0 pt ] see  MyClasses.py
"""
# Instantiate a rectangle  with the lower-left corner at x=20, y=50 that's
# 80 (wide) by 150 (height)
from MyClasses import Rectangle

rt = Rectangle(Point(-10, -10), 20, 8)
rt.draw()# ??? <- draw the rectangle rt    


"""
Problem 15

Using the Rectangle class, draw 10 rectangles at random coordinates 
   (assume your canvas goes from -300 to + 300 in each direction. 
   Also randomize the rectangle's width and height  to be between 10 and 100
[ 2 pts ] draw 10 Rectangle objects at random places
"""
#????
from MyClasses import RandomRectangle
ten_ran_rec = RandomRectangle(10)
ten_ran_rec.draw()




"""
Problem 16

Square class - Instantiate a square  (Square class is already defined in Myclasses.py)

Draw a square with the lower left corner at -100, -20 and a side length of 50
[ 1 pt ] Draw square
"""

# instantiate a square with with the lower-left corner at -100,-20
# with a side length of 50:    
from MyClasses import Square
sq = Square(Point(-100, -20), 50)

sq.draw()


"""
Problem 17

Explain why Square and Rectangle do not need to define their own draw() methods to be able to draw their basic shape
[ 1 pt ] How can Square draw itself w/o having definded a draw() method?
"""
print "Although Square does not explicitly define a draw() method, sq.draw() works here because ???"
   



"""
Problem 18

Optional:  

In MyClasses.py create a  new subclass of Rectangle called ArtzyRectangle.
Overwrite its draw() method so that it randomly varies one or more visual 
aspects like different line widths, different line or fill colors, etc.
Change your code where you draw 10 rectangles of random sizes at random
places, but now use your ArtzyRectangle class.

[ 0 pt ] see  MyClasses.py
"""
ten_ran_rec = RandomRectangle(10)
from MyClasses import ArtzyRectangle
for rec in ten_ran_rec.rec_list:
    art_rec = ArtzyRectangle(rec)
    art_rec.draw()
raw_input("Take a screenshot and press any key to continue...")
  

  


