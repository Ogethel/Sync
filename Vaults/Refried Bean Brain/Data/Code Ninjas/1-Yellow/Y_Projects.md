[[HUB-Code Ninjas]]
# Yellow Belt
## 01-01 Rain Catcher p1
```js
// rain -> Update Every Frame
// Make each clone fall with moveY($this)
moveY($this); 

// Bonus, change the speed of the rain
// Speed is controlled by the properties panel, changed x speed from 50 -> 75
```

## 01-02 Rain Catcher p2
```js
// turtle(group) -> Update Every Frame
var rightArrowPressed = isKeyPressed(Keys.rightArrow);

if(rightArrowPressed){
    moveX($this, $this.speedX());
}

var leftArrowPressed = isKeyPressed(Keys.leftArrow);

if(leftArrowPressed){
    moveX($this, -$this.speedX());
}

// turtle(sprite) -> Update Every Frame
// Didn't like it animating all the time
if(isKeyPressed(Keys.leftArrow) || isKeyPressed(Keys.rightArrow)){
    $this.incrementAnimation(); // Technically all that was needed
}

```

## 01-03 Rain Catcher p3
```js
// First time working with Initialize When Scene Starts
// Working with random method
if($this.scene.state() == "Play"){
	createTimer(1000, function(){
		var ndrop = drop.clone();
		var rainX = random(760, 40);
		ndrop.x(rainX);
		ndrop.y(10);
	});
}

// Updated example for the Turtle Movement component
var rightArrowPressed = isKeyPressed(Keys.rightArrow);
if(rightArrowPressed && $this.x()<700){
    moveX($this);
    if($this.scaleX()<0){
        $this.scaleX(-$this.scaleX());
    }
    var sp = $this.findName("turtleSprite");
    sp.incrementAnimation();
}
var leftArrowPressed = isKeyPressed(Keys.leftArrow);
if(leftArrowPressed && $this.x()>100){
    moveX($this, -$this.speedX());
    if($this.scaleX()>0){
        $this.scaleX(-$this.scaleX());
    }
    var sp = $this.findName("turtleSprite");
    sp.incrementAnimation();
}
```

## 01-04 Rain Catcher p4
```js
// Clone Lighting bolt(and be carefull of syntax as it has to be right on variables and doesn't tell you if they're wrong)
if($this.scene.state() == "PLAY") {
    createTimer(1000, function() {
    	var ndrop = drop.clone();
    	var rainx = random(760, 40);
    	ndrop.x(rainx);
    	ndrop.y(10);
    	
    });

    createTimer(3000, function() {
    	var nbolt = bolt.clone();
    	var boltx = random(760, 40);
    	nbolt.x(boltx);
    	nbolt.y(10);
    	
    });
}

// Tabs don't matter so this could also be written:
if($this.scene.state() == "PLAY") {
createTimer(1000, function() {
	var ndrop = drop.clone();
	var rainx = random(760, 40);
	ndrop.x(rainx);
	ndrop.y(10);
	
});

createTimer(3000, function() {
	var nbolt = bolt.clone();
	var boltx = random(760, 40);
	nbolt.x(boltx);
	nbolt.y(10);
	
});

}
// And it would run fine
```

## 01-05 Rain Catcher p5
```js
if($this.scene.state() == "PLAY"){
    createTimer(1000,  function(){
    var ndrop = drop.clone();
    var rainX = random(760,40);
    ndrop.x(rainX);
    ndrop.y(10); 
    });
    
    createTimer(5000, function(){
        var nbolt = bolt.clone();
        var boltx = random(760,40);
        nbolt.x(boltx);
        nbolt.y(10);
    });
    
    //Add createTimer function for snowflake here
    createTimer(7000, function(){ // 500 = half second
        var nflake = snowflake.clone();
        var flakex = random(760,40);
        nflake.x(flakex);
        nflake.y(10);
    });

}

```

## 01-06 Rain Catcher p6
```js
// if the bucket's powerup equals "frozen"
// OR if the timer equals null
if ($this.powerup == "frozen" || $this.timer === null){
    // change the color of the bucket to blue
    $this.fill("#0000FF");
    $this.timer = createTimer(2000, function(){
        // after 2 seconds, powerup is null
        $this.powerup = null;
    }, false);
    
} else if($this.powerup === null){
    // change the bucket color back to grey
    $this.fill("#BBBBBB");
}

```

