
TruGolf: Unity Developer Test  

### **Submission should include:**  
- Zip File containing the Unity Project. It should be ready to build and run.  
- Comments about how you obtained the solution and overcame some of the complexity. Let us  know how long you spent on the task.  

### **Basic Functionality**  
- User fires a projectile (subject to physics, not simply a vector)  
- A NPC begins moving at a constant speed to intersect the projectile in flight.  
- A timer counts up.  
- Points are accrued and rewarded  

### **Details**  
- **Game Resolution set to 1280x1024**  
- **Starting the program, starts a “session” that is active until the “game” is closed.**  
- **Main Menu**  
	- Display “Current Score is: X” (where “X” is the current total of ALL accrued points this  session)  
	- Option Level 1  
	- Option Level 2  
	- Option Exit  
	- If/When the level is completed, they are returned to this menu, and allowed to make any other selection.  
- Set this up as unit =meter  
- Use primitives—we don’t need to get fancy.  

- #### **Levels (Generic)**  
	- **A player primitive**  
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