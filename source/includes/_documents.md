# Documents

## Upload PDF document

```shell
curl -X POST \
  http://api.dialogram.fr/api/document \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F 'file=@C:\path\to\my_file.pdf' \
  -F name=myDocument \
  -F description=My document description \
  -F public=true
```

```javascript
var form = new FormData();
form.append("file", "C:\\Users\\path\\to\\my_file.pdf");
form.append("name", "myDocument");
form.append("description", "My document description");
form.append("public", "true");
form.append("category", "entertainment")

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document",
  "method": "POST",
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "Authorization": "Bearer <your_access_token>",
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

> The above request returns a JSON structured like this:

```json
{
    "data": [
        {
            "type": "documents",
            "id": "<document_id>",
            "name": "myDocument",
            "link": "api.dialogram.fr/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "usageName": "<timestamp>-<file_name>.pdf",
            "nbPage": 35,
            "public": false,
            "description": "My document description",
            "status": 1,
            "category": "entertainment",
            "idTranslation": null,
            "idOwner": "<owner_id>",
            "creationDate": "2019-01-30T19:31:06.424Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint upload a new PDF document to the remote server. You will need to send the data by form-data since we are dealing with documents using HTTP.

#### HTTP Request

`POST http://api.dialogram.fr/api/document`

#### Query Parameters

Key naming | Content
---------- | -------
file (type: file) | Your pdf file
name (type: string) | Your document name
description (type: string) | Your document description
public (type: boolean) | Your document privacy
category (type: string) | Your document category (health, finance, administrative entertainment, business)

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Get PDF document

```shell
curl -X GET \
  http://api.dialogram.fr/api/document/:idDocument \
  -H 'Authorization: Bearer <your_access_token>' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
  }
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
            "type": "documents",
            "id": "<document_id>",
            "name": "myDocument",
            "link": "api.dialogram.fr/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "usageName": "<timestamp>-<file_name>.pdf",
            "nbPage": 35,
            "public": false,
            "description": "My document description",
            "status": 1,
            "category": "entertainment",
            "idTranslation": null,
            "idOwner": "<owner_id>",
            "creationDate": "2019-01-30T19:31:06.424Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint get a previously created PDF document from the remote server. You only need to be authenticated with the user that uploads the document and the document id.

#### HTTP Request

`GET http://api.dialogram.fr/api/document/:idDocument`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>


## Get User Documents

```shell
curl -X GET \
  http://api.dialogram.fr/api/user/documents \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: 5127421b-d83a-4730-b9b8-7a20955dac1c' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/user/documents",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "59497a27-d494-4bf5-a225-db888692d29a"
  }
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
            "type": "documents",
            "id": "5c2e260e581ae035587a4346",
            "name": "PLD Dialogram",
            "link": "http://api.dialogram.fr/medias/1546528270492-PLD_DIALOGRAM.pdf?accessToken=<your_access_token>",
            "usageName": "<timestamp>-<file_name>.pdf",
            "nbPage": 23,
            "public": false,
            "description": null,
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5c2e2528581ae035587a4344",
            "creationDate": "2019-01-29T19:31:06.424Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "access": [
                "W",
                "D"
            ],
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        },
        {
            "type": "documents",
            "id": "5c2e349d1679630b18f5636f",
            "name": "Insurance file",
            "link": "http://api.dialogram.fr/medias/1546531997311-INSURANCE_FILE.pdf?accessToken=<your_access_token>",
            "usageName": "<timestamp>-<file_name>.pdf",
            "nbPage": 2,
            "public": false,
            "description": "Medical insurance company",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5c2e2528581ae035587a4344",
            "creationDate": "2019-01-29T19:31:06.424Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "access": [
                "W",
                "D"
            ],
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint get all the user documents

#### HTTP Request

`GET http://api.dialogram.fr/api/user/documents`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>


## Update PDF document

```shell
curl -X PUT \
  http://api.dialogram.fr/api/document/update/:idDocument \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'cache-control: no-cache' \
  -d '{
	     "name" : "newName",
	     "description": "Now we have a nice description, and the file is public",
	     "public" : "true",
       "category": "entertainment"
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/update/:idDocument",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache"
  },
  "processData": false,
  "data": "{\r\n\t    \"name\" : \"newName\",\r\n\t\t\"description\": \"Now we have a nice description, and the file is public\",\r\n\t    \"public\" : \"true\"\r\n}"
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
          "type": "documents",
          "id": "<document_id>",
          "name": "newName",
          "link": "api.dialogram.fr/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
          "usageName": "<timestamp>-<file_name>.pdf",
          "nbPage": 35,
          "public": true,
          "description": "Now we have a nice description, and the file is public",
          "status": 1,
          "category": "entertainment",
          "idTranslation": null,
          "idOwner": "<owner_id>",
          "creationDate": "2019-01-29T19:31:06.424Z",
          "editDate": "2019-01-30T20:14:56.747Z",
          "editDate": null,
            "timestamp": 1554198073930,
            "access": [
                "W",
                "D"
            ],
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint update the data file. You only need to be authenticated with the user that uploads the document and the document id. A new field "editDate" will be set with the date of edit.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/update/:id`

#### Query Parameters
``
{
  "name" : "newName",
	"description": "Now we have a nice description, and the file is public",
	"public" : "true",
  "category" : "entertainment"
}
``

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Delete Document by ID

```shell
curl -X DELETE \
  http://api.dialogram.fr/api/document/:idDocument \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: f2472e62-d64f-496e-8190-a115225d1e94' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument",
  "method": "DELETE",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "b68839fd-bcdf-4ee8-ac90-8dd5c667eacc"
  }
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

This endpoint delete a document by ID.

#### HTTP Request

`DELETE http://api.dialogram.fr/api/document/:idDocument`

#### Query Parameters

NONE

## Likes 🗀

### Likes a document
```shell
curl --request PUT \
  --url http://api.dialogram.fr/api/document/:idDocument/like \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/like",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [
                  <user_ID>
                  ],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint like a document.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/like`

### Remove like on a document
```shell
curl --request PUT \
  --url http://api.dialogram.fr/api/document/:idDocument/unlike \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/unlike",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint remove the like of a document previously liked.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/unlike`

## Favorite 🗀

### Favorite a document
```shell
curl --request PUT \
  --url http://api.dialogram.fr/api/document/:idDocument/favorite \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/favorite",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [
                  <user_ID>
                ],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint favorite a document.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/favorite`

### Remove favorite on a document
```shell
curl --request PUT \
  --url http://api.dialogram.fr/api/document/:idDocument/unfavorite \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 19cc57d1-5777-476b-8784-ec3b8d4ef5bc' \
  --header 'cache-control: no-cache' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/unfavorite",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint remove the favorite of a document.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/unfavorite`

## Comment 🗀

### Comment a document
```shell
curl -X PUT \
  http://api.dialogram.fr/api/document/:idDocument/comment \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: fab6e99e-bbd3-4b36-87a7-3cc8da86a743' \
  -H 'cache-control: no-cache' \
  -d '{
	"comment": "A new comment for your document"
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/comment",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
  },
  "processData": false,
  "data": "{\n\t\"comment\": \"A new comment for your document\"\n}"
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
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": [
                  {
                      "type": "comment",
                      "id": "<comment_id>",
                      "comment": "A new comment",
                      "likes": [],
                      "creationDate": "2019-04-02T14:31:12.602Z",
                      "lastUpdateDate": null,
                      "edited": false,
                      "ownerId": "<owner_id>"
                  }
                ]
            }
        }
    ],
    "includes": []
}
```

This endpoint comment a document.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/comment`

### Edit your document comment
```shell
curl -X PUT \
  http://api.dialogram.fr/api/document/:idDocument/comment/edit/:idComment \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: fab6e99e-bbd3-4b36-87a7-3cc8da86a743' \
  -H 'cache-control: no-cache' \
  -d '{
	"comment": "An edited comment for your document"
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/comment/edit/:idComment",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
  },
  "processData": false,
  "data": "{\n\t\"comment\": \"An edited comment for your document\"\n}"
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
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": [
                  {
                      "type": "comment",
                      "id": "<comment_id>",
                      "comment": "A new comment",
                      "likes": [],
                      "creationDate": "2019-04-02T14:31:12.602Z",
                      "lastUpdateDate": "2019-04-03T15:10:40.102Z",
                      "edited": true,
                      "ownerId": "<owner_id>"
                  }
                ]
            }
        }
    ],
    "includes": []
}
```

This endpoint comment a document.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/comment/edit/:idComment`

