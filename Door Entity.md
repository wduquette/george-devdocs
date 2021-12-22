# Door Entity
#doc 

A door entity defines a door, a feature that can be opened and closed.  It is defined by:

- A `Door` component that defines
	- The door's current state, open or closed
	- Its terrain type when closed
	- The sprite to use when closed
	- The sprite to use when open
	- #todo For locked doors, a condition variable that indicates whether it is locked or not.
- A `Loc` for its location
- A `Feature` for its terrain type, based on whether it is open or closed.
- A `Sprite` for its appearance, based on whether it is open or closed.

## Operation

The player selects a closed door on the map.  The player's character moves to the door, and opens it, changing the entity's `Door`, `Feature`, and `Sprite` components to allow passage.