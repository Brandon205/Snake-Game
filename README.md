# Project-1

Day 1 - 
On day one my main goal was to make up a plan that was easy to fall back on when thinking of the different actions that my game will have to do. Also in my plan was a good wireframe of the different parts to my code, this is a vital part to planning as it allows you to look back on it when needing to see what needs to do what and when. 
Another big part of my planning stage was making a list of goals and stretch goals, which were goals that would not be included in my base project. All in all my base project that I wanted to have done before moving onto making things in my list of stretch goals was just the base Snake game, which includes a snake that moves and eats, and when the snake eats he grows a little. The snake must avoid running into the walls or running into himself, both of which will end the game.
One of the hardest parts of making the wireframe was the coming up with the logic for all of the different aspects. As you can see below I started to make some designs on how the document would flow and how one function would lead to the next.
Also on day 1 I began the coding I was able to get the basic canvas drawn, the gameLoop function constructed, along with a few different functions and variables that I just made to somewhat structure the start of the logic. 
![Wireframe1](img/Wireframe.png)
![Wireframe2](img/stretchGoals.png)

Day 2 & 3 - 
Day 2 was a very big day as far as progress goes, my goal was to try to get the MVP done by day 3. On day 2 I was faced with the challenge of making most of the game logic including the growth function that I knew I would need to make. This was by far the most challenging part of the project so far because not only was I going to need to rewrite my movement function, but I was also going to need to make a new one that would apply to any tail pieces that would be added to the array. To solve this issue I first started using for loops to loop through all of the tail pieces and then moving them from inside of that loop, but there were problems with that at first where because of the names that I gave everything it was very wordy and confusing. Since then I was able to slim it down and have it make sense too. Below the move function there is the grow function which is pretty simple, it just adds an object to the array of tail parts, and increases the length counter I have.

```javascript
function move() {
for (let i = 0; i < snake.tail.length; i++) {
    ctx.fillStyle = "green";
    ctx.fillRect(snake.tail[i].x, snake.tail[i].y, 20, 20);
    //Check tail x and y's against the head piece
    if (snake.long > 3) {
    if (snake.tail[i].x == snake.x && snake.tail[i].y == snake.y) {
        snake.alive = false;
        topRight.textContent = 'Game Over! Press Space to restart';
    }
}
}
}

function grow() {
    snake.tail.push({x: snake.x, y: snake.y});
    snake.long++;
}
```

Other things that I was able to get working in the MVP version of my project are all of the game over conditions like running into walls and running into yourself, which you can see the logic to up above.