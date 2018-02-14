---
title: Connectable v1.0.0
language_tabs:
  - javascript--nodejs
  - shell
toc_footers: []
includes: []
search: true
highlight_theme: atom-one-dark
headingLevel: 2


---


<h1 id="Connectable">Connectable v1.0.0</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


Connectable API


Base URLs:


* <a href="https://connectable.heroku.com/api">https://connectable.heroku.com/api</a>


License: <a href="https://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a>


# Authentication


- oAuth2 authentication. HTTP Bearer authentication strategy using Passport.


    - Flow: implicit
    - Authorization URL = [https://connectable.auth0.com](https://connectable.auth0.com)


|Scope|Scope Description|
|---|---|
|read:users|Get a users information.|


<h1 id="Connectable-Default">Default</h1>


## createUser


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'POST',
  uri: 'https://connectable.heroku.com/api/users',
  const headers = {
    'Content-Type':'application/json',
    'Accept':'application/json'
  },
  body: body
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X POST https://connectable.heroku.com/api/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


`POST /users`


Create a new user.


> Body parameter


```json
{
  "email": "string",
  "username": "string",
  "phone_number": "string",
  "picture": "string",
  "name": "string",
  "nickname": "string",
  "given_name": "string",
  "family_name": "string"
}
```


<h3 id="post__users-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[userBody](#schemauserbody)|false|No description|


> Example responses


```json
{
  "id": "string",
  "object": "string",
  "account_balance": 0,
  "created": 0,
  "currency": "string",
  "default_source": "string",
  "delinquent": true,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "email": "string",
  "invoice_prefix": "string",
  "livemode": true,
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  },
  "subscriptions": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "application_fee_percent": 0,
        "billing": "string",
        "billing_cycle_anchor": 0,
        "cancel_at_period_end": true,
        "canceled_at": 0,
        "created": 0,
        "current_period_end": 0,
        "current_period_start": 0,
        "customer": "string",
        "days_until_due": 0,
        "discount": 0,
        "ended_at": 0,
        "items": [
          {
            "id": "string",
            "object": "string",
            "created": 0,
            "plan": {
              "id": "string",
              "object": "string",
              "amount": 0,
              "created": 0,
              "currency": "string",
              "interval": "string",
              "interval_count": 0,
              "livemode": true,
              "nickname": "string",
              "product": "string",
              "trial_period_days": 0
            },
            "quantity": 0,
            "subscription": "string"
          }
        ],
        "livemode": true,
        "plan": {
          "id": "string",
          "object": "string",
          "amount": 0,
          "created": 0,
          "currency": "string",
          "interval": "string",
          "interval_count": 0,
          "livemode": true,
          "nickname": "string",
          "product": "string",
          "trial_period_days": 0
        },
        "quantity": 0,
        "start": 0,
        "status": "string",
        "tax_percent": 0,
        "trial_end": 0,
        "trial_start": 0
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  },
  "sources": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "address_city": "string",
        "address_country": "string",
        "address_line1": "string",
        "address_line1_check": "string",
        "address_line2": "string",
        "address_state": "string",
        "address_zip": "string",
        "address_zip_check": "string",
        "brand": "string",
        "country": "string",
        "customer": "string",
        "cvc_check": "string",
        "dynamic_last4": "string",
        "exp_month": 0,
        "exp_year": 0,
        "fingerprint": "string",
        "funding": "string",
        "last4": "string",
        "name": "string",
        "tokenization_method": "string"
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  }
}
```


<h3 id="post__users-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully created new user.|[customer](#schemacustomer)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|


<aside class="success">
This operation does not require authentication
</aside>


## getUser


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'GET',
  uri: 'https://connectable.heroku.com/api/users/{id}',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X GET https://connectable.heroku.com/api/users/{id} \
  -H 'Accept: application/json'


```


`GET /users/{id}`


Returns the full user object.


<h3 id="get__users_{id}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|undefined|true|The users primary id|


> Example responses


```json
{
  "email": "string",
  "email_verified": true,
  "username": "string",
  "phone_number": "string",
  "phone_verified": true,
  "user_id": "string",
  "created_at": "string",
  "updated_at": "string",
  "identities": [
    {
      "connection": "string",
      "user_id": "string",
      "provider": "string",
      "isSocial": true
    }
  ],
  "picture": "string",
  "name": "string",
  "nickname": "string",
  "multifactor": [
    "string"
  ],
  "last_ip": "string",
  "last_login": "string",
  "logins_count": 0,
  "blocked": true,
  "given_name": "string",
  "family_name": "string"
}
```


<h3 id="get__users_{id}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully retrieved user.|[user](#schemauser)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No user could be found for the given id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## updateUser


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'PUT',
  uri: 'https://connectable.heroku.com/api/users/{id}',
  const headers = {
    'Content-Type':'application/json',
    'Accept':'application/json'
  },
  body: body
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X PUT https://connectable.heroku.com/api/users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


`PUT /users/{id}`


Updates the specified user object.


> Body parameter


```json
{
  "email": "string",
  "username": "string",
  "phone_number": "string",
  "picture": "string",
  "name": "string",
  "nickname": "string",
  "given_name": "string",
  "family_name": "string"
}
```


<h3 id="put__users_{id}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|
|body|body|[userBody](#schemauserbody)|true|No description|


> Example responses


```json
{
  "email": "string",
  "email_verified": true,
  "username": "string",
  "phone_number": "string",
  "phone_verified": true,
  "user_id": "string",
  "created_at": "string",
  "updated_at": "string",
  "identities": [
    {
      "connection": "string",
      "user_id": "string",
      "provider": "string",
      "isSocial": true
    }
  ],
  "picture": "string",
  "name": "string",
  "nickname": "string",
  "multifactor": [
    "string"
  ],
  "last_ip": "string",
  "last_login": "string",
  "logins_count": 0,
  "blocked": true,
  "given_name": "string",
  "family_name": "string"
}
```


<h3 id="put__users_{id}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user updated successfully.|[user](#schemauser)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No user could be found for the given id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## deleteUser


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'DELETE',
  uri: 'https://connectable.heroku.com/api/users/{id}',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X DELETE https://connectable.heroku.com/api/users/{id} \
  -H 'Accept: application/json'


```


`DELETE /users/{id}`


Deletes the user and all of their associated resources.


<h3 id="delete__users_{id}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|undefined|true|The users primary id|


> Example responses


```json
"string"
```


<h3 id="delete__users_{id}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user successfully deleted.|string|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No user could be found for the given id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## getBilling


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'GET',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X GET https://connectable.heroku.com/api/users/{id}/billing \
  -H 'Accept: application/json'


```


`GET /users/{id}/billing`


Returns the stripe customer object.


<h3 id="get__users_{id}_billing-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|


> Example responses


```json
{
  "id": "string",
  "object": "string",
  "account_balance": 0,
  "created": 0,
  "currency": "string",
  "default_source": "string",
  "delinquent": true,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "email": "string",
  "invoice_prefix": "string",
  "livemode": true,
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  },
  "subscriptions": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "application_fee_percent": 0,
        "billing": "string",
        "billing_cycle_anchor": 0,
        "cancel_at_period_end": true,
        "canceled_at": 0,
        "created": 0,
        "current_period_end": 0,
        "current_period_start": 0,
        "customer": "string",
        "days_until_due": 0,
        "discount": 0,
        "ended_at": 0,
        "items": [
          {
            "id": "string",
            "object": "string",
            "created": 0,
            "plan": {
              "id": "string",
              "object": "string",
              "amount": 0,
              "created": 0,
              "currency": "string",
              "interval": "string",
              "interval_count": 0,
              "livemode": true,
              "nickname": "string",
              "product": "string",
              "trial_period_days": 0
            },
            "quantity": 0,
            "subscription": "string"
          }
        ],
        "livemode": true,
        "plan": {
          "id": "string",
          "object": "string",
          "amount": 0,
          "created": 0,
          "currency": "string",
          "interval": "string",
          "interval_count": 0,
          "livemode": true,
          "nickname": "string",
          "product": "string",
          "trial_period_days": 0
        },
        "quantity": 0,
        "start": 0,
        "status": "string",
        "tax_percent": 0,
        "trial_end": 0,
        "trial_start": 0
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  },
  "sources": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "address_city": "string",
        "address_country": "string",
        "address_line1": "string",
        "address_line1_check": "string",
        "address_line2": "string",
        "address_state": "string",
        "address_zip": "string",
        "address_zip_check": "string",
        "brand": "string",
        "country": "string",
        "customer": "string",
        "cvc_check": "string",
        "dynamic_last4": "string",
        "exp_month": 0,
        "exp_year": 0,
        "fingerprint": "string",
        "funding": "string",
        "last4": "string",
        "name": "string",
        "tokenization_method": "string"
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  }
}
```


<h3 id="get__users_{id}_billing-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The Stripe customer object exists and is returned.|[customer](#schemacustomer)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|A Stripe customer could not be found for the given user id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## updateBilling


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'PUT',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing',
  const headers = {
    'Content-Type':'application/json',
    'Accept':'application/json'
  },
  body: body
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X PUT https://connectable.heroku.com/api/users/{id}/billing \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


`PUT /users/{id}/billing`


Update a stripe customer object.


> Body parameter


```json
{
  "id": "string",
  "currency": "string",
  "default_source": "string",
  "description": "string",
  "email": "string",
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  }
}
```


<h3 id="put__users_{id}_billing-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[customerBody](#schemacustomerbody)|true|No description|
|id|path|string|true|The users primary id|


> Example responses


```json
{
  "id": "string",
  "object": "string",
  "account_balance": 0,
  "created": 0,
  "currency": "string",
  "default_source": "string",
  "delinquent": true,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "email": "string",
  "invoice_prefix": "string",
  "livemode": true,
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  },
  "subscriptions": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "application_fee_percent": 0,
        "billing": "string",
        "billing_cycle_anchor": 0,
        "cancel_at_period_end": true,
        "canceled_at": 0,
        "created": 0,
        "current_period_end": 0,
        "current_period_start": 0,
        "customer": "string",
        "days_until_due": 0,
        "discount": 0,
        "ended_at": 0,
        "items": [
          {
            "id": "string",
            "object": "string",
            "created": 0,
            "plan": {
              "id": "string",
              "object": "string",
              "amount": 0,
              "created": 0,
              "currency": "string",
              "interval": "string",
              "interval_count": 0,
              "livemode": true,
              "nickname": "string",
              "product": "string",
              "trial_period_days": 0
            },
            "quantity": 0,
            "subscription": "string"
          }
        ],
        "livemode": true,
        "plan": {
          "id": "string",
          "object": "string",
          "amount": 0,
          "created": 0,
          "currency": "string",
          "interval": "string",
          "interval_count": 0,
          "livemode": true,
          "nickname": "string",
          "product": "string",
          "trial_period_days": 0
        },
        "quantity": 0,
        "start": 0,
        "status": "string",
        "tax_percent": 0,
        "trial_end": 0,
        "trial_start": 0
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  },
  "sources": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "address_city": "string",
        "address_country": "string",
        "address_line1": "string",
        "address_line1_check": "string",
        "address_line2": "string",
        "address_state": "string",
        "address_zip": "string",
        "address_zip_check": "string",
        "brand": "string",
        "country": "string",
        "customer": "string",
        "cvc_check": "string",
        "dynamic_last4": "string",
        "exp_month": 0,
        "exp_year": 0,
        "fingerprint": "string",
        "funding": "string",
        "last4": "string",
        "name": "string",
        "tokenization_method": "string"
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  }
}
```


<h3 id="put__users_{id}_billing-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully updated Stripe customer object.|[customer](#schemacustomer)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|A Stripe customer could not be found for the given user id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## createBilling


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'POST',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing',
  const headers = {
    'Content-Type':'application/json',
    'Accept':'application/json'
  },
  body: body
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X POST https://connectable.heroku.com/api/users/{id}/billing \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


`POST /users/{id}/billing`


Create a new stripe customer object.


> Body parameter


```json
{
  "id": "string",
  "currency": "string",
  "default_source": "string",
  "description": "string",
  "email": "string",
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  }
}
```


<h3 id="post__users_{id}_billing-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[customerBody](#schemacustomerbody)|true|No description|
|id|path|string|true|The users primary id|


> Example responses


```json
{
  "id": "string",
  "object": "string",
  "account_balance": 0,
  "created": 0,
  "currency": "string",
  "default_source": "string",
  "delinquent": true,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "email": "string",
  "invoice_prefix": "string",
  "livemode": true,
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  },
  "subscriptions": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "application_fee_percent": 0,
        "billing": "string",
        "billing_cycle_anchor": 0,
        "cancel_at_period_end": true,
        "canceled_at": 0,
        "created": 0,
        "current_period_end": 0,
        "current_period_start": 0,
        "customer": "string",
        "days_until_due": 0,
        "discount": 0,
        "ended_at": 0,
        "items": [
          {
            "id": "string",
            "object": "string",
            "created": 0,
            "plan": {
              "id": "string",
              "object": "string",
              "amount": 0,
              "created": 0,
              "currency": "string",
              "interval": "string",
              "interval_count": 0,
              "livemode": true,
              "nickname": "string",
              "product": "string",
              "trial_period_days": 0
            },
            "quantity": 0,
            "subscription": "string"
          }
        ],
        "livemode": true,
        "plan": {
          "id": "string",
          "object": "string",
          "amount": 0,
          "created": 0,
          "currency": "string",
          "interval": "string",
          "interval_count": 0,
          "livemode": true,
          "nickname": "string",
          "product": "string",
          "trial_period_days": 0
        },
        "quantity": 0,
        "start": 0,
        "status": "string",
        "tax_percent": 0,
        "trial_end": 0,
        "trial_start": 0
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  },
  "sources": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "address_city": "string",
        "address_country": "string",
        "address_line1": "string",
        "address_line1_check": "string",
        "address_line2": "string",
        "address_state": "string",
        "address_zip": "string",
        "address_zip_check": "string",
        "brand": "string",
        "country": "string",
        "customer": "string",
        "cvc_check": "string",
        "dynamic_last4": "string",
        "exp_month": 0,
        "exp_year": 0,
        "fingerprint": "string",
        "funding": "string",
        "last4": "string",
        "name": "string",
        "tokenization_method": "string"
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  }
}
```


<h3 id="post__users_{id}_billing-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully created Stripe customer.|[customer](#schemacustomer)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bad user id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## deleteBilling


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'DELETE',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X DELETE https://connectable.heroku.com/api/users/{id}/billing \
  -H 'Accept: application/json'


```


