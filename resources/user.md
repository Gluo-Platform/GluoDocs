# Gluo users

## Get a user

### `GET` /user/{user_query}

Search for a user by the provided `user_query` (should be a `user_id`). If you are looking for a user by username, append `?username=true` to the end (`/user/{username}?username=true`).  
If you are looking for more information on yourself, pass along your user token and use `@me` as `user_query` (`/user/@me`).  

Returns a [large user object](/v4/core/objects.md#large-user-object)

## Get a user's following

### `GET` /user/{user_id}/following

You can get the users the user of the `user_id` follows if they have their `PUBLIC_INTERACTIONS` set to `true`. This is a privacy measure taken so that people can chose if they want to share their followings.

Returns an array of [small user objects](/v4/core/objects.md#small-user-object) if the user has `PUBLIC_INTERACTIONS` set to `true`.

Makes use of pagination:
`/user/{user_id}/following?page={page_number}&object_count={object_count}`  
By default `page_number` is 1. `object_count` is 10.

## Get a user's followers

### `GET` /user/{user_id}/followers

You can get the followers of a user if they have their `PUBLIC_INTERACTIONS` set to `true`. This is a privacy measure taken so that people can chose if they want to share their followers.

Returns an array of [small user objects](/v4/core/objects.md#small-user-object) if the user has `PUBLIC_INTERACTIONS` set to `true`.

Makes use of pagination:
`/user/{user_id}/followers?page={page_number}&object_count={object_count}`  
By default `page_number` is 1. `object_count` is 10.
