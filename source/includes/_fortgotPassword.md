# Forgot Password

## Landing page

```shell
curl -X GET \
   http://api.dialogram.fr:3000/api/password/reset \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:3000/api/password/reset",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns a JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint ask the user to enter the adress mail linked to the account he forgots the password.

### HTTP Request

`GET http://api.dialogram.fr:3000/api/password/reset`

### Query Parameters

NONE

<aside class="success">
You don't have to be authentificated.
</aside>

## Send token by email

```shell
curl -X POST \
   http://api.dialogram.fr:3000/api/password/reset \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:3000/api/password/reset",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns a JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint create a token and send it to the referenced email.

### HTTP Request

`POST http://api.dialogram.fr:3000/api/password/reset`

### Query Parameters

``
{
    "email" : "myMail@domain.com"
}
``

## Landing page reset password

```shell
curl -X GET \
   http://api.dialogram.fr:3000/api/password/reset/:token \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:3000/api/password/reset/:token",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns a JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint ask for the user to enter the new password.

### HTTP Request

`GET http://api.dialogram.fr:3000/api/password/reset/:token`

### Query Parameters

NONE

## Reset password by token

```shell
curl -X POST \
   http://api.dialogram.fr:3000/api/password/reset/:token \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:3000/api/password/reset/:token",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns a JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint reset the user password and create a new one.
All the sessions will be deleted and an email will be sent to the account to inform that the password have been changed.

### HTTP Request

`POST http://api.dialogram.fr:3000/api/password/reset/:token`

### Query Parameters

``
{
     "paswword" : "myNewPassword1234",
     "confirm" : "myNewPassword1234"
}
``