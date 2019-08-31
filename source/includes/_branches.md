# Branches

## Create Branche

```shell
curl -X POST \
  https://api.dialogram.fr/api/document/:idDocument/branche \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "BrancheName"
}
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/translation",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
  },
  "processData": false,
  "data": "{\n    \"name\": \"BrancheName\"\n}"
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
            "type": "branches",
            "id": "5d6a3c6b802353124060b0cb",
            "name": "BrancheName",
            "idDocument": "5d6a3c5f802353124060b0c2",
            "translation": [],
            "commits": [],
            "version": 1,
            "master": false,
            "merged": false,
            "timestamp": 1567243307,
            "certificated": false,
            "likes": null
        }
    ],
    "includes": []
}
```

This endpoint create a new branche for translating a document.

#### HTTP Request

`POST https://api.dialogram.fr/api/document/:idDocument/branche`

#### Query Parameters
``
{
    "name": "BrancheName"
}
``

<aside class="success">
Remember — a happy user is an authenticated user by token!
</aside>

## Get Branche

```shell
curl -X GET \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache'
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
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
            "type": "branches",
            "id": "5d6a3c6b802353124060b0cb",
            "name": "BrancheName",
            "idDocument": "5d6a3c5f802353124060b0c2",
            "translation": [],
            "commits": [],
            "version": 1,
            "master": false,
            "merged": false,
            "timestamp": 1567243307,
            "certificated": false,
            "likes": null
        }
    ],
    "includes": []
}
```

This endpoint get a branche by ID.

#### HTTP Request

`GET https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche`

## Get Master Branche

```shell
curl -X GET \
  https://api.dialogram.fr/api/document/:idDocument/branche \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache'
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
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
            "type": "branches",
            "id": "4e6a3a6b812353124060b0tg",
            "name": "master",
            "idDocument": "5d6a3c5f802353124060b0c2",
            "translation": [],
            "commits": [],
            "version": 1,
            "master": true,
            "merged": false,
            "timestamp": 1567243307,
            "certificated": false,
            "likes": null
        }
    ],
    "includes": []
}
```

This endpoint get the master branche by document ID.

#### HTTP Request

`GET https://api.dialogram.fr/api/document/:idDocument/branche`


## Create a Commit

```shell
curl -X POST \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache' \
  -d '{
	"message": "Modification du titre",
	"description": "Erreur de video sur le titre principale",
    "translation": [
        [
            {
                "x": "999",
                "y": "999",
                "width": "555",
                "height": "555",
                "idVideo": "5d6963472316d60ab03c7e2e"
            },
            {
                "x": "111",
                "y": "111",
                "width": "666",
                "height": "666",
                "idVideo": "5d6963472316d60ab03c7e2e"
            }
        ]
    ]
}
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
  },
  "processData": false,
  "data": "{\n\t\"message\": \"Modification du titre\",\n\t\"description\": \"Erreur de video sur le titre principale\",\n    \"translation\": [\n        [\n            {\n                \"x\": \"999\",\n                \"y\": \"999\",\n                \"width\": \"555\",\n                \"height\": \"555\",\n                \"idVideo\": \"5d6963472316d60ab03c7e2e\"\n            },\n            {\n                \"x\": \"111\",\n                \"y\": \"111\",\n                \"width\": \"666\",\n                \"height\": \"666\",\n                \"idVideo\": \"5d6963472316d60ab03c7e2e\"\n            }\n        ]\n    ]\n}"
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
            "type": "commits",
            "id": "5d6a42ca802353124060b0d8",
            "idBranche": "5d6a3c6b802353124060b0cb",
            "message": "Modification du titre",
            "description": "Erreur de video sur le titre principale",
            "commitedTranslation": [],
            "savedTranslation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    }
                ]
            ]
        }
    ],
    "includes": []
}
```

This endpoint create a commit on the given branche. 

#### HTTP Request

`POST https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit`

#### Query Parameters
``
{
	"message": "Modification du titre",
	"description": "Erreur de video sur le titre principale",
    "savedTranslation": [
        [
            {
                "x": "999",
                "y": "999",
                "width": "555",
                "height": "555",
                "idVideo": "5d6963472316d60ab03c7e2e"
            },
            {
                "x": "111",
                "y": "111",
                "width": "666",
                "height": "666",
                "idVideo": "5d6963472316d60ab03c7e2e"
            }
        ]
    ]
}
``

## Get a Commit

```shell
curl -X GET \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
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
            "type": "commits",
            "id": "5d6a42ca802353124060b0d8",
            "idBranche": "5d6a3c6b802353124060b0cb",
            "message": "Modification du titre",
            "description": "Erreur de video sur le titre principale",
            "commitedTranslation": [],
            "savedTranslation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    }
                ]
            ]
        }
    ],
    "includes": []
}
```

This endpoint create a commit on the given branche. 

#### HTTP Request

`GET https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit`

## Commit a commit

```shell
curl -X PUT \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit/commit \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache'
}
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit/commit",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
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
            "type": "commits",
            "id": "5d6a42ca802353124060b0d8",
            "idBranche": "5d6a3c6b802353124060b0cb",
            "message": "Modification du titre",
            "description": "Erreur de video sur le titre principale",
            "commitedTranslation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    }
                ]
            ],
            "savedTranslation": []
        }
    ],
    "includes": []
}
```

