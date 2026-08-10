# App


## Scopes

Not all information about a app is accessible to everyone. Certain fields are limited to specific permissions.

1. Fields marked ALL are available ANY time a App is referenced.
2. Fields marked LARGE extend the app in cases where it is the primary author.
3. Just like ALL, the USER scope is public. Unlike ALL its fields are only 
present when fetching a app

## App Object

| field | type | description | scope |
|-------|------|-------------|-------|
| id | snowflake | Unique app ID | ALL |
| username | string | Appname | ALL |
| avatar | [MediaObject]() | The app's avatar | ALL |
| permissions | bitflags | App [permissions](/permissions.md#general-permissions) | LARGE |
| status | string | The app's status | LARGE |
| banner | [BannerObject](./user.md#bannerobject) | The app's banner | USER |
| about | string | The app's about-me | USER |
| private | boolean | Is it a private app | USER |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the app | USER |

```json
{"TODO": "exmaple app"}
```


## Get current app

{% hint icon="code" style="success" %}
**`GET`** `/app/@me`
{% endhint %}

Returns the [app](app.md#app-object) object for the Authenticated client.


## Get app

{% hint icon="code" style="success" %}
**`GET`** `/app/{app.id}`
{% endhint %}

Returns the [app](app.md#app-object) object for the provided id.


## Create Reaction

{% hint icon="code" style="info" %}
**`POST`** `/app/reaction/create`
{% endhint %}

Apps are allowed to create a reaction in the name of a user under posts with an
[App Instance](./post.md#app-instance).

**JSON Params**

| field | type | description |
|-------|------|-------------|
| key | string | App Instance key |
| user_id | snowflake | User that is reacting |
| post_id | snowflake | Post reacted to |
| description | string(1:500) | Reaction description |
