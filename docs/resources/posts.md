# Post Resource
## Getting posts 
### `GET` https://xxxxxxxxx/xxxxxxxxx/{post_id}
Returns a `post` object if the provided `post_id` exists.
```json
{
   "post_id": 2,
   "parent_name": "kipteam",
   "parent_pfp": "kipteam.png",
   "parent_badge": "team",
   "name": "another test",
   "description": "YEEEE",
   "topic": "test",
   "is_image": true,
   "image_name": "1658484500.png",
   "upload_date": 1658484499,
   "likes": 3,
   "liked": true,
   "comments": 1,
   "is_private": false,
   "visible": false,
   "validated": true
}
```
_Move reactions to their own endpoint_

## Creating posts
### `POST` https://xxxxxxxxx/xxxxxxxxxxxx
JSON Parameters required:
| field | type   | details |
|-------|--------|---------|
| name  | string | Post title (1-25 characters) |
| description  | string | Post description (1-500 characters) |
| topic  | string | Post topic (1-17 characters) |

## Deleting posts 
### `DELETE` https://xxxxxxxxx/xxxxxxxxxxxxxxx/{post_id}
Deletes the post, only accessible for the owners of said post. Returns a [success response](/docs/resources/common_responses.md#success).