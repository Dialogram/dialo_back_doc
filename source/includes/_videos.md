# Videos

## Upload A Video

```shell
curl -X POST \
  http://api.dialogram.fr:8080/api/document/5c26a80ece633f35dce3b790/video \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
  -H 'cache-control: no-cache' \
  -d '{
	"idOwner" : "dzedaozeidjadaze",
	"title" : "Detroit records talkshow",
	"description" : "Mike Banks, the creator of Underground Resistance tell the story of the sound of detroit",
	"public" : true,
	"publishedAt" : "2018-02-02",
	"tags" : ["detroit", "ur", "records"],
	"metadata" : ["one", "two", "three"],
	"source": {
			"type" : "upload",
			"uri" : "/videos/v2398v320EUioezj21"
	},
	"assets": {
			"iframe" : "<iframe src=\"https://embed.api.video/vod/dzio19328912ide\">",
			"player" : "https://embed.api.video/vod/vi23uize3892",
			"hls": "https://cdn.api.video/vod/ieozdjzi093209",
			"thumbnail" : "https://cdn.api.video/vod/v239832923"
	}
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/5c26a80ece633f35dce3b790/video",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "0daefc40-fbce-4f9a-8af8-a1e4d3d89053"
  },
  "processData": false,
  "data": "{\n\t\"idOwner\" : \"dzedaozeidjadaze\",\n\t\"title\" : \"Detroit records talkshow\",\n\t\"description\" : \"Mike Banks, the creator of Underground Resistance tell the story of the sound of detroit\",\n\t\"public\" : true,\n\t\"publishedAt\" : \"2018-02-02\",\n\t\"tags\" : [\"detroit\", \"ur\", \"records\"],\n\t\"metadata\" : [\"one\", \"two\", \"three\"],\n\t\"source\": {\n\t\t\t\"type\" : \"upload\",\n\t\t\t\"uri\" : \"/videos/v2398v320EUioezj21\"\n\t},\n\t\"assets\": {\n\t\t\t\"iframe\" : \"<iframe src=\\\"https://embed.api.video/vod/dzio19328912ide\\\">\",\n\t\t\t\"player\" : \"https://embed.api.video/vod/vi23uize3892\",\n\t\t\t\"hls\": \"https://cdn.api.video/vod/ieozdjzi093209\",\n\t\t\t\"thumbnail\" : \"https://cdn.api.video/vod/v239832923\"\n\t}\n}"
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
            "type": "videos",
            "id": "5c26a818ce633f35dce3b793",
            "idOwner": "dzedaozeidjadaze",
            "title": "Detroit records talkshow",
            "description": "Mike Banks, the creator of Underground Resistance tell the story of the sound of detroit",
            "public": true,
            "publishedAt": "2018-02-02",
            "tags": [
                "detroit",
                "ur",
                "records"
            ],
            "metadata": [
                "one",
                "two",
                "three"
            ],
            "source": {
                "type": "upload",
                "uri": "/videos/v2398v320EUioezj21"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/dzio19328912ide\">",
                "player": "https://embed.api.video/vod/vi23uize3892",
                "hls": "https://cdn.api.video/vod/ieozdjzi093209",
                "thumbnail": "https://cdn.api.video/vod/v239832923"
            }
        }
    ],
    "includes": []
}
```

This endpoint upload a video for the document to be translated.

#### HTTP Request

`POST http://api.dialogram.fr:8080/api/document/:idDocument/video`

#### Query Parameters
``
{
	"idOwner" : "dzedaozeidjadaze",
	"title" : "Detroit records talkshow",
	"description" : "Mike Banks, the creator of Underground Resistance tell the story of the sound of detroit",
	"public" : true,
	"publishedAt" : "2018-02-02",
	"tags" : ["detroit", "ur", "records"],
	"metadata" : ["one", "two", "three"],
	"source": {
			"type" : "upload",
			"uri" : "/videos/v2398v320EUioezj21"
	},
	"assets": {
			"iframe" : "<iframe src=\"https://embed.api.video/vod/dzio19328912ide\">",
			"player" : "https://embed.api.video/vod/vi23uize3892",
			"hls": "https://cdn.api.video/vod/ieozdjzi093209",
			"thumbnail" : "https://cdn.api.video/vod/v239832923"
	}
}
``

## Get Video

```shell
curl -X GET \
  http://api.dialogram.fr:8080/api/document//video/ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: f2472e62-d64f-496e-8190-a115225d1e94' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document//video/",
  "method": "GET",
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
    "data": [
        {
            "type": "videos",
            "id": "5c26a818ce633f35dce3b793",
            "idOwner": "dzedaozeidjadaze",
            "title": "Detroit records talkshow",
            "description": "Mike Banks, the creator of Underground Resistance tell the story of the sound of detroit",
            "public": true,
            "publishedAt": "2018-02-02",
            "tags": [
                "detroit",
                "ur",
                "records"
            ],
            "metadata": [
                "one",
                "two",
                "three"
            ],
            "source": {
                "type": "upload",
                "uri": "/videos/v2398v320EUioezj21"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/dzio19328912ide\">",
                "player": "https://embed.api.video/vod/vi23uize3892",
                "hls": "https://cdn.api.video/vod/ieozdjzi093209",
                "thumbnail": "https://cdn.api.video/vod/v239832923"
            }
        }
    ],
    "includes": []
}
```

This endpoint get the video by ID.

#### HTTP Request

`GET http://api.dialogram.fr:8080/api/document/:idDocument/video`

#### Query Parameters

NONE

## Update Video

```shell
curl -X PUT \
  http://api.dialogram.fr:8080/api/document//video/ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 5927c68a-c72f-4da5-a1ca-49de4aa6d072' \
  -H 'cache-control: no-cache' \
  -d '{
	"title" : "Chicago records talkshow",
	"description" : "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
	"public" : true,
	"tags" : ["chicago", "jack youor body", "records"],
	"metadata" : ["uno", "dos", "tres"]
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document//video/",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "ed9cdbcf-4320-4f60-9a61-e3ca316e941f"
  },
  "processData": false,
  "data": "{\n\t\"title\" : \"Chicago records talkshow\",\n\t\"description\" : \"Marshall Jefferson, the creator of House music tell the story of the sound of chicago\",\n\t\"public\" : true,\n\t\"tags\" : [\"chicago\", \"jack youor body\", \"records\"],\n\t\"metadata\" : [\"uno\", \"dos\", \"tres\"]\n}"
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
            "type": "videos",
            "id": "5c26a0f7ec67c433405a506e",
            "idOwner": "dzedaozeidjadaze",
            "title": "Chicago records talkshow",
            "description": "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
            "public": true,
            "publishedAt": "2018-02-02",
            "tags": [
                "chicago",
                "jack youor body",
                "records"
            ],
            "metadata": [
                "uno",
                "dos",
                "tres"
            ],
            "source": {
                "type": "upload",
                "uri": "/videos/v2398v320EUioezj21"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/dzio19328912ide\">",
                "player": "https://embed.api.video/vod/vi23uize3892",
                "hls": "https://cdn.api.video/vod/ieozdjzi093209",
                "thumbnail": "https://cdn.api.video/vod/v239832923"
            }
        }
    ],
    "includes": []
}
```

This endpoint update the video data of the document both specified by ID.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/document/:idDocument/video/:idVideo`

#### Query Parameters
``
{
	"title" : "Chicago records talkshow",
	"description" : "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
	"public" : true,
	"tags" : ["chicago", "jack youor body", "records"],
	"metadata" : ["uno", "dos", "tres"]
}
``
