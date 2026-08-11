# Endpoint Permissions

These endpoints either require a App Authorization Header or no header at all. 
(Anything accessible to an App is also accessible to a User)


## No Authorization

- [/auth/login](./HTTP_API_RESOURCES/auth.md#login) 


## Minimum of App Authorization

- [/app/@me](./HTTP_API_RESOURCES/app.md#get-current-app)
- [/app/reaction/create](./HTTP_API_RESOURCES/app.md#create-reaction)
- [/post/create](./HTTP_API_RESOURCES/post.md#create--edit-post)
- [/post/edit](./HTTP_API_RESOURCES/post.md#create--edit-post)
- [/user/{query}](./HTTP_API_RESOURCES/user.md#get-user)
