# Post Resource
## Getting posts 
### `GET` https://xxxxxxxxx/xxxxxxxxx/posts/{topic}?page={page_number}?object_count={object_count}
Returns all public posts under the provided [topic](/docs/core/objects.md#topic).  
If `?page={x}` is not added it will automatically return the first page. You can add any number that is a valid page to get posts in return otherwise it will error appropriatly.  
If `?object={x}` is not added to the url it will use the default object limit of 25 objects per page. Any number can be used within a range of 10 -> 50.
Response:
| field | type   | details |
|-------|--------|---------|
| posts  | array | Returns an array of corresponding objects |
| next_page  | boolean | Returns if there is a next page | 

## Get a specific post
### `GET` https://xxxxxxxxx/xxxxxxxxx/{post_id}
Returns a [post](/docs/core/objects.md#posts) object if the provided `post_id` exists.

## Creating posts
### `POST` https://xxxxxxxxx/xxxxxxxxxxxx
JSON Parameters required:
| field | type   | details | nullable |
|-------|--------|---------|----------|
| name  | string | Post title (1-25 characters) | false |
| description  | string | Post description (1-500 characters) | false | 
| topic  | string | Post topic (1-17 characters) | true |
| attachment_name | string | Filename AND extension (no max) | true |
| attachment_base64 | string | File turned into base64 (UTF-8 decoded) | true |

## Deleting posts 
### `DELETE` https://xxxxxxxxx/xxxxxxxxxxxxxxx/{post_id}
Deletes the post, only accessible for the owners of said post.