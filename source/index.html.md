---
title: Dialogram API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
  - json

toc_footers:
  - <a href='http://www.dialogram.fr/'>Follow us on our website !</a>
  - <a href='https://gitlab.com/Dialogram'>Contribute to the project !</a>
  - <a href='https://www.getpostman.com/collections/ec4646f66c95dda4d8de'>Get the postman collection !</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - sessions
  - documents
  - translation
  - videos
  - explore
  - errors

search: true
---

Welcome to the Dialogram API documentation! You can use our API to access API endpoints, which can be used to interacte with our server. You will find all the informations you need to build your app or module according to the respectives routes.

We have language bindings with Curl and Javascript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# User

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

## Create a user

```shell
# With shell, you can just copy and paste the following request after editing the needed body parameter.
curl -X POST \
  http://localhost:8080/api/user \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ce79c653-5c2f-40de-8df8-955ffac0ae8e' \
  -H 'User-Agent: Mozilla/5.0 (Linux; U; Android 4.0.3; en-in; SonyEricssonMT11i Version/4.0 Mobile Safari/534.30' \
  -H 'cache-control: no-cache' \
  -d '{
"nickName" : "UserName",
  "profile": {
			"firstName" : "John",
			"lastName" : "Bryan"
	},
"email" : "my-user@domain.com",
"password" : "password123"
}'
```

```javascript

# This snippet has been made using JQuery & Ajax.

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "f662c84a-7b42-4bc3-91fe-057f773361b5"
  },
  "processData": false,
  "data": "{\n\t\"nickName\" : \"UserName\",\n\t\"profile\": {\n\t\t\"firstName\" : \"John\",\n\t\t\"lastName\" : \"Bryan\"\n\t},\n\t\"email\" : \"my-user@domain.com\",\n\t\"password\" : \"password123\"\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
> The above request returns a JSON structured like this:

```json
{
    "data": [
        {
            "type": "user",
            "id": "5be1e7415f019d0b44ed1ff2",
            "nickName": "UserName",
            "profile": {
                "firstName": "John",
                "lastName": "Bryan"
            },
            "email": "my-user@domain.com"
        }
    ],
    "includes": [
        {
            "type": "session",
            "id": "5be1e7425f019d0b44ed1ff3",
            "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1YmUxZTc0MTVmMDE5ZDBiNDRlZDFmZjIiLCJpYXQiOjE1NDE1MzE0NTgsImV4cCI6MTU3MzA4OTA1OH0.3Em43RVafYzpVOhdYEeLk7DZcjcJCdQ_lsvGz76QS-8",
            "deviceName": "Safari on AndroidOS OS",
            "user": "5be1e7415f019d0b44ed1ff2"
        }
    ]
}
```

This endpoint allow you to create a user

#### HTTP Request

`POST http://api.dialogram.fr:8080/api/user`

The Dialogram API use token to allow access to the API. You can register a new Dialogram API token by creating a new user according the user creation route's specifications.

#### Query Parameters

``json
{
"nickName" : "UserName",
  "profile": {
			"firstName" : "John",
			"lastName" : "Bryan"
	},
"email" : "my-user@domain.com",
"password" : "password123"
}
``

<aside class="success">
  Remember — a happy user is an authenticated user!
</aside>

## Get a user

```shell
curl -X GET \
  http://api.dialogram.fr:8080/api/user/ \
   -d '{
      nickName = "Username",
      email = "myUser@domain.com",
      password = "JeSuisUnTest123"
}'
```

```javascript
var settings = {
   "async": true,
   "crossDomain": true,
   "url": "http://api.dialogram.fr:8080/api/user/",
   "method": "GET",
   "headers": {},
   "data": "{\n\tnickName = \"Username\",\n\temail = \"myUser@domain.com\",\n\tpassword = \"JeSuisUnTest\"\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [
    {
      "type": "user",
      "id": "5b3536658eabca0aab16ab05",
      "nickName": "UserName",
      "profile": {},
      "email": "my-user@domain.com"
    }
   ],
  "includes": []
}
```

This endpoint retrieves all users.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/user/`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Settings 🗀

### Update public information

```shell
curl --request PUT \
  --url http://api.dialogram.fr:8080/api/user/settings/public \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
  --data '
  {
  	"profile": {
      			"firstName" : "Indiana",
      			"lastName" : "Jones"
              }
  } '
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/settings/public",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
  },
  "processData": false,
  "data": " { \n\t\"profile\": {\n\t\t\t\"firstName\" : \"Indiana\",\n\t\t\t\"lastName\" : \"Jones\"\n\t}\n } "
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [
    {
      "type": "user",
      "id": "5be1e7415f019d0b44ed1ff2",
      "nickName": "UserName",
      "profile": {
         "firstName": "Indiana",
         "lastName": "Jones"
       },
      "email": "my-user@domain.com"
    }
   ],
  "includes": []
}
```

This endpoint update all public information of users.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/user/settings/public`

