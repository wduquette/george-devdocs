# Exit Entity
#doc 

An exit entity represents an exit from this [[Region]] to another region.  It consists of:

- An `Exit` component, defining the name of the other region and the name of a [[Point Entity]] in that region.
- The `Loc` of the cell the player character must enter to be transferred to the other region

The given cell will usually also have:

- A `Feature`, to determine the exit's passability.  A player character can only use passable exits.
- A `Sprite`, to display the exit.

However, these can be defined by the same entity or a different one.

## Operation

The player clicks on the exit.  The player's character maneuvers to the exit; and if it is passable, is transferred to the relevant region.