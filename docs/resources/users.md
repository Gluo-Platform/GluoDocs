# User Resource
## Getting users 
### `GET` https://xxxxxxxxx/xxxx/xxxxxxxx/{user_query}
You can search for users by their ID by adding `?id=true` at the end of the url.  
Returns a [user](/docs/core/objects.md#extensive-user-object) object if the provided `username` or `user_id` exists.

## Get a profile picture
### `GET` https://media.gluo.xyz/pfp/{user_pfp}
Provide the `user_pfp` field attached in a [simple user](/docs/core/objects.md#simple-user-object) or [extensive user](/docs/core/objects.md#extensive-user-object) object, get an image in return.

## Getting a user's followers
### `GET` https://xxxxxxxxx/xxxxxxxxx/{user_id}
Returns all users that follow the provided user if they allowed this in their settings.
If `?page={x}` is not added it will automatically return the first page. You can add any number that is a valid page to get posts in return otherwise it will error appropriatly.  
If `?object={x}` is not added to the url it will use the default object limit of 25 objects per page. Any number can be used within a range of 10 -> 50.
Response:
| field | type   | details |
|-------|--------|---------|
| users  | array | Returns an array of [simple user](/docs/core/objects.md#simple-user-object) objects |
| next_page  | boolean | Returns if there is a next page | 

## Getting the people a user follows
### `GET` https://xxxxxxxxx/xxxxxxxxx/{user_id}
Returns all users a user follows if they allowed this in their settings.
If `?page={x}` is not added it will automatically return the first page. You can add any number that is a valid page to get posts in return otherwise it will error appropriatly.  
If `?object={x}` is not added to the url it will use the default object limit of 25 objects per page. Any number can be used within a range of 10 -> 50.
Response:
| field | type   | details |
|-------|--------|---------|
| users  | array | Returns an array of [simple user](/docs/core/objects.md#simple-user-object) objects |
| next_page  | boolean | Returns if there is a next page | 