# Tiled JSON Schema 1.6
#spec

This is the schema as used by New George.  Where a field's value is described as "Always {value}", that means that it will never have any other value _in our use case._  For example, we only use orthogonal maps.

## Top-level Record

Field Name   | Description
------------ | ------------
height       | Height of map in tiles
width        | Width of map in tiles
layers       | Array of [[#Layer Record]]
tileheight   | Height of a tile in pixels
tilewidth    | Width of a tile in pixels
version      | Ignored. The schema version. [^1] Always `1.6`
tiledversion | Ignored. The Tiled version
tilesets     | Ignored. Array of [[#Tile Set Record]]
type         | Ignored. Always `map`
renderorder  | Ignored. Always `right-down`
infinite     | Ignored. Always `false`
orientation  | Ignored.  Always `orthogonal`
properties   | Ignored.
nextlayerid  | Ignored.
nextobjectid | Ignored.

[^1]: In Schema 1, this was a numeric value.

## Layer Record

Data about a layer in the map, either a `tilelayer` or an `objectgroup`.

Field Name  | Description
----------- | ------------
id          | The layer ID
name        | The layer name
type        | `tilelayer` or `objectgroup`
height      | For `tilelayer`, height in tiles; always same as map.
width       | For `tilelayer`, width in tiles; always same as map.
data        | For `tilelayer`, an array of tile set indices, by row
objects     | For `objectgroup`, an array of [[#Object Record]].
draworder   | For `objectgroup`.  Always `topdown`.
opacity     | Ignored. 0.0 to 1.0
visible     | Ignored. `true` or `false`.  Always `true`.
x           | Ignored. X offset of layer in pixels.  Always 0.
y           | Ignored. Y offset of layer in pixels.  Always 0.

In the `tilelayer` `data` array, a `0` indicates a missing tile.

## Object Record

An object in an `objectgroup`

Field Name  | Description
----------- | ------------
id          | The object ID
type        | Type of object
name        | Name of object
x           | X coordinate of the object in pixels
y           | Y coordinate of the object in pixels
height      | Height of the object in pixels (?)
width       | Width of the object in pixels (?)
visible     | Ignored. Always true.
rotation    | Ignored.  Always 0.
properties  | Ignored. A map of custom.  Currently ignored.

Objects are located and sized by pixel coordinates.  All objects are tied to tiles; `x,y` is the pixel coordinate of the upper-left corner of the tile (IIRC) and `width,height` is always `0,0`.

The `type` and `name` are strings that we define for George's use.  In Old George, the `type` is a simple word like `Point` and the `name` encodes any relevant info about the object, e.g., `regionName:pointName` names a point in another region.

At present we don't use `properties`; relevant data is encoded in the `name` of the object.

## Tile Set Record

A Tiled map can contain multiple tile sets; each is defined by a Tile Set record.  We do not use this data; however, here are some details.

A tile in a tile set image is naturally indexed from 0 to N-1, working across and then down.

Each tile set in the map is assigned a `firstgid`, which is the index used in `tilelayer.data` to refer to the first tile in the tile set.  The first tile set in the map always has a `firstgid` of `1`.  This allows every tile in the map to be referred to by a unique `gid`.  

Here is a partial list of fields.

Field Name  | Description
----------- | ------------
firstgid    | The `gid` of the first tile in the set.
image       | The name of the tile set image, relative to the `.json` file
name        | A human-readable name for the tile set
tileheight  | The height of a tile in pixels
tilewidth   | The width of a tile in pixels.
tilecount   | Number of tiles in the set

Old George only used maps with a single tile set.  We might or might not do the same.

_Created on 2021-11-28._
