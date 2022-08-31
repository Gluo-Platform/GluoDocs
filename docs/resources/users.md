# User Resource
## Getting users 
### `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{user_query}
You can search for users by their ID by adding `?id=true` at the end of the url
Returns a `user object` if the provided `username` or `user_id` exists.
```json
{
   "user_id": 2,
   "username": "kipteam",
   "status": "Hi, this platform is great cuz Gluo",
   "about": "Hi",
   "pfp": "kipteam.png",
   "visible": true,
   "private": false,
   "validated": false,
   "premium": 2,
   "creation_date": 1659088389,
   "following": 8,
   "followers": 14,
   "permission_level": 5,
}
```

## Get the posts of a user
### `GET` https://xxxxxxxxx/xxxxxx/xxxxxxxxxx/{user_id}
Returns all posts by the provided user.
```json
{
   "4":{
      "user_id": 2,
      "username": "kipteam",
      "user_pfp": "kipteam.png",
      "permission_level": 5,
      "post_id": 4,
      "name": "test",
      "description": "temp",
      "topic": "test",
      "is_image": false,
      "image_name": "",
      "upload_date": 1658511254,
      "likes": 2,
      "liked": true,
      "comments": 3,
      "is_private": false,
      "visible": true,
      "validated": true,
   },
   "2":{
      "user_id": 2,
      "username": "kipteam",
      "user_pfp": "kipteam.png",
      "permission_level": 5,
      "name": "another test",
      "description": "YEEEE",
      "post_id": 2,
      "tag": "test",
      "is_image": true,
      "image_name": "1658484500.png",
      "upload_date": 1658484499,
      "likes": 3,
      "liked": true,
      "comments":1,
      "is_private": false,
      "visible": false,
      "validated": true,
   }
}
```

## Getting a user's followers
### `GET` https://xxxxxxxxx/xxxxxxxxx/{user_id}
Returns the provided user's followers IF they allowed this in their settings.
```json
{
   "followers": {
      "ToroEen": {
         "user_id": 10,
         "username": "ToroEen",
         "pfp": "ToroEen.png",
         "status": "Hi, I am a Gluo user!",
         "permission_level": 5,
      },
      "kipteam": {
         "user_id": 2,
         "username": "kipteam",
         "pfp": "kipteam.png",
         "status":"Hi, this platform is great cuz Gluo",
         "permission_level": 5,
      }
   }
}
```

## Getting the people a user follows
### `GET` https://xxxxxxxxx/xxxxxxxxx/{user_id}
Returns the users a user follows IF they allowed this in their settings.
```json
{
   "following": {
      "kipteam": {
         "user_id": 2,
         "username": "kipteam",
         "pfp": "kipteam.png",
         "status": "Hi, this platform is great cuz Gluo",
         "permission_level": 5,
      },
      "Gluo": {
         "user_id": 32,
         "username": "Gluo",
         "pfp": "Gluo.png",
         "status": "Hi, I am Gluo!",
         "permission_level": 5,
      },
   }
}
```