# Documents

## Upload PDF document

```shell
curl -X POST \
  http://api.dialogram.fr:8080/api/document \
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

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document",
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
            "link": "api.dialogram.fr:8080/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "nbPage": 35,
            "public": false,
            "description": "My document description",
            "status": 1,
            "idOwner": "<owner_id>"
        }
    ],
    "includes": []
}
```

This endpoint upload a new PDF document to the remote server. You will need to send the data by form-data since we are dealing with documents using HTTP.

#### HTTP Request

`POST http://api.dialogram.fr:8080/api/document`

#### Query Parameters

Key naming | Content
---------- | -------
file (type: file) | Your pdf file
name (type: string) | Your document name
description (type: string) | Your document description
public (type: boolean) | Your document privacy

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Get PDF document

```shell
curl -X GET \
  http://api.dialogram.fr:8080/api/document/:idDocument \
  -H 'Authorization: Bearer <your_access_token>' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/:idDocument",
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
            "link": "api.dialogram.fr:8080/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "nbPage": 35,
            "public": false,
            "description": "My document description",
            "status": 1,
            "idOwner": "<owner_id>"
        }
    ],
    "includes": []
}
```

This endpoint get a previously created PDF document from the remote server. You only need to be authenticated with the user that uploads the document and the document id.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/document/:idDocument`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Get User Documents

```shell
curl -X GET \
  http://api.dialogram.fr:8080/api/user/documents \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: 5127421b-d83a-4730-b9b8-7a20955dac1c' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/user/documents",
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
            "link": "http://api.dialogram.fr:8080/medias/1546528270492-PLD_DIALOGRAM.pdf?accessToken=<your_access_token>",
            "nbPage": 23,
            "public": false,
            "description": null,
            "status": -1,
            "idOwner": "5c2e2528581ae035587a4344"
        },
        {
            "type": "documents",
            "id": "5c2e349d1679630b18f5636f",
            "name": "Insurance file",
            "link": "http://api.dialogram.fr:8080/medias/1546531997311-INSURANCE_FILE.pdf?accessToken=<your_access_token>",
            "nbPage": 2,
            "public": false,
            "description": "Medical insurance company",
            "status": -1,
            "idOwner": "5c2e2528581ae035587a4344"
        }
    ],
    "includes": []
}
```

This endpoint get all the user documents

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/documents`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>


## Update PDF document

```shell
curl -X PUT \
  http://api.dialogram.fr:8080/api/document/update/:idDocument \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'cache-control: no-cache' \
  -d '{
	     "name" : "newName",
	     "description": "Now we have a nice description, and the file is public",
	     "public" : "true"
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/update/:idDocument",
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
          "link": "api.dialogram.fr:8080/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
          "nbPage": 35,
          "public": true,
          "description": "Now we have a nice description, and the file is public",
          "status": 1,
          "idOwner": "<owner_id>"
        }
    ],
    "includes": []
}
```

This endpoint update the data file. You only need to be authenticated with the user that uploads the document and the document id.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/document/update/:id`

#### Query Parameters
``
{
  "name" : "newName",
	"description": "Now we have a nice description, and the file is public",
	"public" : "true"
}
``

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>