This endpoint commit a commit on the given branche. 

#### HTTP Request

`PUT https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit`

## Save a translation

```shell
curl -X PUT \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache' \
  -d '{
    "translation": [
        [
            {
                "x": "999",
                "y": "999",
                "width": "555",
                "height": "555",
                "idVideo": "5d6963472316d60ab03c7e2e"
            },
            {
                "x": "111",
                "y": "111",
                "width": "666",
                "height": "666",
                "idVideo": "5d6963472316d60ab03c7e2e"
            }
        ]
    ]
}
'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
  },
  "processData": false,
  "data": "{\n    \"translation\": [\n        [\n            {\n                \"x\": \"999\",\n                \"y\": \"999\",\n                \"width\": \"555\",\n                \"height\": \"555\",\n                \"idVideo\": \"5d694fc1a880b03efce0156d\"\n            },\n            {\n                \"x\": \"111\",\n                \"y\": \"111\",\n                \"width\": \"666\",\n                \"height\": \"666\",\n                \"idVideo\": \"5d694fc1a880b03efce0156d\"\n            }\n        ],\n\t\t[\n            {\n                \"x\": \"999\",\n                \"y\": \"999\",\n                \"width\": \"555\",\n                \"height\": \"555\",\n                \"idVideo\": \"5d694fc1a880b03efce0156d\"\n            },\n            {\n                \"x\": \"111\",\n                \"y\": \"111\",\n                \"width\": \"666\",\n                \"height\": \"666\",\n                \"idVideo\": \"5d694fc1a880b03efce0156d\"\n            }\n        ]\n    ]\n}"
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
            "type": "commits",
            "id": "5d6a42ca802353124060b0d8",
            "idBranche": "5d6a3c6b802353124060b0cb",
            "message": "Modification du titre",
            "description": "Erreur de video sur le titre principale",
            "commitedTranslation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d694fc1a880b03efce0156d"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d694fc1a880b03efce0156d"
                    }
                ]
            ],
            "savedTranslation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d694fc1a880b03efce0156d"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d694fc1a880b03efce0156d"
                    }
                ],
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d694fc1a880b03efce0156d"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d694fc1a880b03efce0156d"
                    }
                ]
            ]
        }
    ],
    "includes": []
}
```

This endpoint save translation data inside the commit on the given branche. 

#### HTTP Request

`PUT https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit`

#### Query Parameters
``
{
	"translation": [
        [
            {
                "x": "999",
                "y": "999",
                "width": "555",
                "height": "555",
                "idVideo": "5d6963472316d60ab03c7e2e"
            },
            {
                "x": "111",
                "y": "111",
                "width": "666",
                "height": "666",
                "idVideo": "5d6963472316d60ab03c7e2e"
            }
        ]
    ]
}
``

## Push a Commit

```shell
curl -X PUT \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit/push \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: ebeff399-a623-42a5-a917-0dbbcf01c189' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit/push",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "dc9b3b70-4657-4d73-becd-8ab957e69e38"
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
            "type": "branches",
            "id": "5d6a3c6b802353124060b0cb",
            "name": "BrancheName",
            "idDocument": "5d6a3c5f802353124060b0c2",
            "translation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    }
                ]
            ],
            "commits": [
                "5d6a42ca802353124060b0d8"
            ],
            "version": 1,
            "master": false,
            "merged": false,
            "timestamp": 1567243307,
            "certificated": false,
            "likes": null
        }
    ],
    "includes": []
}
```

This endpoint push a commit on the given branche. 

#### HTTP Request

`PUT https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/commit/:idCommit/push`


## Merge a branche

```shell
curl -X GET \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/merge \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 18c389d0-37ca-4762-8ea1-e0d61489c0b6' \
  -H 'cache-control: no-cache' \
  -d '{
	"delete": false
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/merge",
  "method": "GET",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "6b36c235-3178-44bd-a6f0-2b4e54d1525f"
  },
  "processData": false,
  "data": "{\n\t\"delete\": false\n}"
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
            "type": "branches",
            "id": "5d6a3c5f802353124060b0c4",
            "name": "master",
            "idDocument": "5d6a3c5f802353124060b0c2",
            "idOwner": "5d6966c97cb05a34982652e7",
            "translation": [
                [
                    {
                        "x": "999",
                        "y": "999",
                        "width": "555",
                        "height": "555",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    },
                    {
                        "x": "111",
                        "y": "111",
                        "width": "666",
                        "height": "666",
                        "idVideo": "5d6963472316d60ab03c7e2e"
                    }
                ]
            ],
            "commits": [
                "5d6a42ca802353124060b0d8"
            ],
            "version": 1.1,
            "master": true,
            "merged": false,
            "timestamp": 1567246676268,
            "certificated": false,
            "likes": null
        }
    ],
    "includes": []
}
```

This endpoint get the translation area of the document. 

#### HTTP Request

`GET https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche/merge`

#### Query Parameters

Key naming | Content
---------- | -------
delete (type: boolean) | Delete your branche after merge

## Delete a Branche

```shell
curl -X DELETE \
  https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: abcdff79-f8a5-4130-a870-426d100b03fc' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche",
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

This endpoint delete a branche.

#### HTTP Request

`DELETE https://api.dialogram.fr/api/document/:idDocument/branche/:idBranche`