`DELETE /users/{id}/billing`


Delete the stipe customer object.


<h3 id="delete__users_{id}_billing-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|


> Example responses


```json
"string"
```


<h3 id="delete__users_{id}_billing-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully deleted.|string|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|A Stripe customer could not be found for the given user id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## getInvoices


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'GET',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing/invoices',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X GET https://connectable.heroku.com/api/users/{id}/billing/invoices \
  -H 'Accept: application/json'


```


`GET /users/{id}/billing/invoices`


Returns the invoices associated with a users account.


<h3 id="get__users_{id}_billing_invoices-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|
|limit|query|integer|false|The maximum number of line items to return. Default value is 10.|
|page|query|integer|false|The pagination page of results to return.|


> Example responses


```json
[
  {
    "id": "string",
    "object": "string",
    "amount_due": 0,
    "application_fee": 0,
    "attempt_count": 0,
    "attempted": true,
    "billing": "string",
    "charge": "string",
    "closed": true,
    "currency": "string",
    "customer": "string",
    "date": 0,
    "description": "string",
    "discount": {
      "object": "string",
      "coupon": {
        "id": "string",
        "object": "string",
        "amount_off": {},
        "created": 0,
        "currency": "string",
        "duration": "string",
        "duration_in_months": 0,
        "livemode": true,
        "max_redemptions": 0,
        "percent_off": 0,
        "redeem_by": "2018-02-14",
        "times_redeemed": 0,
        "valid": true
      },
      "customer": "string",
      "end": 0,
      "start": 0,
      "subscription": "string"
    },
    "due_date": 0,
    "ending_balance": 0,
    "forgiven": true,
    "lines": {
      "data": {
        "id": "string",
        "object": "string",
        "amount": 0,
        "currency": "string",
        "description": "string",
        "discountable": true,
        "livemode": true,
        "period": {
          "start": 0,
          "end": 0
        },
        "plan": {
          "id": "string",
          "object": "string",
          "amount": 0,
          "created": 0,
          "currency": "string",
          "interval": "string",
          "interval_count": 0,
          "livemode": true,
          "nickname": "string",
          "product": "string",
          "trial_period_days": 0
        },
        "proration": true,
        "quantity": 0,
        "subscription": "string",
        "subscription_item": "string",
        "type": "string"
      },
      "has_more": true,
      "object": "string",
      "url": "string"
    },
    "livemode": true,
    "next_payment_attempt": 0,
    "number": "string",
    "paid": true,
    "period_end": 0,
    "period_start": 0,
    "receipt_number": "string",
    "starting_balance": 0,
    "statement_descriptor": "string",
    "subscription": "string",
    "subtotal": 0,
    "tax": 0,
    "tax_percent": 0,
    "total": 0,
    "webhooks_delivered_at": 0
  }
]
```


<h3 id="get__users_{id}_billing_invoices-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The invoices were successfully retrieved.|Inline|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No invoices could be found for the given user.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request body. The message will vary depending on the cause.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|


<h3 id="get__users_{id}_billing_invoices-responseschema">Response Schema</h3>


Status Code **200**


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[[invoice](#schemainvoice)]|false|No description|
|» Root Type for invoice|[invoice](#schemainvoice)|false|The root of the invoice type's schema.|
|»» id|string|false|Unique identifier for the object.|
|»» object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|»» amount_due|integer(int32)|false|Final amount due at this time for this invoice. If the invoice’s total is smaller than the minimum charge amount, for example, or if there is account credit that can be applied to the invoice, the amount_due may be 0. If there is a positive starting_balance for the invoice (the customer owes money), the amount_due will also take that into account. The charge that gets generated for the invoice will be for the amount specified in amount_due.|
|»» application_fee|integer|false|The fee in cents that will be applied to the invoice and transferred to the application owner’s Stripe account when the invoice is paid.|
|»» attempt_count|integer(int32)|false|Number of payment attempts made for this invoice, from the perspective of the payment retry schedule. Any payment attempt counts as the first attempt, and subsequently only automatic retries increment the attempt count. In other words, manual payment attempts after the first attempt do not affect the retry schedule.|
|»» attempted|boolean|false|Whether an attempt has been made to pay the invoice. An invoice is not attempted until 1 hour after the invoice.created webhook, for example, so you might not want to display that invoice as unpaid to your users.|
|»» billing|string|false|Either charge_automatically, or send_invoice. When charging automatically, Stripe will attempt to pay this invoice using the default source attached to the customer. When sending an invoice, Stripe will email this invoice to the customer with payment instructions.|
|»» charge|string|false|ID of the latest charge generated for this invoice, if any.|
|»» closed|boolean|false|Whether the invoice is still trying to collect payment. An invoice is closed if it’s either paid or it has been marked closed. A closed invoice will no longer attempt to collect payment.|
|»» currency|string|false|Three-letter ISO currency code, in lowercase. Must be a supported currency.|
|»» customer|string|false|The customer id for the given invoice.|
|»» date|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|»» description|string|false|An arbitrary string attached to the object. Often useful for displaying to users.|
|»» discount|[discount](#schemadiscount)|false|The root of the discount type's schema.|
|»»» object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|»»» coupon|[coupon](#schemacoupon)|false|The root of the coupon type's schema.|
|»»»» id|string|false|Unique identifier for the object.|
|»»»» object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|»»»» amount_off|object|false|Amount (in the currency specified) that will be taken off the subtotal of any invoices for this customer.|
|»»»» created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|»»»» currency|string|false|If amount_off has been set, the three-letter ISO code for the currency of the amount to take off.|
|»»»» duration|string|false|One of forever, once, and repeating. Describes how long a customer who applies this coupon will get the discount.|
|»»»» duration_in_months|integer(int32)|false|If duration is repeating, the number of months the coupon applies. Null if coupon duration is forever or once.|
|»»»» livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|»»»» max_redemptions|integer|false|Maximum number of times this coupon can be redeemed, in total, before it is no longer valid.|
|»»»» percent_off|integer(int32)|false|Percent that will be taken off the subtotal of any invoices for this customer for the duration of the coupon. For example, a coupon with percent_off of 50 will make a $100 invoice $50 instead.|
|»»»» redeem_by|string(date)|false|Date after which the coupon can no longer be redeemed.|
|»»»» times_redeemed|integer(int32)|false|Number of times this coupon has been applied to a customer.|
|»»»» valid|boolean|false|Taking account of the above properties, whether this coupon can still be applied to a customer.|
|»»» customer|string|false|No description|
|»»» end|integer(int32)|false|If the coupon has a duration of repeating, the date that this discount will end. If the coupon has a duration of once or forever, this attribute will be null.|
|»»» start|integer(int32)|false|Date that the coupon was applied.|
|»»» subscription|string|false|The subscription that this coupon is applied to, if it is applied to a particular subscription.|
|»» due_date|integer(int32)|false|The date on which payment for this invoice is due. This value will be null for invoices where billing=charå†ge_automatically.|
|»» ending_balance|integer(int32)|false|Ending customer balance after the invoice is frozen. invoices are frozen approximately an hour after successful webhook delivery or when payment collection is attempted for the invoice. If the invoice has not been frozen yet, this will be null.|
|»» forgiven|boolean|false|Whether the invoice has been forgiven. Forgiving an invoice instructs us to update the subscription status as if the invoice were successfully paid. Once an invoice has been forgiven, it cannot be unforgiven or reopened.|
|»» lines|[lines](#schemalines)|false|The root of the lines type's schema.|
|»»» data|[line_item](#schemaline_item)|false|The root of the Line Item type's schema.|
|»»»» id|string|false|Unique identifier for the object.|
|»»»» object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|»»»» amount|integer(int32)|false|The amount, in cents.|
|»»»» currency|string|false|Three-letter ISO currency code, in lowercase. Must be a supported currency.|
|»»»» description|string|false|An arbitrary string attached to the object. Often useful for displaying to users.|
|»»»» discountable|boolean|false|If true, discounts will apply to this line item. Always false for prorations.|
|»»»» livemode|boolean|false|Whether this is a test line item.|
|»»»» period|[period](#schemaperiod)|false|The root of the period type's schema.|
|»»»»» start|integer(int32)|false|No description|
|»»»»» end|integer(int32)|false|No description|
|»»»» plan|[plan](#schemaplan)|false|The root of the plan type's schema.|
|»»»»» id|string|false|Unique identifier for the object.|
|»»»»» object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|»»»»» amount|integer(int32)|false|The amount in cents to be charged on the interval specified.|
|»»»»» created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|»»»»» currency|string|false|Three-letter ISO currency code, in lowercase. Must be a supported currency.|
|»»»»» interval|string|false|One of day, week, month or year. The frequency with which a subscription should be billed.|
|»»»»» interval_count|integer(int32)|false|The number of intervals (specified in the interval property) between each subscription billing. For example, interval=month and interval_count=3 bills every 3 months.|
|»»»»» livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|»»»»» nickname|string|false|A brief description of the plan, hidden from customers.|
|»»»»» product|string|false|The product whose pricing this plan determines.|
|»»»»» trial_period_days|integer(int32)|false|No description|
|»»»» proration|boolean|false|Whether this is a proration.|
|»»»» quantity|integer(int32)|false|The quantity of the subscription, if the line item is a subscription or a proration.|
|»»»» subscription|string|false|When type is invoiceitem, the subscription that the invoice item pertains to, if any. Left blank when type is already subscription, as it’d be redundant with id.|
|»»»» subscription_item|string|false|No description|
|»»»» type|string|false|A string identifying the type of the source of this line item, either an invoiceitem or a subscription.|
|»»» has_more|boolean|false|True if this list has another page of items after this one that can be fetched.|
|»»» object|string|false|String representing the object’s type. Objects of the same type share the same value. Always has the value “list”.|
|»»» url|string|false|The URL where this list can be accessed.|
|»» livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|»» next_payment_attempt|integer|false|The time at which payment will next be attempted. This value will be null for invoices where billing=send_invoice.|
|»» number|string|false|A unique, identifying string that appears on emails sent to the customer for this invoice. This starts with the customer’s unique invoice_prefix if it is specified.|
|»» paid|boolean|false|Whether payment was successfully collected for this invoice. An invoice can be paid (most commonly) with a charge or with credit from the customer’s account balance.|
|»» period_end|integer(int32)|false|End of the usage period during which invoice items were added to this invoice.|
|»» period_start|integer(int32)|false|Start of the usage period during which invoice items were added to this invoice.|
|»» receipt_number|string|false|This is the transaction number that appears on email receipts sent for this invoice.|
|»» starting_balance|integer(int32)|false|Starting customer balance before the invoice is frozen. If the invoice has not been frozen yet, this will be the current customer balance.|
|»» statement_descriptor|string|false|Extra information about an invoice for the customer’s credit card statement.|
|»» subscription|string|false|The subscription that this invoice was prepared for, if any.|
|»» subtotal|integer(int32)|false|Total of all subscriptions, invoice items, and prorations on the invoice before any discount is applied.|
|»» tax|integer|false|The amount of tax included in the total, calculated from tax_percent and the subtotal. If no tax_percent is defined, this value will be null.|
|»» tax_percent|integer|false|This percentage of the subtotal has been added to the total amount of the invoice, including invoice line items and discounts. This field is inherited from the subscription’s tax_percent field, but can be changed before the invoice is paid. This field defaults to null.|
|»» total|integer(int32)|false|Total after discount.|
|»» webhooks_delivered_at|integer(int32)|false|The time at which webhooks for this invoice were successfully delivered (if the invoice had no webhooks to deliver, this will match date). invoice payment is delayed until webhooks are delivered, or until all webhook delivery attempts have been exhausted.|


<aside class="success">
This operation does not require authentication
</aside>


## getInvoice


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'GET',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing/invoices/{invoiceId}',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X GET https://connectable.heroku.com/api/users/{id}/billing/invoices/{invoiceId} \
  -H 'Accept: application/json'


```


