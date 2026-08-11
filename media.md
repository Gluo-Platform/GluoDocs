# Media

Media in Gluo is stored on a separate CDN. Access to the resources can only be
done with signed access-urls.

**Base url**
```shell
https://cdn.gluo.xyz/
```


## Uploading media

Initially you will have to make a request to the API for a media-key. This key 
has limited uses, depending on what you are uploading.

**For posts**

{% hint icon="code" style="success" %}
**`GET`** `/post/media-key`
{% endhint %}

**For Avatars & Banners**

{% hint icon="code" style="success" %}
**`GET`** `/client/settings/media-key`
{% endhint %}

**For Group Feed Icons**

{% hint icon="code" style="success" %}
**`GET`** `/feed/media-key`
{% endhint %}

The responses for all these requests are structured the same. The values of the
data object depend on the request.

```json
{
    "data": {
        "id": ..., 
        "max": 1,
        "size": 10
    },
    "key": ...
}
```

**Data Object**

| field | type | description |
|-------|------|-------------|
| id | snowflake | Associated client ID |
| max | integer | Maximum amount of uses |
| size | integer | Maximum file size in MBs |

After getting the key you make a request to one of these endpoints, depending
on what ...
