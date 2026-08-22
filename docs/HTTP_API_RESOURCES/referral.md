# Referral

{% hint style="danger" %}
This page is subject to change as Premium is ondergoing some re-conceptualisation...
{% endhint %}

Referrals are used both internally for referral identification and externally
for users to get rewards. Every referral equates to one coin, once the referred 
user has activated their account, created at least one post and 14 days have 
passed.


## Referral Object

| field | type | description |
|-------|------|-------------|
| id | string | Unique referral ID |
| user_id | snowflake | ID of owner |
| creation_timestamp | unix timestamp | Timestamp of creation |


## Create Referral

{% hint icon="code" style="info" %}
**`POST`** `/premium/referral/create`
{% endhint %}

Every User can have 1 referral. Team can have up to a 100 and provide a custom 
name.

**JSON Params**
| field | type | description |
|-------|------|-------------|
| name | string(1:32)? | Name, ignored for non Team users |
