# Gluo Searching

## Search in the app

### `GET` /search/{query}

Optional query parameters:
| field | type | nullable | details |
|-------|------|----------|---------|
| user | bool | true | Should it look for only users |
| exact_user | bool | true | Should it look for only users |
| post | bool | true | Should it look for only posts |
| exact_post | bool | true | Should it look for only posts |
| topic | bool | true | Should it look for only topics |
| exact_topic | bool | true | Should it look for only topics |

You can add any of the above and have them stack to limit your results to anything you want.  
Examples:

- `/search/{query}?user=true&exact_post=true` will return any user that has the query anywhere in their in username and posts that have an exact match for the description or title with the query.
- `/search/{query}?exact_user=true&exact_post=true&exact_topic=true` will return the user with an exact username match, posts with an exact title or description match and topics with an exact match.

Returns a list for each match type (`users`, `posts` and `topics`).
