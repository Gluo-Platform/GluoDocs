# Gluo users

## Get a user

### `GET` /user/{user_query}

Search for a user by the provided `user_query`. If you are looking for a user by ID, append `?id=true` to the end (`/user/{user_id}?id=true`).  
If you are looking for more information on yourself, pass along your user token and use `@me` as `user_query` (`/user/@me`).  

Returns a [large user object](/v4/core/objects.md#large-user-object)

## Get a user's following

### `GET` /user/{user_id}/following

You can get the users the user of the `user_id` follows if they have their `PUBLIC_INTERACTIONS` set to `true`. This is a privacy measure taken so that people can chose if they want to share their followings.

Returns an array of [small user objects](/v4/core/objects.md#small-user-object) if the user has `PUBLIC_INTERACTIONS` set to `true`.

## Get a user's followers

### `GET` /user/{user_id}/followers

You can get the followers of a user if they have their `PUBLIC_INTERACTIONS` set to `true`. This is a privacy measure taken so that people can chose if they want to share their followers.

Returns an array of [small user objects](/v4/core/objects.md#small-user-object) if the user has `PUBLIC_INTERACTIONS` set to `true`.
