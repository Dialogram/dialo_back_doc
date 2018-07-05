---
title: Dialogram API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
  - json

toc_footers:
  - <a href='http://www.dialogram.fr/'>Follow us on our website !</a>
  - <a href='https://www.getpostman.com/collections/e3c872477622e06c07da'>Get the postman collection !</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

Welcome to the Dialogram API documentation! You can use our API to access API endpoints, which can be used to interacte with our server. You will find all the informations you need to build your app or module according to the respectives routes.

We have language bindings with Curl and Javascript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

The Dialogram API is based on the node-express-boilerplate made with heart by [Liroo](https://github.com/Liroo/node-express-boilerplate).

# User

## Create a user

```shell
# With shell, you can just copy and paste the following request after editing the needed body parameter.
curl --request POST \
--url http://51.38.179.218:3000/api/user \
--header 'Content-Type: application/json' \
--data '{\n"nickName" : "NewUser",\n"email" : "NewUser@mymail.com",\n"password" : "Password123"\n}'
```

```javascript

# This snippet has been made using JQuery & Ajax.

var settings = {
	"async": true,
	"crossDomain": true,
	"url": "http://51.38.179.218:3000/api/user",
	"method": "POST",
	"headers": {
		"Content-Type": "application/json",
	},
	"processData": false,
	"data": "{\n\t\"nickName\" : \"NewUser\",\n\t\"email\" : \"NewUser@mymail.com\",\n\t\"password\		" : \"Password123\"\n}"
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
          "id": "5b3e092bf2e2422577a65013",
          "nickName": "NewUser",
          "profile": {},
          "email": "NewUser@mymail.com"
      }
   ],
   "includes": [
       {
           "type": "session",
           "id": "5b3e092bf2e2422577a65014",
           "token": "YOUR USER TOKEN",
           "deviceName": "Unknown",
           "user": "5b3e092bf2e2422577a65013" // User id
       }
   ]
}
```

This endpoint allow you to create a user

### HTTP Request

`POST http://51.38.179.218:3000/api/user`

The Dialogram API use token to allow access to the API. You can register a new Dialogram API token by creating a new user according the user creation route's specifications.

<aside class="success">
  Remember — a happy user is an authenticated user!
</aside>

## Get User

```shell
curl -X GET \
  http://51.38.179.218:3000/api/user/ \
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
   "url": "http://51.38.179.218:3000/api/user/",
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
      "nickName": "Lucas",
      "profile": {},
      "email": "lucas.onillon@epitech.eu"
    }
   ],
  "includes": []
}
```

This endpoint retrieves all users.

### HTTP Request

`GET http://51.38.179.218:3000/api/user/`

### Query Parameters

NONE

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

# Session

## Create a session

```shell
curl -X POST \
   http://51.38.179.218:3000/api/session \
   -H 'Content-Type: application/json' \
   -d '{
      "nickName" : "NewUser",
      "email" : "usermail@domain.com",
      "password" : "JeSuisUnTest",
      "userId": "Your User ID"
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://51.38.179.218:3000/api/session",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{\n\t\"nickName\" : \"NewUser\",\n\t\"email\" : \"usermail@domain.com\",\n\t\"password\" : \"JeSuisUnTest\",\n\t\"userId\": \"Your User ID\"\n}"
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
            "user": "Your User ID"
        }
    ],
    "includes": []
}
```

This endpoint create a session linked to the specified user ID.

### HTTP Request

`POST http://51.38.179.218:3000/api/session`

NONE

<aside class="success">
Note that you need to create a user before being able to create its session.
</aside>
