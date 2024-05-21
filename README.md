# Bouncing-Balls-Project
A program that shows how Javascript Objects make little balls bounce around on the screen and change color when they touch each other.

In this project I will write a program that will show how Javascript Objects can be used in making little balls bounce around on the screen, and change color when they touch each other. The project made use of the Canvas API for drawing the balls to the screen, and the "requestAnimationFrame" API for animating the whole display.

bouncing balls off walls, and checking whether they have hit each other (otherwise known as collision detection).

- Getting started

I set constants called width and height, to set the width and height of the canvas element (represented by the canvas.width and canvas.height properties) to equal the width and height of the browser viewport

- Drawing the ball

I write a function to tell the ball to draw itself onto the screen. 

First, we use beginPath() to state that we want to draw a shape on the paper.
Next, we use fillStyle to define what color we want the shape to be — we set it to our ball's color property.
Next, we use the arc() method to trace an arc shape on the paper. Its parameters are:
The x and y position of the arc's center — we are specifying the ball's x and y properties.
The radius of the arc — in this case, the ball's size property.
The last two parameters specify the start and end number of degrees around the circle that the arc is drawn between. Here we specify 0 degrees, and 2 * PI, which is the equivalent of 360 degrees in radians (annoyingly, you have to specify this in radians). That gives us a complete circle. If you had specified only 1 * PI, you'd get a semi-circle (180 degrees).
Last of all, we use the fill() method, which basically states "finish drawing the path we started with beginPath(), and fill the area it takes up with the color we specified earlier in fillStyle."

if the x coordinate is greater than the width of the canvas (the ball is going off the right edge).
if the x coordinate is smaller than 0 (the ball is going off the left edge).
if the y coordinate is greater than the height of the canvas (the ball is going off the bottom edge).
if the y coordinate is smaller than 0 (the ball is going off the top edge).

- Animating the ball

A while loop that creates a new instance of a Ball() using random values generated with a random() and randomRGB() functions, then push()es it onto the end of our balls array, but only while the number of balls in the array is less than 25. So when there are 25 balls in the array, no more balls will be pushed. 

- Adding collision detection 

For each ball, I check every other ball to see if it has collided with the current ball. To do this, I use a for...of loop to loop through all the balls in the balls[] array.
Immediately inside the for loop, I use an if statement to check whether the current ball being looped through is the same ball as the one that is currently check, to prevent checking whether a ball has collided with itself! To do this, I check whether the current ball (i.e., the ball whose collisionDetect method is being invoked) is the same as the loop ball (i.e., the ball that is being referred to by the current iteration of the for loop in the collisionDetect method). I then use "!" to negate the check, so that the code inside the if statement only runs if they are not the same.
I then use a common algorithm to check the collision of two circles, by checking whether any of the two circle's areas overlap. This is explained further in 2D collision detection.
If a collision is detected, the code inside the inner if statement is run. In this case, I only set the color property of both the circles to a new random color. 
Then I call this method in each frame of the animation. 
