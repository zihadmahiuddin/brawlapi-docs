# Get Top Clubs

This endpoint retrieves the global 200 top clubs on the leaderboard.

## HTTP Request

`https://api.brawlapi.cf/v1/leaderboards/clubs?count=LIMIT&region=REGION`

### URL Parameters

| Parameter | Description                                                                                  |
| --------- | -------------------------------------------------------------------------------------------- |
| `LIMIT`   | The number of clubs to return (1-200) [Default: 200]                                         |
| `REGION`  | "global" or the 2 character name of the region to fetch clubs of to return [Default: global] |

## Response

https://api.brawlapi.cf/v1/leaderboards/clubs

<a href="/json/leaderboards_global_clubs.json">Full JSON response(Global)</a>
<a href="/json/leaderboards_regional_clubs.json">Full JSON response(Regional)</a>

The above endpoint returns JSON structured like this for global:

```json
[
  {
    "id": {
      "high": 0,
      "low": 2250634
    },
    "tag": "YLQ9VRGP",
    "name": "Omen",
    "badgeId": 2,
    "badgeUrl": "https://media.githubusercontent.com/media/fourjr/bs-assets/master/club_badges/clan_badge_01_03.png",
    "position": 1,
    "trophies": 1612573,
    "membersCount": 98
  },
    ...
]
```

And for regional:

```json
[
  {
    "tag": "#CC8JLV8",
    "name": "Tribe Draco",
    "trophies": 1027556,
    "rank": 1,
    "memberCount": 94
  },
    ...
]
```
