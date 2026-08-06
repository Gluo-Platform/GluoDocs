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
| banner | [BannerObject]() | The user's banner | LARGE |
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


## Get current user
<mark class="color-green">**GET**</mark> `/user/@me`

Returns the [user](user.md#user-object) object for the Authenticated client.


## Get user
**By ID**  
<mark class="color-green">**GET**</mark> `/user/{user.id}`

**BY username**  
<mark class="color-green">**GET**</mark> `/user/{user.username}?username=true`

Returns the [user](user.md#user-object) object for a given user.

<!-- <mark class="color-blue">**POST**</mark> `/api/v1/users`
<mark class="color-yellow">**PUT**</mark> `/api/v1/users/{id}`
<mark class="color-red">**DELETE**</mark> `/api/v1/users/{id}` -->