## PY - Rain Catcher Complete
```js


```

## PY - Color Change
```js
// Purple Logic
rectangle.fill("#9608AF");

// Green Logic
rectangle.fill("#43C318");

// Blue Logic
rectangle.fill("#186EC3");

// Red Logic
rectangle.fill("#DE2121");

// Yellow Logic
rectangle.fill("#FEFD06");


```

## 02-01 Meteors p1
```js
var rot = random(359);
$this.rotation(rot);
```

## 02-02 Meteors p2
```js
// Existing Initialize Metor Code:
moveX($this);
moveY($this);

var bullet = $this.scene.projectile;

if(bullet && $this.isTouching(bullet)){
    
    $this.scaleX($this.scaleX()/2);
    $this.scaleY($this.scaleY()/2);
    $this.offsetX($this.offsetX()/2);
    $this.offsetY($this.offsetY()/2);
    
    $this.scene.projectile = null;
    bullet.remove();
    
    $this.scene.scoreValue++;
    score.text("Score: "+$this.scene.scoreValue);
    //this is where you add the code in step 3, inside the if ($this.isTouching(bullet)) statement
    if($this.scaleX() >= 0.25){
		var ncircle = $this.clone();
		ncircle.x($this.x() + 100);
		
	} else {
		$this.remove();
	}
}

if($this.y()>700){
    $this.y(0);
}

if($this.y()<-100){
    $this.y(600);
}

if($this.x()>900){
    $this.x(0);
}

if($this.x()<-100){
    $this.x(800);
}



```

## PY - Rolling Dice
```js
var rollD1 = Math.round(random(5));
die1.frameIndex(rollD1);

var rollD2 = Math.round(random(5));
die2.frameIndex(rollD2);

totalText.text(rollD1 + rollD2 + 2);

```

## 03-01 Hiding Ninja
```js
ninja.toggleVisible();

if($this.scene.state() == "PLAY"){
    var ninjaTime1 = random(3000,1000);
    createTimer(ninjaTime1, function(){
        ninja.toggleVisible();
    });
}


```

## 03-02 Hiding Ninjas
```js
// Base Code
if($this.scene.state() == "PLAY"){
    var ninjaTime1 = random(3000, 1000)
  createTimer(ninjaTime1,  function(){
        ninja_1.toggleVisible();
    });  
    var ninjaTime2 = random(3000, 1000)
  createTimer(ninjaTime2,  function(){
        ninja_2.toggleVisible();
    });
    var ninjaTime3 = random(3000, 1000)
  createTimer(ninjaTime3,  function(){
        ninja_3.toggleVisible();
    });
    var ninjaTime4 = random(3000, 1000)
  createTimer(ninjaTime4,  function(){
        ninja_4.toggleVisible();
    });
}
// Each ninja also has the following under initialize:
if($this.scene.state() == "PLAY"){
    $this.visible(false);
}

// Solution:
// On ninjas 1 through 4 add the following under the Mouse Click Event
$this.toggleVisible();

// Added Code for a more fuctional game:
// Mouse click for each ninja:
if($this.visible()){
    $this.toggleVisible();
    $this.scene.score+=1;
    lblScore.text($this.scene.score);
}
// Initialize for each ninja
if($this.scene.state() == "PLAY"){
    $this.visible(false);
}

// Revized Initialize Function for the game scene
$this.score = 0;
if($this.scene.state() == "PLAY"){
    var ninjaTime1 = random(3000, 1000)
  createTimer(ninjaTime1,  function(){
        if(ninja_1.visible()){
            $this.scene.score-=1;
            lblScore.text($this.scene.score);
        }
        ninja_1.toggleVisible();
    });  
    var ninjaTime2 = random(3000, 1000)
  createTimer(ninjaTime2,  function(){
        if(ninja_2.visible()){
            $this.scene.score-=1;
            lblScore.text($this.scene.score);
        }
        ninja_2.toggleVisible();
    });
    var ninjaTime3 = random(3000, 1000)
  createTimer(ninjaTime3,  function(){
        if(ninja_3.visible()){
            $this.scene.score-=1;
            lblScore.text($this.scene.score);
        }
        ninja_3.toggleVisible();
    });
    var ninjaTime4 = random(3000, 1000)
  createTimer(ninjaTime4,  function(){
        if(ninja_4.visible()){
            $this.scene.score-=1;
            lblScore.text($this.scene.score);
        }
        ninja_4.toggleVisible();
    });
}


```

