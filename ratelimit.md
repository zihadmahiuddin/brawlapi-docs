# Ratelimit

The following headers are provided to manage ratelimits.

| Header Name             | Description                                                |
| ----------------------- | ---------------------------------------------------------- |
| `X-Ratelimit-Limit`     | The total amount of requests you can make per time window. |
| `X-Ratelimit-Remaining` | Requests Left for the time window.                         |
| `X-Ratelimit-Reset`     | Unix seconds when your ratelimit resets.                   |
