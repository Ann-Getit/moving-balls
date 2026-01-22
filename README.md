this project is a bouncing balls simulation build with HTML, CSS and JavaScript.

a table is drawn using a canvas element.  added balls to the canvas where they move, bounnce off the walls and collide to eachother. 
to achieve this had to calculate continuously the ball and the space around them.

HTML
used HTML to structure the page by creating:
- one canvas container
- 2 buttons for interaction 

CSS
with CSS i styled and position the elements to create a cleand and readable layout.

JavaScrip
first i created 6 balls and gave them each different:
colors, 
positions(y and x),
speedX and speedY.
All balls are stored together in a single array, which is used to draw, move, and handle collisions

4 functions being used for logic:
drawCanvas()
this function handles the main animation logic.
a for loop is used to draw each ball and update its position by adding its current speed values. 
to prevent balls from sticking to the edges, their speed is reduced every frame. 
to make each ball bounce of the walls if statement is used for each side of the walls making it show the whole ball bij calculating the radius in de statement.
added 2 nested forloop to make each ball bounce from eachother the logic is implemented in the checkBounce() function.
2 if statement stop the balls completely when their speed becomes very small.
if speedX and speedY is smaller than 0.05, using math.abs() the value is set to 0.

moveB() this is UI button
this function is triggerd by clicking the MoveBalls button.
a for loop is used to update the speed of each ball.
this effectivelly start or adjust the movement of all balls at once. each button click activate the movement values.

checkBounce()
this function contains the logic for ball to ball collisions.
the distance between 2 balls is calculated.
a collision is detected when the distance is smaller than 2 times the radius.
the interaction is simplified by reversing the velocity and adjusting adding *= -1;
the positions of each ball are adjusted so they do not overlap after collision.

addBalls() UI button
this function adds new balls.
using if statement to track the number of balls if it is smaller then the max giving ball, 
new bal being made using the:
- colors from the array,
- random x and y positions,
- random speedX and speedY values. 
the new ball is added to the main array using: ballen.push(newBall); because canvas s in ballen to draw and need to also draw new balls.
aantalB++; every new request (every click from the addBalls button) it adds a new ball till the max reach to 10 balls then button is disabled.
