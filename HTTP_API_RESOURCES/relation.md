# Relations


## Add friend

{% hint icon="code" style="info" %}
**`POST`** `/user/relations/friend`
{% endhint %}

Send friend request to user.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| user_id | snowflake | Unique user ID |


## Delete friend request

{% hint icon="code" style="danger" %}
**`DELETE`** `/user/relations/{user.id}/request/delete`
{% endhint %}

Delete outgoing friend request to provided user.


## Remove friend

{% hint icon="code" style="danger" %}
**`DELETE`** `/user/relations/friend/{user.id}/remove`
{% endhint %}

Remove given user as friend.


## Get friend requests

{% hint icon="code" style="success" %}
**`GET`** `/user/relations/requests`
{% endhint %}

Returns a [paginated (`key:users`)](/README.md#http-api) list of [LARGE User](./user.md#user-object) objects.


## Get number of friend requests

{% hint icon="code" style="success" %}
**`GET`** `/user/relations/requests`
{% endhint %}

Returns number of friend requests.

```json
{
    "total": 69
}
```


## Manage friend request

{% hint icon="code" style="warning" %}
**`PUT`** `/user/relations/request/{user.id}/{accept | reject}`
{% endhint %}

Either `accept` or `reject` the friend request of the specified user.


## Get Friends

{% hint icon="code" style="success" %}
**`GET`** `/user/relations/friends`
{% endhint %}

Returns a [paginated (`key:users`)](/README.md#http-api) list of [LARGE User](./user.md#user-object) objects.


## Toggle following

{% hint icon="code" style="warning" %}
**`PUT`** `/user/relations/following/{client.id}/toggle`
{% endhint %}

Toggle whether the requesting user follows the client.

I immediately want to point out that the Gluo Following system is not what it 
is in other social media platforms. Following is the best way to describe the
system, but it caries a meaning that we don't want to associate with it. For 
that reason following is the internal naming convention but to the outside we
use "Add to feed" and "Remove from feed". Because that is what the system is
in essence. A way to add someone's content to your feed (following them) or 
removing it (unfollowing them).


## Get followers

{% hint icon="code" style="success" %}
**`GET`** `/user/relations/followers`
{% endhint %}

Returns a [paginated (`key:users`)](/README.md#http-api) list of [LARGE User](./user.md#user-object) objects.


## Get following

{% hint icon="code" style="success" %}
**`GET`** `/user/relations/following`
{% endhint %}

Returns a [paginated (`key:users`)](/README.md#http-api) list of [LARGE User](./user.md#user-object) objects.


## Remove follower

{% hint icon="code" style="danger" %}
**`DELETE`** `/user/relations/follower/{user.id}/remove`
{% endhint %}

Removes the user as a follower.


## Toggle blocked

{% hint icon="code" style="warning" %}
**`PUT`** `/user/relations/blocked/{client.id}/toggle`
{% endhint %}

Toggle whether the requesting user blocked the client.


## Get blocked

{% hint icon="code" style="success" %}
**`GET`** `/user/relations/blocked`
{% endhint %}

Returns a [paginated (`key:users`)](/README.md#http-api) list of [LARGE User](./user.md#user-object) objects.
