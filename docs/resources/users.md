# User Resource
## Getting users 
### `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{username} OR `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{user_id}
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
   "following":{
      "kipteam":{
         "user_id":2,
         "username":"kipteam",
         "pfp":"kipteam.png",
         "status":"Hi, this platform is great cuz Gluo",
         "permission_level": 5,
      },
      "Gluo":{
         "user_id":32,
         "username":"Gluo",
         "pfp":"Gluo.png",
         "status":"Hi, I am Gluo!",
         "permission_level": 5,
      },
   }
}
```