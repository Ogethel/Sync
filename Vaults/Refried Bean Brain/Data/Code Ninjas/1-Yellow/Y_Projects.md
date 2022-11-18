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


```

## 03-01 Hiding Ninja
```js


```

## 03-02 Hiding Ninjas
```js


```

## 03-03 Whack a Ninja
```js


```

## 03-04 Ninja Supplies
```js


```

## PY - What's Inside?
```js


```

## PY - Rock Paper Scissors
```js


```

## 04-01 Bumper Car
```js


```

## 04-02 Balloon Protect
```js


```

## 04-03 Ninja Snacks
```js


```

## 04-04 Shuriken Toss p1
```js


```

## 04-05 Space Tour
```js


```

## 04-06 Shuriken Toss p2
```js


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