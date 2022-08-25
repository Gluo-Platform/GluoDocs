# Post Resource
## Getting posts % GET https://api.gluo.xyz/post/{post_id}
Returns a post object if the provided post_id exists.
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
   "validated": true,
   "reactions": {
      "40": {
         "reaction_id": 40,
         "parent_name": "ayumi",
         "parent_pfp": "ayumi.jpg",
         "parent_badge": "team",
         "description": "",
         "upload_date": 1659524423,
         "likes": 0,
         "liked": false,
         "is_private": false,
         "visible": true,
         "validated": true
      }
   }
}
```
_Move reactions to their own endpoint?_

## Creating posts % POST https://api.gluo.xyz/createpost
JSON Parameters required:
| field | type   | details |
|-------|--------|---------|
| name  | string | Post title (1-25 characters) |
| description  | string | Post description (1-500 characters) |
| topic  | string | Post topic (1-17 characters) |

## Deleting posts % DELETE https://api.gluo.xyz/deletepost/{post_id}
Deletes the post, only accessible for the owners of said post. Returns a [success response](/docs/resources/common_responses.md#success).