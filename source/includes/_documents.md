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
  -F nbPage=35
```

```javascript
var form = new FormData();
form.append("file", "C:\\Users\\path\\to\\my_file.pdf");
form.append("name", "myDocument");
form.append("nbPage", "35");

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
            "type": "document",
            "id": "5c18a505c2706510b6b90598",
            "name": "myDocument",
            "link": "api.dialogram.fr:8080/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "idTranslation": -1,
            "public": false,
            "status": 1,
            "nbPage": 35
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
nbPage (type: string) | The number of pages in the pdf file

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Get PDF document

```shell
curl -X GET \
  http://api.dialogram.fr:8080/api/document/<id_document> \
  -H 'Authorization: Bearer <your_access_token>' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/<id_document>",
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
            "type": "document",
            "id": "5c18a505c2706510b6b90598",
            "name": "myDocument",
            "link": "api.dialogram.fr:8080/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "idTranslation": -1,
            "public": false,
            "status": 1,
            "nbPage": 35
        }
    ],
    "includes": []
}
```

This endpoint get a previously created PDF document from the remote server. You only need to be authenticated with the user that uploads the document and the document id.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/document:<document_id>`

#### Query Parameters

NONE

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>