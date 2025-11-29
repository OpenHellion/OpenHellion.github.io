---
title: Stations
---

Stations are a type of [space objects](space-objects), which contains a collection of [stuctures](level-design). The definitions of stations are stored on the server, and are located in the Data folder. Each file in the Stations folder describes a collection of stations, and are loaded all at once.

In essence, station objects are blueprints of individual space station parts put together.

In the code, stations are categorised as a ``Ship``.

## Example
```json
[
  {
    "Version": "0.3",
    "Name": "Xanthus Cell Block A",
    "Invulnerable": false,
    "SystemsOnline": true,
    "DoorsLocked": false,
    "HealthMultiplier": 1,
    "DockingControlsDisabled": false,
    "AirPressure": 0,
    "AirQuality": 0,
    "LocalAngularVelocity": [
      1.5,
      1.7,
      0.6
    ],
    "AutoStabilizationDisabled": true,
    "Structures": [
      {
        "StructureID": 0,
        "StructureType": "Generic_Debris_Corridor001",
        "Invulnerable": false,
        "SystemsOnline": true,
        "DoorsLocked": false,
        "HealthMultiplier": 0.5,
        "DockingControlsDisabled": false,
        "AirPressure": 0,
        "AirQuality": 0,
        "DockingPorts": [
          {
            "OrderID": 1,
            "DockedStructureID": 1,
            "Locked": false
          }
        ]
      },
      {
        (...)
      }
    ]
  },
  {
    (...)
  }
]
```
