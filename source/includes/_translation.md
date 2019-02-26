# Translations

## Create Translation

```shell
curl -X POST \
  http://api.dialogram.fr:8080/api/document/:idDocument/translation \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache' \
  -d '{
	"translation":[
		[
			{"x":"0", "y":"0", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"},
			{"x":"20", "y":"400", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"}
		],
		[
			{"x":"110", "y":"20", "width":"10", "height":"10", "idVideo": "123456789d922bd46b1724"},
			{"x":"10", "y":"500", "width":"30", "height":"30", "idVideo": "123456789d922bd46b1724"}
		]
	]
}
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/:idDocument/translation",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
  },
  "processData": false,
  "data": "{\n\t\"translation\":[\n\t\t[\n\t\t\t{\"x\":\"0\", \"y\":\"0\", \"width\":\"150\", \"height\":\"40\", \"idVideo\": \"6dzed4545d922bd46b1724\"},\n\t\t\t{\"x\":\"20\", \"y\":\"400\", \"width\":\"150\", \"height\":\"40\", \"idVideo\": \"6dzed4545d922bd46b1724\"}\n\t\t],\n\t\t[\n\t\t\t{\"x\":\"110\", \"y\":\"20\", \"width\":\"10\", \"height\":\"10\", \"idVideo\": \"123456789d922bd46b1724\"},\n\t\t\t{\"x\":\"10\", \"y\":\"500\", \"width\":\"30\", \"height\":\"30\", \"idVideo\": \"123456789d922bd46b1724\"}\n\t\t]\n\t]\n}\n"
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
            "type": "translations",
            "id": "5c2e68cba133a6173c81eb84",
            "idDocument": "5c2e684cce87402410164056",
            "translation": [
              [
          			{"x":"0", "y":"0", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"},
          			{"x":"20", "y":"400", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"}
          		],
          		[
          			{"x":"110", "y":"20", "width":"10", "height":"10", "idVideo": "123456789d922bd46b1724"},
          			{"x":"10", "y":"500", "width":"30", "height":"30", "idVideo": "123456789d922bd46b1724"}
          		]
            ]
        }
    ],
    "includes": []
}
```

This endpoint create the translation of the document by indicating the field that should be translated.

#### HTTP Request

`POST http://api.dialogram.fr:8080/api/document/:idDocument/translation`

#### Query Parameters
``
{
	"translation":[
		[
			{"x":"0", "y":"0", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"},
			{"x":"20", "y":"400", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"}
		],
		[
			{"x":"110", "y":"20", "width":"10", "height":"10", "idVideo": "123456789d922bd46b1724"},
			{"x":"10", "y":"500", "width":"30", "height":"30", "idVideo": "123456789d922bd46b1724"}
		]
	]
}
``

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Update Translation

```shell
curl -X PUT \
  http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache' \
  -d '{
	"translation":[
		[
			{"x":"999", "y":"999", "width":"555", "height":"555", "idVideo": "6dzed4545d922bd46b1724"},
			{"x":"111", "y":"111", "width":"666", "height":"666", "idVideo": "6dzed4545d922bd46b1724"}
		]
	]
}
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
  },
  "processData": false,
  "data": "{\n    \"translation\": [\n        [\n            {\n                \"x\": \"999\",\n                \"y\": \"999\",\n                \"width\": \"555\",\n                \"height\": \"555\",\n                \"idVideo\": \"6dzed4545d922bd46b1724\"\n            },\n            {\n                \"x\": \"111\",\n                \"y\": \"111\",\n                \"width\": \"666\",\n                \"height\": \"666\",\n                \"idVideo\": \"6dzed4545d922bd46b1724\"\n            }\n        ]\n    ]\n}"
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
            "type": "translations",
            "id": "5c2e68cba133a6173c81eb84",
            "idDocument": "5c2e684cce87402410164056",
            "translation": [
              [
          			{"x":"999", "y":"999", "width":"555", "height":"555", "idVideo": "6dzed4545d922bd46b1724"},
          			{"x":"111", "y":"111", "width":"666", "height":"666", "idVideo": "6dzed4545d922bd46b1724"}
          		]
            ]
        }
    ],
    "includes": []
}
```

This endpoint update the translation of the document.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation`

#### Query Parameters
``
{
  "translation": [
    [
      {"x":"999", "y":"999", "width":"555", "height":"555", "idVideo": "6dzed4545d922bd46b1724"},
      {"x":"111", "y":"111", "width":"666", "height":"666", "idVideo": "6dzed4545d922bd46b1724"}
    ]
  ]
}
``

## Get Translation by ID

```shell
curl -X GET \
  http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 18c389d0-37ca-4762-8ea1-e0d61489c0b6' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "6b36c235-3178-44bd-a6f0-2b4e54d1525f"
  },
  "processData": false,
  "data": ""
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
            "type": "translations",
            "id": "5c2e68cba133a6173c81eb84",
            "idDocument": "5c2e684cce87402410164056",
            "translation": [
              [
          			{"x":"0", "y":"0", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"},
          			{"x":"20", "y":"400", "width":"150", "height":"40", "idVideo": "6dzed4545d922bd46b1724"}
          		],
          		[
          			{"x":"110", "y":"20", "width":"10", "height":"10", "idVideo": "123456789d922bd46b1724"},
          			{"x":"10", "y":"500", "width":"30", "height":"30", "idVideo": "123456789d922bd46b1724"}
          		]
            ]
        }
    ],
    "includes": []
}
```

This endpoint get the translation of the document. 

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation`

#### Query Parameters

NONE

## Delete Translation

```shell
curl -X DELETE \
  http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: abcdff79-f8a5-4130-a870-426d100b03fc' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation",
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

This endpoint delete a translation.

#### HTTP Request

`DELETE http://api.dialogram.fr:8080/api/document/:idDocument/translation/:idTranslation`
