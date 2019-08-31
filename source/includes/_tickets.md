# Tickets

## Create a ticket

```shell
curl -X POST \
  https://api.dialogram.fr/api/report \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
  -H 'cache-control: no-cache' \
  -d '{
	"title": "Bug on Video API",
	"category": "bug",
	"description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos."
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
  },
  "processData": false,
  "data": "{\n\t\"title\": \"Bug on Video API\",\n\t\"category\": \"bug\",\n\t\"description\": \"Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.\"\n}"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint authenticate you to the video API

#### HTTP Request

`POST https://api.dialogram.fr/api/report`

#### Query Parameters

``
{
	"title": "Bug on Video API",
	"category": "bug",
	"description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos."
}
``

## Get ticket by ID

```shell
curl -X GET \
  https://api.dialogram.fr/api/report/:idTicket \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report/:idTicket",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint get a ticket by ID.

#### HTTP Request

`GET https://api.dialogram.fr/api/report/:idTicket`

#### Query Parameters

NONE

## Get ticket by category

```shell
curl -X GET \
  https://api.dialogram.fr/api/report/category/:category \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report/category/:category",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint get a ticket by category.

#### HTTP Request

`GET https://api.dialogram.fr/api/report/category/:category`

#### Query Parameters

NONE

## Get ticket by status

```shell
curl -X GET \
  https://api.dialogram.fr/api/report/category/:category \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report/status/:status",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint get a ticket by status.

#### HTTP Request

`GET https://api.dialogram.fr/api/report/status/:status`

#### Query Parameters

NONE

## Close ticket

```shell
curl -X PUT \
  https://api.dialogram.fr/api/report/close/:idTicket \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report/close/:idTicket",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint close a ticket.

#### HTTP Request

`PUT https://api.dialogram.fr/api/report/close/:idTicket`

#### Query Parameters

NONE

## Get ticket by userID

```shell
curl -X GET \
  https://api.dialogram.fr/api/report/user/:userId \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report/user/:userId",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint get a ticket by userID.

#### HTTP Request

`GET https://api.dialogram.fr/api/report/user/:userId`

#### Query Parameters

userId

## Get user ticket

```shell
curl -X GET \
  https://api.dialogram.fr/api/report/user/ticket \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/report/user/ticket",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
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
            "type": "ticket",
            "id": "5ca0896bb325da56582fe795",
            "title": "Bug on Video API",
            "category": "bug",
            "status": false,
            "description": "Video API bug when you try to upload a video from this endpoit GET /api/video. Morever it doesnt return all the videos.",
            "idOwner": "5ca088496e26a4429471d1f3",
            "creationDate": "2019-03-31T09:33:31.566Z",
            "closedDate": null,
            "timestamp": 1554024781
        }
    ],
    "includes": []
}
```

This endpoint get all ticket belong to the user.

#### HTTP Request

`GET https://api.dialogram.fr/api/report/user/ticket`

#### Query Parameters

NONE