# To Do

My current To Do list.

Current Branch: **master**

- [x] Implement Floobham "mannikins"
- [x] Add `App.println()`, and make it redirect to the Debugger when the debugger is open.
- [x] Make entity IDs global
- [x] Simplify entity transfer
- [ ] Provide better Mannikin names.
- [ ] Implement Items and Chests
- Things to Ponder
	- [ ] Consider managing mannikin strings that they don't repeat until all have been seen.
	- [ ] Consider generalizing signs and mannikins to be one kind of thing.
	- [ ] Consider defining a basic NPC dialog mechanism, and revising mannikins to use it.
	- [ ] Consider merging strings into a global table.
- Debugger
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