---
title: Dialogram API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
  - json

toc_footers:
  - <a href='https://www.dialogram.fr/'>Follow us on our website !</a>
  - <a href='https://gitlab.com/Dialogram'>Contribute to the project !</a>
  - <a href='https://www.getpostman.com/collections/e42e47b610196f463bbe'>Get the postman collection !</a>
  - <a href='https://www.getpostman.com/collections/5e4ac786b9f225a9d125'>Get the staging postman collection !</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - sessions
  - videos
  - documents
  - permissions
  - branches
  - translationArea
  - translationVideo
  - explore
  - apiVideo
  - tickets
  - errors

search: true
---

Welcome to the Dialogram API documentation! You can use our API to access API endpoints, which can be used to interacte with our server. You will find all the informations you need to build your app or module according to the respectives routes.

We have language bindings with Curl and Javascript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right. 


# User

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

## Authentication 🗀

### Create a user

```shell
# With shell, you can just copy and paste the following request after editing the needed body parameter.
curl -X POST \
  https://api.dialogram.fr/api/user \
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
  "url": "https://api.dialogram.fr/api/user",
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://ui-avatars.com/api/?name=John+Bryan",
                    "public_id": "null"
                },
                "birthday": null,
                "gender": null,
                "country": null,
                "hometown": null,
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": [
        {
            "type": "session",
            "id": "<id>",
            "provider": "Dialogram",
            "token": "<user_token>",
            "device": {
                "userAgent": "Safari",
                "OS": "AndroidOS"
            },
            "user": "<user_id>"
        }
    ]
}
```

This endpoint allow you to create a user

#### HTTP Request

`POST https://api.dialogram.fr/api/user`

The Dialogram API use token to allow access to the API. You can register a new Dialogram API token by creating a new user according the user creation route's specifications.

#### Query Parameters

``
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

### Authenticate with Facebook

```shell
# With shell, you can just copy and paste the following request after editing the needed body parameter.
curl -X POST \
  https://api.dialogram.fr/api/auth/facebook \
  -H 'Authorization: Bearer <user_facebook_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'cache-control: no-cache'
```

```javascript

# This snippet has been made using JQuery & Ajax.

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/auth/facebook",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Authorization": "Bearer <user_facebook_access_token>",
  },
  "processData": false
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Facebook",
                    "userId": "<user_id>"
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://res.cloudinary.com/dialogram/image/upload/v1549490326/profile_pictures/<id>.jpg",
                    "public_id": "<public_id>"
                },
                "birthday": "<facebook_user_birthday>",
                "gender": "<facebook_user_gender>",
                "country": null,
                "hometown": "<facebook_user_hometown>",
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint allow you to create a user

#### HTTP Request

`POST https://api.dialogram.fr/api/auth/facebook`

Create a Dialogram account or log in using Facebook API authentication.

#### Query Parameters

NONE

<aside class="success">
  Remember — Use your Facebook access token!
</aside>

### Authenticate with Google

```shell
curl -X POST \
  https://api.dialogram.fr/api/auth/google \
  -H 'Authorization: Bearer <user_google_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'cache-control: no-cache'
```

```javascript

# This snippet has been made using JQuery & Ajax.

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/auth/google",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "f662c84a-7b42-4bc3-91fe-057f773361b5",
    "Authorization": "Bearer <user_google_access_token>",
  },
  "processData": false
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Google",
                    "userId": "<user_id>"
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://res.cloudinary.com/dialogram/image/upload/v1549490326/profile_pictures/<id>.jpg",
                    "public_id": "<public_id>"
                },
                "birthday": "<google_user_birthday>",
                "gender": "<google_user_gender>",
                "country": null,
                "hometown": "<google_user_hometown>",
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint allow you to create a user

#### HTTP Request

`POST https://api.dialogram.fr/api/auth/google`

Create a Dialogram account or log in using Google API authentication.

#### Query Parameters

NONE

## Get a user by ID

```shell
curl -X GET \
  https://api.dialogram.fr/api/user/profile/:idUser \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
   "async": true,
   "crossDomain": true,
   "url": "https://api.dialogram.fr/api/user/profile/:idUser",
   "method": "GET",
   "headers": {}
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://ui-avatars.com/api/?name=John+Bryan",
                    "public_id": "null"
                },
                "birthday": null,
                "gender": null,
                "country": null,
                "hometown": null,
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint retrieves a specific user.

#### HTTP Request

`GET https://api.dialogram.fr/api/user/profile/:idUser`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is a confirmed account by email and authenticated by token!
</aside>

## Get my user

