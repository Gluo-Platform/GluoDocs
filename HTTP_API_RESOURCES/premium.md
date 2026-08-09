# Premium

{% hint style="danger" %}
This page is subject to change as Premium is ondergoing some re-conceptualisation...
{% endhint %}

The [Premium Object](#premium-object) is tightly coupled to the User. When a 
User (non App) is activated, a Premium Object will be created.


## Premium Object

| field | type | description |
|-------|------|-------------|
| user_id | snowflake | Unique user ID |
| active | boolean | Whether this user currently has premium |
| active_package | bitflags | Currently entitled [premium permissions](/permissions.md#premium-permissions) |
| package | bitflags | Next entitled [premium permissions](/permissions.md#premium-permissions) |
| shareable_coins | integer | Amount of shareable Gluo coins |
| unshareable_coins | integer | Amount of unshareable Gluo coins |
| next_payment_timestamp | unix timestamp | Timestamp of last premium edit |
