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

In response your app will receive a [0001 (Hello)](events.md#0001-hello) event
to acnkowledge the connection.
