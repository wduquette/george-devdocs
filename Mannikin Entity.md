# Mannikin Entity
#doc 

A mannikin entity is the simplest kind of [[NPC]].  It has no behavior of its own, but can tell the player one of a number of things when the player interacts with it.  Every mannikin entity has:

- A `Mannikin` component, giving its name.
- A `Loc` component, giving its location
- A `Feature` component, giving its terrain type.
	- Mannikins usually stand on what would normally be floor; but they aren't passable, so they usually have a terrain type of `FENCE`.
- A `Sprite` component

## Operation

A mannikin has at least three entries in the region's strings table:

- `<name>.name`: The name for display
- `<name>.description`: A brief description
- `<name>.greeting*`: One or more "greetings".

When the player interacts with the mannikin, an overlay displays its Sprite (and background terrain), its display name, description, and a randomly chosen greeting from its list.