# Media

Media in Gluo is stored on a separate CDN. Access to the resources can only be
done with signed access-urls.

**Base url**
```shell
https://cdn.gluo.xyz/
```


## Media Access Urls

For this you will need **signed access urls**. These are structured as follows

```shell
image/default.webp?e=1786784248&s=z-tm45mgujooLsMteDu7fedqdwKZohYke1I98F2QCdI
└─ Media type      │            └─ HMAC Signature
      │            └─ Unix Expiration Timestamp
      └─ File name and extension
```

The API returns these when requesting resources containing media. You only have
to append them to the base url.

```shell
https://cdn.gluo.xyz/image/default.webp?e=1786784248&s=z-tm45mgujooLsMteDu7fedqdwKZohYke1I98F2QCdI
```


## Uploading media

### Media signatures

Initially you will have to make a request to the API for a media-signature. This signature 
has limited uses, depending on what you are uploading.

**For posts & drafts**

{% hint icon="code" style="success" %}
**`GET`** `https://api.gluo.xyz/post/media-signature`
{% endhint %}

**For Avatars & Banners**

{% hint icon="code" style="success" %}
**`GET`** `https://api.gluo.xyz/client/settings/media-signature`
{% endhint %}

**For Group Feed Icons**

{% hint icon="code" style="success" %}
**`GET`** `https://api.gluo.xyz/feed/media-signature`
{% endhint %}

The responses for all these requests are structured the same. The values of the
data object depend on the request.

```json
{
    "data": {
        "id": 7494123429654695936,
        "max": 10,
        "size": 50,
        "time": 1787130308.785774,
        "type": "post"
    },
    "signature": "DEjTYrWO+WrRxO0rzNiFGOL+7MptdeZPOn9ep+tQ4Ho36347nAacY6UhpVCE+lkHDxnK2MJA1O2qDRWPKQn6WRrokcDVe3ZF8JUHu7SNrRTQetlCW5ZqwjDPflnUAaBwMjWYOmG0YiLrUsztkkMGxfDi1HltSv0gXRonc1bAe8fNXsBEutx2Gffnwu2BRTifcI/wRlB7XSZIEwD9v+2CnWjOH9IB9Bb+z73OchuLEI+b/QivrPrY837ynv/B80gyP6qkULvwUmn6QFQLsmzVIGis10vqpDXxgNeBfFT4vHXrBJIci3whkdd7CuCYYn1yHDtS53VALFZtEpKam0ISjw=="
}
```

**Data Object**

| field | type | description |
|-------|------|-------------|
| id | snowflake | Associated client ID |
| time | unix timestamp | When signature was created |
| type | "post" \| "avatar" \| "banner" \| "icon" | What type of media upload the token validates |
| max | integer | Maximum amount of uses |
| size | integer | Maximum file size in MBs |

After getting the signature you make a request to the upload endpoint.

### Uploading

{% hint icon="code" style="warning" %}
**`POST`** `https://cdn.gluo.xyz/upload`
{% endhint %}

**Authorization**

```shell
Bearer DEjTYrWO+WrRxO0rzNiFGOL+7MptdeZPOn9ep+tQ4Ho36347nAacY6UhpVCE+lkHDxnK2MJA1O2qDRWPKQn6WRrokcDVe3ZF8JUHu7SNrRTQetlCW5ZqwjDPflnUAaBwMjWYOmG0YiLrUsztkkMGxfDi1HltSv0gXRonc1bAe8fNXsBEutx2Gffnwu2BRTifcI/wRlB7XSZIEwD9v+2CnWjOH9IB9Bb+z73OchuLEI+b/QivrPrY837ynv/B80gyP6qkULvwUmn6QFQLsmzVIGis10vqpDXxgNeBfFT4vHXrBJIci3whkdd7CuCYYn1yHDtS53VALFZtEpKam0ISjw==
```

Expects a Bearer Authorization header with the signature retreived from the 
[Media signature](#media-signatures) endpoints.

For uploading, the body must be `multipart/form-data` body. This must also be 
reflected by the `Content-Type` header. Firstly you are required to attach your
media as a `file`. Secondly data must be added. This is the data returnede by 
the [Media signature](#media-signatures) endpoints.

This will return a status and a name. This name is important as it is what you
will pass to the API when it requires media.

```json
{"json": "TODO"}
```
