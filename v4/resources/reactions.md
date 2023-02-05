# Gluo Reactions

## Create a reaction

### `POST` /reaction/create

JSON Parameters required:
| field | type | nullable | details |
|-------|------|----------|---------|
| post_id | int | false | The post the reaction is posted under |
| description | string | false | The description of the post |

Returns a [reaction object](/v4/core/objects.md#reaction-object) upon successfull creation.

## Edit a reaction

### `POST` /reaction/edit

JSON Parameters required:
| field | type | nullable | details |
|-------|------|----------|---------|
| reaction_id | int | false | The reaction you want to edit |
| description | string | false | The description of the post |

The original reaction will be updated and get it's value changed.  
Returns the updated [reaction object](/v4/core/objects.md#reaction-object) upon successfull editing.

## Get a reaction

### `GET` /reaction/{reaction_id}

Returns a [reaction object](/v4/core/objects.md#reaction-object) when found.
