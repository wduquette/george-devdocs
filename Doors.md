# Doors

A door is defined by a `Door` component, which contains:

- The door's state, `CLOSED` or `OPEN`
- The door's terrain type when closed, `closedTerrain`
- The door's sprites by name, `closedSprite` and `openSprite`
- TODO: For locked doors, the name of a `condition` variable that indicates whether it is locked or unlocked.

A data-drive `Region`, as read from disk, can create basic doors from the region as follows:

- Define two terrain tiles, `open_door` and `closed_door`.  
	- `closed_door` tiles should have `TerrainType.DOOR`.
	- `open_door` tiles should have `TerrainType.NONE`.
- The `Region` will create the relevant `Door` component on load.

The `Planner`/`Executer` are responsible for the opening/closing door logic.

The `Animator` is responsible for setting the door's sprite to match its state.

## Futures

- Allow doors to be added to Tiled maps as "feature" objects.  This would allow:
	- Configuring the open and closed sprites
	- Creating locked doors by associating them with a locked condition variable.

- A `Door` can have `TerrainType.DOOR` or `TerrainType.GATE`, depending on whether it's opaque or not.  If a region can commonly have simple doors of both kinds added on the `Features` terrain layer, we might want to add simple "gates"
	- Region could look for `open_gate` and `closed_gate` terrain tiles on load.

## Ponderings

Doors are tricky.

At base a door is a barrier that blocks passage unless open.  There are several kinds.

**Quest Barrier:** a cell that is impassable until the user has completed some particular quest.

**Obstacle:** a quest barrier that vanishes when the quest is completed.  For example, the castle gate might open, and forever stay open; the landslide might be blown away exploded and so be gone.  Obstacles are always special cases, and could be handled by changing or removing a named feature.

**Keyed Door:** is a door that can only be unlocked by the player when in possession of a _key item_.  Once unlocked it remains unlocked, and effectively becomes a normal door.  However, the user must open it explicitly.

**Normal Locked Door:** is a door with a lock that the player might be able to pick given the necessary skills, if I should happen to implement that.  Once picked it becomes a normal door.

**Normal Door:** an unlocked door that can be open or closed, and can be opened or closed by the player.

## Observations

Every door can be open or closed.

A closed door can be locked.

Every door can have a different sprite in each state, and needs to know what the sprites are so that it can switch them when opened/closed.  (I can't assume that there are only two door sprites.)

A locked door is associated with a [[Condition Variable]].  If "locked", the door is locked; if "unlocked", the door is unlocked.

## User Actions

This is tricky, too.  It's reasonable to open a door as the default action when you click on it.  It's unreasonable to close it again when you click on it, because more likely you just wanted to move to that space.  That means the player needs a way to signal their intentions:

- Right click interacts with target (I kind of like this one) and does alternate action (if any)
- Click tool, then click door
- Aim plus keypress
- Click and select open from pop up (or have a context sensitive toolbar that changes based on location)
- Or simply don't allow open doors to be closed.

Not at all sure what the right answer

## Conclusions

Obstacles are distinct from other doors (since they can't be open/closed).

Doors have:

- An open sprite 
- A closed sprite
- An open/closed state
- A locked sprite, possibly null
- A locked condition name, possibly null

A door is locked based on the value of the named condition.

Opening, closing, or unlocking the door's state will select a different sprite.
