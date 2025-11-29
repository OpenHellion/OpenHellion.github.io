---
title: Loading modules and celestial bodies on the client
---

When starting the game, you are launched into a preloading screen. When this is active, the `SceneLoader` class opens all the scenes located in the Environment folder inside the Scenes folder. The contents of the scenes are moved to the `VesselsGeometryCache` game object where they are made inactive and await use. This is called pooling, and is a way to prevent loading screens in the game.

Definitions of the scenes are written in `Data/Structures.json` and `Data/Asteroids.json`. These json files define which scenes can be loaded, and contain the path, name, and guid of the scenes. [Stations](stations) are a set of structures forming larger space stations.

Calling the `GetLoadedScene` function will give you a reference to the root game object of the loaded scene. Which you can use in your game.

### Connecting to game
When connecting to a server, you will receive a set of messages from the server giving your client information about the world state. These are `PlayerSpawnRequest` and `MovementMessage`.

`PlayerSpawnRequest` gives you all of the SpaceObjects that are in your area (vessels and asteroids that you can see), and handles the spawning of these in the way mentioned above.

`MovementMessage` is in part a quite misleading name, as it actually gives your client information about all of the SpaceObjects the server has registered (a security risk?), and creates GameObjects to represent all of these in the game. This is highly inefficient, and improvements should be discussed.
