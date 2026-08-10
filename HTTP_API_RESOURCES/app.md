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
| appname | string | Unique appname (1-30 characters) | ALL |
| avatar | [MediaObject]() | The app's avatar | ALL |
| permissions | bitflags | App [permissions](/permissions.md#general-permissions) | LARGE |
| status | string | The app's status | LARGE |
| banner | [BannerObject](#bannerobject) | The app's banner | USER |
| about | string | The app's about-me | USER |
| private | boolean | Is it a private account | USER |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the account | USER |

```json
{"TODO": "exmaple app"}
```


## BannerObject
| field | type | description |
|-------|------|-------------|
| type | "hex" \| "media" | Type of the banner |
| value | string \| [MediaObject]() | Hexcode or banner media object |


## Get current app

{% hint icon="code" style="success" %}
**`GET`** `/app/@me`
{% endhint %}

Returns the [app](app.md#app-object) object for the Authenticated client.


## Get app

**By ID**
{% hint icon="code" style="success" %}  
**`GET`** `/app/{app.id}`
{% endhint %}

**BY appname**
{% hint icon="code" style="success" %}  
**`GET`** `/app/{app.appname}?appname=true`
{% endhint %}

Returns the [app](app.md#app-object) object for a given app.
Add the `?relation=true` parameter to receive a 
[WebSocket Event](/WEBSOCKET_API/events.md#0002-apprelation) with 
the relation status of the requesting and requested app.
