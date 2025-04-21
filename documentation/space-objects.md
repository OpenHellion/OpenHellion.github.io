---
title: Space objects
---

Space objects are the object that exist in the world. These are objects that the player can interact with and travel to. All physical objects in the game are one of types below.

The objects are divided into two main catagories: `SpaceObjectTransferable` and `ArtificalBody`. `Station`, `Asteroid` and `Ship` are interresting as they can exist on the map, which is because they are `SpaceObjectVessel` types.

## Space object types
|Type         |Description                                               |Type
|-------------|----------------------------------------------------------|------
|Player       |Player is a type of space object that represents a player.|SpaceObjectTransferable
|DynamicObject|Usually represent physical items. Examples are tools and canisters.|SpaceObjectTransferable
|Corpse       |Player corpse. Representation of a player that used to exist.|SpaceObjectTransferable
|Pivot (PlayerPivot, DynamicObjectPivot, CorpsePivot)|A space object that contains another space object. Probably exists to contain the owned object when it moves outside a `Ship` or `Asteroid`.|ArtificalBody
|Ship         |A representation of a man-made space object. Either a ship or space station.|ArtificalBody (SpaceObjectVessel)
|Asteroid     |An asteroid in the world. Must not be confused with `CelestialBody`.|ArtificalBody (SpaceObjectVessel)
|Station      |Unused. Causes confusion with ship, which all space stations are.|ArtificalBody (SpaceObjectVessel)
|CelestialBody|Unused. Was probably going to reference planets, has no implementation. The class with the same name is found on the sun and every planet, but is not a space object.|None

