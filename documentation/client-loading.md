---
title: Loading artificial bodies on the client
---

When starting the game, you are launched into a preloading screen. When this is active, the `SceneLoader` class opens all the scenes located in the Environment folder inside the Scenes folder. The contents of the scenes are moved to the `VesselsGeometryCache` game object where they are made inactive and await use. This is called pooling, and serves to speed up loading in game.

Definitions of the scenes are written in `Data/Structures.json` and `Data/Asteroids.json`. These json files define which scene files can be loaded, and contain the path, name, and guid of the scenes with other data that is relevant for the game to spawn the scene in games. [Stations](stations) are a set of structures forming larger space stations.

Calling the `GetLoadedScene` function will give you a reference to the root game object of the loaded scene. Which you can use in your game.

## Spawning of objects
The client handles spawning of objects by sending `ObjectsSpawnRequest` to the server for a specific object by using its guid. This request is sent when first connecting to a server and when the player moves near an object that hasn't been loaded yet.

When the client receives a response to the `ObjectsSpawnRequest` message, the client loads the required scenes and fills in the data as described above.

### When first connecting to the game
When joining a server, the client will receive the guid of the artificial body the player is on. This is done in `PlayerSpawnRequest`. This guid is then used by the client to ask the server for the data required to spawn the object.

### In the game
Another way the client loads artificial bodies happens when the player moves close to another artificial body. When `MovementMessage` is received, the client gets a list of all space objects close to the player. When parsing the `MovementMessage`, the client will check if any of the objects do not exist and then spawn them as described under spawning.

![A diagram showing how movement is processed between the client and the server.](res/Movement.drawio.svg)

### Overview

![A diagram showing how spawning objects work on the client.](res/SpawningClient.drawio.svg)
