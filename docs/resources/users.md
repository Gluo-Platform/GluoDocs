# Post Resource
## Getting users 
### `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{username} OR `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{user_id}
Returns a `user object` if the provided `username` or `user_id` exists.
```json
{
   "user_id": 2,
   "username": "kipteam",
   "status": "Hi, this platform is great cuz Gluo",
   "about": "Hi",
   "badges": "['tester', 'moderator', 'administrator', 'team']",
   "pfp": "kipteam.png",
   "visible": true,
   "private": false,
   "validated": false,
   "creation_date":1659088389,
   "moderator":true,
   "administrator":true,
   "team":true,
   "following":8,
   "followers":14,
   "badge":"team"
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
         "badge": "tester",
         "pfp": "ToroEen.png",
         "status": "Hi, I am a Gluo user!"
      },
      "kipteam": {
         "user_id": 2,
         "username": "kipteam",
         "badge": "team",
         "pfp": "kipteam.png",
         "status":"Hi, this platform is great cuz Gluo"
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
         "badge":"team",
         "pfp":"kipteam.png",
         "status":"Hi, this platform is great cuz Gluo"
      },
      "Gluo":{
         "user_id":32,
         "username":"Gluo",
         "badge":"",
         "pfp":"Gluo.png",
         "status":"Hi, I am Gluo!"
      },
   }
}
```