# Generally Available Endpoints

These endpoints either require a Bot Authorization Header or no header at all. (Anything accessible to a bot is also accessible to a User)

## No Authorization

- [/auth/login](./HTTP_API_RESOURCES/auth.md#login) 


## Minimum of Bot Authorization

- [/user/@me](./HTTP_API_RESOURCES/user.md#get-current-user)
- [/user/{query}](./HTTP_API_RESOURCES/user.md#get-user)