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


## Create draft

{% hint icon="code" style="info" %}
**`POST`** `/draft/create`
{% endhint %}

**JSON Params**

| field | type | description |
|-------|------|-------------|
| quote_id? | snowflake | Quoted post ID |
| reaction_quote_id? | snowflake | Quoted reaction ID |
| description | string(1:1000)? | Draft description |
| media | EditMedia | List of associated media |
| poll | string(1:50) list | All options for the poll |


## Edit draft

{% hint icon="code" style="warning" %}
**`PATCH`** `/draft/{draft.id}/edit`
{% endhint %}

| field | type | description |
|-------|------|-------------|
| description | string(1:1000)? | Draft description |
| media | EditMedia | List of associated media |
| poll | string(1:50) list | All options for the poll |


## Get drafts

{% hint icon="code" style="success" %}
**`GET`** `/drafts`
{% endhint %}

Returns a [paginated](/README.md#gluo-api-reference) list of 
[draft](#draft-object) objects.


## Delete draft

{% hint icon="code" style="danger" %}
**`DELETE`** `/draft/{draft.id}/delete`
{% endhint %}

Deletes the draft if the User owns it.
