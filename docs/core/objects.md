# Gluo Objects
## Simple user object
| field | type   | details |
|-------|--------|---------|
| user_id  | int | Unique user ID |
| username  | string | Unique username (1-25 characters) |
| user_pfp  | string | Query for a user [profile picture](/docs/resources/users.md#get-a-profile-picture) |
| permissions  | integer | User [permissions](permissions.md#general-permissions) |
| premium  | integer | User's [premium-level](permissions.md#premium-levels) |
| status  | string | The user's status (1-75 characters) |
Example response
```json
{
    "user_id": 10,
    "username": "ToroEen",
    "user_pfp": "ToroEen.png",
    "permissions": 1,
    "premium": 0,
    "status": "Hi, I am a Gluo user!"
}
```

## Extensive user object
| field | type   | details |
|-------|--------|---------|
| user_id  | int | Unique user ID |
| username  | string | Unique username (1-25 characters) |
| user_pfp  | string | Query for a user [profile picture](/docs/resources/users.md#get-a-profile-picture) |
| permissions  | integer | User [permissions](permissions.md#general-permissions) |
| premium  | integer | User's [premium-level](permissions.md#premium-levels) |
| status  | string | The user's status (1-75 characters) |
| about  | string | The user's about-me (1-250 characters) |
| private  | boolean | Is it a private account |
| public_interactions  | boolean | Are their [followers](/docs/resources/users.md#getting-a-users-followers) and [following](/docs/resources/users.md#getting-the-people-a-user-follows) public |
| creation_date  | unix timestamp | The user's status (1-75 characters) |
| followers  | integer | Amount of people that follow the user |
| following  | integer | Amount of people the user follows |
| is_following  | boolean | Is the account making the api call following the user |
| is_requested  | boolean | Has the account making the api call requested to follow the user |
Example response
```json
{
    "user_id": 10,
    "username": "ToroEen",
    "user_pfp": "ToroEen.png",
    "permissions": 1,
    "premium": 0,
    "status": "Hi, I am a Gluo user!",
    "about": "Another awesome Gluo user.",
    "private": true,
    "visible": true,
    "public_interactions": false,
    "creation_date": 1659088389,
    "followers": 4,
    "following": 3,
    "is_following": false,
    "is_requested": true
}
```

## Posts
A post always contains a [simple user](objects.md#simple-user-object) object.
| field | type   | details |
|-------|--------|---------|
| post_id  | int | Unique post ID |
| title  | string | Post title (1-50 characters) |
| description | string | Post description (1-1000 characters) |
| topic  | string | Post topic (1-17 characters) |
| type  | int | The post type |
and a lot more ...
```json
{
   "user_id" : 2,
   "username": "kipteam",
   "user_pfp": "kipteam.png",
   "permissions": 63,
   "premium": 0,
   "status": "Hi, I am a Gluo user!",
   
   "post_id": 2,
   "name": "another test",
   "description": "YEEEE",
   "topic": "test",
   "type": 2,
   "image_name": "1658484500.png",
   "upload_date": 1658484499,
   "likes": 3,
   "liked": true,
   "comments": 1,
   "visible": false,
   "validated": true
}
```

## Reactions