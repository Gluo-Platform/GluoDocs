# Client Settings

## Update profile

{% hint icon="code" style="warning" %}
**`PATCH`** `/client/settings/profile`
{% endhint %}

At least one field must be set.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| status? | string(0:75) | Optional status |
| about? | string(0:250) | Optional about |


## Update privacy

{% hint icon="code" style="warning" %}
**`PATCH`** `/client/settings/profile`
{% endhint %}

Update privacy settings

| field | type | description |
|-------|------|-------------|
| private | boolean | Whether account is private |
| invisible | boolean | Whether account is invisible |