`GET /users/{id}/billing/invoices/{invoiceId}`


Returns an invoice object per the given invoiceId.


<h3 id="get__users_{id}_billing_invoices_{invoiceId}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|invoiceId|path|string|true|invoice primary id.|
|id|path|string|true|The users primary id|


> Example responses


```json
{
  "id": "string",
  "object": "string",
  "amount_due": 0,
  "application_fee": 0,
  "attempt_count": 0,
  "attempted": true,
  "billing": "string",
  "charge": "string",
  "closed": true,
  "currency": "string",
  "customer": "string",
  "date": 0,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "due_date": 0,
  "ending_balance": 0,
  "forgiven": true,
  "lines": {
    "data": {
      "id": "string",
      "object": "string",
      "amount": 0,
      "currency": "string",
      "description": "string",
      "discountable": true,
      "livemode": true,
      "period": {
        "start": 0,
        "end": 0
      },
      "plan": {
        "id": "string",
        "object": "string",
        "amount": 0,
        "created": 0,
        "currency": "string",
        "interval": "string",
        "interval_count": 0,
        "livemode": true,
        "nickname": "string",
        "product": "string",
        "trial_period_days": 0
      },
      "proration": true,
      "quantity": 0,
      "subscription": "string",
      "subscription_item": "string",
      "type": "string"
    },
    "has_more": true,
    "object": "string",
    "url": "string"
  },
  "livemode": true,
  "next_payment_attempt": 0,
  "number": "string",
  "paid": true,
  "period_end": 0,
  "period_start": 0,
  "receipt_number": "string",
  "starting_balance": 0,
  "statement_descriptor": "string",
  "subscription": "string",
  "subtotal": 0,
  "tax": 0,
  "tax_percent": 0,
  "total": 0,
  "webhooks_delivered_at": 0
}
```


