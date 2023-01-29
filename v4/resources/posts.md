# Gluo Posts

## Creating posts

### `POST` /post/create

JSON Parameters required:
| field | type | nullable | details |
|-------|------|----------|---------|
| title | string | false | The title of the post |
| description | string | false/true | The description of the post (can only be null if attachment provided) |
| topics | array | true | The topics of the post |
| attachment_base64 | string | true | Attachment in base64 format |

Returns a [post object](/v4/core/objects.md#post-object) upon successfull creation.

## Get a specific post

### `GET` /post/{post_id}

Returns a [post object](/v4/core/objects.md#post-object) for the post with the provided `post_id`.

## Get posts under a topic

### `GET` /posts/{topic}

Returns a list of [post objects](/v4/core/objects.md#post-object) that all have this topic.  
Makes use of pagination:

`/posts/{topic}?page={page_number}&object_count={object_count}`
By default `page_number` is 1. `object_count` is 10.

## Get posts by a user

### `GET` user/{user_id}/posts

Returns a list of [post objects](/v4/core/objects.md#post-object) posted by the provided user.  
Makes use of pagination:

`/posts/{topic}?page={page_number}&object_count={object_count}`
By default `page_number` is 1. `object_count` is 10.