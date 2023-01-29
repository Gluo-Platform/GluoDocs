# Gluo users

## Get a user 

### `GET` /user/{user_query}

Search for a user by the provided `user_query`. If you are looking for a user by ID, append `?id=true` to the end (`/user/{user_id}?id=true`).  
If you are looking for more information on yourself, pass along your user token and use `@me` as `user_query` (`/user/@me`).  
Returns a [large user object](/v4/core/objects.md#large-user-object)

```json
{
    "user_id": 5,
    "username": "kipteam",
    "permissions": 64,
    "avatar": "default.png",
    "status": "Hi, I am a Gluo user!",
    "about": "Another awesome Gluo user.",
    "following": 0,
    "followers": 0,
    "posts": 6,
    "private": false,
    "is_following": false,
    "is_requested": false,
    "public_interactions": false,
    "creation_timestamp": 1674061579
}
```
