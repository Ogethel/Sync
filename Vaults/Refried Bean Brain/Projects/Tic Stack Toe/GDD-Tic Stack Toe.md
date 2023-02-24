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
		-   Local Multiplayer
		-   Online Multiplayer
		-   SG (Stretch Goal) - Campaign 
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
		- Art; Head & Hands mapped to correct gestures
		- Able to Teleport, Pick up/Place Objects/Manipulate the Gameboard
		- 
		- This is where the projectile originates from  
		- This never needs to move—it’s just representational.  
		- (Changes to Angle/Direction/Velocity do not need to be reflected in the look or position of the player primitive.)  
		- Two Units tall and 0.5 Units wide  
	- **Projectile**  
		- Use a primitive to represent the projectile  
		- The projectile should leave a tracer behind it.  
		- Direction and velocity will be determined by the player  
		- 0.25, 0.25,0.25 units in size  
		- Projectile starts at a height of ½ unit  
	- **NPC primitive**  
		- The NPC should consistently start from a location in front and to the side of the player primitive.  
			- 40 Units in front of the “player primitive”  
			- 5 Units to the side  
		- Size: One Unit Square  
		- The NPC Starts moving when the user fires the projectile.
		- Must move at a fixed rate of speed  
		- It should intersect the projectile in flight, if possible—not simply follow and overtake it.  
		- The NPC leaves a tracer in its wake.  
	- **Game Camera**  
		- Game Camera Needs to capture all the action:  
			- The origination of the shot (“player primitive”)  
			- The NPC origination location  
			- To the intersection of the projectile and NPC  
		- A three-quarter view (not horizontal or top-down)  
	- **Three user input fields across the bottom; These determine the direction and velocity of the Projectile**  
		- You can choose whatever interface design you like...does not need to be fancy  
		- Launch Angle  
		- (“zero” launch angle would be horizontal)  
		- Launch Direction  
		- (“zero” direction would be “straight forward”)  
		- Launch Velocity  
		- A button simply called “Fire”—that fires the projectile.  
			- User MUST select Angle / Direction / Velocity before the FIRE button becomes active/selectable.  
			- A single projectile.  
	- **A visible Timer**  
		- The Timer counts up in Seconds (1,2,3...)  
		- Points are tied to the Timer. Every Second is worth a point. (Example: 5 seconds = 5 points)  
- #### **Level 1**  
	- NPC moves at 15 Units per second  
	- Launch Angle: User can enter an angle between 10 and 85 degrees  
	- Launch Direction: User can enter an angle from -10 to +10 degrees  
	- Launch Velocity: User can enter a Velocity of 1 to 80 (unit per second)  
- #### **Level 2**  
	- NPC moves at 20 Units per second  
	- Launch Angle: User can enter an angle between 25 and 75 degrees  
	- Launch Direction: User can enter an angle from -30 to +30 degrees  
	- Launch Velocity: User can enter a Velocity of 1 to 50 (unit per second)  
	
### **How the “game” is played**  
- **User Adjusts Angle / Direction / Velocity**  
- **User Selects Fire**  
	- The Projectile goes into motion  
	- The NPC goes into motion  
	- The Timer starts counting up in Seconds (1,2,3...)  
	- When the NPC intersects with the Projectile.  
		- All animation stops.  
		- If the intersection happens in the air
		- Across the Top of the screen, it will say “You Win X Points”  (Where “X” is the number of points (seconds) accrued)  
		- If the intersection occurs on the ground  
		- Across the Top of the screen, it will say “You Lose”  
		- The screen will remain visible (with the text) for 5 seconds, and then return to the Main Men

# Visual Development Guide
## Gameplay
## Main Character
## Enemy Concepts
## Current Designs

# Gameplay
## Mechanics
### Gameplay Loop
## Development Platform