```shell
curl -X GET \
  https://api.dialogram.fr/api/user/ \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
   "async": true,
   "crossDomain": true,
   "url": "https://api.dialogram.fr/api/user/",
   "method": "GET",
   "headers": {}
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://ui-avatars.com/api/?name=John+Bryan",
                    "public_id": "null"
                },
                "birthday": null,
                "gender": null,
                "country": null,
                "hometown": null,
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint retrieves your user.

#### HTTP Request

`GET https://api.dialogram.fr/api/user/`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is a confirmed account by email and authenticated by token!
</aside>


## Search user(s)

```shell
curl -X GET \
  https://api.dialogram.fr/api/search/user/to_find \
  -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1YzYxM2Y1YmQ0YTMzYjc5ZWNiZjU1ZTMiLCJpYXQiOjE1NDk4NzcwODMsImV4cCI6MTU4MTQzNDY4M30.FW6yuM4x3-Oi7Nlxv_iRTE-pSwpIzgBC_Kuyf45sRY8' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/search/user/to_find",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1YzYxM2Y1YmQ0YTMzYjc5ZWNiZjU1ZTMiLCJpYXQiOjE1NDk4NzcwODMsImV4cCI6MTU4MTQzNDY4M30.FW6yuM4x3-Oi7Nlxv_iRTE-pSwpIzgBC_Kuyf45sRY8"
  }
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
            "id": "userID1",
            "nickName": "to_find1",
            "<user1_data>"
        },
        {
            "type": "user",
            "id": "userID2",
            "nickName": "try_to_find_me",
            "<user2_data>"
        },
        {
            "type": "user",
            "id": "userID3",
            "nickName": "not_hard_to_find",
            "<user3_data>"
        }
    ],
    "includes": []
}
```

This endpoint retrieves all users wherein the query parameter can be found using fuzzy search.

#### HTTP Request

`GET https://api.dialogram.fr/api/search/user/:to_find`

#### Query Parameters

``
to_find: the string that will be search in all the users nickname in database.
``

<aside class="success">
Remember — a happy user is a confirmed account by email and authenticated by token! — a happy user is an authenticated user by token!
</aside>

## Follow 🗀

### Follow an user
```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/follow \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
  --data '
  {
  	"nickName": "Indiana_jones"
  } '
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/follow",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
  },
  "processData": false,
  "data": "{\n\t\"nickName\": \"Indiana_jones\"\n}"
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://ui-avatars.com/api/?name=John+Bryan",
                    "public_id": "null"
                },
                "birthday": null,
                "gender": null,
                "country": null,
                "hometown": null,
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": ["<Indiana_jones_ID>"],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint follow an user.

#### HTTP Request

`PUT https://api.dialogram.fr/api/user/follow`

### Unfollow an user
```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/unfollow \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
  --data '
  {
  	"nickName": "Indiana_jones"
  } '
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/unfollow",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
  },
  "processData": false,
  "data": "{\n\t\"nickName\": \"Indiana_jones\"\n}"
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "John",
                "lastName": "Bryan",
                "profilePicture": {
                    "url": "https://ui-avatars.com/api/?name=John+Bryan",
                    "public_id": "null"
                },
                "birthday": null,
                "gender": null,
                "country": null,
                "hometown": null,
                "description": null,
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint follow an user.

#### HTTP Request

`PUT https://api.dialogram.fr/api/user/unfollow`


## Settings 🗀

### Update public information

```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/settings/public \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
  --data '
  {
  	"profile": {
      			"firstName" : "Harrison",
      			"lastName" : "Ford",
                "birthday": "13/07/1942",
                "gender": "male",
                "country": "USA",
                "hometown": "Chicago",
                "description": "Acteur américain"
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
  "data": " { \n\t\"profile\": {\n       \"firstName\" : \"Harrison\",\n       \"lastName\" : \"Ford\",\n       \"birthday\": \"13/07/1942\",\n       \"gender\": \"male\",\n       \"country\": \"USA\",\n       \"hometown\": \"Chicago\",\n       \"description\": \"Acteur américain\"\n    }\n } "
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "Harrison",
                "lastName": "Ford",
                "profilePicture": {
                    "url": "https://ui-avatars.com/api/?name=Harrison+Ford",
                    "public_id": "null"
                },
                "birthday": "13/07/1942",
                "gender": "male",
                "country": "USA",
                "hometown": "Chicago",
                "description": "Acteur américain",
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
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
       "firstName" : "Harrison",
       "lastName" : "Ford",
       "birthday": "13/07/1942",
       "gender": "male",
       "country": "USA",
       "hometown": "Chicago",
       "description": "Acteur américain"
    }
 }
``

<aside class="success">
Remember — a happy user is a confirmed account by email and authenticated by token!
</aside>

### Update Profil Picture

```shell
curl --request POST \
  --url https://api.dialogram.fr/api/user/settings/profilePicture \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F 'image=@/home/user/Images/<file_name>.jpg'
