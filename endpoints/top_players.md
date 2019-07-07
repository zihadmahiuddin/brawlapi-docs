# Get Top Players

This endpoint retrieves the global 200 top players on the leaderboard.

## HTTP Request

`https://api.brawlapi.cf/v1/leaderboards/players?count=LIMIT&brawler=NAME&region=REGION`

### URL Parameters

| Parameter | Description                                                                                    |
| --------- | ---------------------------------------------------------------------------------------------- |
| `LIMIT`   | The number of players to return (1-200) [Default: 200]                                         |
| `NAME`    | A brawler leaderboard to fetch                                                                 |
| `REGION`  | "global" or the 2 character name of the region to fetch players of to return [Default: global] |

## Response

https://api.brawlapi.cf/v1/leaderboards/players

<a href="/json/leaderboards_global_players.json">Full JSON response(Global)</a>
<a href="/json/leaderboards_regional_players.json">Full JSON response(Regional)</a>

The above endpoint returns JSON structured like this for global:

```json

[
  {
    "id": {
      "high": 1,
      "low": 809152
    },
    "tag": "2VQ82YGY",
    "name": "AKTwistiTwik",
    "nameColorCode": "4DDBA2",
    "avatarId": 28000041,
    "avatarUrl": "https://media.githubusercontent.com/media/fourjr/bs-assets/master/player_icons/28000041.png",
    "position": 1,
    "trophies": 23728,
    "clubName": "A Few Good Men",
    "expLevel": 100
  },
    ...
]
```

And for regional:

```json
{
  "items": [
    {
      "tag": "#888UR8",
      "name": "ItstheUDAY",
      "nameColor": "0xfff9c908",
      "trophies": 15638,
      "rank": 1,
      "club": {
        "name": "Tribe Gaming"
      }
    },
    ...
  ]
}
```
