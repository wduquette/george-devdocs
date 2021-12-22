# Entity Table
#design, #pending

The `EntityTable` is the basic data structure for George's [[Entity|entities]].  It is a `Map<Long,Entity>`, where each `Entity` contains a `TypeMap` of the entity components.  (As a result, an entity can have only one component of a given class at a time).

The `Entity` class provides easy access to the standard components.

An `Entity` can mix-and-match the components it needs.  For the standard kinds of entity (terrain, feature, mobile, etc.) there will be a component that identifies the kind; it might have data of its own, or it might simply be a sentinel, to make queries easier.

## Queries

`EntityTable::query` takes one or more component `Class<?>` objects, and returns a stream of all entities that have all of the indicated classes.  This is the fundamental query.

_Created on 2021-11-28._