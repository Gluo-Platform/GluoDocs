# Draft

Drafts are unfinished, unuploaded posts.


## Draft Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique draft ID |
| quote_id | snowflake? | Quoted post ID |
| reaction_quote_id | snowflake? | Quoted reaction ID |
| description | string | Draft description |
| media | [EditMedia](/HTTP_API_RESOURCES/post.md#edit-media) | List of associated media |
| poll | string list | All options for the poll |
| coins | integer | Any coins that would be gifted with the post |


## Create & edit draft

{% hint style="info" %}
**`POST`** `/draft/save`
{% endhint %}
{% hint style="warning" %}
**`PATCH`** `/draft/save`
{% endhint %}


| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique draft ID |
| quote_id? | snowflake? | Quoted post ID |
| reaction_quote_id? | snowflake? | Quoted reaction ID |
| description? | string(1:1000) | Draft description |
| media | [EditMedia]() | List of associated media |
| poll? | string list | All options for the poll |
| coins? | integer | Any coins that would be gifted with the post |
