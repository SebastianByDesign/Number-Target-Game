# Number Target Game

A fix for the Codecademy Learn ReactJS tutorial game.

### How To Play ###

From the Codecademy Lesson:

> The goal of this game is to click on high numbers. Every click has to be a higher number than the previous click.

### The Problem ###

The game's sole purpose was to teach how to use React Lifecycle Methods, not so much to be fully functional. 

The following issues were present:
- After beating the game, the background color turns yellow, but the number targets keep popping up 
- The game only ends by clicking on a number that is lower than the Top Number
- Clicking on New Game after beating the game results in the screen returning to yellow
- The Top Number does not reset when you click New Game

### The Solution ###

To challenge myself, I fixed these issues by making a couple changes and additions to the code.

1. Added another if statement in componentDidUpdate of App.js to end the game when the player reaches or surpasses 950,000.
```jsx
    if (this.state.latestClick >= 950*1000) {
      this.endGame();
```
2. Added `this.state.highest = 0;` in componentWillUpdate of TopNumber.js if the game is reset.
3. Changed the playing field's width from 250px to 90%, to play on fullscreen.
