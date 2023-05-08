# Gluo Groups

## Join a group

### `POST` /group/join

JSON Parameters required:
| field | type | nullable | details |
|-------|------|----------|---------|
| group_invite | str | false | The invite (code) of the guild you want to join |

Returns a [member object](/core/objects.md#member-object) upon successfully joining.

## Get a group

### `GET` /group/{group_id}

Returns a [group object](/core/objects.md#group-object) for the group with the provided `group_id`.

## Leave a group

### `DELETE` /group/{group_id}/leave

Delete your member account permanently. The requesting authorization-token must be a member of the group. Returns `204 No Content` on success.
