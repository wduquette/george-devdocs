# Region
#doc

A `Region` is an object that represents a map and all the [[Entity|entities]] on the map.

- The terrain is stored as an array of `TerrainTile` objects read from a `TerrainTileSet` and mapped to `Cell` coordinates.
- Entities on the map are represented as [[Entity]] objects in the region's `EntityTable`.

## Defining Regions

- A region can (#todo) be defined entirely in Java; see Old George's "Sewers".
- A region can be defined entirely by data files.  See [[Data-Driven Regions]].
- The two models can be combined.  A region can be primarily data-driven but also include custom code.  (Again, #todo)

