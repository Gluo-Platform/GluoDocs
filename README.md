# Gluo API Reference

Official developer API documentation for the Gluo API. Alongside query-able 
endpoints, this reference also contains endpoints that are limited to Users 
or limited to internal use only. All generally available endpoints are listed
[here](./general_endpoints.md).

**Base url**
```shell
https://api.gluo.xyz/
```


## Error messages

**Field error**
```json
{
    "error": "Validation Failed",
    "details": [
        {
            "field": "email_address",
            "message": "Email address already exists.",
            "code": 4006
        }
    ]
}
```

**General error**
```json
{
    "error": "Validation Failed",
    "details": [
        {
            "message": "No body was provided",
            "code": 4004
        }
    ]
}
```

_REMOVE: I am currently still in the process of migrating error messages, so 
you might run into an error of a different format, in that case report this to
me so I can fix it rather than introducing support for it._


## Authentication

Authenticating with the Gluo API can be done in two ways:

1. Using a User token gained by a login request 
2. Using a _Bot_ token _(TODO: this system is not yet finished)_

**Example User Authorization Header**
```shell
Authorization: Bearer 89f4865eb59c0aba22fc9f9b9b75fc5218a1f502b3835a4ce26cc39ab50f351c92d3ac882eb4594856ea4c7f7e4620ef0fb94ea06ac892633d5cef1630e24766
```

**Example Bot Authorization Header**
```shell
Authorization: Bot 89f4865eb59c0aba22fc9f9b9b75fc5218a1f502b3835a4ce26cc39ab50f351c92d3ac882eb4594856ea4c7f7e4620ef0fb94ea06ac892633d5cef1630e24766
```


## Nullable and Optional Resource fields

This API will describe returned objects and request bodies. These are 
represented by tables of fields using the expected name. Some fields are 
optional or nullable. The used syntax for the documentation is as follows
| Field | Type | Description |
|-------|------|-------------|
| field | string | Required string field |
| field? | string | Optional string field |
| field | string? | Nullable string field |
| field? | string? | Optional and nullable string field |


## HTTP API

**Content-Type**

Clients must provide a valid `Content-Type` header. Gluo will only accept 
`application/json`.

**Rate limiting**

_TODO_


## WebSocket API

The WebSocket API is used for mainting consistent state between client and 
server. This is used for receiving real-time events that the client can track
to update local state. For opening a WebSocket connection read more [here]()


## Media

**Base url**
```shell
https://cdn.gluo.xyz/
```

Media in Gluo is stored on a separate CDN. Access to the resources can only be
done with signed access-urls. These are returned by relevant API requests (post
object contains a signed url, etc...). Extension and file formats are all 
handled by this service and provided to you through the API. For uploading and
retreiving media, read more [here]()
