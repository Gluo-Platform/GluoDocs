# Events

The events emitted and received by our WebSocket API do not use a sensical 
namingconvention. While all events do have a name, they are only used for 
referencing and not recognised by the API.


## Server Events

These are sent by the server to the client.


### 0001 Hello

Upon establishing a successfull connection.


### 0002 User Relation

Send when the `?relation=true` parameter is appended when fetching a user.

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique user ID |
| is_s | boolean | Is subscribed to user |
| is_f | boolean | Is friend of user |
| req_f | boolean | Requested to friend user |


### 0003 Single Post Statistics

Send when the `?statistics=true` parameter is appended when fetching a post.

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique post ID |
| a_id | snowflake | User ID of author |
| lks | integer | Total post likes |
| rns | integer | Total post reactions |
| is_s | boolean | Is subscribed to user |
| is_f | boolean | Is friend of user |
| req_f | boolean | Requested to friend user |
| lkd | boolean | Liked the post |
| bkd | boolean | Bookmarked the post |


### 0004 Post Statistics Page

This event is always advanced by two 
[0003 (Single Post Statistics)](#0003-single-post-statistics) events. This 
event contains the rest of the posts on that same page. (Same structure as 0003)