<h3 id="get__users_{id}_billing_invoices_{invoiceId}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|invoice successfully retrieved.|[invoice](#schemainvoice)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bad user id or invoice could not be found.|None|


<aside class="success">
This operation does not require authentication
</aside>


## createSource


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'POST',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing/sources',
  const headers = {
    'Content-Type':'application/json',
    'Accept':'application/json'
  },
  body: body
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X POST https://connectable.heroku.com/api/users/{id}/billing/sources \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


`POST /users/{id}/billing/sources`


Create a new billing source associated with a users account.


> Body parameter


```json
{
  "address_city": "string",
  "address_country": "string",
  "address_line1": "string",
  "address_line2": "string",
  "address_state": "string",
  "address_zip": "string",
  "country": "string",
  "exp_month": 0,
  "exp_year": 0,
  "name": "string",
  "source": "string",
  "object": "string",
  "default_for_currency": true,
  "cvc": "string",
  "number": "string"
}
```


<h3 id="post__users_{id}_billing_sources-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sourceBody](#schemasourcebody)|true|No description|
|id|path|string|true|The users primary id|


> Example responses


```json
{
  "id": "string",
  "object": "string",
  "address_city": "string",
  "address_country": "string",
  "address_line1": "string",
  "address_line1_check": "string",
  "address_line2": "string",
  "address_state": "string",
  "address_zip": "string",
  "address_zip_check": "string",
  "brand": "string",
  "country": "string",
  "customer": "string",
  "cvc_check": "string",
  "dynamic_last4": "string",
  "exp_month": 0,
  "exp_year": 0,
  "fingerprint": "string",
  "funding": "string",
  "last4": "string",
  "name": "string",
  "tokenization_method": "string"
}
```


<h3 id="post__users_{id}_billing_sources-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Billing source successfully created.|[source](#schemasource)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bad user id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## getSource


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'GET',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing/sources/{sourceId}',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X GET https://connectable.heroku.com/api/users/{id}/billing/sources/{sourceId} \
  -H 'Accept: application/json'


```


`GET /users/{id}/billing/sources/{sourceId}`


Returns the billing source associated with a users account.


<h3 id="get__users_{id}_billing_sources_{sourceId}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|
|sourceId|path|string|true|No description|


> Example responses


```json
{
  "object": "string",
  "data": [
    {
      "id": "string",
      "object": "string",
      "address_city": "string",
      "address_country": "string",
      "address_line1": "string",
      "address_line1_check": "string",
      "address_line2": "string",
      "address_state": "string",
      "address_zip": "string",
      "address_zip_check": "string",
      "brand": "string",
      "country": "string",
      "customer": "string",
      "cvc_check": "string",
      "dynamic_last4": "string",
      "exp_month": 0,
      "exp_year": 0,
      "fingerprint": "string",
      "funding": "string",
      "last4": "string",
      "name": "string",
      "tokenization_method": "string"
    }
  ],
  "has_more": true,
  "total_count": 0,
  "url": "string"
}
```


<h3 id="get__users_{id}_billing_sources_{sourceId}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user billing source successfully retrieved.|[sources](#schemasources)|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|user billing source does not exist.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bad user id.|None|


<aside class="success">
This operation does not require authentication
</aside>


## updateSource


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'PUT',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing/sources/{sourceId}',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X PUT https://connectable.heroku.com/api/users/{id}/billing/sources/{sourceId} \
  -H 'Accept: application/json'


```


`PUT /users/{id}/billing/sources/{sourceId}`


Updates the billing source associated with a users account.


<h3 id="put__users_{id}_billing_sources_{sourceId}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|
|sourceId|path|string|true|No description|


> Example responses


```json
{
  "object": "string",
  "data": [
    {
      "id": "string",
      "object": "string",
      "address_city": "string",
      "address_country": "string",
      "address_line1": "string",
      "address_line1_check": "string",
      "address_line2": "string",
      "address_state": "string",
      "address_zip": "string",
      "address_zip_check": "string",
      "brand": "string",
      "country": "string",
      "customer": "string",
      "cvc_check": "string",
      "dynamic_last4": "string",
      "exp_month": 0,
      "exp_year": 0,
      "fingerprint": "string",
      "funding": "string",
      "last4": "string",
      "name": "string",
      "tokenization_method": "string"
    }
  ],
  "has_more": true,
  "total_count": 0,
  "url": "string"
}
```


<h3 id="put__users_{id}_billing_sources_{sourceId}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|user billing source successfully updated.|[sources](#schemasources)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bad user id or source does not exist.|None|


<aside class="success">
This operation does not require authentication
</aside>


## deleteSource


> Code samples


```javascript--nodejs
const rp = require('request-promise')
const options = {
  method: 'DELETE',
  uri: 'https://connectable.heroku.com/api/users/{id}/billing/sources/{sourceId}',
  const headers = {
    'Accept':'application/json'
  }
}
rp(options)
    .then(result => { console.log( result )})
    .catch(err => { console.log(err) })


```


```shell
# You can also use wget
curl -X DELETE https://connectable.heroku.com/api/users/{id}/billing/sources/{sourceId} \
  -H 'Accept: application/json'


```


`DELETE /users/{id}/billing/sources/{sourceId}`


Delete the billing source associated with a users account.


<h3 id="delete__users_{id}_billing_sources_{sourceId}-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The users primary id|
|sourceId|path|string|true|No description|


