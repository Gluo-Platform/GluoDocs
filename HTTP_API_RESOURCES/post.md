# Post


## Post Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique post ID |
| description | string | post descript ion |
| gift_id | string? | ID of associated gift |
| coins | integer | Value of associated gift |
| creation_timestamp | unix timestamp | Timestamp of post creation |
| edit_timestamp | unix timestamp | Timestamp of last post edit |
| author | [user](/HTTP_API_RESOURCES/user.md#user-object) | Post author (LARGE) |
| embed | [EmbedObject]()? | Post embed |
| media | [MediaObject]() list | List of media if any |
| poll | string list | List of choices if any |


## Embed Object

| field | type | description |
|-------|------|-------------|
| type | "post" \| "reaction" | What type of embed this is |
| id | snowflake | Unique post ID | 
| description | string | Post or reaction contents |
| thumbnail | [MediaObject]()? | Optional embed thumbnail |
| author | [user](/HTTP_API_RESOURCES/user.md#user-object) | Post author (ALL) |


## Create & edit post

{% hint style="info" %}
**`POST`** `/post/save`
{% endhint %}
{% hint style="warning" %}
**`PATCH`** `/post/save`
{% endhint %}

Create or edit a post. Post with no contents (no quote, no description, no 
media, no poll and no coins) will not be accepted.

| field | type | description |
|-------|------|-------------|
| post_id | snowflake | Unique post ID |
| quote_id? | snowflake? | Quoted post ID |
| reaction_quote_id? | snowflake? | Quoted reaction ID |
| description? | string(1:1000) | post description |
| media | [EditMedia](#edit-media) | List of associated media |
| poll? | string list | All options for the poll |
| coins? | integer | Any coins that would be gifted with the post |

### Edit Media
| field | type | description |
|-------|------|-------------|
| old | snowflake list | List of currently associated Media that was not removed |
| new | snowflake list | List of new media IDs |
| del | snowflaek list | List of media IDs that were deleted |
