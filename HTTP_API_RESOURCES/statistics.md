# Statistics


## App Statistics

{% hint icon="code" style="success" %}
**`GET`** `/statistics/app`
{% endhint %}

Takes a required `year` and `month` parameter. Will return all statistics for
the given month of the given year.

_TODO: update example_

```json
{
    "dates": [...],
    "user.registered": [...],
    "user.verified": [...],
    "user.referred": [...],
    "post.created": [...],
    "post.edited": [...],
    "reaction.created": [...],
    "reaction.edited": [...]
}
```
