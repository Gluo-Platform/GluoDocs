# User Settings


## Change Password

{% hint icon="code" style="warning" %}
**`PATCH`** `/user/settings/password`
{% endhint %}

**JSON Params**

| field | type | description |
|-------|------|-------------|
| old_password | string(8:128) | Current user password |
| new_password | string(8:128) | New user password |


## Change email

{% hint icon="code" style="warning" %}
**`PATCH`** `/user/settings/email/change`
{% endhint %}

Will send a mail to the new email address with a link 
(`https://www.gluo.xyz/change/email/{token}`) to confirm the address. To 
confirm the change, a follow-up request to 
[Confirm Change Email](#confirm-change-email) should be made.

Will also send a mail to the current email address with an option to revert
these changes. `https://www.gluo.xyz/revert/email/{token}`. Make a request to
[Revert Email Change](#revert-email-change) to revert these changes.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| old_password | string(8:128) | Current user password |
| new_password | string(8:128) | New user password |


## Confirm Change Email

{% hint icon="code" style="warning" %}
**`PATCH`** `/user/settings/email/{token}/change`
{% endhint %}


## Revert Email Change

{% hint icon="code" style="danger" %}
**`DELETE`** `/user/settings/email/{token}/revert`
{% endhint %}

This will undo the change and reset the account password. Prompt the user to
give a new password and make a call to 
[change password](./auth.md#confirm--change-password-reset) to confirm the 
change.


## Delete request

{% hint icon="code" style="danger" %}
**`DELETE`** `/user/settings/delete`
{% endhint %}

Will mark the user's account for deletion. They will have 30 days to revert 
this decision. A mail will be sent with the revert-link.

**JSON Params**

| field | type | description |
|-------|------|-------------|
| password | string(8:128) | Current password |


## Revert deletion request

{% hint icon="code" style="danger" %}
**`DELETE`** `/user/settings/delete/{token}/cancel`
{% endhint %}