```

```javascript
var form = new FormData();
form.append("image", "/home/hazer/Images/<file_name>.jpg");

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/profilePicture",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
  },
  "processData": false,
  "contentType": false,
  "mimeType": "multipart/form-data",
  "data": form
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "Harrison",
                "lastName": "Ford",
                "profilePicture": {
                    "url": "https://res.cloudinary.com/dialogram/image/upload/v1549490326/profile_pictures/<id>.jpg",
                    "public_id": "<public_id"
                },
                "birthday": "13/07/1942",
                "gender": "male",
                "country": "USA",
                "hometown": "Chicago",
                "description": "Acteur américain",
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}
```

This endpoint upload a new profil picture and delete the old one.

#### HTTP Request

`POST https://api.dialogram.fr/api/user/settings/profilePicture`

#### Query Parameters

Key naming | Content
---------- | -------
image (type: file) | Your picture

<aside class="success">
  Remember — a happy user is a confirmed account by email and authenticated by token!
</aside>

### Update password account

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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "Harrison",
                "lastName": "Ford",
                "profilePicture": {
                    "url": "https://res.cloudinary.com/dialogram/image/upload/v1549490326/profile_pictures/<id>.jpg",
                    "public_id": "<public_id"
                },
                "birthday": "13/07/1942",
                "gender": "male",
                "country": "USA",
                "hometown": "Chicago",
                "description": "Acteur américain",
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
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

### Set a password

```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/settings/set/password \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 025a15c0-6d01-4785-8013-3e679a0b12e8' \
  --header 'cache-control: no-cache' \
  --data '
  {
    "newPassword" : "qwerty123"
  }'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/set/password",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "8f458df6-6d6f-4787-b1a8-d9fb5168a0aa"
  },
  "processData": false,
  "data": " { \n\t\"newPassword\" : \"qwerty123\" \n }"
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
            "id": "<user_id>",
            "nickName": "UserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "Harrison",
                "lastName": "Ford",
                "profilePicture": {
                    "url": "https://res.cloudinary.com/dialogram/image/upload/v1549490326/profile_pictures/<id>.jpg",
                    "public_id": "<public_id"
                },
                "birthday": "13/07/1942",
                "gender": "male",
                "country": "USA",
                "hometown": "Chicago",
                "description": "Acteur américain",
                "certificated": false
            },
            "email": "my-user@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
        }
    ],
    "includes": []
}

```

This endpoint set user password and send an email to informe the user.

#### HTTP Request

`PUT https://api.dialogram.fr/api/user/settings/set/password`

#### Query Parameters

``
{
  "newPassword" : "qwerty123"
}
``

<aside class="warning">
    Only available when authenticated by OAuth 2.0
</aside>

### Update account

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
            "id": "<user_id>",
            "nickName": "editUserName",
            "profile": {
                "registerDate": "2019-04-12T15:20:42.823Z",
                "createdWith": {
                    "prodivder": "Dialogram",
                    "userId": null
                },
                "firstName": "Harrison",
                "lastName": "Ford",
                "profilePicture": {
                    "url": "https://res.cloudinary.com/dialogram/image/upload/v1549490326/profile_pictures/<id>.jpg",
                    "public_id": "<public_id"
                },
                "birthday": "13/07/1942",
                "gender": "male",
                "country": "USA",
                "hometown": "Chicago",
                "description": "Acteur américain",
                "certificated": false
            },
            "email": "editMyUser@domain.com",
            "timestamp": 1555082426,
            "features": {
                "follows": [],
                "followers": [],
                "documentsLiked": [],
                "documentsCommented": [],
                "documentsFavorite": []
            }
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

### Confirm mail updated

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

### Send Confirm Account Token by Email

```shell
curl --request PUT \
  --url https://api.dialogram.fr/api/user/settings/send/verification \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 858fabaf-0acd-4eb7-9a63-e4057ff75bc7' \
  --header 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/settings/send/verification",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "47b12022-4582-4d68-972f-90de224f7ea6"
  },
  "processData": false
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

This endpoint send a token by email to validate his user account.

#### HTTP Request

`PUT https://api.dialogram.fr/api/user/settings/send/verification`

<aside class="success">
  You need to be authenticated to access to this request
</aside>

### Confirm Account

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


### Delete Account

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


## Forgot Password 🗀

### Send token by email

```shell
curl -X POST \
   https://api.dialogram.fr/api/password/reset \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/password/reset",
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

`POST https://api.dialogram.fr/api/password/reset`

#### Query Parameters

``
{
    "email" : "myMail@domain.com"
}
``

### Reset password by token

```shell
curl -X POST \
   https://api.dialogram.fr/api/password/reset/:token \
   -H 'Content-Type: application/json' \
   -d '{
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/password/reset/:token",
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

`POST https://api.dialogram.fr/api/password/reset/:token`

#### Query Parameters

``
{
     "paswword" : "myNewPassword1234",
     "confirm" : "myNewPassword1234"
}
``
