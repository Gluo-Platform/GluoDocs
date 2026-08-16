# Gift

{% hint style="danger" %}
This page is subject to change as Premium is ondergoing some re-conceptualisation...
{% endhint %}

Managed and maintained by Users. Can be claimed by other Users.


## Gift Object

| field | type | description |
|-------|------|-------------|
| id | string | Unique gift ID |
| user_id | snowflake | ID of owner |
| receiver_id | snowflake? | ID of receiver |
| coins | integer | Value of Gift |
| creation_timestamp | unix timestamp | Timestamp of creation |
| claim_timestamp | unix timestamp? | Timestamp of claim |


## Create Gift

{% hint icon="code" style="info" %}
**`POST`** `/premium/gift/create`
{% endhint %}

Removes the coins from the user's shareable coins. Setting a gift to 
unshareable is exclusive to Moderators.

**JSON Params**
| field | type | description |
|-------|------|-------------|
| coins | integer | Value of the gift |
| unshareable? | boolean | Whether the gifted coins are shareable |


## Get Gifts

{% hint icon="code" style="success" %}
**`GET`** `/premium/gifts`
{% endhint %}

Returns a [paginated](/README.md#gluo-api-reference) list of 
[gift](#gift-object) objects.


## Claim Gift

{% hint icon="code" style="warning" %}
**`PATCH`** `/premium/gift/{gift.id}/claim`
{% endhint %}

If the gift wasn't claimed already, the requesting user will receive it.


## Delete Gift

{% hint icon="code" style="danger" %}
**`DELETE`** `/premium/gift/{gift.id}/delete`
{% endhint %}

Requires the gift to be unclaimed, returns the value to the users shareable 
coins.

