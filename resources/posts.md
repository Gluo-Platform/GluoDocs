# Gluo Posts

## Get a specific post

### `GET` /post/{post_id}

Returns a [post object](/core/objects.md#post-object) for the post with the provided `post_id`.

## Get posts under a topic

### `GET` /posts/{topic}

Returns a list of [post objects](/core/objects.md#post-object) that all have this topic.  

Makes use of pagination:
`/posts/{topic}?page={page_number}&object_count={object_count}`  
By default `page_number` is 1. `object_count` is 10.

## Get posts by a user

### `GET` user/{user_id}/posts

Returns a list of [post objects](/core/objects.md#post-object) posted by the provided user.  

Makes use of pagination:
`/user/{user_id}/posts?page={page_number}&object_count={object_count}`  
By default `page_number` is 1. `object_count` is 10.
