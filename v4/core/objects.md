# Gluo objects

## Large user object

| field | type | details |
|-------|------|---------|
| user_id | int | Unique user ID |
| username | string | Unique username (1-25 characters) |
| permissions | integer | User [permissions](permissions.md#general-permissions) |
| avatar | string | The user's avatar |
| status | string | The user's status (1-75 characters) |
| about | string | The user's about-me (1-250 characters) |
| followers | integer | Amount of people that follow the user |
| following | integer | Amount of people the user follows |
| posts | integer | Amount of posts by the user |
| private | boolean | Is it a private account |
| is_following | boolean | Is the account making the api call following the user |
| is_requested | boolean | Has the account making the api call requested to follow the user |
| public_interactions | boolean | Are their [followers](/v3/resources/users.md#getting-a-users-followers) and [following](/v3/resources/users.md#getting-the-people-a-user-follows) public |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the account |

Example response

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
    "creation_timestamp": 1674061579
}
```

## Small user object

| field | type | details |
|-------|------|---------|
| user_id  | int | Unique user ID |
| username  | string | Unique username (1-25 characters) |
| permissions  | integer | User [permissions](permissions.md#general-permissions) |
| avatar | string | The user's avatar |
| status  | string | The user's status (1-75 characters) |

```json
{
    "user_id": 5,
    "username": "kipteam",
    "permissions": 64,
    "avatar": "default.png",
    "status": "Hi, I am a Gluo user!",
}
```

## Post object

| field | type | details |
|-------|------|---------|
| user | small_user_object | A [small user object](/v4/core/objects.md#small-user-object) |
| post_id | int | Unique post ID |
| title | string | Post title (1-50 characters) |
| description | string | Post description (1 - 1000) characters. Could be null. |
| topics | array | Array of topics |
| post_type | string | Either `"TEXT"`, `"IMAGE"` (for static and dynamic images) or `"VIDEO"`. |
| attachment_name | string | Unique attachment name |
| likes | int | Amount of likes |
| has_liked | boolean | Has the requesting user liked this post |
| creation_timestamp | int | Timestamp of post creation date |

```json
{
    "user": {
        "user_id": 5,
        "username": "kipteam",
        "permissions": 64,
        "avatar": "default.png",
        "status": "Hi, I am a Gluo user!"
    },
    "post_id": 6,
    "title": "test post",
    "description": "very cool description",
    "topics": ["5", "tESt"],
    "post_type": "TEXT",
    "attachment_name": null,
    "likes": 0,
    "has_liked": false,
    "creation_timestamp": 1674656446
}
```
