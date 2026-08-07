# User

There are two types of user: "Regular" and Bot. They operate very similarly, 
the difference is that the last one is owned by a "Regular" user has less
permissions than a "Regular" user.


## Scopes

Not all information about a user is accessible to everyone. Certain fields are limited to specific permissions.

1. Fields marked ALL are available ANY time a User is referenced.
2. Fields marked LARGE extend the user in cases where it is the primary author.
3. Just like ALL, the USER scope is public. Unlike ALL its fields are only 
present when fetching a user
4. Fields marked with the @ME are only avaible when fetching the 
[current user](#get-current-user)

## User Object

| field | type | description | scope |
|-------|------|-------------|-------|
| id | snowflake | Unique user ID | ALL |
| username | string | Unique username (1-25 characters) | ALL |
| avatar | [MediaObject]() | The user's avatar | ALL |
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


## BannerObject
| field | type | description |
|-------|------|-------------|
| type | "hex" \| "media" | Type of the banner |
| value | string \| [MediaObject]() | Hexcode or banner media object |


## Get current user

{% hint icon="code" style="success" %}
**`GET`** `/user/@me`
{% endhint %}

Returns the [user](user.md#user-object) object for the Authenticated client. 
Add the `?relation=true` parameter to receive a 
[WebSocket Event](/WEBSOCKET_API_RESOURCES/events.md#0002-userrelation) with 
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
[WebSocket Event](/WEBSOCKET_API_RESOURCES/events.md#0002-userrelation) with 
the relation status of the requesting and requested user.