> Example responses


```json
"string"
```


<h3 id="delete__users_{id}_billing_sources_{sourceId}-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully deleted.|string|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bad user id or billing source not found.|None|


<aside class="success">
This operation does not require authentication
</aside>


# Schemas


<h2 id="tocSuser">user</h2>


<a id="schemauser"></a>


```json
{
  "email": "string",
  "email_verified": true,
  "username": "string",
  "phone_number": "string",
  "phone_verified": true,
  "user_id": "string",
  "created_at": "string",
  "updated_at": "string",
  "identities": [
    {
      "connection": "string",
      "user_id": "string",
      "provider": "string",
      "isSocial": true
    }
  ],
  "picture": "string",
  "name": "string",
  "nickname": "string",
  "multifactor": [
    "string"
  ],
  "last_ip": "string",
  "last_login": "string",
  "logins_count": 0,
  "blocked": true,
  "given_name": "string",
  "family_name": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|email|string|false|The user's email|
|email_verified|boolean|false|true if the user's email is verified, false otherwise|
|username|string|false|The user's username|
|phone_number|string|false|The user's phone number (following the E.164 recommendation), only valid for users from SMS connections|
|phone_verified|boolean|false|true if the user's phone_number is verified, false otherwise, only valid for users from SMS connections|
|user_id|string|false|The user's unique identifier|
|created_at|string|false|The date when the user was created|
|updated_at|string|false|The date when the user was last updated (modified)|
|identities|[[identity](#schemaidentity)]|false|An array of objects with information about the user's identities. More than one will exists in case accounts are linked|
|picture|string|false|The user's picture|
|name|string|false|The user's name|
|nickname|string|false|The user's nickname|
|multifactor|[string]|false|The list of multifactor providers that the user has enrolled to|
|last_ip|string|false|The last login IP address|
|last_login|string|false|The last login date for this user|
|logins_count|integer(int32)|false|The number of logins for this user|
|blocked|boolean|false|Indicates whether the user was blocked by an administrator or not|
|given_name|string|false|The user's given name (first name)|
|family_name|string|false|The user's family name (last name)|


<h2 id="tocSidentity">identity</h2>


<a id="schemaidentity"></a>


```json
{
  "connection": "string",
  "user_id": "string",
  "provider": "string",
  "isSocial": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|connection|string|false|The name of the connection for the identity.|
|user_id|string|false|The unique identifier for the user for the identity.|
|provider|string|false|The type of identity provider.|
|isSocial|boolean|false|true if the identity provider is a social provider, falses otherwise|


<h2 id="tocScustomer">customer</h2>


<a id="schemacustomer"></a>


```json
{
  "id": "string",
  "object": "string",
  "account_balance": 0,
  "created": 0,
  "currency": "string",
  "default_source": "string",
  "delinquent": true,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "email": "string",
  "invoice_prefix": "string",
  "livemode": true,
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  },
  "subscriptions": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "application_fee_percent": 0,
        "billing": "string",
        "billing_cycle_anchor": 0,
        "cancel_at_period_end": true,
        "canceled_at": 0,
        "created": 0,
        "current_period_end": 0,
        "current_period_start": 0,
        "customer": "string",
        "days_until_due": 0,
        "discount": 0,
        "ended_at": 0,
        "items": [
          {
            "id": "string",
            "object": "string",
            "created": 0,
            "plan": {
              "id": "string",
              "object": "string",
              "amount": 0,
              "created": 0,
              "currency": "string",
              "interval": "string",
              "interval_count": 0,
              "livemode": true,
              "nickname": "string",
              "product": "string",
              "trial_period_days": 0
            },
            "quantity": 0,
            "subscription": "string"
          }
        ],
        "livemode": true,
        "plan": {
          "id": "string",
          "object": "string",
          "amount": 0,
          "created": 0,
          "currency": "string",
          "interval": "string",
          "interval_count": 0,
          "livemode": true,
          "nickname": "string",
          "product": "string",
          "trial_period_days": 0
        },
        "quantity": 0,
        "start": 0,
        "status": "string",
        "tax_percent": 0,
        "trial_end": 0,
        "trial_start": 0
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  },
  "sources": {
    "object": "string",
    "data": [
      {
        "id": "string",
        "object": "string",
        "address_city": "string",
        "address_country": "string",
        "address_line1": "string",
        "address_line1_check": "string",
        "address_line2": "string",
        "address_state": "string",
        "address_zip": "string",
        "address_zip_check": "string",
        "brand": "string",
        "country": "string",
        "customer": "string",
        "cvc_check": "string",
        "dynamic_last4": "string",
        "exp_month": 0,
        "exp_year": 0,
        "fingerprint": "string",
        "funding": "string",
        "last4": "string",
        "name": "string",
        "tokenization_method": "string"
      }
    ],
    "has_more": true,
    "total_count": 0,
    "url": "string"
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|account_balance|integer(int32)|false|Current balance, if any, being stored on the customer’s account. If negative, the customer has credit to apply to the next invoice. If positive, the customer has an amount owed that will be added to the next invoice. The balance does not refer to any unpaid invoices; it solely takes into account amounts that have yet to be successfully applied to any invoice. This balance is only taken into account for recurring billing purposes (i.e., subscriptions, invoices, invoice items).|
|created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|currency|string|false|Three-letter ISO code for the currency the customer can be charged in for recurring billing purposes.|
|default_source|string|false|ID of the default source attached to this customer.|
|delinquent|boolean|false|When the customer’s latest invoice is billed by charging automatically, delinquent is true if the invoice’s latest charge is failed. When the customer’s latest invoice is billed by sending an invoice, delinquent is true if the invoice is not paid by its due date.|
|description|string|false|An arbitrary string attached to the object. Often useful for displaying to users.|
|discount|[discount](#schemadiscount)|false|No description|
|email|string|false|The customer’s email address.|
|invoice_prefix|string|false|The prefix for the customer used to generate unique invoice numbers.|
|livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|shipping|[shipping](#schemashipping)|false|No description|
|subscriptions|[subscriptions](#schemasubscriptions)|false|No description|
|sources|[sources](#schemasources)|false|No description|


<h2 id="tocSshipping">shipping</h2>


<a id="schemashipping"></a>


```json
{
  "address": {
    "city": "string",
    "country": "string",
    "line1": "string",
    "line2": "string",
    "postal_code": "string",
    "state": "string"
  },
  "name": "string",
  "phone": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|address|[address](#schemaaddress)|false|No description|
|name|string|false|customer name.|
|phone|string|false|customer phone (including extension).|


<h2 id="tocSaddress">address</h2>


<a id="schemaaddress"></a>


```json
{
  "city": "string",
  "country": "string",
  "line1": "string",
  "line2": "string",
  "postal_code": "string",
  "state": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|city|string|false|City/District/Suburb/Town/Village.|
|country|string|false|2-letter country code.|
|line1|string|false|address line 1 (Street address/PO Box/Company name).|
|line2|string|false|address line 2 (Apartment/Suite/Unit/Building).|
|postal_code|string|false|ZIP or postal code|
|state|string|false|State/County/Province/Region.|


<h2 id="tocSdiscount">discount</h2>


<a id="schemadiscount"></a>


```json
{
  "object": "string",
  "coupon": {
    "id": "string",
    "object": "string",
    "amount_off": {},
    "created": 0,
    "currency": "string",
    "duration": "string",
    "duration_in_months": 0,
    "livemode": true,
    "max_redemptions": 0,
    "percent_off": 0,
    "redeem_by": "2018-02-14",
    "times_redeemed": 0,
    "valid": true
  },
  "customer": "string",
  "end": 0,
  "start": 0,
  "subscription": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|coupon|[coupon](#schemacoupon)|false|No description|
|customer|string|false|No description|
|end|integer(int32)|false|If the coupon has a duration of repeating, the date that this discount will end. If the coupon has a duration of once or forever, this attribute will be null.|
|start|integer(int32)|false|Date that the coupon was applied.|
|subscription|string|false|The subscription that this coupon is applied to, if it is applied to a particular subscription.|


<h2 id="tocScoupon">coupon</h2>


<a id="schemacoupon"></a>


```json
{
  "id": "string",
  "object": "string",
  "amount_off": {},
  "created": 0,
  "currency": "string",
  "duration": "string",
  "duration_in_months": 0,
  "livemode": true,
  "max_redemptions": 0,
  "percent_off": 0,
  "redeem_by": "2018-02-14",
  "times_redeemed": 0,
  "valid": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|amount_off|object|false|Amount (in the currency specified) that will be taken off the subtotal of any invoices for this customer.|
|created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|currency|string|false|If amount_off has been set, the three-letter ISO code for the currency of the amount to take off.|
|duration|string|false|One of forever, once, and repeating. Describes how long a customer who applies this coupon will get the discount.|
|duration_in_months|integer(int32)|false|If duration is repeating, the number of months the coupon applies. Null if coupon duration is forever or once.|
|livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|max_redemptions|integer|false|Maximum number of times this coupon can be redeemed, in total, before it is no longer valid.|
|percent_off|integer(int32)|false|Percent that will be taken off the subtotal of any invoices for this customer for the duration of the coupon. For example, a coupon with percent_off of 50 will make a $100 invoice $50 instead.|
|redeem_by|string(date)|false|Date after which the coupon can no longer be redeemed.|
|times_redeemed|integer(int32)|false|Number of times this coupon has been applied to a customer.|
|valid|boolean|false|Taking account of the above properties, whether this coupon can still be applied to a customer.|


<h2 id="tocSsubscriptions">subscriptions</h2>


<a id="schemasubscriptions"></a>


```json
{
  "object": "string",
  "data": [
    {
      "id": "string",
      "object": "string",
      "application_fee_percent": 0,
      "billing": "string",
      "billing_cycle_anchor": 0,
      "cancel_at_period_end": true,
      "canceled_at": 0,
      "created": 0,
      "current_period_end": 0,
      "current_period_start": 0,
      "customer": "string",
      "days_until_due": 0,
      "discount": 0,
      "ended_at": 0,
      "items": [
        {
          "id": "string",
          "object": "string",
          "created": 0,
          "plan": {
            "id": "string",
            "object": "string",
            "amount": 0,
            "created": 0,
            "currency": "string",
            "interval": "string",
            "interval_count": 0,
            "livemode": true,
            "nickname": "string",
            "product": "string",
            "trial_period_days": 0
          },
          "quantity": 0,
          "subscription": "string"
        }
      ],
      "livemode": true,
      "plan": {
        "id": "string",
        "object": "string",
        "amount": 0,
        "created": 0,
        "currency": "string",
        "interval": "string",
        "interval_count": 0,
        "livemode": true,
        "nickname": "string",
        "product": "string",
        "trial_period_days": 0
      },
      "quantity": 0,
      "start": 0,
      "status": "string",
      "tax_percent": 0,
      "trial_end": 0,
      "trial_start": 0
    }
  ],
  "has_more": true,
  "total_count": 0,
  "url": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|object|string|false|String representing the object’s type. Objects of the same type share the same value. Always has the value “list”.|
|data|[[subscription](#schemasubscription)]|false|Array of subscription objects.|
|has_more|boolean|false|True if this list has another page of items after this one that can be fetched.|
|total_count|integer(int32)|false|No description|
|url|string|false|The URL where this list can be accessed.|


<h2 id="tocSsubscription">subscription</h2>


<a id="schemasubscription"></a>


```json
{
  "id": "string",
  "object": "string",
  "application_fee_percent": 0,
  "billing": "string",
  "billing_cycle_anchor": 0,
  "cancel_at_period_end": true,
  "canceled_at": 0,
  "created": 0,
  "current_period_end": 0,
  "current_period_start": 0,
  "customer": "string",
  "days_until_due": 0,
  "discount": 0,
  "ended_at": 0,
  "items": [
    {
      "id": "string",
      "object": "string",
      "created": 0,
      "plan": {
        "id": "string",
        "object": "string",
        "amount": 0,
        "created": 0,
        "currency": "string",
        "interval": "string",
        "interval_count": 0,
        "livemode": true,
        "nickname": "string",
        "product": "string",
        "trial_period_days": 0
      },
      "quantity": 0,
      "subscription": "string"
    }
  ],
  "livemode": true,
  "plan": {
    "id": "string",
    "object": "string",
    "amount": 0,
    "created": 0,
    "currency": "string",
    "interval": "string",
    "interval_count": 0,
    "livemode": true,
    "nickname": "string",
    "product": "string",
    "trial_period_days": 0
  },
  "quantity": 0,
  "start": 0,
  "status": "string",
  "tax_percent": 0,
  "trial_end": 0,
  "trial_start": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|application_fee_percent|number|false|A non-negative decimal between 0 and 100, with at most two decimal places. This represents the percentage of the subscription invoice subtotal that will be transferred to the application owner’s Stripe account.|
|billing|string|false|Either charge_automatically, or send_invoice. When charging automatically, Stripe will attempt to pay this subscription at the end of the cycle using the default source attached to the customer. When sending an invoice, Stripe will email your customer an invoice with payment instructions.|
|billing_cycle_anchor|integer(int32)|false|Determines the date of the first full invoice, and, for plans with month or year intervals, the day of the month for subsequent invoices.|
|cancel_at_period_end|boolean|false|If the subscription has been canceled with the at_period_end flag set to true, cancel_at_period_end on the subscription will be true. You can use this attribute to determine whether a subscription that has a status of active is scheduled to be canceled at the end of the current period.|
|canceled_at|integer(int32)|false|If the subscription has been canceled, the date of that cancellation. If the subscription was canceled with cancel_at_period_end, canceled_at will still reflect the date of the initial cancellation request, not the end of the subscription period when the subscription is automatically moved to a canceled state. Measured in seconds since the Unix epoch.|
|created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|current_period_end|integer(int32)|false|End of the current period that the subscription has been invoiced for. At the end of this period, a new invoice will be created.|
|current_period_start|integer(int32)|false|Start of the current period that the subscription has been invoiced for.|
|customer|string|false|ID of the customer who owns the subscription.|
|days_until_due|integer|false|Number of days a customer has to pay invoices generated by this subscription. This value will be null for subscriptions where billing=charge_automatically.|
|discount|number|false|Describes the current discount applied to this subscription, if there is one. When billing, a discount applied to a subscription overrides a discount applied on a customer-wide basis.|
|ended_at|integer(int32)|false|If the subscription has ended, the date the subscription ended.|
|items|[[subscription_items](#schemasubscription_items)]|false|No description|
|» object|string|false|No description|
|» data|[any]|false|No description|
|» has_more|boolean|false|No description|
|» total_count|integer(int32)|false|No description|
|» url|string|false|No description|
|livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|plan|[plan](#schemaplan)|false|No description|
|quantity|integer(int32)|false|The quantity of the plan to which the customer should be subscribed. For example, if your plan is $10/user/month, and your customer has 5 users, you could pass 5 as the quantity to have the customer charged $50 (5 x $10) monthly.|
|start|integer(int32)|false|Date the most recent update to this subscription started.|
|status|string|false|Possible values are trialing, active, past_due, canceled, or unpaid. A subscription still in its trial period is trialing and moves to active when the trial period is over. If subscription billing=charge_automatically it becomes past_due when payment to renew it fails and canceled or unpaid (depending on your subscriptions settings) when Stripe has exhausted all payment retry attempts. If subscription billing=send_invoice it becomes past_due when its invoice is not paid by the due date, and canceled or unpaid if it is still not paid by an additional deadline after that. Note that when a subscription has a status of unpaid, no subsequent invoices will be attempted (invoices will be created, but then immediately automatically closed.) After receiving updated payment information from a customer, you may choose to reopen and pay their closed invoices.|
|tax_percent|number|false|If provided, each invoice created by this subscription will apply the tax rate, increasing the amount billed to the customer.|
|trial_end|integer(int32)|false|If the subscription has a trial, the end of that trial.|
|trial_start|integer(int32)|false|Measured in seconds since the Unix epoch.|


<h2 id="tocSplan">plan</h2>


<a id="schemaplan"></a>


```json
{
  "id": "string",
  "object": "string",
  "amount": 0,
  "created": 0,
  "currency": "string",
  "interval": "string",
  "interval_count": 0,
  "livemode": true,
  "nickname": "string",
  "product": "string",
  "trial_period_days": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|amount|integer(int32)|false|The amount in cents to be charged on the interval specified.|
|created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|currency|string|false|Three-letter ISO currency code, in lowercase. Must be a supported currency.|
|interval|string|false|One of day, week, month or year. The frequency with which a subscription should be billed.|
|interval_count|integer(int32)|false|The number of intervals (specified in the interval property) between each subscription billing. For example, interval=month and interval_count=3 bills every 3 months.|
|livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|nickname|string|false|A brief description of the plan, hidden from customers.|
|product|string|false|The product whose pricing this plan determines.|
|trial_period_days|integer(int32)|false|No description|


<h2 id="tocSsources">sources</h2>


<a id="schemasources"></a>


```json
{
  "object": "string",
  "data": [
    {
      "id": "string",
      "object": "string",
      "address_city": "string",
      "address_country": "string",
      "address_line1": "string",
      "address_line1_check": "string",
      "address_line2": "string",
      "address_state": "string",
      "address_zip": "string",
      "address_zip_check": "string",
      "brand": "string",
      "country": "string",
      "customer": "string",
      "cvc_check": "string",
      "dynamic_last4": "string",
      "exp_month": 0,
      "exp_year": 0,
      "fingerprint": "string",
      "funding": "string",
      "last4": "string",
      "name": "string",
      "tokenization_method": "string"
    }
  ],
  "has_more": true,
  "total_count": 0,
  "url": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|object|string|false|A string describing the object type returned.|
|data|[[source](#schemasource)]|false|source object. Can be card or bank account.|
|has_more|boolean|false|Whether or not there are more elements available after this set. If false, this set comprises the end of the list.|
|total_count|integer(int32)|false|No description|
|url|string|false|The URL for accessing this list.|


<h2 id="tocSsource">source</h2>


<a id="schemasource"></a>


```json
{
  "id": "string",
  "object": "string",
  "address_city": "string",
  "address_country": "string",
  "address_line1": "string",
  "address_line1_check": "string",
  "address_line2": "string",
  "address_state": "string",
  "address_zip": "string",
  "address_zip_check": "string",
  "brand": "string",
  "country": "string",
  "customer": "string",
  "cvc_check": "string",
  "dynamic_last4": "string",
  "exp_month": 0,
  "exp_year": 0,
  "fingerprint": "string",
  "funding": "string",
  "last4": "string",
  "name": "string",
  "tokenization_method": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|The type of payment source. Should be "card".|
|address_city|string|false|City/District/Suburb/Town/Village.|
|address_country|string|false|Billing address country, if provided when creating card.|
|address_line1|string|false|address line 1 (Street address/PO Box/Company name).|
|address_line1_check|string|false|If address_line1 was provided, results of the check: pass, fail, unavailable, or unchecked.|
|address_line2|string|false|address line 2 (Apartment/Suite/Unit/Building).|
|address_state|string|false|State/County/Province/Region.|
|address_zip|string|false|Zip/Postal Code.|
|address_zip_check|string|false|ZIP or postal code|
|brand|string|false|Card brand. Can be Visa, American Express, MasterCard, Discover, JCB, Diners Club, or Unknown.|
|country|string|false|Two-letter ISO code representing the country of the card. You could use this attribute to get a sense of the international breakdown of cards you’ve collected.|
|customer|string|false|The customer that this card belongs to. This attribute will not be in the card object if the card belongs to an account or recipient instead.|
|cvc_check|string|false|If a CVC was provided, results of the check: pass, fail, unavailable, or unchecked.|
|dynamic_last4|string|false|(For tokenized numbers only.) The last four digits of the device account number.|
|exp_month|integer(int32)|false|Two digit number representing the card's expiration month.|
|exp_year|integer(int32)|false|Two or four digit number representing the card's expiration year.|
|fingerprint|string|false|Uniquely identifies this particular bank account. You can use this attribute to check whether two bank accounts are the same.|
|funding|string|false|Card funding type. Can be credit, debit, prepaid, or unknown.|
|last4|string|false|The last 4 digits of the card.|
|name|string|false|Cardholder's full name.|
|tokenization_method|string|false|If the card number is tokenized, this is the method that was used. Can be apple_pay or android_pay.|


<h2 id="tocSinvoice">invoice</h2>


<a id="schemainvoice"></a>


```json
{
  "id": "string",
  "object": "string",
  "amount_due": 0,
  "application_fee": 0,
  "attempt_count": 0,
  "attempted": true,
  "billing": "string",
  "charge": "string",
  "closed": true,
  "currency": "string",
  "customer": "string",
  "date": 0,
  "description": "string",
  "discount": {
    "object": "string",
    "coupon": {
      "id": "string",
      "object": "string",
      "amount_off": {},
      "created": 0,
      "currency": "string",
      "duration": "string",
      "duration_in_months": 0,
      "livemode": true,
      "max_redemptions": 0,
      "percent_off": 0,
      "redeem_by": "2018-02-14",
      "times_redeemed": 0,
      "valid": true
    },
    "customer": "string",
    "end": 0,
    "start": 0,
    "subscription": "string"
  },
  "due_date": 0,
  "ending_balance": 0,
  "forgiven": true,
  "lines": {
    "data": {
      "id": "string",
      "object": "string",
      "amount": 0,
      "currency": "string",
      "description": "string",
      "discountable": true,
      "livemode": true,
      "period": {
        "start": 0,
        "end": 0
      },
      "plan": {
        "id": "string",
        "object": "string",
        "amount": 0,
        "created": 0,
        "currency": "string",
        "interval": "string",
        "interval_count": 0,
        "livemode": true,
        "nickname": "string",
        "product": "string",
        "trial_period_days": 0
      },
      "proration": true,
      "quantity": 0,
      "subscription": "string",
      "subscription_item": "string",
      "type": "string"
    },
    "has_more": true,
    "object": "string",
    "url": "string"
  },
  "livemode": true,
  "next_payment_attempt": 0,
  "number": "string",
  "paid": true,
  "period_end": 0,
  "period_start": 0,
  "receipt_number": "string",
  "starting_balance": 0,
  "statement_descriptor": "string",
  "subscription": "string",
  "subtotal": 0,
  "tax": 0,
  "tax_percent": 0,
  "total": 0,
  "webhooks_delivered_at": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|amount_due|integer(int32)|false|Final amount due at this time for this invoice. If the invoice’s total is smaller than the minimum charge amount, for example, or if there is account credit that can be applied to the invoice, the amount_due may be 0. If there is a positive starting_balance for the invoice (the customer owes money), the amount_due will also take that into account. The charge that gets generated for the invoice will be for the amount specified in amount_due.|
|application_fee|integer|false|The fee in cents that will be applied to the invoice and transferred to the application owner’s Stripe account when the invoice is paid.|
|attempt_count|integer(int32)|false|Number of payment attempts made for this invoice, from the perspective of the payment retry schedule. Any payment attempt counts as the first attempt, and subsequently only automatic retries increment the attempt count. In other words, manual payment attempts after the first attempt do not affect the retry schedule.|
|attempted|boolean|false|Whether an attempt has been made to pay the invoice. An invoice is not attempted until 1 hour after the invoice.created webhook, for example, so you might not want to display that invoice as unpaid to your users.|
|billing|string|false|Either charge_automatically, or send_invoice. When charging automatically, Stripe will attempt to pay this invoice using the default source attached to the customer. When sending an invoice, Stripe will email this invoice to the customer with payment instructions.|
|charge|string|false|ID of the latest charge generated for this invoice, if any.|
|closed|boolean|false|Whether the invoice is still trying to collect payment. An invoice is closed if it’s either paid or it has been marked closed. A closed invoice will no longer attempt to collect payment.|
|currency|string|false|Three-letter ISO currency code, in lowercase. Must be a supported currency.|
|customer|string|false|The customer id for the given invoice.|
|date|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|description|string|false|An arbitrary string attached to the object. Often useful for displaying to users.|
|discount|[discount](#schemadiscount)|false|No description|
|due_date|integer(int32)|false|The date on which payment for this invoice is due. This value will be null for invoices where billing=charå†ge_automatically.|
|ending_balance|integer(int32)|false|Ending customer balance after the invoice is frozen. invoices are frozen approximately an hour after successful webhook delivery or when payment collection is attempted for the invoice. If the invoice has not been frozen yet, this will be null.|
|forgiven|boolean|false|Whether the invoice has been forgiven. Forgiving an invoice instructs us to update the subscription status as if the invoice were successfully paid. Once an invoice has been forgiven, it cannot be unforgiven or reopened.|
|lines|[lines](#schemalines)|false|No description|
|livemode|boolean|false|Flag indicating whether the object exists in live mode or test mode.|
|next_payment_attempt|integer|false|The time at which payment will next be attempted. This value will be null for invoices where billing=send_invoice.|
|number|string|false|A unique, identifying string that appears on emails sent to the customer for this invoice. This starts with the customer’s unique invoice_prefix if it is specified.|
|paid|boolean|false|Whether payment was successfully collected for this invoice. An invoice can be paid (most commonly) with a charge or with credit from the customer’s account balance.|
|period_end|integer(int32)|false|End of the usage period during which invoice items were added to this invoice.|
|period_start|integer(int32)|false|Start of the usage period during which invoice items were added to this invoice.|
|receipt_number|string|false|This is the transaction number that appears on email receipts sent for this invoice.|
|starting_balance|integer(int32)|false|Starting customer balance before the invoice is frozen. If the invoice has not been frozen yet, this will be the current customer balance.|
|statement_descriptor|string|false|Extra information about an invoice for the customer’s credit card statement.|
|subscription|string|false|The subscription that this invoice was prepared for, if any.|
|subtotal|integer(int32)|false|Total of all subscriptions, invoice items, and prorations on the invoice before any discount is applied.|
|tax|integer|false|The amount of tax included in the total, calculated from tax_percent and the subtotal. If no tax_percent is defined, this value will be null.|
|tax_percent|integer|false|This percentage of the subtotal has been added to the total amount of the invoice, including invoice line items and discounts. This field is inherited from the subscription’s tax_percent field, but can be changed before the invoice is paid. This field defaults to null.|
|total|integer(int32)|false|Total after discount.|
|webhooks_delivered_at|integer(int32)|false|The time at which webhooks for this invoice were successfully delivered (if the invoice had no webhooks to deliver, this will match date). invoice payment is delayed until webhooks are delivered, or until all webhook delivery attempts have been exhausted.|


<h2 id="tocSlines">lines</h2>


<a id="schemalines"></a>


```json
{
  "data": {
    "id": "string",
    "object": "string",
    "amount": 0,
    "currency": "string",
    "description": "string",
    "discountable": true,
    "livemode": true,
    "period": {
      "start": 0,
      "end": 0
    },
    "plan": {
      "id": "string",
      "object": "string",
      "amount": 0,
      "created": 0,
      "currency": "string",
      "interval": "string",
      "interval_count": 0,
      "livemode": true,
      "nickname": "string",
      "product": "string",
      "trial_period_days": 0
    },
    "proration": true,
    "quantity": 0,
    "subscription": "string",
    "subscription_item": "string",
    "type": "string"
  },
  "has_more": true,
  "object": "string",
  "url": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|data|[line_item](#schemaline_item)|false|No description|
|has_more|boolean|false|True if this list has another page of items after this one that can be fetched.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value. Always has the value “list”.|
|url|string|false|The URL where this list can be accessed.|


<h2 id="tocSperiod">period</h2>


<a id="schemaperiod"></a>


```json
{
  "start": 0,
  "end": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|start|integer(int32)|false|No description|
|end|integer(int32)|false|No description|


<h2 id="tocSsubscription_items">subscription_items</h2>


<a id="schemasubscription_items"></a>


```json
{
  "id": "string",
  "object": "string",
  "created": 0,
  "plan": {
    "id": "string",
    "object": "string",
    "amount": 0,
    "created": 0,
    "currency": "string",
    "interval": "string",
    "interval_count": 0,
    "livemode": true,
    "nickname": "string",
    "product": "string",
    "trial_period_days": 0
  },
  "quantity": 0,
  "subscription": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value. Always has the value “list”.|
|created|integer(int32)|false|Time at which the object was created. Measured in seconds since the Unix epoch.|
|plan|[plan](#schemaplan)|false|No description|
|quantity|integer(int32)|false|The quantity of the plan to which the customer should be subscribed.|
|subscription|string|false|No description|


<h2 id="tocSline_item">line_item</h2>


<a id="schemaline_item"></a>


```json
{
  "id": "string",
  "object": "string",
  "amount": 0,
  "currency": "string",
  "description": "string",
  "discountable": true,
  "livemode": true,
  "period": {
    "start": 0,
    "end": 0
  },
  "plan": {
    "id": "string",
    "object": "string",
    "amount": 0,
    "created": 0,
    "currency": "string",
    "interval": "string",
    "interval_count": 0,
    "livemode": true,
    "nickname": "string",
    "product": "string",
    "trial_period_days": 0
  },
  "proration": true,
  "quantity": 0,
  "subscription": "string",
  "subscription_item": "string",
  "type": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|object|string|false|String representing the object’s type. Objects of the same type share the same value.|
|amount|integer(int32)|false|The amount, in cents.|
|currency|string|false|Three-letter ISO currency code, in lowercase. Must be a supported currency.|
|description|string|false|An arbitrary string attached to the object. Often useful for displaying to users.|
|discountable|boolean|false|If true, discounts will apply to this line item. Always false for prorations.|
|livemode|boolean|false|Whether this is a test line item.|
|period|[period](#schemaperiod)|false|No description|
|plan|[plan](#schemaplan)|false|No description|
|proration|boolean|false|Whether this is a proration.|
|quantity|integer(int32)|false|The quantity of the subscription, if the line item is a subscription or a proration.|
|subscription|string|false|When type is invoiceitem, the subscription that the invoice item pertains to, if any. Left blank when type is already subscription, as it’d be redundant with id.|
|subscription_item|string|false|No description|
|type|string|false|A string identifying the type of the source of this line item, either an invoiceitem or a subscription.|


<h2 id="tocScustomerbody">customerBody</h2>


<a id="schemacustomerbody"></a>


```json
{
  "id": "string",
  "currency": "string",
  "default_source": "string",
  "description": "string",
  "email": "string",
  "shipping": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postal_code": "string",
      "state": "string"
    },
    "name": "string",
    "phone": "string"
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|Unique identifier for the object.|
|currency|string|false|Three-letter ISO code for the currency the customer can be charged in for recurring billing purposes.|
|default_source|string|false|ID of the default source attached to this customer.|
|description|string|false|An arbitrary string attached to the object. Often useful for displaying to users.|
|email|string|false|The customer’s email address.|
|shipping|[shipping](#schemashipping)|false|No description|


<h2 id="tocSsourcebody">sourceBody</h2>


<a id="schemasourcebody"></a>


```json
{
  "address_city": "string",
  "address_country": "string",
  "address_line1": "string",
  "address_line2": "string",
  "address_state": "string",
  "address_zip": "string",
  "country": "string",
  "exp_month": 0,
  "exp_year": 0,
  "name": "string",
  "source": "string",
  "object": "string",
  "default_for_currency": true,
  "cvc": "string",
  "number": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|address_city|string|false|City/District/Suburb/Town/Village.|
|address_country|string|false|Billing address country, if provided when creating card.|
|address_line1|string|false|address line 1 (Street address/PO Box/Company name).|
|address_line2|string|false|address line 2 (Apartment/Suite/Unit/Building).|
|address_state|string|false|State/County/Province/Region.|
|address_zip|string|false|Zip/Postal Code.|
|country|string|false|Two-letter ISO code representing the country of the card. You could use this attribute to get a sense of the international breakdown of cards you’ve collected.|
|exp_month|integer(int32)|true|Two digit number representing the card's expiration month.|
|exp_year|integer(int32)|true|Two or four digit number representing the card's expiration year.|
|name|string|false|Cardholder's full name.|
|source|string|true|Either a token, like the ones returned by Stripe.js, or a dictionary containing a user's credit card details (with the options shown below). Stripe will automatically validate the card.|
|object|string|true|The type of payment source. Should be "card".|
|default_for_currency|boolean|false|Only applicable on accounts (not customers or recipients). If you set this to true (or if this is the first external account being added in this currency) this card will become the default external account for its currency.|
|cvc|string|true|Card security code. Highly recommended to always include this value, but it's only required for accounts based in European countries.|
|number|string|true|The card number, as a string without any separators.|


<h2 id="tocSuserbody">userBody</h2>


<a id="schemauserbody"></a>


```json
{
  "email": "string",
  "username": "string",
  "phone_number": "string",
  "picture": "string",
  "name": "string",
  "nickname": "string",
  "given_name": "string",
  "family_name": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|email|string|false|The user's email|
|username|string|false|The user's username|
|phone_number|string|false|The user's phone number (following the E.164 recommendation), only valid for users from SMS connections|
|picture|string|false|The user's picture|
|name|string|false|The user's name|
|nickname|string|false|The user's nickname|
|given_name|string|false|The user's given name (first name)|
|family_name|string|false|The user's family name (last name)|


