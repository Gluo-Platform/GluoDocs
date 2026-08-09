# Overview

Gluo Apps are available to [Group Feeds](/HTTP_API_RESOURCES/feed.md#group-feeds).


## Install the SDK

```shell
npm install @gluo-platform/app-sdk
```


## Setup

```ts
import { AppSDK } from '@gluo-platform/app-sdk';

const sdk = new AppSDK();
```


## Methods

### on()

Used to subscribe to a specific [SDK Event](#sdk-events)

```ts
sdk.on("READY", (payload) => {
    console.log("Application served to client");
});
```


### send()

```ts
sdk.send()
```


## Events

| name | description |
|------|-------------|
| READY | Send when your application is served |
