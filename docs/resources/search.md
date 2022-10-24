# Search Resource
## Get posts & users with a specific search query
### `GET` https://xxxxxxxxx/xxxxxxxxx/xxxx/{query}
Returns all matches with your query for bots posts and users. If no match was found it will return an empty list.  
Query formatting 
| prefix | actual query | response |
|-------|--------|---------|
| !user:  | string | Returns all exact user matches. |
| !post:  | string | Returns all exact post matches. |
| !  | string | Returns all exact user and post matches. |
| user: | string | Returns all user matches. |
| post: | string | Returns all post matches. |
|  | string | Returns all post and user matches |
Some examples:
```js
!user:kipteam //returns all users (1) with the exact username "kipteam"
!kipteam //returns all users (1) with the exact username "kipteam" and all posts with an exact title OR description of "kipteam" -> response shown below.
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