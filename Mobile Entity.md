# Mobile Entity

A mobile entity represents a creature that can move about the map.  Mobiles are rendered after [[Feature Entity|features]] but before [[VisualEffect Entity|visual effects]].

There are several kinds of mobile.  Every mobile will have:

- A `Mobile` component
- A `Loc`
- A `Sprite`

When a mobile is actively moving, it will have a `Plan` component, which defines its planned movement.  The [[Planner System]] provides the plan, and the [[Executor System]] executes it.  The `Plan` component is removed when the move is complete.

A mobile entity can be a [[Player Entity]], etc.