## 03-03 Whack a Ninja
```js
// Scene
$this.scene.score = 0;
if($this.scene.state() == "PLAY"){
    ninja_1.visible(false);
    ninja_2.visible(false);
    ninja_3.visible(false);
    ninja_4.visible(false);
    ninja_5.visible(false);
  
    //write the code for step 3 (ninja_1) here
    var ninjaTime1 = random(3000, 1000);
    
    createTimer(ninjaTime1, function(){
        if(ninja_1.visible()){
            ninja_1.visible(false); // Hides the ninja
        } else {
            ninja_1.visible(true); // Reveals the ninja
        }
    });
    //write the code for step 4 (ninja_2) here
        var ninjaTime2 = random(3000, 1000);
    
    createTimer(ninjaTime2, function(){
        if(ninja_2.visible()){
            ninja_.visible(false); // Hides the ninja
        } else {
            ninja_2.visible(true); // Reveals the ninja
        }
    });
    //write the code for step 4 (ninja_3) here
        var ninjaTime3 = random(3000, 1000);
    
    createTimer(ninjaTime3, function(){
        if(ninja_3.visible()){
            ninja_3.visible(false); // Hides the ninja
        } else {
            ninja_3.visible(true); // Reveals the ninja
        }
    });
    //write the code for step 4 (ninja_4) here
        var ninjaTime4 = random(3000, 1000);
    
    createTimer(ninjaTime4, function(){
        if(ninja_4.visible()){
            ninja_4.visible(false); // Hides the ninja
        } else {
            ninja_4.visible(true); // Reveals the ninja
        }
    });
    //write the code for step 4 (ninja_5) here
        var ninjaTime5 = random(3000, 1000);
    
    createTimer(ninjaTime5, function(){
        if(ninja_5.visible()){
            ninja_5.visible(false); // Hides the ninja
        } else {
            ninja_5.visible(true); // Reveals the ninja
        }
    });
}

// Under each Ninja
$this.scene.score+=1;
score.text($this.scene.score);

if($this.visible()){
    $this.visible(false);
}

// Bonus Changes
// Scene Initialize
$this.scene.score = 0;
if($this.scene.state() == "PLAY"){
    ninja_1.visible(false);
    ninja_2.visible(false);
    ninja_3.visible(false);
    ninja_4.visible(false);
    ninja_5.visible(false);
}

// Background Mouse Click
$this.scene.score-=1;
score.text($this.scene.score);

```

## 03-04 Ninja Supplies
```js
// for the sword, star, and staff place the following in the mouse up function:
if ($this.isTouching(ninja)){
    $this.remove(); // Remove the orginal sword
    star.toggleDraggable(); // make the ninja star draggable, change to staff on star
    swordIcon.toggleVisible();
    // Makes the sword icon visible, change to star and then staff
} else {
    // otherwise the sword should return to the pile, these change per object
    $this.y(314);
}

```

