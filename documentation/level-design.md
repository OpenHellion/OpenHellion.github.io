---
title: Level design
---

Level design in Hellion are based on Unity scenes. Every physical object in the scene has a scene has an *InSceneID* to make the server be able to execute logic with objects defined in a Unity scene. On the server side, levels are defined by adding an entry into one of two JSON files.

All levels in Hellion are either *structures* or *asteroids*. *Celestial bodies* (planets) also exist, but as these are not objects you cannot interact with, they will not be covered in detail. For more information, see [space objects](space-objects). Structures can be combined into [stations](stations).

## Triggers and attach points
Two central concepts in Hellion level design are *triggers* and *attach points*. The state of attach points and triggers are always saved by the game.

**Triggers** are objects that execute an action when triggered. Every trigger has a *trigger event*. This is an event that causes the trigger to trigger the action it is set to do.

Functionally, triggers are a kind of "sensor" in the game, and is the main way players affect the world. Fulfillement of many quests are handled by triggers, while other uses are buttons for opening and closing doors.

**Attach points** are objects in the game that items can be attached to, which allow for special functionality such as charging.

## Adding new ships or asteroids (levels)
As explained in the [Loading](client-loading) page, adding new structures or asteroids to the game require adding entries in the `Data/Structures` and `Data/Asteroids` JSON files and creating a Unity scene at the path defined in these files.

Example:

```json
[
  {
    "ItemID": 3,
    "ScenePath": "Assets/Scene/Environment/Station/Module/AltCorp/AltCorp_CorridorModule/AltCorp_CorridorModule.unity",
    "SceneName": "AltCorp_CorridorModule",
    "GameName": "AltCorp_CorridorModule",
    "Mass": 55228.582,
    "RadarSignature": 25.0,
    "RadarSignatureHealthMultipliers": [
      4.0,
      3.89711928,
      3.62139916,
      3.222222,
      2.74897122,
      2.25102854,
      1.77777767,
      1.37860084,
      1.10288072,
      1.0
    ],
    "HeatCollectionFactor": 10000.0,
    "HeatDissipationFactor": 20.0,
    "StructureConnections": [],
    "SpawnPoints": [],
    "DynamicObjects": [
      {
        "ItemID": 97,
        "Position": [
          0.0529999472,
          3.46949983,
          0.889600039
        ],
        "Forward": [
          -2.83242571E-06,
          0.0592841431,
          -0.9982413
        ],
        "Up": [
          1.35609213E-09,
          0.9982411,
          0.0592841431
        ],
        "AttachPointInSceneId": 48,
        "AuxData": {
          "PartType": 11,
          "Category": 2,
          "ItemType": 600,
          "Tier": 1,
          "TierMultipliers": [
            0.5,
            0.4,
            0.3,
            0.2
          ],
          "AuxValues": [],
          "MaxHealth": 100.0,
          "Health": 100.0,
          "Armor": 0.0,
          "Damageable": false,
          "Repairable": false,
          "UsageWear": 0.0,
          "MeleeDamage": 0.0,
          "Slots": [],
          "ExplosionDamage": 0.0,
          "ExplosionRadius": 0.0,
          "ExplosionDamageType": 0
        },
        "SpawnSettings": [
          {
            "Case": 0,
            "Tag": "",
            "RespawnTime": -1.0,
            "SpawnChance": -1.0,
            "MinHealth": 1.0,
            "MaxHealth": 1.0,
            "WearMultiplier": 1.0
          }
        ]
      }
    ],
    "AttachPoints": [
      {
        "Scope": 3,
        "MinTier": 0,
        "MaxTier": 0,
        "PartDecay": 0.0,
        "SlotIndex": 0,
        "InSceneID": 48,
        "ItemTypes": [],
        "GenericSubTypes": [],
        "MachineryPartTypes": [
          11
        ],
        "AttachPointType": 2,
        "IsActive": true
      }
    ],
    "SubSystems": [
      {
        "InSceneID": 1313,
        "Type": 8,
        "RoomID": 102,
        "ResourceRequirements": [
          {
            "ResourceType": 9,
            "Nominal": 0.1,
            "Standby": 0.0
          }
        ],
        "SpawnSettings": [],
        "OperationRate": 1.0,
        "AutoTuneOperationRate": false,
        "Status": 1,
        "MachineryPartSlots": [
          48
        ],
        "ResourceContainers": [
          105
        ],
        "PowerUpTime": 0.0,
        "CoolDownTime": 0.0,
        "AutoReactivate": true,
        "RadarSignature": 0.0,
        "AuxData": {
          "Acceleration": 6.0,
          "RotationAcceleration": 20.0,
          "RotationStabilization": 19.0,
          "AuxDataType": 5
        }
      }
    ],
    "Generators": [],
    "Rooms": [
      {
        "InSceneID": 102,
        "UseGravity": false,
        "GravityAutoToggle": true,
        "AirFiltering": true,
        "Volume": 60.73573,
        "AirQuality": 0.0,
        "AirPressure": 0.0,
        "PressurizeSpeed": 3.0,
        "DepressurizeSpeed": 3.0,
        "VentSpeed": 5.0,
        "ParentRoomID": 0
      }
    ],
    "ResourceContainers": [
      {
        "InSceneID": 105,
        "DistributionSystemType": 9,
        "CargoCompartment": {
          "ID": 0,
          "AllowedResources": [
            103
          ],
          "AllowOnlyOneType": true,
          "Capacity": 50.0,
          "Name": "RCS",
          "Type": 7,
          "Resources": [
            {
              "ResourceType": 103,
              "Quantity": 0.0,
              "SpawnSettings": [
                {
                  "Case": 0,
                  "Tag": "",
                  "MinQuantity": 25.0,
                  "MaxQuantity": 50.0
                }
              ]
            }
          ]
        },
        "NominalInput": 0.0,
        "NominalOutput": 100.0,
        "IsInUse": true,
        "AuxData": null
      }
    ],
    "Collision": "AltCorp_CorridorModule",
    "Colliders": null,
    "Doors": [
      {
        "InSceneID": 1043,
        "Room1ID": 102,
        "Room2ID": 0,
        "PassageArea": 2.0,
        "IsSealable": true,
        "HasPower": true,
        "IsLocked": false,
        "IsOpen": false,
        "LockedAutoToggle": false,
        "PositionRelativeToDockingPort": [
          -0.002999934,
          -1.86409986,
          -0.139800072
        ]
      }
    ],
    "SceneTriggerExecutors": [
      {
        "InSceneID": 1049,
        "DefaultStateID": 3,
        "TagAction": 0,
        "Tags": "",
        "States": [
          {
            "StateID": 1,
            "PlayerDisconnectToStateID": 0,
            "PlayerDisconnectToStateImmediate": false
          }
        ],
        "ProximityTriggers": [
          {
            "TriggerID": 1,
            "ActiveStateID": 0,
            "InactiveStateID": 3
          }
        ]
      }
    ],
    "DockingPorts": [
      {
        "InSceneID": 5,
        "OrderID": 3,
        "Position": [
          0.301,
          3.57799983,
          3.006
        ],
        "Rotation": [
          -3.909704E-07,
          0.7071068,
          0.7071068,
          4.09781933E-07
        ],
        "DoorsIDs": [],
        "DoorPairingDistance": 0.5,
        "Locked": false,
        "MergeExecutors": [],
        "MergeExecutorDistance": 1.0
      }
    ],
    "SpawnObjectChanceData": [
      {
        "InSceneID": 106
      }
    ],
    "CargoBay": null,
    "NameTags": [
      {
        "InSceneID": 1040,
        "NameTagText": "DOCKING PORT B"
      }
    ],
    "RepairPoints": [
      {
        "InSceneID": 109,
        "RoomID": 102,
        "DamageType": 2,
        "AffectedSystemID": -1,
        "MalfunctionThreshold": 0.1,
        "RepairThreshold": 0.8,
        "External": true
      }
    ],
    "HasSecuritySystem": false,
    "MaxHealth": 1500.0,
    "Health": 1500.0,
    "BaseArmor": 0.0,
    "InvulnerableWhenDocked": false,
    "SpawnSettings": [],
    "AdditionalTags": []
  },
  {
    (...)
  }
]
```

