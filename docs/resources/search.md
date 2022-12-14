# Search Resource
## Get posts & users with a specific search query
### `GET` https://xxxxxxxxx/xxxxxxxxx/xxxx/{query}
Returns all matches with your query for bots posts and users. If no match was found it will return an empty list.  
Query formatting 
| prefix | actual query | response |
|-------|--------|---------|
| !user:  | string | Returns all exact user matches. |
| !topic:  | string | Returns an exact topic match (if one exists). |
| !post:  | string | Returns all exact post matches. |
| !  | string | Returns all exact user, topic and post matches. |
| user: | string | Returns all user matches. |
| topic: | string | Returns all topic matches. |
| post: | string | Returns all post matches. |
|  | string | Returns all user, topic and post matches |

Some examples:
```js
query = "!user:kipteam"
//returns all users (1) with the exact username "kipteam"
query = "!post:kipteam"
//returns all posts with an title OR description being exactly "kipteam"
query = "!kipteam"
//returns all users (1) with the exact username "kipteam" and all posts with an exact title OR description of "kipteam" -> response shown below.
```
Response:
```json
{
    "users": [{
        "user_id": 2,
        "username": "kipteam",
        "user_pfp": "1664984592.webp",
        "status": "Hi, this platform is great cuz Gluo",
        "permissions": 63,
        "premium": 131
    }],
    "topics": ["kipteam"],
    "posts": [{
        "user_id": 2,
        "username": "kipteam",
        "user_pfp": "1664984592.webp",
        "permissions": 63,
        "premium": 131,
        "post_id": 171,
        "name": "kipteam",
        "description": "KIPTEAM (just testing, I didn't become narcissistic)",
        "topic": "test",
        "type": 1,
        "image_name": null,
        "upload_date": 1666631405,
        "liked": false,
        "likes": 0,
        "comments": 0,
        "visible": true,
        "validated": false
    }]
}
```