## PY - What's Inside?
```js
// Objective:
// When a door is clicked on, it opens and shows a random picture
// Clicking again closes the door and hides the picture
// Only 1 door can be open at a time
// Do this by hiding and revealing door sprites
// The images are randomized by frame number

// Hint: you'll need to use a round fuction to find the correct frameIndex! 
// Use the code below as a reference:

// card_1.frameIndex(Math.round(random(8, 1)));

// Scene Initialize:
if($this.scene.state() == "PLAY"){
    card_1.frameIndex(Math.round(random(8, 1)));
    card_2.frameIndex(Math.round(random(8, 1)));
    card_3.frameIndex(Math.round(random(8, 1)));
    card_4.frameIndex(Math.round(random(8, 1)));
}

// Closed Door Mouse Click
if($this.visible()){
    if (openDoor1.visible()){
        openDoor1.toggleVisible();
        door_1.toggleVisible();
    }
    if (openDoor2.visible()){
        openDoor2.toggleVisible();
        door_2.toggleVisible();
    }
    if (openDoor3.visible()){
        openDoor3.toggleVisible();
        door_3.toggleVisible();
    }
    $this.toggleVisible();
    openDoor4.toggleVisible();
}

// Initialize
if($this.scene.state() == "PLAY"){
    $this.toggleDraggable();
}

// Open Door Initialize
if($this.scene.state() == "PLAY"){
    $this.toggleVisible(false);
    $this.toggleDraggable();
}
```

## PY - Rock Paper Scissors
```js
// Code for Each Button Option, on Mouse Click
var ran1 = Math.round(random(2,0));
RPS1.frameIndex(ran1);
RPS2.frameIndex(2);

if (ran1 == 2){
    results.text("It's a Tie!");
}

if (ran1 == 1){
    results.text("You Lost!");
}

if (ran1 === 0){
    results.text("You Won!");
}

```

## PY - Robot Builder
```js
// On Each Part
if($this.isTouching(bodySpace)){
    $this.x(336);
    $this.y(204);
    $this.draggable(false);
}

```
## 04-01 Bumper Car
```js


```

## 04-02 Balloon Protect
```js
//Update every Frame
$this.moveForward(1);

if($this.isTouching(balloon)){
    balloon.remove();
}

if($this.x()>770){ // Value was 30 for other dot & Sign was flipped
    $this.flipDirection();
}

//Mouse Button Up
$this.flipDirection();

```

## 04-03 Ninja Snacks
```js
// Scene Intialize:
if($this.scene.state() == "PLAY"){
    createTimer(3000, function(){
        var napple = apple.clone();
        napple.x(680);
        napple.y(14);
    });
}

// Apple Update
var mouth = ninja.findName("mouth");

if(!$this.clicked){
    $this.moveY(100);
    if($this.y()>600){
        $this.remove();
    }
}

if($this.isTouching(mouth)){
    $this.remove();
}

// Apple Initialize
$this.draggable(false);

// Apple Mouse Click
var mouth = ninja.findName("mouth");

$this.moveTo(mouth.x,mouth.y);

// Ninja Update:
$this.moveForward(1);
if($this.y() <= -130 || $this.y() >= 50){
    $this.flipDirection();
}

```

## 04-04 Shuriken Toss p1
```js
// Target Mouse Click
star.moveToObject($this);

```

## 04-05 Space Tour
```js
// Meteor Mouse Click
rocket.pointToObject($this);
rocket.moveToObject($this);

```

## 04-06 Shuriken Toss p2
```js
// Star Update Every Frame
if($this.thrown && $this.x()>0 && $this.x()<800 && $this.y()>0 && $this.y()<600){
    $this.moveForwardByRotation();
} else{
    $this.thrown=false;
    $this.x(454);
    $this.y(462);
}

// background mouse click
if(!star.thrown){
    star.pointToCursor();
    star.rotation(star.rotation() - 90);
    star.thrown=true;
}

// ninja Initialize
if($this.scene.state() == "PLAY"){
createTimer(3000,  function(){
    var ntarget = target.clone();
    ntarget.x(730);
    ntarget.y(34); 
});
}

// Target update every frame
if($this.isTouching(star)){
    star.x(454);
    star.y(462);
    star.thrown=false;
    $this.remove();
}

if($this.x() <= 0){
    $this.remove();
}
moveX($this,-50);
```

## 04-07 Ninja Battle
```js


```

## PY - Candy Sort
```js


```

## 05-01 Starscape
```js


```

## 05-02 Zapper p1
```js


```

## 05-03 Zapper p2
```js


```

## 05-04 Wall Blaster
```js


```

## PY - Color Change p2
```js


```

## PY - Bubbles
```js


```

## 06-01 Meteors Deluxe
```js


```

## PY- Bug Invaders
```js


```