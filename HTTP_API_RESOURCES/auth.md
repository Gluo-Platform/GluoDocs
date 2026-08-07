# Auth

All related to the authentication of ["Regular"](user.md#user) users.


## Register - Create user

{% hint icon="code" style="info" %}
**`POST`** `/auth/register`
{% endhint %}

Will create a new user object and send them a email-verification message. Will
return a success message.


**JSON Parameters**
| field | type | description |
|-------|------|-------------|
| username | string(1:30) | Unique username |
| email | string(1:128) | Unique email address |
| password | string(8:128) | User password |
| referral? | string(10:10) | Referral ID used to register |


## Activate

{% hint icon="code" style="info" %}
**`POST`** `/auth/activate`
{% endhint %}

Active a newly created user account with a token sent per email.

**JSON Parameters**
| field | type | description |
|-------|------|-------------|
| token | string(86:256) | Authentication token sent to the user over email |


## Resend activation email

{% hint icon="code" style="info" %}
**`POST`** `/auth/email/resend`
{% endhint %}

Will resend the activation email. _TODO: figure out spam prevention, API or frontend-server_

**JSON Parameters**
| field | type | description |
|-------|------|-------------|
| email | string(1:128) | Email address of user |


## Request password reset

{% hint icon="code" style="info" %}
**`POST`** `/auth/password/reset`
{% endhint %}

Will send a reset password email to the user. Endpoint falls under [strict]() ratelimits under the assumption that you cannot forget a password you just changed 🙏.

**JSON Parameters**
| field | type | description |
|-------|------|-------------|
| email | string(1:128) | Email address of user |


## Confirm & Change password Reset

{% hint icon="code" style="info" %}
**`POST`** `/auth/password/reset`
{% endhint %}

Allows the user to change set a new password given an authentication token.

**JSON Parameters**
| field | type | description |
|-------|------|-------------|
| token | string(86:256) | Authentication token sent to the user over email |
| password | string(8:128) | New user password |


## Login

{% hint icon="code" style="info" %}
**`POST`** `/auth/login`
{% endhint %}

No authentication required for this endpoint. Ratelimist apply. Trade a password and identifier for an Authorization token.

**JSON Parameters**
| field | type | description |
|-------|------|-------------|
| identifier | string(1:128) | Username or email address |
| password | string(8:128) | Associated password |
