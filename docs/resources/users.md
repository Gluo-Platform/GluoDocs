# User Resource
## Getting users 
### `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{user_query}
You can search for users by their ID by adding `?id=true` at the end of the url
Returns a `user object` if the provided `username` or `user_id` exists.
```json
{
    "user_id": 10,
    "username": "ToroEen",
    "user_pfp": "ToroEen.png",
    "permission_level": 0,
    "status": "Hi, I am a Gluo user!",
    "about": "Another awesome Gluo user.",
    "visible": true,
    "private": true,
    "validated": false,
    "premium": 0,
    "creation_date": 1659088389,
    "followers": 4,
    "following": 3,
    "is_following": false,
    "is_requested": true
}
```

## Get the posts of a user
### `GET` https://xxxxxxxxx/xxxxxx/xxxxxxxxxx/{user_id}
Returns all posts by the provided user.
```json
[{
    "user_id": 2,
    "username": "kipteam",
    "user_pfp": "kipteam.png",
    "permission_level": 0,
    "post_id": 4,
    "name": "test",
    "description": "temp",
    "topic": "test",
    "is_image": false,
    "image_name": "",
    "upload_date": 1658511254,
    "liked": true,
    "likes": 2,
    "comments": 3,
    "visible": true,
    "validated": true
}, {
    "user_id": 2,
    "username": "kipteam",
    "user_pfp": "kipteam.png",
    "permission_level": 0,
    "post_id": 2,
    "name": "another test",
    "description": "YEEEE",
    "topic": "test",
    "is_image": true,
    "image_name": "1658484500.png",
    "upload_date": 1658484499,
    "liked": true,
    "likes": 3,
    "comments": 1,
    "visible": false,
    "validated": true
}]
```

## Getting a user's followers
### `GET` https://xxxxxxxxx/xxxxxxxxx/{user_id}
Returns the provided user's followers IF they allowed this in their settings.
```json
[{
    "user_id": 2,
    "username": "kipteam",
    "user_pfp": "kipteam.png",
    "status": "Hi, this platform is great cuz Gluo aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "permission_level": 0
}, {
    "user_id": 32,
    "username": "Gluo",
    "user_pfp": "Gluo.png",
    "status": "Hi, I am Gluo!",
    "permission_level": 0
}]
```

## Getting the people a user follows
### `GET` https://xxxxxxxxx/xxxxxxxxx/{user_id}
Returns the users a user follows IF they allowed this in their settings.
```json
[{
    "user_id": 2,
    "username": "kipteam",
    "user_pfp": "kipteam.png",
    "status": "Hi, this platform is great cuz Gluo aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "permission_level": 0
}, {
    "user_id": 32,
    "username": "Gluo",
    "user_pfp": "Gluo.png",
    "status": "Hi, I am Gluo!",
    "permission_level": 0
}]
```