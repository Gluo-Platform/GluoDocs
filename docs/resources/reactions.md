# Reaction Resource
## Getting reactions 
### `GET` https://xxxxxxxxx/xxxxxxxxxx/{reaction_id}
Returns a `reaction object` if the provided `reaction_id` exists.
```json
{
    "user_id": 2,
    "username": "kipteam",
    "user_pfp": "kipteam.png",
    "permissions": 63,
    "premium": 0,
    "reaction_id": 83,
    "description": "using trello on mobile is annoying",
    "upload_date": 1659804320,
    "liked": true,
    "likes": 1
}
```

## Getting all reactions
### `GET` https://xxxxxxxxx/xxxxx/xxxxxxxxxxxxx/{post_id}
```json
[{
    "user_id": 13,
    "username": "ayumi",
    "user_pfp": "ayumi.jpg",
    "permissions": 1,
    "premium" : 0,
    "reaction_id": 82,
    "description": "use trello board when ",
    "upload_date": 1659804017,
    "liked": false,
    "likes": 0
}, {
    "user_id": 2,
    "username": "kipteam",
    "user_pfp": "kipteam.png",
    "permissions": 63,
    "premium": 0,
    "reaction_id": 83,
    "description": "using trello on mobile is annoying",
    "upload_date": 1659804320,
    "liked": true,
    "likes": 1
}]
```

## Creating reactions 
### `POST` https://xxxxxxxxx/xxxxxxxxxxxxxxxx
JSON Parameters required:
| field | type   | details | can be empty |
|-------|--------|---------|----------|
| post_id  | integer | Post ID of the post that the reaction should be appended to | false |
| description  | string | Post description (1-500 characters) | false |

## Deleting reactions 
### `DELETE` https://xxxxxxxxx/xxxxxxxxxxxxxxxx/{reaction_id}
Deletes the reaction, only accessible for the owners of said reaction or the owner of the post.