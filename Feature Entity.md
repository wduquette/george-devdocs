# Feature Entity
#doc 

A feature entity represents some static terrain feature that is rendered on top of the base terrain.  There many kinds of feature.

Features are rendered after the base terrain but before [[Mobile Entity|mobiles]].

Every feature will have:

- A `Feature` component, giving the feature's `TerrainType` (which may be none)
- A `Loc`, giving its location
- A `Sprite`, determining its appearance.

A feature entity can also be a [[Door Entity]], a [[Sign Entity]], etc.