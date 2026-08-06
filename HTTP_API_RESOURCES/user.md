# User

There are two types of user: "Regular" and Bot. They operate very similarly, 
the difference is that the last one is owned by a "Regular" user has less
permissions than a "Regular" user.


## Scopes

Not all information about a user is accessible to everyone. Certain fields are limited to specific permissions.

1. The LARGE scope is public, but not always present. When the user is the Author of a post or reaction, fields marked LARGE will not be present.
2. Fields marked with the USER scope are only available to the requesting User.

## User Object

| field | type | description | scope |
|-------|------|-------------|-------|
| id | snowflake | Unique user ID | ALL |
| username | string | Unique username (1-25 characters) | ALL |
| avatar | [MediaObject]() | The user's avatar | ALL |
| banner | [BannerObject](#bannerobject) | The user's banner | LARGE |
| permissions | integer | User [permissions](permissions.md#general-permissions) | ALL |
| status | string | The user's status | ALL |
| about | string | The user's about-me | LARGE |
| private | boolean | Is it a private account | LARGE |
| invisible | boolean | Is the user in invisible mode | USER |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the account | LARGE |
| email_address? | string | Email address of user | USER |
| streak | integer | Current posting streak of usr | LARGE |
| feeds | [Feed]() list | List of user feeds | USER |

```json
{"TODO": "exmaple user"}
```


## BannerObject
| field | type | description |
|-------|------|-------------|
| type | "hex" \| "media" | Type of the banner |
| value | string \| [MediaObject]() | Hexcode or banner media object |


## Get current user

{% hint style="success" %}
**`GET`** `/user/@me`
{% endhint %}

Returns the [user](user.md#user-object) object for the Authenticated client.


## Get user

**By ID**
{% hint style="success" %}  
**`GET`** `/user/{user.id}`
{% endhint %}

**BY username**
{% hint style="success" %}  
**`GET`** `/user/{user.username}?username=true`
{% endhint %}

Returns the [user](user.md#user-object) object for a given user.
