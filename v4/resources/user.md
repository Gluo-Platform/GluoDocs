# Gluo users
### `GET` /user/{user_query}?id={search_for_id}
Search for a user by the provided `user_query`. If you are looking for a user by their username pass in the username as `user_query` and pass in `false` for `?id=` (`search_for_id`). If you are looking for a user by ID, do set `?id=` (`search_for_id`) to `true`.  
If you are looking for more information on yourself, pass along an authentication token and use `@me` as `user_query`.