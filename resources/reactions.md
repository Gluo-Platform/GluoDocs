# Gluo Reactions

## Get a reaction

### `GET` /reaction/{reaction_id}

Returns a [reaction object](/v4/core/objects.md#reaction-object) if a valid `reaction_id` is provided.

## Get all reactions under a post

### `GET` /post/{post_id}/reactions

Returns an array of [reaction objects](/v4/core/objects.md#reaction-object) if a valid `post_id` is provided.

## Get all reactions by a user

### `GET` /user/{user_id}/reactions

Returns an array of [reaction objects](/v4/core/objects.md#reaction-object) if a valid `user_id` is provided.