## Adding celestial bodies (advanced)
On the server, open the `Data/SolarSystem.json` file and add your new celestial body. Make sure the GUID isn't taken. On the client, add create a new planet at the paths you defined in `Data/SolarSystem.json`.

Example:
```json
"CelestialBodies": [
  {
    "GUID": 1,
    "Name": "Hellion",
    "ParentGUID": -1,
    "Mass": 1.2500000414766919E+31,
    "Radius": 8452280000.0,
    "RotationPeriod": 1165276.8402099609,
    "Eccentricity": 0.0,
    "SemiMajorAxis": 0.0,
    "Inclination": 0.0,
    "ArgumentOfPeriapsis": 0.0,
    "LongitudeOfAscendingNode": 0.0,
    "PlanetsPrefabPath": "Environment/SolarSystem/Planet/ProxyPlanets/Hellion",
    "MainCameraPrefabPath": "Environment/SolarSystem/Planet/ProxyPlanets/Hellion",
    "NavigationPrefabPath": "Environment/SolarSystem/Planet/ProxyPlanets/HellionMap",
    "AsteroidGasBurstTimeMin": 30.0,
    "AsteroidGasBurstTimeMax": 60.0,
    "AsteroidGasBurstDmgMultiplier": 1.0,
    "AsteroidResources": [
      {
        "Type": 1,
        "Min": 10000.0,
        "Max": 15000.0
      },
      {
        (...)
      }
    ],
    "ScanningSensitivityModifierValues": [
      0.3,
      (...)
    ],
    "RadarSignatureModifierValues": [
      1.0,
      (...)
    ]
  },
  {
    (...)
  }
]
```
