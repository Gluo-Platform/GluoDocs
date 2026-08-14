# Notifications

## Notification Object

| field | type | description |
|-------|------|-------------|
| id | snowflake | Unique notification ID |
| type | [NotificationType](#notification-type) | Type of notification |
| important | bool | Used for announcements, or system messages |
| is_read | bool | Whether user marked as read |
| creation_timestamp | unix time | Timestamp of creation |
| target | [NotificationTarget](#notification-target)? | Optional targetted entity |


### Notification Target

| field | type | description |
|-------|------|-------------|
| id | snowflake | ID of target |
| type | "post" \| "reaction" \| "user" \| "app" | Type of the entity |


## Notification Type 

| name | description |
|------|-------------|


## Get notifications

{% hint icon="code" style="success" %}
**`GET`** `/notifications/{sort_type}`
{% endhint %}

Could either be `all`, `unread` or `important`. Returns a [paginated (`key:notifications`)](/README.md#gluo-api-reference) list of 
[notification](#notification-object) objects.


## Read notification

{% hint icon="code" style="warning" %}
**`PATCH`** `/notification/{notification.id}/read/toggle`
{% endhint %}

```json
{
    "is_read": true
}
```


## Delete notification

{% hint icon="code" style="danger" %}
**`DELETE`** `/notification/{notification.id}/delete`
{% endhint %}


## Mark all as read

{% hint icon="code" style="warning" %}
**`PATCH`** `/notifications/read/all`
{% endhint %}
