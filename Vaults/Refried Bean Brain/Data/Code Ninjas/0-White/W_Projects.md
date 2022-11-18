[[HUB-Code Ninjas]]
# White Belt
[[GDP Functions and Examples]]
## Prove Yourself - Under the Stars
```js
spin(yStar, -25);
spin(bStar, 35);
```
## 03-02 Laser Chase
```js
if(laser.x()<getMouseX()){
    moveX(laser, 325);
}

if (laser.x()>getMouseX()){
    moveX(laser, -325);
}
```
## 03-03 Space Zapper
```js

if(ship.y()<getMouseY()){
    moveY(ship, 400);
}

if (ship.y()>getMouseY()){
    moveY(ship, -400);
}

// For Fun Code
// Scene -> Initialize when scene starts
$this.changeScale = function(){

    if (star.scaleX() < 2 && star.scaleX() > .9){
        star.scaleX(star.scaleX()+0.1);
        star.scaleY(star.scaleY()+0.1);
        
        if (star.scaleX() > 2){

            star.scaleX(1);
            star.scaleY(1);
        }
    }

}

if ($this.scene.state() == "PLAY"){

    createTimer(900, $this.changeScale);
}

// star object -> Update Every Frame
if($this.scaleX() < 1.5){
    spin($this, 25);
}else{
    spin($this, -45);
}

// console.log(star.scaleX());
```

## 04-01 Coconut Chaos
```js
if (isKeyPressed(Keys.rightArrow)){
    moveX(ninjas, 300);
}

if (isKeyPressed(Keys.leftArrow)){
    moveX(ninjas, -300);
}
```

## Hungry Ninja
```js
// Place in Scene->Update Every Frame
// Move Ninja onto top conveyer belt
if (isKeyPresed(Keys.upArrow)){
	ninja.x(400);
	ninja.y(240);
}

if (isKeyPressed(Keys.leftArrow)){
	ninja.x(340);
	ninja.y(300);
}

if (isKeyPressed(Keys.downArrow)){
	ninja.x(400);
	ninja.y(360);
}

if (isKeyPressed(Keys.rightArrow)){
	ninja.x(460);
	ninja.y(300);
}

if (ninja.ateFood()){
	ninja.score += 1;
	scoreLabel.text(ninja.score);
}


```

## Prove Yourself - Air Hockey
```js
/**
 * leftPaddle
 * if the up arrow is pressed, move the leftPaddle up
 * if the down arrow is pressed, move the leftPaddle down
**/
// -400 is up because (0,0) is in the upper left of screen
if (isKeyPressed(Keys.upArrow) || isKeyPressed(Keys.w)){
	moveY(leftPaddle, -500);
}

if (isKeyPressed(Keys.downArrow) || isKeyPressed(Keys.s)){
	moveY(leftPaddle, 500);
}

/**
 * rightPaddle
 * if the rightPaddle is below the mouse, move the rightPaddle up
 * if the rightPaddle is above the mouse, move the rightPaddle down
**/

if (rightPaddle.y() > getMouseY()){
	moveY(rightPaddle, -500);
}

if (rightPaddle.y() < getMouseY()){
	moveY(rightPaddle, 500);
}

/**
 * walls
 * if the ball touches right wall, give player 1 a point and reset the ball
 * if the ball touches left wall, give player 2 a point and reset the ball
**/

if (ball.isTouchingRightWall()){
	leftPaddle.score += 1;
	leftScoreLabel.text(leftPaddle.score);
	ball.x(400);
	ball.y(300);
}

if (ball.isTouchingLeftWall()){
	rightPaddle.score += 1;
	rightScoreLabel.text(rightPaddle.score);
	ball.x(400);
	ball.y(300);
}
```