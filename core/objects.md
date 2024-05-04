# Gluo objects

## User object

| field | type | details |
|-------|------|---------|
| user_id | int | Unique user ID |
| username | string | Unique username (1-25 characters) |
| badge | string | The user's main badge |
| permissions | integer | User [permissions](permissions.md#general-permissions) |
| avatar | string | The user's avatar |
| status | string | The user's status (1-75 characters) |
| about | string | The user's about-me (1-250 characters) |
| followers | integer | Amount of people that follow the user |
| following | integer | Amount of people the user follows |
| posts | integer | Amount of posts by the user |
| is_following | boolean | Is the account making the api call following the user |
| is_requested | boolean | Has the account making the api call requested to follow the user |
| is_blocked | boolean | Is the account making the api call blocked by the user |
| online | boolean | Is the user currently online (only works when the user is not in invisible)|
| private | boolean | Is it a private account |
| invisible | boolean | Is the user in invisible mode |
| public_interactions | boolean | Are their [followers](/v3/resources/users.md#getting-a-users-followers) and [following](/v3/resources/users.md#getting-the-people-a-user-follows) public |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the account |

Example response

```json
{
    "user_id": 1,
    "username": "Johndoe",
    "permissions": 3,
    "avatar": "default.png",
    "status": "Hi, I am a Gluo user!",
    "about": "Another awesome Gluo user.",
    "following": 3,
    "followers": 7,
    "posts": 5,
    "is_following": false,
    "is_requested": false,
    "is_blocked": false,
    "online": true,
    "private": false,
    "invisible": false,
    "public_interactions": false,
    "creation_timestamp": 1674061579.0
}
```

## Post object

| field | type | details |
|-------|------|---------|
| user | user_object | A [user object](#user-object) |
| post_id | int | Unique post ID |
| is_pinned | boolean | ??? |
| description | string | Post description (1 - 1000) characters. Could be null. |
| topics | array | Array of topics |
| post_type | string | Either `"TEXT"`, `"IMAGE"` (for static and dynamic images) or `"VIDEO"`. |
| attachments | array | Array of attachments |
| likes | int | Amount of likes |
| has_liked | boolean | Has the requesting user liked this post |
| reactions | int | Amount of reactions under a post |
| has_saved | boolean | Has the requesting user saved this post |
| creation_timestamp | int | Timestamp of post creation date |
| poll | poll_object | A [poll-object](#poll-object) |
| embed | embed_object | An [embed-object](#embed-object) |
| gift | gift_object | A [gift-object](#gift-object) |

Example response

```json
{
    "user": {
        "user_id": 1,
        "username": "Johndoe",
        "permissions": 3,
        "avatar": "default.png",
        "status": "Hi, I am a Gluo user!",
        "about": "Another awesome Gluo user.",
        "following": 3,
        "followers": 7,
        "posts": 5,
        "is_following": false,
        "is_requested": false,
        "is_blocked": false,
        "online": true,
        "private": false,
        "invisible": false,
        "public_interactions": false,
        "creation_timestamp": 1674061579.0
    },
    "post_id": "1",
    "is_pinned": false,
    "description": "Gluo is actually a really cool platform",
    "topics": [
        "gluo",
        "cool"
    ],
    "post_type": "TEXT",
    "attachments": [],
    "likes": 3,
    "has_liked": false,
    "reactions": 0,
    "has_saved": false,
    "creation_timestamp": 1714687167.8024268,
    "poll": null,
    "embed": null,
    "gift": null
}
```

## Reaction object

| field | type | details |
|-------|------|---------|
| user | user_object | A [user object](#user-object) |
| post_id | int | Unique post ID |
| reaction_id | int | Unique reaction ID |
| reply | reaction_reply | A [reaction reply object](#reaction-reply-object) |
| description | string | Reaction description (1-500 characters) |
| likes | int | Amount of likes |
| has_liked | boolean | Has the requesting user liked this reaction |
| creation_timestamp | int | Timestamp op reaction creation date |

Example response

```json
{
    "user": {
        "user_id": 5,
        "username": "kipteam",
        "permissions": 64,
        "avatar": "default.png",
        "status": "Hi, I am a Gluo user!"
    },
    "post_id": 7,
    "reaction_id": 1,
    "description": "very cool reaction",
    "reply": null,
    "likes": 0,
    "has_liked": false,
    "creation_timestamp": 1675610927.9662814
}
```

## Reaction reply object
| field | type | details |
|-------|------|---------|
| avatar | string | The user's avatar |
| username | string | The user's name |
| description | string | The reply's description |
| reaction_id | int | The reply's id |

Example response
```json
{
    "avatar": "default.png",
    "username": "kipteam",
    "description": "very cool reaction",
    "reaction_id": 1
}
```


## Group object

YET TO BE DEFINED.

## Member object

YET TO BE DEFINED.
