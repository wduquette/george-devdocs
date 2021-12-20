# To Do

My current To Do list.

- [x] Look at the Old George "World" map code and see if there's anything special I missed.
- [x] Add Exits to the entities table
- [x] Add another region, e.g., Floobham
- [x] See how Floobham defines features
- [x] Create global image set solution
	- [x] (?) Images loaded from any region or sprite set should be globally accessible by name. 
	- [x] Sprites and terrain tiles should share an interface. 
- [ ] Implement [[Doors]].
- [ ] Move devdocs to its own repo.
- [ ] Support moving to another region, e.g., Floobham
- [ ] Implement Floobham "mannikins"
- [ ] Implement debugger
	- [ ] Pops up on F1.
	- [ ] Distinct window
	- [ ] Entity tab with live list of entities
	- [ ] Conditions tab with live list of condition variables, + control.
	- [ ] Ability to jump to region
- [ ] Implement Floobham NPCs
- [ ] Implement movement limits (the player can only move so far)
- [ ] Implement Mover list
	- Probably a `Mover` sealed type.  
	- `Mover.Leader(playerId)`
	- `Mover.Monsters()` (if all monsters move at the same time)
- [ ] Allow the Tiled map object for Signs to include a sprite name for display. 
- [ ] Render log messages on the map as a heads up display. (?)
- [ ] Render quest status on the map as a heads-up display
- [ ] Script to copy asset files to `resources`
- [ ] Implement Old George's Line-of-Sight algorithm generically.
- [ ] Ponder [[Saving the Game]]

_Created on 2021-11-27._