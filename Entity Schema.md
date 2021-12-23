# Entity Schema

This table shows the kinds of entity, with the components and subtypes.

## Entity Grammar

Entity Type  | Components
------------ | ----------
Exit         | +Loc
Feature      | +Label +Loc +Sprite ?Terrain
^ Sign       |  
^ Door       | 
^ Mannikin   | 
Item         | +Label +Loc +Sprite ?Inventory ?Equipment
LogMessage   |
Mobile       | +Label +Loc +Sprite ?Plan
^ Player     |
Point        | +Loc
VisualEffect | ?Loc ?Sprite

- `^`:  subtype,  `+`: always, `?`: maybe

## Component Parameters

This table shows the data associated with each component.

Component Type | Parameters
-------------- | ----------
Door           | state closedTerrain closedSprite openSprite
Equipment      | slot
Exit           | regionName pointName
Feature        | 
Inventory      | ownerId
Item           | key
Label          | label
Loc            | cell rowOffset colOffset
LogMessage     | lastTick message
Mannikin       | key
Mobile         | key
Plan           | steps
Player         | 
Point          | name
Sign           | key
Sprite         | name
Terrain        | terrainType
VisualEffect   | animation

## Component Parameter Conventions

This table shows naming conventions for component parameters

Name Format   | Meaning
------------- | -------
name          | The name of this entity, for entity lookups
{type}Name    | Reference to a named entity.
{role}Id      | Refers to another entity by its ID
key           | A key or key prefix into the strings table
{role}Sprite  | A sprite name for a particular use
{role}Terrain | A terrain type for a particular use

- A `key` also serves as a `name`

_Created on 2021-12-23._