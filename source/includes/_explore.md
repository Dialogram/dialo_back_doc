# Explore

## Search

```shell
curl -X GET \
  'http://api.dialogram.fr:8080/api/search/?limit=5&page=2' \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: 9ae7f131-5f76-4cf6-9c54-51c0a31af75c' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/search/?limit=5&page=2",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "749eb01d-2208-45c5-81a0-f2fc93b2966b"
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
            "usageName": "<timestamp>-<file_name>.pdf",
            "nbPage": 35,
            "public": false,
            "description": "My document description",
            "status": 1,
            "category": "entertainment",
            "idTranslation": null,
            "idOwner": "<owner_id>",
            "creationDate": "2019-01-30T19:31:06.424Z",
            "__v": 0
        },
        {
            "type": "documents",
            "id": "<document_id>",
            "name": "myDocument",
            "link": "api.dialogram.fr:8080/medias/<timestamp>-<file_name>.pdf?accessToken=<your_access_token>",
            "usageName": "<timestamp>-<file_name>.pdf",
            "nbPage": 35,
            "public": false,
            "description": "My document description",
            "status": 1,
            "category": "entertainment",
            "idTranslation": null,
            "idOwner": "<owner_id>",
            "creationDate": "2019-01-30T19:31:06.424Z",
            "__v": 0
        }
    ],
    "includes": [
        {
            "type": "pagination",
            "total": 20,
            "limit": 2
        }
    ]
}
```

This endpoint return all the documents using a pagination system.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/search/`

#### Query Parameters

Key naming | Content
---------- | -------
limit | The limit of documents per page
page | The page number
offset | Use offset or page to skip a position
