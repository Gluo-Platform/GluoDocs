# Feed

There are two types of feeds.
1. **Personal feeds** are specific to the user and provide content from all
over (public) Gluo. Users are give some control over what a feed shows them.
2. **Group feeds** are shared feeds between users. The content of these feeds
is created by the members of the feed. Content consists of 
[Posts](./post.md#post-object) and [Shared Posts]().


## Feed Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique feed ID |
| type | "feed" \| "group_feed" | Type of feed |
| name | string(1:32) | Feed name |
| icon | string(1:128) | Font-Awesome Icon **or** signed cdn url |

```json
{
    "icon": "fa-home",
    "id": 7494123429667278848,
    "name": "fa-home",
    "type": "feed"
}
```


## Create & edit personal feed

{% hint icon="code" style="info" %}
**`POST`** `/feed/create`
{% endhint %}
{% hint icon="code" style="warning" %}
**`PUT`** `/feed/edit`
{% endhint %}


**JSON Params**

| field | type | description |
|-------|------|-------------|
| id? | snowflake | Unique feed ID (required when editing) |
| name | string(1:32) | Feed name |
| icon | string(1:128) | Font-Awesome Icon |
| topics | string(1:32) list | List of interests |
| prefer_media | boolean | Whether this feed should preference media |
| anyone | boolean | Limited to friends & subscriptions or not |


## Create & edit group feed

{% hint icon="code" style="info" %}
**`POST`** `/feed/group/create`
{% endhint %}
{% hint icon="code" style="warning" %}
**`PUT`** `/feed/group/edit`
{% endhint %}


**JSON Params**

| field | type | description |
|-------|------|-------------|
| id? | snowflake | Unique feed ID (required when editing) |
| public | boolean | Whether the feed is invite only |
| name | string(1:32) | Feed name |
| icon | string(1:128)? | Font-Awesome Icon |


## Get feeds

{% hint icon="code" style="success" %}
**`GET`** `/feeds`
{% endhint %}

Returns a [paginated](/README.md#gluo-api-reference) list of 
[feed](#feed-object) objects, this includes personal and group feeds. If you
want only feeds of a specific type, specify so with the `?type=` query 
parameter. Accepted values are `feed` and `group_feed`.


## Delete feed

{% hint icon="code" style="danger" %}
**`DELETE`** `/feed/{feed.type}/{feed.id}/delete`
{% endhint %}

Deletes the feed if the User owns it.


## Get feed posts


## Get group feed posts


## Get group feed post reactions