#### Query Parameters

``
 {
	"profile": {
			"firstName" : "Indiana",
			"lastName" : "Jones"
	}
 }
``

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

### Update password account

```shell
curl --request PUT \
  --url http://api.dialogram.fr:8080/api/user/settings/password \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 025a15c0-6d01-4785-8013-3e679a0b12e8' \
  --header 'cache-control: no-cache' \
  --data '
  {
    "currentPassword" : "password123",
    "newPassword" : "qwerty123"
  }'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/settings/password",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "8f458df6-6d6f-4787-b1a8-d9fb5168a0aa"
  },
  "processData": false,
  "data": " { \n\t\"currentPassword\" : \"password123\",\n\t\"newPassword\" : \"qwerty123\" \n }"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [
        {
            "type": "user",
            "id": "5be1e7415f019d0b44ed1ff2",
            "nickName": "UserName",
            "profile": {
                "firstName": "John",
                "lastName": "Bryan"
            },
            "email": "my-user@domain.com"
        }
    ],
    "includes": []
}
```

This endpoint update user password and send an email to informe the user.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/user/settings/password`

#### Query Parameters

``
{
  "currentPassword" : "password123",
  "newPassword" : "qwerty123"
}
``

### Update account

```shell
curl --request PUT \
  --url http://api.dialogram.fr:8080/api/user/settings/account \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: d72ba363-5244-4415-bc54-2abaaa687ccc' \
  --header 'cache-control: no-cache' \
  --data '
  {
    "nickName" : "editUserName",
    "email" : "editMyUser@domain.com"
  } '
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/settings/account",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "aeecb6ed-521e-4bd2-b19c-5d94bd57229d"
  },
  "processData": false,
  "data": " { \n\t\"nickName\" : \"editUserName\",\n\t\"email\" : \"editMyUser@domain.com\"\n } "
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [
        {
            "type": "user",
            "id": "5be1e7415f019d0b44ed1ff2",
            "nickName": "editUserName",
            "profile": {
                "firstName": "John",
                "lastName": "Bryan"
            },
            "email": "editMyUser@domain.com"
        }
    ],
    "includes": []
}
```

This endpoint update user account settings such as mail address or nickname. You should confirm to your new mail address if it have been edited.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/user/settings/account`

#### Query Parameters

``
{
  "nickName" : "editUserName",
  "email" : "editMyUser@domain.com"
}
``

### Confirm mail updated

```shell
curl --request GET \
  --url http://api.dialogram.fr:8080/api/user/settings/account/email/ \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: ae95d1d7-026c-43b3-8119-6635bdb5d0b6' \
  --header 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/settings/account/email/",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "68fd0a4b-2ed5-4303-b6b0-d544cc80df7f"
  },
  "processData": false,
  "data": ""
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint update the user mail address by token with the new one.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/user/settings/account/email/:token`

<aside class="success">
Remember — Your token will only be accessible in your mailbox !
</aside>

### Confirm Account

```shell
curl --request GET \
  --url http://api.dialogram.fr:8080/api/user/settings/confirm/:token \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 858fabaf-0acd-4eb7-9a63-e4057ff75bc7' \
  --header 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/settings/confirm/:token",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "47b12022-4582-4d68-972f-90de224f7ea6"
  },
  "processData": false,
  "data": ""
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint confirm user account by token.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/user/settings/confirm/:token`

<aside class="success">
Remember — Your token will only be accessible in your mailbox !
</aside>


### Delete Account

```shell
curl -X DELETE \
  http://api.dialogram.fr:8080/api/user/settings/account/delete \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: abcdff79-f8a5-4130-a870-426d100b03fc' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/settings/account/delete",
  "method": "DELETE",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "fabace17-36b7-42b6-ad17-e0bcc84abe58"
  },
  "processData": false,
  "data": ""
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

> The above request returns JSON structured like this:

```json
{
    "data": [],
    "includes": []
}
```

This endpoint delete an authenticated user account.

#### HTTP Request

`DELETE http://api.dialogram.fr:8080/api/user/settings/account/delete`


## Forgot Password 🗀

### Send token by email

```shell
curl -X POST \
   http://api.dialogram.fr:8080/api/password/reset \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/password/reset",
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

#### HTTP Request

`POST http://api.dialogram.fr:8080/api/password/reset`

#### Query Parameters

``
{
    "email" : "myMail@domain.com"
}
``

### Reset password by token

```shell
curl -X POST \
   http://api.dialogram.fr:8080/api/password/reset/:token \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/password/reset/:token",
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

#### HTTP Request

`POST http://api.dialogram.fr:8080/api/password/reset/:token`

#### Query Parameters

``
{
     "paswword" : "myNewPassword1234",
     "confirm" : "myNewPassword1234"
}
``
