# Client Settings

## Update profile

{% hint icon="code" style="warning" %}
**`PATCH`** `/client/settings/profile`
{% endhint %}

Not adding an optional field, means it will not update whatever it currently 
is. If you want to reset any of these fields, pass an empty string. If the
banner starts with #, it will be assumed to be a hex code.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| status? | string(0:75) | Optional status |
| about? | string(0:250) | Optional about |
| avatar? | snowflake | New avatar ID |
| banner? | snowflake \| string(7:7) | New banner ID |


## Update privacy

{% hint icon="code" style="warning" %}
**`PATCH`** `/client/settings/profile`
{% endhint %}

Update privacy settings

| field | type | description |
|-------|------|-------------|
| private | boolean | Whether account is private |
| invisible | boolean | Whether account is invisible |