### Like a document comment
```shell
curl -X PUT \
  http://api.dialogram.fr/api/document/:idDocument/comment/:idComment/like \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: fab6e99e-bbd3-4b36-87a7-3cc8da86a743' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/comment/:idComment/like",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": [
                  {
                      "type": "comment",
                      "id": "<comment_id>",
                      "comment": "A new comment",
                      "likes": [
                        "<user_id>"
                      ],
                      "creationDate": "2019-04-02T14:31:12.602Z",
                      "lastUpdateDate": null,
                      "edited": false,
                      "ownerId": "<owner_id>"
                  }
                ]
            }
        }
    ],
    "includes": []
}
```

This endpoint like a document comment.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/comment/:idComment/like`

### Remove like on a document comment
```shell
curl -X PUT \
  http://api.dialogram.fr/api/document/:idDocument/comment/:idComment/unlike \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: fab6e99e-bbd3-4b36-87a7-3cc8da86a743' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/comment/:idComment/unlike",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": [
                  {
                      "type": "comment",
                      "id": "<comment_id>",
                      "comment": "A new comment",
                      "likes": [],
                      "creationDate": "2019-04-02T14:31:12.602Z",
                      "lastUpdateDate": null,
                      "edited": false,
                      "ownerId": "<owner_id>"
                  }
                ]
            }
        }
    ],
    "includes": []
}
```

This endpoint remove your like on a document comment.

#### HTTP Request

`PUT http://api.dialogram.fr/api/document/:idDocument/comment/:idComment/unlike`

### Delete a document comment
```shell
curl -X DELETE \
  http://api.dialogram.fr/api/document/:idDocument/uncomment/:idComment \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: fab6e99e-bbd3-4b36-87a7-3cc8da86a743' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/document/:idDocument/uncomment/:idComment",
  "method": "DELETE",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "46cb8c95-74e6-4435-9ad0-f20abeaece71"
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
    "data": [
        {
            "type": "documents",
            "id": "5ca32c243a6a6d45c456c495",
            "name": "myDocument",
            "link": "http://api.dialogram.fr/medias/document.pdf?accessToken=<acess_token>",
            "usageName": "document.pdf",
            "nbPage": 35,
            "public": true,
            "description": "My document description",
            "status": -1,
            "category": "health",
            "idTranslation": null,
            "idOwner": "5ca32c0c3a6a6d45c456c490",
            "creationDate": "2019-04-02T09:32:20.342Z",
            "editDate": null,
            "timestamp": 1554198073930,
            "features": {
                "likes": [],
                "favorites": [],
                "comments": []
            }
        }
    ],
    "includes": []
}
```

This endpoint delete a document comment.

#### HTTP Request

`DELETE http://api.dialogram.fr/api/document/:idDocument/uncomment/:idComment`
