[[HUB-Code Ninjas]]
[[Orange Belt]]

```js
// this function takes an array
// shuffles it randomly and returns it
$this.shuffle = function(arr){
    arr.sort(() => random(1, -1));
    return arr;
};

// set up the scene
if($this.scene.state()=="PLAY"){

    // Solution as an ortered arry of tile numbers
    $this.solution=[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 0];
    // Shuffle funtion will randomize the tiles
    $this.puzzleTiles=$this.shuffle([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 0]);
    
    // Loop helper variables to aid in placing tiles
    var xOffset=200;
    var yOffset=100;
    var tileSpacing=100;
    // Variable to itterate through the array
    var tileIndex = 0;
    console.log(tileIndex);
    // Loop to itterate through our array and place the tiles
    for (var row=0;row<4;row++) {
        console.log("for loop 1");
        for (var col=0;col<4;col++) {
            console.log("for loop 2");
            // find the current tile in the shuffled array
            var currentTileNumber=$this.puzzleTiles[tileIndex];

            console.log(currentTileNumber);
            // find the tile object
            var tile = $this.findName("tile" + currentTileNumber);
            // assign the tile its number for future use
            tile.number = currentTileNumber;
            // make the tile see through
            tile.opacity(0.5);
            // place the tile in the correct spot in the gird
            tile.x(col * tileSpacing + xOffset);
            tile.y(row * tileSpacing + yOffset);
            // increment tileIndex to move to the next tile
            tileIndex++;
        }
    }
    
}

$this.checkMove = function(clickedTile){
    var xDistance = Math.abs(clickedTile.x() - tile0.x());
    var yDistance = Math.abs(clickedTile.y() - tile0.y());
    
    if ((xDistance === 100 && yDistance === 0) || (xDistance === 0 && yDistance === 100)){
        var originalClickedTileX = clickedTile.x();
        var originalClickedTileY = clickedTile.y();
        
        clickedTile.x(tile0.x());
        clickedTile.y(tile0.y());
    }
};
```
