# Data-Driven Regions
#doc 

A data-driven [[Region]] is defined as follows:

- The region is defined by a number of files in the `resources/assets/regions/<regionName>` folder.
- The primary file is the `<regionName>.region` file; it identifies:
	- The region's [[Terrain Tile Set]], a `.terrain` file
	- The region's [[Strings Table]], a `.strings` file
	- The region's tile map, a [[Tiled Map Data]] `.json` file

The [[Tiled Map Data]] file, a [[Tiled JSON Schema 1.6]] file, is processed as follows:

- The strings table is loaded.
- The terrain tile set is loaded.
- The Tiled `.json` file is loaded:
	- The base terrain is read from the `Terrain` tile layer
	- Simple [[Feature Entity|features]] are read from the `Feature` tile layer
	- Other entity types are read from whatever object group layers there may be.

The remainder of this file explains how specific [[Entity]] types are created from the Tiled data.

## Terrain Features

Every non-empty tile in the `Feature` tile layer is turned into a [[Feature Entity]] using the relevant `TerrainTile`'s location, sprite, and terrain type.

### Doors

Each terrain tile on this layer with the name `closed_door` or `open_door` defines a simple [[Door Entity]] using those two sprites.

2021-12-21: #todo In the future, more complex doors will be defined using an object in an object group later.

## Object Group Objects

At present, all objects in object group layers identify a single point on the map, a point that is also the upper left corner of a terrain tile.  Each object defines some kind of entity on the map.

## Signs

An object of type `Sign` defines a [[Sign Entity]] with the given object name.

2021-12-21: #todo If the object has a `sprite` property, it should be given the named `Sprite`; otherwise it can use `feature.sign`.

## Mannikins

An object of type `Mannikin` defines a [[Mannikin Entity]] with the given object name.  The object must have a `sprite` property, which defines the mannikin's `Sprite`.

## Points

An object of type `Point` defines a [[Point Entity]] with the given name.

## Exits

An object of type `Exit` defines an [[Exit Entity]].  The object name is parsed as `<regionName>:<pointName>`.

