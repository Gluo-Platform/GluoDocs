# Reaction Resource
## Getting reactions 
### `GET` https://xxxxxxxxx/xxxxxxxxxx/{reaction_id}
Returns a [reaction](/docs/core/objects.md#reactions) object if the provided `reaction_id` exists.

## Getting all reactions
### `GET` https://xxxxxxxxx/xxxxx/xxxxxxxxxxxxx/{post_id}
Returns all reactions under the provided [post](/docs/core/objects.md#posts).  
If `?page={x}` is not added it will automatically return the first page. You can add any number that is a valid page to get posts in return otherwise it will error appropriatly.  
If `?object={x}` is not added to the url it will use the default object limit of 50 objects per page. Any number can be used within a range of 10 -> 100.
Response:
| field | type   | details |
|-------|--------|---------|
| reactions  | array | Returns an array of [reaction](/docs/core/objects.md#reactions) objects |
| next_page  | boolean | Returns if there is a next page | 

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