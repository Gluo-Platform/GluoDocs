# Reaction


## Reaction Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique reaction ID |
| post_id | snowflake | Unique post ID |
| reply | [ReplyObject]()? | If present, replied reaction |
| pinned | boolean | Whether this reaction is pinned by post Author |
| description | string | reaction descript ion |
| creation_timestamp | unix timestamp | Timestamp of reaction creation |
| edit_timestamp | unix timestamp | Timestamp of last reaction edit |
| author | [user](/HTTP_API_RESOURCES/user.md#user-object) | Reaction author (LARGE) |


## Reply Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique reaction ID | 
| description | string | Reaction contents |
| author | [user](/HTTP_API_RESOURCES/user.md#user-object) | Reaction author (ALL) |


## Create & edit reaction

{% hint style="info" %}
**`POST`** `/app/reaction/save`
{% endhint %}
{% hint style="warning" %}
**`PATCH`** `/app/reaction/save`
{% endhint %}

Create or edit a reaction. When creating, reaction_id should not be added, when
editing it should.

Create or edit a reaction. 
**JSON Params**

| field | type | description |
|-------|------|-------------|
| reaction_id? | snowflake | Unique reaction ID (required when editing) |
| reply_id? | snowflake | Reaction replied to |
| post_id? | snowflake | Post reacted to |
| description | string(1:500) | Reaction description |
