# Get Events

This endpoint retrieves the upcoming and current events.

## HTTP Request

`https://api.brawlapi.cf/v1/events?type`

### URL Parameters

| Parameter | Description                                                        |
| --------- | ------------------------------------------------------------------ |
| `type`    | The type of events to return (`current`/`upcoming`) [Default: all] |

## Response

https://api.brawlapi.cf/v1/events

<a href="/json/events.json">Full JSON response</a>

The above endpoint returns JSON structured like this:

```json

{
    "current": [
        ...
        {
            "slot": 4,
            "slotName": "Special Events",
            "startTimeInSeconds": 0,
            "startTime": "2018-12-10T07:18:38.360Z",
            "endTimeInSeconds": 22344,
            "endTime": "2018-12-10T14:00:00.360Z",
            "freeKeys": 10,
            "mapId": 1500023,
            "mapName": "G.G. Corral",
            "mapImageUrl": "https://fourjr.github.io/bs-assets/map_images/1500023.png",
            "gameMode": "Heist",
            "hasModifier": true,
            "modifierId": 3,
            "modifierName": "Meteor Shower"
        },
        ...
    ],
    "upcoming": [
        ...
        {
            "slot": 7,
            "slotName": "Ticketed Events",
            "startTimeInSeconds": 432744,
            "startTime": "2018-12-15T08:00:00.360Z",
            "endTimeInSeconds": 605544,
            "endTime": "2018-12-17T08:00:00.360Z",
            "freeKeys": 2,
            "mapId": 1500039,
            "mapName": "Keep Safe",
            "mapImageUrl": "https://fourjr.github.io/bs-assets/map_images/1500039.png",
            "gameMode": "Robo Rumble",
            "hasModifier": false,
            "modifierId": null,
            "modifierName": null
        }
        ...
    ]
}
```
