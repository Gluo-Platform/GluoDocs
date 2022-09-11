# Rate limiting
Our API works with three levels of rate limits.
- `(hl)` High level
- `(ml)` Medium level
- `(ll)` Low level
Every endpoint has a specific has one of these three levels according to how frequently said endpoint can be accessed. 

## High level `(hl)`
This is the one with the highest rate limit. Any request to a low level endpoint is limited to 1 every second.  
The following endpoints are seen as low level endpoints:
- Creating a post
- Creating a reaction
- Delete a post
- Delete a reaction

## Medium level `(ml)`
This level is for endpoints that can't handle too many request whilst allowing more than a high level endpoint. Any endpoint of medium level can be requested 15 times per second.  
These endpoints are of medium level:
- getting all posts by a user

## Low level `(ll)`
All endpoints with this rate limit are fairly accessible. You can make up to 30 requests per second. 
Most of our endpoints have a high level rate limit:
- getting a user
- getting a specific post
- get a user's followers
- get a user's following