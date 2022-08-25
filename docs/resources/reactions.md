# Reaction Resource
## Getting reactions 
### `GET` https://xxxxxxxxx/xxxxxxxxxx/{reaction_id}
Returns a `reaction object` if the provided `reaction_id` exists.
```json
doesn't exist, will come
```

## Getting all reactions
### `GET` https://xxxxxxxxx/xxxxxxxxxxxxx/{post_id}
```json
doesn't exist either, will come too
```

## Creating reactions 
### `POST` https://xxxxxxxxx/xxxxxxxxxxxxxxxx
JSON Parameters required:
| field | type   | details |
|-------|--------|---------|
| post_id  | integer | Post ID of the post that the reaction should be appended to |
| description  | string | Post description (1-500 characters) |

## Deleting reactions 
### `DELETE` https://xxxxxxxxx/xxxxxxxxxxxxxxxx/{reaction_id}
Deletes the reaction, only accessible for the owners of said reaction. Returns a [success response](/docs/resources/common_responses.md#success).