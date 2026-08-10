# Post


## Post Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique post ID |
| description | string | post descript ion |
| creation_timestamp | unix timestamp | Timestamp of post creation |
| edit_timestamp | unix timestamp | Timestamp of last post edit |
| author | [user](/HTTP_API_RESOURCES/user.md#user-object) | Post author (LARGE) |
| embed | [EmbedObject](#embed-object)? | Post embed |
| media | [MediaObject]() list | List of media if any |
| poll | [ChoiceObject](#choice-object) list | List of choices if any |
| app_url | string(1:256)? | Url to application (only available to [App clients](./app.md#app)) |


## Embed Object

| field | type | description |
|-------|------|-------------|
| type | "post" \| "reaction" | What type of embed this is |
| id | snowflake | Unique post ID | 
| description | string | Post or reaction contents |
| thumbnail | [MediaObject]()? | Optional embed thumbnail |
| author | [user](/HTTP_API_RESOURCES/user.md#user-object) | Post author (ALL) |


## Choice Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique choice ID | 
| choice | string | Post or reaction contents |


## Create & edit post

{% hint icon="code" style="info" %}
**`POST`** `/app/post/save`
{% endhint %}
{% hint icon="code" style="warning" %}
**`PATCH`** `/app/post/save`
{% endhint %}

Create or edit a post. Post with no contents (no quote, no description, no 
media and no poll) will not be accepted. 

If the client is an App, it may set is_app to `true`, to attach an 
[App Instance]() to the post. Once set, this cannot be edited. Can only be 
combined with a description.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| id? | snowflake | Unique post ID (required when editing) |
| quote_id? | snowflake | Quoted post ID |
| reaction_quote_id? | snowflake | Quoted reaction ID |
| description | string(1:1000)? | Draft description |
| media | EditMedia | List of associated media |
| poll | string(1:50) list | All options for the poll |
| is_app? | boolean | Whether post is app instance (cannot be edited), requires client to be [app](./app.md#app) |

**Edit Media**
| field | type | description |
|-------|------|-------------|
| old | snowflake list | List of currently associated Media that was not removed |
| new | snowflake list | List of new media IDs |
| del | snowflaek list | List of media IDs that were deleted |

### Media-keys

{% hint icon="code" style="success" %}
**`GET`** `/app/post/media-key`
{% endhint %}

Will grant you a media-key which is required to authenticate requests to the 
MediaApi. Returns a [media key]() object. Read more on uploading media [here]()


## Like post

{% hint icon="code" style="warning" %}
**`PATCH`** `/app/post/{post.id}/like/toggle?value=1`
{% endhint %}

Takes a queryparameter `value` that must have a value between 1 and 5 when 
present. This parameter is only optional when removing a like. Returns the 
current status:

```json
{
    "has_liked": true,
    "delta_likes": -3
}
```


## Vote on poll

{% hint icon="code" style="info" %}
**`POST`** `/app/post/poll/vote`
{% endhint %}

Will make the requesting user vote for that choice. If they already have a vote
under the post, it will be removed.

**JSON Params**
| field | type | description |
|-------|------|-------------|
| post_id | snowflake | Post that owns the poll |
| choice_id | snowflake | Id of the voted poll option |
