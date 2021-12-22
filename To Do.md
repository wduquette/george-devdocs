# To Do

My current To Do list.

Current Branch: **master**

- [x] Implement Floobham "mannikins"
- [ ] Consider managing mannikins strings that they don't repeat until all have been seen.
- [ ] Define a basic NPC dialog mechanism, and revise mannikins to use it.
- [ ] Consider merging strings into a global table.
- [ ] Implement control bar in GameView
	- [ ] And implement the inspection tool.
	- [ ] Add a normal movement button.
- [ ] Implement debugger
	- [ ] Conditions tab with live list of condition variables, + control.
- [ ] Define user interaction for closing doors.
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