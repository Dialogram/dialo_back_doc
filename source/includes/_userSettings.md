# User Settings

## Update public information

```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/settings/public \
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
  "url": "https://api.dialogram.fr/api/user/settings/public",
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

`PUT https://api.dialogram.fr/api/user/settings/public`

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

## Update password account

```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/settings/password \
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
  "url": "https://api.dialogram.fr/api/user/settings/password",
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

`PUT https://api.dialogram.fr/api/user/settings/password`

#### Query Parameters

``
{
  "currentPassword" : "password123",
  "newPassword" : "qwerty123"
}
``

## Update account

```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/settings/account \
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
  "url": "https://api.dialogram.fr/api/user/settings/account",
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

`PUT https://api.dialogram.fr/api/user/settings/account`

#### Query Parameters

``
{
  "nickName" : "editUserName",
  "email" : "editMyUser@domain.com"
}
``

## Confirm mail updated

```shell
curl --request GET \
  --url https://api.dialogram.fr/api/user/settings/account/email/ \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: ae95d1d7-026c-43b3-8119-6635bdb5d0b6' \
  --header 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/account/email/",
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

`GET https://api.dialogram.fr/api/user/settings/account/email/:token`

<aside class="success">
Remember — Your token will only be accessible in your mailbox !
</aside>

## Confirm Account

```shell
curl --request GET \
  --url https://api.dialogram.fr/api/user/settings/confirm/:token \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 858fabaf-0acd-4eb7-9a63-e4057ff75bc7' \
  --header 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/confirm/:token",
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

`GET https://api.dialogram.fr/api/user/settings/confirm/:token`

<aside class="success">
Remember — Your token will only be accessible in your mailbox !
</aside>

## Landing Page Delete Account

```shell
curl -X GET \
  https://api.dialogram.fr/api/user/settings/account/delete \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 8c338b67-b8ff-4303-9463-dcdf8868f8ee' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/account/delete",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "763077d7-dd73-44b5-befd-4ab799d47120"
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

This endpoint is the landing page for deleting your user account.

#### HTTP Request

`GET https://api.dialogram.fr/api/user/settings/account/delete`


## Delete Account

```shell
curl -X DELETE \
  https://api.dialogram.fr/api/user/settings/account/delete \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: abcdff79-f8a5-4130-a870-426d100b03fc' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/account/delete",
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

`DELETE https://api.dialogram.fr/api/user/settings/account/delete`
