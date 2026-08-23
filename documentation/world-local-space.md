---
title: Solar system space and local space
---

Hellion uses two types of coordinate spaces: solar system space and local space. Coordinate spaces are a fundamental part of Unity programming, but in Hellion spaces are treated a bit differently.

When you are on a ship. the ship object is always located at XYZ 0, 0, 0 on the game client, not at the actual position of the ship in world space.

A technical explaination of this is how Unity uses [32-bit floats](https://en.wikipedia.org/wiki/Single-precision_floating-point_format) for world position, where the largest number is 2,147,483,647.

Therefore, in a world as large as Hellion, it is common to use [64-bit floats](https://en.wikipedia.org/wiki/Double-precision_floating-point_format), which has a limit at (2^63)-1.

Instead of switiching to an engine that supports 64-bit floats, it is much more efficient to transform every object nearby into a per-player local space. Therefore, Hellion uses two spaces internally: *local space* for [space objects](space-objects) near the player and *solar system space* for orbital calculations and objects stored on the server. Space objects are translated between the spaces at the server-client boundry on the server.

Even though the coordinate spaces are separate and have different origins, rotation is not, and both the client and server use the same rotation plane. Local and solar system positions are independent of object rotation.
