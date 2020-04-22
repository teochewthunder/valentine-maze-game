# Valentine Maze Game
This little project is mostly JavaScript, with a little supporting HTML and CSS.  Several square divs are arranged on the board (a rectangular div) in a 5 by 4 grid, all floated left. Each square div has two "entry" points, except for two div that have only one "entry" point each (**Start Div** and **End Div**). Of all the divs that have two "entry" points, some have their "entry" points arranged **perpendicularly** while some have their "entry" points arranged in **parallel**.

## General flow
1. When user clicks on "start", a timer countdown begins.
2. All divs are rotated clockwise ninety degrees for a random number of times.
3. User has to rotate the divs (by clicking on them) so as to form a complete line (from "entry" point to "entry" point) from **Start Div** to **End Div**.
4. Once the user does so, the timer stops and a congratulatory message is displayed.
5. If the timer reaches zero before the user is done, the game stops.

## JavaScript
- Each div will be rotated 90 degrees clockwise with each click. Click event is active when the game begins, and disabled when it ends.
- An algorithmn is used to determine if a complete path has been found. Basically, an array is created, starting with the **Start Div** as the first element. If a div is "connected" to it and in turn has another div "connected" to it, it is added to the array. If not, the algorithm returns `false`. If the next div is the **End Div**, the algorithmn returns *true*.
- During initialization, the **Start Div** is placed on the far left of the grid, and the **End Div** on the far right. The rest of the grid is populated by square divs that randomly have **perpendicular** and **parallel** "entry" points.
- An algorithmn is used to determine if there is any possible complete path between **Start Div** and **End Div**. If not, restart initialization.
