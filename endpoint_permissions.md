# Endpoint Permissions

These endpoints either require a App Authorization Header or no header at all. 
Most endpoints accessible to an App is also accessible to a User. This is not 
the case for `/app/reaction/create`.


## No Authorization

Ratelimits apply.

- [/auth/login](./HTTP_API_RESOURCES/auth.md#login) 
- [/statistics/app](./HTTP_API_RESOURCES/statistics.md#app-statistics)
- [/user/{query}](./HTTP_API_RESOURCES/user.md#get-user)


## Minimum of App Authorization

- [/app/@me](./HTTP_API_RESOURCES/app.md#get-current-app)
- [/app/reaction/create](./HTTP_API_RESOURCES/app.md#create-reaction)
- [/post/create](./HTTP_API_RESOURCES/post.md#create--edit-post)
- [/post/edit](./HTTP_API_RESOURCES/post.md#create--edit-post)
