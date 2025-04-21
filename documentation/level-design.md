---
title: Level-design
---

Each vessel in the game has its own scene. The scene is composed of a root game object and several child game objects that

A central aspect of level design in OpenHellion is the use of *triggers*. These are game objects that do something in the game when triggered. As an example: the fufillment of many quests are handled by triggers, although many other triggers exist, such as door open/close or interaction.

Every trigger has a *trigger event*. This is an event that causes the trigger to trigger the action it is set to do. Triggers are therefore a sort of sensor in the game, and is the main way players interact with stuff in the game.

*Attach points* are another kind of logic in OpenHellion scenes. These are objects in the game that items can be attached to, which allow for special functionality such as charging. These are automatically saved as long as they are defined on

## Adding new ships or asteroids
As explained in the [Loading](client-loading) page, adding new structures or asteroids to the game require adding entries in the `Data/Structures` and `Data/Asteroids` files. In addition, adding the definition to the SceneId enum will make finding the scene easier.
