# Gluo Reactions

## Create a reaction

### `POST` /reaction/create

JSON Parameters required:
| field | type | nullable | details |
|-------|------|----------|---------|
| post_id | int | false | The post the reaction is posted under |
| description | string | false | The description of the post |

Returns a [reaction object](/v4/core/objects.md#reaction-object) upon successful creation.

## Edit a reaction

### `POST` /reaction/edit

JSON Parameters required:
| field | type | nullable | details |
|-------|------|----------|---------|
| reaction_id | int | false | The reaction you want to edit |
| description | string | false | The description of the post |

The original reaction will be updated and get it's value changed.  
Returns the updated [reaction object](/v4/core/objects.md#reaction-object) upon successful edit.

## Delete a reaction

### `DELETE` /reaction/{reaction_id}/delete

Delete a reaction permanently. The requesting authorization-token must be linked to the owning user. Returns `204 No Content` on success.

## Get a reaction

### `GET` /reaction/{reaction_id}

Returns a [reaction object](/v4/core/objects.md#reaction-object) if a valid `reaction_id` is provided.

## Get all reactions under a post

### `GET` /post/{post_id}/reactions

Returns an array of [reaction objects](/v4/core/objects.md#reaction-object) if a valid `post_id` is provided.

## Get all reactions by a user

### `GET` /user/{user_id}/reactions

Returns an array of [reaction objects](/v4/core/objects.md#reaction-object) if a valid `user_id` is provided.
