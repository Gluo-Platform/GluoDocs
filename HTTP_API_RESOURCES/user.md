# User


## Scopes

Not all information about a user is accessible to everyone. Certain fields are 
limited to specific permissions.

1. Fields marked ALL are available ANY time a User is referenced.
2. Fields marked LARGE extend the user in cases where it is the primary author.
3. Fields marked USER are only present when fetching a full user
4. Fields marked with the @ME are only avaible when fetching the 
[current user](#get-current-user)

## User Object

| field | type | description | scope |
|-------|------|-------------|-------|
| id | snowflake | Unique user ID | ALL |
| username | string | Unique username (1-30 characters) | ALL |
| avatar | [Media Access ULR]() | The user's avatar | ALL |
| permissions | bitflags | User [permissions](/permissions.md#general-permissions) | LARGE |
| status | string | The user's status | LARGE |
| banner | [BannerObject](#bannerobject) | The user's banner | USER |
| about | string | The user's about-me | USER |
| private | boolean | Is it a private account | USER |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the account | USER |
| streak | integer | Current posting streak of usr | USER |
| email_address? | string | Email address of user | @ME |
| invisible | boolean | Is the user in invisible mode | @ME |
| feeds | [Feed]() list | List of user feeds | @ME |

```json
{"TODO": "exmaple user"}
```


### BannerObject
| field | type | description |
|-------|------|-------------|
| type | "hex" \| "image" | Type of the banner |
| value | string \| [Media Access ULR]() | Hexcode or banner media object |


## User media object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique media ID |
| post_id | snowflake | Unique post ID |
| url | [Media Access ULR]() | Signed media url |

```json
{"TODO": "example media"}
```


## Get current user

{% hint icon="code" style="success" %}
**`GET`** `/user/@me`
{% endhint %}

Returns the [user](user.md#user-object) object for the Authenticated client. 
Add the `?relation=true` parameter to receive a 
[WebSocket Event](/WEBSOCKET_API/events.md#0002-userrelation) with 
the relation status of the requesting and requested user.


## Get user

**By ID**
{% hint icon="code" style="success" %}  
**`GET`** `/user/{user.id}`
{% endhint %}

**BY username**
{% hint icon="code" style="success" %}  
**`GET`** `/user/{user.username}?username=true`
{% endhint %}

Returns the [user](user.md#user-object) object for a given user.
Add the `?relation=true` parameter to receive a 
[WebSocket Event](/WEBSOCKET_API/events.md#0002-userrelation) with 
the relation status of the requesting and requested user.


## Get user bookmarks

{% hint icon="code" style="success" %}
**`GET`** `/user/bookmarks/`
{% endhint %}

Returns a [paginated (`key:posts`)](/README.md#gluo-api-reference) list of 
[post](./post.md#post-object) objects.


## Get archive

{% hint icon="code" style="success" %}
**`GET`** `/user/archive/`
{% endhint %}

Returns a [paginated (`key:posts`)](/README.md#gluo-api-reference) list of 
[post](./post.md#post-object) objects.


## Get user posts

{% hint icon="code" style="success" %}
**`GET`** `/user/{user.id}/posts`
{% endhint %}

Returns a [paginated (`key:posts`)](/README.md#gluo-api-reference) list of 
[post](./post.md#post-object) objects.


## Get user media

{% hint icon="code" style="success" %}
**`GET`** `/user/{user.id}/media`
{% endhint %}

Returns a [paginated (`key:media`)](/README.md#gluo-api-reference) list of 
[user media]() objects.


## Get user reactions

{% hint icon="code" style="success" %}
**`GET`** `/user/{user.id}/reactions`
{% endhint %}

Returns a [paginated (`key:reactions`)](/README.md#gluo-api-reference) list of 
[user media]() objects. Unless the visited user is also the requesting user,
this will not include any reactions placed under posts of private authors.


## Get user streak

{% hint icon="code" style="success" %}
**`GET`** `/user/{user.id}/streak`
{% endhint %}

```json
{
    "todo": "example"
}
```