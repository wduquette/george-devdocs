# Entity
#doc 

An `Entity` is an object that exists as part of a [[Region]].  Entities can represent many different things, including static terrain features, mobiles (e.g., monsters), and labeled points of interest.

Each `Entity` has a unique ID (a Java `long`) and some number of attached [[Component|components]].  The components compose, [[Entity Component System]] fashion, to represent a single object.

- The `Entity` contains a `TypeMap`: a hash map where the key is a `Class<? extends Component>` and the value is an instance of that class.  This allows each entity to be defined by a different constellation of components; and further allows the application to query an entity for the components it has.

## Component Types

For a full list of component types, see the `com.wjduquette.george.ecs` package.  There are several components that used by a variety of entity types.

- `Loc` component
	- A location on the map, plus a pixel offset used by the [[Animator]] and [[Renderer]] systems.  Most entities have a `Loc`
- `Sprite` component
	- An image used to render the entity on the map.
	- All entities that can be rendered have a sprite.
	- A `Sprite` is rendered at the entity's `Loc`.
- `Feature`
	- Identifies an entity as being a static terrain feature
	- A feature can modify the terrain type of the underlying terrain.
	- The feature's terrain type can change based on game rules (i.e., a door can change from blocking passage to allowing it).
	- Entities tagged with `Feature` are rendered after the base terrain but before mobiles.
- `Mobile`
	- Identifies an entity as a `mobile`, a thing that can move around the map (i.e., a player character, a monster).
	- Entities tagged with `Mobile` are rendered after features but before visual effects.


## Entity Types

An entity is a cluster of components, not any specific Java class.  The following combinations are typical

- [[Door Entity]]
- [[Exit Entity]]
- [[Feature Entity]]
- [[Mannikin Entity]]
- [[Mobile Entity]]
- [[Player Entity]]
- [[Point Entity]]
- [[Sign Entity]]
- [[VisualEffect Entity]]
