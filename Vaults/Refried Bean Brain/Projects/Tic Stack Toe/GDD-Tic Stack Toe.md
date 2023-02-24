[[D-Tic Stack Toe]]


# Project Overview

### Summary:
Completely reproduce the Tic Stack Toe game in Unity.  At a high level this includes basic VR functionality of being able to move and interact with objects; The ability to place Xs and Os on a 4x4 grid with the ability to stack; Check win function that checks if there is a four in a row; Multiplayer; An AI system for playing against in the case that local or multiplayer is unavailable.

### Stretch Goals:
- Develop a world/setting to play in
- Develop a single player campaign
### **Finished Game Should Include:**  
- A Build that is bug free and uploaded to Itch.io and/or Steam
- Well documented assets and scripts that I can add to a Unity repo on github that can serve as a starting point for future projects
- Comments about how you obtained the solution and overcame some of the complexity.
- Document how long I spent on the project for future reference.

### **Basic Functionality**  
-   VR Player base class that obtains stats via scriptable objects
-   Base X/O Intractable
-   Board Logic; including placing pieces and detecting winning situations
-   An AI for playing against in single player. 
-   Turn timer that is configured pre game and which lasts the whole match. 
-   Online and Local Multiplayer
	-   Eventually cross compatible across platforms
-   Stretch Goals

### **Details**  
-   Game Resolution set to 1280x1024 for VR, but UI should be resolutions agnostic
-   Starting the program, starts a “session” that is active until the “game” is closed. 
-   Main Menu 
	-   Game Mode
		-   Single Player
			- Main Menu
				- Session Settings
					- Adjust Settings
					- Play
		-   Local Multiplayer
			- Main Menu
			- Session Settings
				- Adjust Settings
				- Play
		-   Online Multiplayer
			- Main Menu
			- Session Settings
				- Adjust Settings
				- Play
		-   SG (Stretch Goal) - Campaign 
			- Mission Select
	-   How to Play
		-   Slideshow
		-   Tutorial Level
	-   Settings
		-   Controls/Keybinds
		-   Music
		-   Multiplayer Voice Chat
	-   Exit 
-   If/When a game is finished, a reset, select level, continue, or exit option will appear above the table 

-   Scene Unit in Unity defaults to a meter, use this as the point of reference for asset development.
-   Prototype with primitives
-   Replace with Art Assets as they come in

- #### **Levels (Generic)**  
	- **A player primitive**  
		- Art; Head & Hands mapped to correct gestures, Stretch-Skins
		- Camera Spawned at Head Height
		- Able to Teleport, Pick up/Place Objects/Manipulate the Gameboard
		- Local and Online Multiplayer compatible
	- **Interactable/Gameboard Logic**  
		- Art; 1 Board, 2 Game Pieces, Stretch-Skins
		- **Board**
			- Should be in a Central Location
			- Thematic for the level (1800s, Sci-fi, etc.)
			- **Game Logic**
				- Understand where each piece is
				- Check for valid moves
				- Check for Win conditions
				- Display Widget for valid moves
		- **X-Game Piece**
			- Retrievable from a central location
			- Capable of being realistically interacted with (Stacked to pass time, knocked over, etc.)
			- Is only placed on board when released while widget active
				- Either player can move spawned extra pieces, but only the X player may place X pieces on the board
		- **O-Game Piece**
			- Same as X-Game Piece
		- **Skins**
			- 1-12 Game Piece Skins?
	- **AI Behavior**  
		- Art; AI should have at least a color distinction from normal players
		- Procedural Animation
			- Arc is calculated from the rest position to Game Piece Spawn location
			- Arc is calculated from Game Piece Spawn to square AI would like to move to
		- Behaviour Tree
			- Turn Begin/Calculate Move
			- Take Turn/Place Piece State
			- Turn End State
			- Idle State
			- Win Game State
			- Loose Game State
		- Clear Debugs should be used for testing
	- **Game Camera**  
		- Game Camera Needs to capture all the action:  
			- The origination of the shot (“player primitive”)  
			- The NPC origination location  
			- To the intersection of the projectile and NPC  
		- A three-quarter view (not horizontal or top-down)  
	- **Level Flow**  
		- X-Player begins and places piece
		- O-Player then takes their turn and the cycle repeats
		- On Turn Change, notification will display briefly as well as a in world visual clue 
		- Players may pause at anytime
			- For Online matches, leaving the game must be accompanied by a short message selected prior to quitting
		- Once a Player has won, the table will display options
			- Play Again
			- Back to Main Menu
			- Back to Multiplayer HUB
			- Quit Application
	- **Turn Timer (When Set/In Campaign)**  
		- When Selected, a Turn Timer will be displayed in game
		- When a Player's time reaches 0, a random spot on the board will be selected and play passed to the opposing player
		- 3 Missed Turns in a row will boot you from an online match
- #### **Level 1**  
	- A Library like Room, fun interactable books
- #### **Level 2**  
	- Sci-fi Room, fun lights and sounds to engage with
	
### **Additional Design Notes**  
- **Target Demographic**
	- Currently it is just me and Brandon
	- (Need to research)

# Visual Development Guide
## Gameplay
## Main Character
## Enemy Concepts
## Current Designs

# Gameplay
## Mechanics
### Gameplay Loop
## Development Platform


