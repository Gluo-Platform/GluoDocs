# App SDK

The Gluo App SDK can be used **client-side** to make communicating with Gluo
easier. If your app is dependant on server-side logic, we do not have any 
installable libraries or packages for that. We however have code snippets and 
examples [here](todo).


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
Apps can create posts with [App Instances](/HTTP_API_RESOURCES/post.md#app-instance) 
which are treated as regular posts by the backend. When a post with an 
`app_url` comes into view for a user, a [MOUNT](#events) event will be emitted. 
If this is the first time your instance is loaded, it will be preceded by an 
[INIT](#events) event.


### Testing

You can emulate the flow (for testing reasons) with the test method. This takes
an optional time argument (milliseconds) which is how long it will wait before
sending the `UNMOUNT` event.

```ts
sdk.test(1000);
```


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
    "app_id": ...,
    "post_id": ...,
    "user_id": ...,
    "username": ...,
    "avatar": ...,
    "key": ...,
}
```
