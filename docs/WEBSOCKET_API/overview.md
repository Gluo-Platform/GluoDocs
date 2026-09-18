# Overview

**Base Url**
```shell
wss://api.gluo.xyz/io/
```

## Initiate Connection

When establishing a connection you should provide a token key in the auth option
of your SocketIO client. 
[Read more on socket.io](https://socket.io/docs/v4/client-options/#auth). The
value of this field should be the client token.

In response your app will receive a [0001 (Hello)](./events.md#0001-hello) event
to acnkowledge the connection.


## Posts

In case of fetching a single post, the 
[0003 (Single Post Statistics)](./events.md#0003-single-post-statistics) is 
emitted. When fetching a page of posts this event is fired **twice** and then
followed by a 
[0004 (Multiple Post Statistics)](./events.md#0003-multiple-post-statistics) 
