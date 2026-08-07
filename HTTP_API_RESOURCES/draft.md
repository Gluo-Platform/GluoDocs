# Draft

Drafts are unfinished, unuploaded posts.


## Draft Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique draft ID |
| quote_id | snowflake? | Quoted post ID |
| reaction_quote_id | snowflake? | Quoted reaction ID |
| description | string | Draft description |
| media | EditMedia | List of associated media |
| poll | string(1:50) list | All options for the poll |
| coins | integer | Any coins that would be gifted with the post |


## Create & edit draft

{% hint icon="code" style="info" %}
**`POST`** `/draft/save`
{% endhint %}
{% hint icon="code" style="warning" %}
**`PATCH`** `/draft/save`
{% endhint %}


**JSON Params**

| field | type | description |
|-------|------|-------------|
| id? | snowflake | Unique draft ID (required when editing) |
| quote_id? | snowflake? | Quoted post ID |
| reaction_quote_id? | snowflake? | Quoted reaction ID |
| description? | string(1:1000) | Draft description |
| media | EditMedia | List of associated media |
| poll? | string(1:50) list | All options for the poll |
| coins? | integer | Any coins that would be gifted with the post |


## Get drafts

{% hint icon="code" style="success" %}
**`GET`** `/drafts`
{% endhint %}

Returns a [paginated (`key:drafts`)](/README.md#gluo-api-reference) list of 
[draft](#draft-object) objects.


## Delete draft

{% hint icon="code" style="danger" %}
**`DELETE`** `/draft/{draft.id}/delete`
{% endhint %}

Deletes the draft if the User owns it.
