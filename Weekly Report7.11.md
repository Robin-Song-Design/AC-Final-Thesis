## Technical Progress

Succesfully wrote the pipeline of **writing trajectory file and reload it** into grasshopper visualization.
## Testing on Models

Collision Free Model:
Best Performance. But because of no collision, it's hard to see where agents will be stucked.

Social Force Model:
Agents are easily stucked and never continue to move, but I have not found out how to change params to fix it.  **At least from this model I can tell where most probably the agents will be stucked.**

![[Pasted image 20250711164202.png]]

**Agents tend to get stuck :**
	1. At large corners; 
	2. in multiple nested rooms (with two doors); 
	3. in meeting rooms with only a single passage in the middle;
	4. obstacles near the exit.
## Experiments design:

Because I have just set up the pipeline, I didn't set up a bunch of experiments.
#### I am thinking about doing the following:

**1. Corner Congestion Issues**
- **Parameters to Test**: Corner radius , corridor width expansion (1.5× normal width at turns), Corner geometry, obstacle clearance distance (3m radius), intermediate waypoint placement

**2. Multi-Room Transition Problems**
- **Parameters to Test**: Door spacing (≥3m), transition zone width (2× door width), door width progression (1.2m → 1.5m),Door alignment (offset vs. direct)

**3. Single Corridor Bottlenecks**
- **Parameters to Test**: 
	- Main corridor width (2.4m), 
	- auxiliary corridor addition (1.2m each side), 

**4. Exit Proximity Obstacles**
- **Parameters to Test**: Obstacle clearance distance (5m from exits), exit width standards (≥1.5m single, ≥1.2m dual)

