# Sign Entity
#doc 

A sign entity is a [[Feature Entity]] representing a sign the user can click on and read.  Every sign entity has:

- A `Sign` component giving the sign's name
- A `Loc`
- A `Feature` giving its terrain type (if any) and determining when it is rendered
- A `Sprite`

## Operation

The sign's name is the name of the string in the region's strings table.  When the player triggers the sign, its sprite and the string value are displayed on an overlay until the user clicks again. 