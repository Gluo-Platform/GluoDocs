# App


## Scopes

Not all information about an app is accessible to everyone. Certain fields are 
limited to specific permissions.

1. Fields marked ALL are available ANY time an App is referenced.
2. Fields marked LARGE extend the app in cases where it is the primary author.
3. Fields marked APP are only present when fetching a full app

## App Object

| field | type | description | scope |
|-------|------|-------------|-------|
| id | snowflake | Unique app ID | ALL |
| username | string | Appname | ALL |
| avatar | [Media Access ULR](/media.md#media-access-urls) | The app's avatar | ALL |
| permissions | bitflags | App [permissions](/permissions.md#general-permissions) | LARGE |
| status | string | The app's status | LARGE |
| banner | [BannerObject](./user.md#bannerobject) | The app's banner | APP |
| about | string | The app's about-me | APP |
| private | boolean | Is it a private app | APP |
| creation_timestamp | unix timestamp | Unix timestamp of the creation date of the app | APP |

```json
{
  "id": "7494368590875856896",
  "username": "TEST",
  "avatar": "image/default.webp?e=1786812552&s=3_7oIcWPC6wX2Ok1rQX42SVt_ZH8YXQtjtB4G8ejhvk",
  "permissions": 1,
  "status": "Hi, I am a Gluo user!",
  "banner": {
    "type": "hex",
    "value": "#000000"
  },
  "about": "",
  "private": false,
  "creation_timestamp": 1786796710.7006962
}
```


## Create App

{% hint icon="code" style="info" %}
**`POST`** `/app/create`
{% endhint %}

Users with the [developer permission](/permissions.md#general-permissions) cna
own up to 5 apps.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| app_name | string(1:50) | App display nmae |
| app_url | string(1:256) | Unique application URL |
| avatar | snowflake? | App avatar |
| status | string(1:75)? | App status |
| about | string(1:500)? | App about-me |
| banner | snowflake? | App banner |

```json
{
  "token": "19h4YSI9AAEKiXt0Oh8TMHjKNOflz5PcFVyCcmvXm8FpOECMf1WG81iE9n-OWDh-8r-Ji8TQZi4MLOiIJwb55w"
}
```


## Set On-Add behaviour

{% hint icon="code" style="warning" %}
**`PUT`** `/app/on-add`
{% endhint %}

The JSON Params for this request are the same of a 
[post](./post.md#create--edit-post). The provided post is what the app will 
send immediately after being added to a feed. It is important to note that this initial post is <u>not</u> allowed to contain any media.


## Get current app

{% hint icon="code" style="success" %}
**`GET`** `/app/@me/`
{% endhint %}

Returns the [app](app.md#app-object) object for the Authenticated client.


## Get app

{% hint icon="code" style="success" %}
**`GET`** `/app/{app.id}/`
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


## Add App

{% hint icon="code" style="info" %}
**`POST`** `/app/add`
{% endhint %}

Add a public app to a Group Feed. Will immediately create a post, if it has 
[on-add](#set-on-add-behaviour) behaviour setup.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| app_id | snowflake | Unique App ID |
| feed_id | snowflake | Unique Group Feed ID |
