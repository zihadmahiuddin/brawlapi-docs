# Search Players

This endpoint retrieves players by their name from a database. It only returns players that the API has seen before. A maximum of 100 players will be returned.

!> From the Terms of Use: You are not allowed to use "match anything regex" or any other means to attempt to or retrieve our player tag database.

## HTTP Request

`GET https://api.brawlapi.cf/v1/player/search?name=NAME`

### URL Parameters

| Parameter | Description                                                                                                           |
| --------- | --------------------------------------------------------------------------------------------------------------------- |
| `NAME`    | The name of the player you are searching for. For regex searches, prepend your search with `r:` (No flags are added). |

## Response

#### Normal string query

https://api.brawlapi.cf/v1/player/search?name=john

<a href="/json/players_search_john.json">Full JSON response</a>

#### Regex search query (filters all players with color codes)

https://api.brawlapi.cf/v1/player/search?name=r%3a%3Cc%5B0-9%5D%3E.*%3C%5C%2Fc%3E

Search query before the URL encoding: `r:<c[0-9]>.*<\/c>`

<a href="/json/players_search_regexcolor.json">Full JSON response</a>

The above endpoint returns JSON structured like this:

```json

[
    {
        "name": "apple",
        "tag": "2PP"
    },
    ...
]

```
