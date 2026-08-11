# Statistics


## Statistic object

| field | type | description |
|-------|------|-------------|
| dates | date list | List of dates (in order) |
| values | int list | Metrics per date (in order) |


## App Statistics

{% hint icon="code" style="success" %}
**`GET`** `/statistics/app`
{% endhint %}

Takes a required `year` and `month` parameter. Will return all statistics for
the given month of the given year. Here is an example response where `[...]` is
a list of [Statistic Objects](#statistic-object)

```json
{
    "user.registered": [...],
    "user.verified": [...],
    "user.referred": [...],
    "post.created": [...],
    "post.edited": [...],
    "reaction.created": [...],
    "reaction.edited": [...]
}
