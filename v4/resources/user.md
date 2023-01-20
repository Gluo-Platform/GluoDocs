# Gluo users
### `GET` /user/{user_query}?id={search_for_id}
Search for a user by the provided `user_query`. If you are looking for a user by their username pass in the username as `user_query` and pass in `false` for `?id=` (`search_for_id`). If you are looking for a user by ID, do set `?id=` (`search_for_id`) to `true`.  
If you are looking for more information on yourself, pass along an authentication token and use `@me` as `user_query`.  
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
    "posts": 0,
    "private": false,
    "is_following": false,
    "is_requested": false,
    "public_interactions": false,
    "creation_date": 1674061579
}
```