# Point Entity
#doc 

A point entity names a point on the map.  A point entity has:

- A `Point` component that gives it a name.
- A `Loc`: the map location


Points are not rendered.

## Operation

- When a player character is transferred into a region, it is placed at a point named by the [[Exit Entity]] that triggered the transfer.
- When the game begins, the player is placed at the point called `origin` on the "Overworld" map.

