# Overview

Gluo Apps are available to [Group Feeds](/HTTP_API_RESOURCES/feed.md#group-feeds).
Features explained here are only accessible to active [Apps](/HTTP_API_RESOURCES/app.md)
through [App Instances]().


## Install the SDK

```shell
npm install @gluo-platform/app-sdk
```


## Setup

```ts
import { AppSDK } from '@gluo-platform/app-sdk';

const sdk = new AppSDK();
```


## Flow

Posts [Post](/HTTP_API_RESOURCES/post.md) are served to users through our API. 
Apps can create posts with [App Instances]() which are treated as regular posts
by the backend. When a post with an `app_url` comes into view for a user, a 
[MOUNT](#events) event will be emitted. If this is the first time your instance 
is loaded, it will be preceded by an [INIT](#events) event.


## Methods

### on()

Used to subscribe to a specific [SDK Event](#sdk-events)

```ts
sdk.on("INIT", (payload) => {
    console.log(`Initiated for user: ${payload.user_id}`);
});
```


### send()

```ts
sdk.send()
```


## Events

| name | description |
|------|-------------|
| [INIT](#init) | Send once and is followed by MOUNT event |
| MOUNT | Send when your application is served |
| UNMOUNT | Send when your application is no longer active |


### Init

Called once for every instance and only if the instance is ever loaded by the
user. Contains a payload _TODO: PROVIDE ACTUAL VALUES_

```json
{
    "theme": "light",
    "post_id": ...,
    "user_id": ...,
    "username": ...,
    "avatar": ...
}
```