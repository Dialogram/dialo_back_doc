# Permissions

## Add edit permission

```shell
curl -X PUT \
  http://api.dialogram.fr:8085/api/document/:idDocument/waccess \
  -H 'Authorization: Bearer <user token>' \
  -H 'Content-Type: application/json' \
  -d '{
	"user": [
		"userId1",
        "userId2"
		]
    }'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8085/api/document/:idDocument/waccess",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <user_token>",
  },
  "processData": false,
  "data": "{\n\t\"user\": [\n\t\t\"userId\"\n\t\t]\n}"
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

This endpoint add the permission to a user or a list of user to edit the data of a specified document.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/document/:idDocument/waccess`

#### Query Parameters
``
idDocument: The id of the target document.
``

## Add deletion permission

```shell
curl -X PUT \
  http://api.dialogram.fr:8085/api/document/:idDocument/daccess \
  -H 'Authorization: Bearer <user token>' \
  -H 'Content-Type: application/json' \
  -d '{
	"user": [
		"userId1",
        "userId2"
		]
    }'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8085/api/document/:idDocument/daccess",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <user_token>",
  },
  "processData": false,
  "data": "{\n\t\"user\": [\n\t\t\"userId\"\n\t\t]\n}"
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

This endpoint add the permission to a user or a list of user to delete the data of a specified document.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/document/:idDocument/daccess`

#### Query Parameters
``
idDocument: The id of the target document.
``

## Remove edit permission

```shell
curl -X DELETE \
  http://api.dialogram.fr:8085/api/document/:idDocument/waccess \
  -H 'Authorization: Bearer <user token>' \
  -H 'Content-Type: application/json' \
  -d '{
	"user": [
		"userId1",
        "userId2"
		]
    }'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8085/api/document/:idDocument/waccess",
  "method": "DELETE",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <user_token>",
  },
  "processData": false,
  "data": "{\n\t\"user\": [\n\t\t\"userId\"\n\t\t]\n}"
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

This endpoint add the permission to a user or a list of user to remove the edit permission of other user(s) toward the data of a specified document.

#### HTTP Request

`DELETE http://api.dialogram.fr:8080/api/document/:idDocument/waccess`

#### Query Parameters
``
idDocument: The id of the target document.
``

## Remove deletion permission

```shell
curl -X DELETE \
  http://api.dialogram.fr:8085/api/document/:idDocument/daccess \
  -H 'Authorization: Bearer <user token>' \
  -H 'Content-Type: application/json' \
  -d '{
	"user": [
		"userId1",
        "userId2"
		]
    }'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8085/api/document/:idDocument/daccess",
  "method": "DELETE",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <user_token>",
  },
  "processData": false,
  "data": "{\n\t\"user\": [\n\t\t\"userId\"\n\t\t]\n}"
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

This endpoint add the permission to a user or a list of user to remove the deletion permission of other user(s) toward the data of a specified document.

#### HTTP Request

`DELETE http://api.dialogram.fr:8080/api/document/:idDocument/daccess`

#### Query Parameters
``
idDocument: The id of the target document.
``