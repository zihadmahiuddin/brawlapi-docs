# Event Notifications

This system allows you to recieve a `POST` request upon a new event starts.

You would have to setup a web server to recieve `POST` requests.  
Resources to setup web servers:

- [Python Flask](http://flask.pocoo.org/)
- [Node.js Express](https://expressjs.com/)

Every few hours when a new event begins, you will recieve a `POST` request with the following structure:

```json
{
    "old": [
        {
            event metadata (refer to /events)
        }
    ],
    "new": [
        {
            event metadata (refer to /events)
        }
    ]
}
```

The data in `old` refers to the event(s) that has just ended.  
The data in `new` refers to the event(s) that has just started.

Some cases where each array consists of more than 1 element:

- Ticketed events are refreshing at the same time as events.

Some cases where the `POST` isn't sent at the most precise timing:

- API server was down.
- Game maintainence break.

This feature is currently in **beta**.

To apply for this feature, head to [your dashboard](https://brawlapi.cf/dashboard) and register at the bottom.
