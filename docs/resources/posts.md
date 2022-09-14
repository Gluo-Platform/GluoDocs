# Post Resource
## Getting posts 
### `GET` https://xxxxxxxxx/xxxxxxxxx/{post_id}
Returns a `post` object if the provided `post_id` exists.
```json
{
   "user_id" : 2,
   "username": "kipteam",
   "user_pfp": "kipteam.png",
   "permissions": 63,
   "premium": 0,
   "post_id": 2,
   "name": "another test",
   "description": "YEEEE",
   "topic": "test",
   "is_image": true,
   "image_name": "1658484500.png",
   "upload_date": 1658484499,
   "likes": 3,
   "liked": true,
   "comments": 1,
   "visible": false,
   "validated": true
}
```

## Creating posts
### `POST` https://xxxxxxxxx/xxxxxxxxxxxx
JSON Parameters required:
| field | type   | details |
|-------|--------|---------|
| name  | string | Post title (1-25 characters) |
| description  | string | Post description (1-500 characters) |
| topic  | string | Post topic (1-17 characters) |
_image uploading coming soon_

## Deleting posts 
### `DELETE` https://xxxxxxxxx/xxxxxxxxxxxxxxx/{post_id}
Deletes the post, only accessible for the owners of said post.