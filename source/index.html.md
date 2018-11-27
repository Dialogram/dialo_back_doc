---
title: Dialogram API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
  - json

toc_footers:
  - <a href='http://www.dialogram.fr/'>Follow us on our website !</a>
  - <a href='https://www.getpostman.com/collections/0c479b1d0da3ab12cabf'>Get the postman collection !</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - userSettings
  - fortgotPassword
  - errors

search: true
---

Welcome to the Dialogram API documentation! You can use our API to access API endpoints, which can be used to interacte with our server. You will find all the informations you need to build your app or module according to the respectives routes.

We have language bindings with Curl and Javascript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# User

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


### Query Parameters

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

### HTTP Request

`POST http://api.dialogram.fr:8080/api/user`

The Dialogram API use token to allow access to the API. You can register a new Dialogram API token by creating a new user according the user creation route's specifications.

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
   "url": "http://api.dialogram.fr:3000/api/user/",
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

### HTTP Request

`GET http://api.dialogram.fr:8080/api/user/`

### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

# Session

## Create a session

```shell
curl -X POST \
   http://api.dialogram.fr:8080/api/session \
   -H 'Content-Type: application/json' \
   -d '{
      "email" : "usermail@domain.com",
      "password" : "JeSuisUnTest",
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/session",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{\n\t\"nickName\" : \"NewUser\",\n\t\"email\" : \"usermail@domain.com\",\n\t\"password\" : \"JeSuisUnTest\",\n}"
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
            "type": "session",
            "id": "Your Session ID",
            "token": "Your User token",
            "deviceName": "Unknown",
        }
    ],
    "includes": []
}
```

This endpoint create a session linked to the specified user ID.

### HTTP Request

`POST http://api.dialogram.fr:8080/api/session`

### Query Parameters

``
   {
      "email" : "usermail@domain.com",
      "password" : "password1234"
   }
``

<aside class="success">
Note that you need to create a user before being able to create its session.
</aside>
