# Frequently Asked Questions

## What are the valid characters in a Supercell tag?

Only these characters are valid in a tag: `0289CGJLPQRUVY` — the numbers `0289` and the letters `CGJLPQRUVY`.

## What status codes can the API return?

| Code | Message                                                                                             |
| ---- | --------------------------------------------------------------------------------------------------- |
| 200  | OK                                                                                                  |
| 400  | Tag isn't valid                                                                                     |
| 401  | Unauthorised                                                                                        |
| 404  | Not found/tag not found                                                                             |
| 429  | Ratelimit hit                                                                                       |
| 503  | Maintainence/unable to connect to sc                                                                |
| 5XX  | [Cloudflare errors](https://support.cloudflare.com/hc/en-us/articles/115003011431-5xx-Server-Error) |

## Is there a ratelimit to use the API?

Yes, check [ratelimit](/ratelimit) for more information.
