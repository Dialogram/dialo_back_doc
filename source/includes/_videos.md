# Videos

## Upload A Video

```shell
curl -X POST \
  https://api.dialogram.fr/api/video \
  --header 'Authorization: Bearer <your_access_token>' \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
  --header 'cache-control: no-cache' \
  --form 'video=@/path/to/my/video.mp4' \
  --form 'title=Title of the Video' \
  --form 'description=Description of the video' \
  --form 'category=entertainment' \
  --form public=true
```

```javascript
var form = new FormData();
form.append("video", "/path/of/my/video.mp4");
form.append("title", "Title of the Video");
form.append("description", "Description of the video");
form.append("category", "entertainment");
form.append("public", "true");

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/video",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "fefdbc25-584f-4af8-b06a-a9e60e766514"
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
            "type": "videos",
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the video",
            "description": "Description of the video",
            "public": true,
            "category": "entertainment",
            "publishedAt": "2019-05-19T13:57:28+02:00",
            "tags": [],
            "metadata": [],
            "source": {
                "type": "upload",
                "uri": "/videos/<url>/source"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/<url>\" width=\"100%\" height=\"100%\" frameborder=\"0\" scrolling=\"no\" allowfullscreen=\"\"></iframe>",
                "player": "https://embed.api.video/vod/<url>",
                "hls": "https://cdn.api.video/vod/<url>/hls/manifest.m3u8",
                "thumbnail": "https://cdn.api.video/vod/<url>/thumbnail.jpg"
            },
            "timestamp": 1558267041
        }
    ],
    "includes": []
}
```

This endpoint upload a video.

#### HTTP Request

`POST https://api.dialogram.fr/api/video`

#### Query Parameters

Key naming | Content
---------- | -------
file (type: file) | Your video file
title (type: string) | Your video title
description (type: string) | Your video description
public (type: boolean) | Your video privacy
category (type: string) | Your video category (health, finance, administrative entertainment, business)

## Get Video

```shell
curl -X GET \
  https://api.dialogram.fr/api/video/:idVideo \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/video/:idVideo",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
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
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the video",
            "description": "Description of the video",
            "public": true,
            "category": "entertainment",
            "publishedAt": "2019-05-19T13:57:28+02:00",
            "tags": [],
            "metadata": [],
            "source": {
                "type": "upload",
                "uri": "/videos/<url>/source"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/<url>\" width=\"100%\" height=\"100%\" frameborder=\"0\" scrolling=\"no\" allowfullscreen=\"\"></iframe>",
                "player": "https://embed.api.video/vod/<url>",
                "hls": "https://cdn.api.video/vod/<url>/hls/manifest.m3u8",
                "thumbnail": "https://cdn.api.video/vod/<url>/thumbnail.jpg"
            },
            "timestamp": 1558267041
        }
    ],
    "includes": []
}
```

This endpoint get the video by ID.

#### HTTP Request

`GET https://api.dialogram.fr/api/video/:idVideo`

#### Query Parameters

NONE

## Get User Videos

```shell
curl -X GET \
  https://api.dialogram.fr/api/user/video \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/user/video",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache"
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
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the first video",
            "description": "Description of the first video",
            "public": true,
            "category": "entertainment",
            "publishedAt": "2019-05-19T13:57:28+02:00",
            "tags": [],
            "metadata": [],
            "source": {
                "type": "upload",
                "uri": "/videos/<url>/source"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/<url>\" width=\"100%\" height=\"100%\" frameborder=\"0\" scrolling=\"no\" allowfullscreen=\"\"></iframe>",
                "player": "https://embed.api.video/vod/<url>",
                "hls": "https://cdn.api.video/vod/<url>/hls/manifest.m3u8",
                "thumbnail": "https://cdn.api.video/vod/<url>/thumbnail.jpg"
            },
            "timestamp": 1558267041
        },
        {
            "type": "videos",
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the second video",
            "description": "Description of the second video",
            "public": true,
            "category": "entertainment",
            "publishedAt": "2019-05-19T14:57:28+02:00",
            "tags": [],
            "metadata": [],
            "source": {
                "type": "upload",
                "uri": "/videos/<url>/source"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/<url>\" width=\"100%\" height=\"100%\" frameborder=\"0\" scrolling=\"no\" allowfullscreen=\"\"></iframe>",
                "player": "https://embed.api.video/vod/<url>",
                "hls": "https://cdn.api.video/vod/<url>/hls/manifest.m3u8",
                "thumbnail": "https://cdn.api.video/vod/<url>/thumbnail.jpg"
            },
            "timestamp": 1558267041
        }
    ],
    "includes": []
}
```

This endpoint get all the user videos.

#### HTTP Request

`GET https://api.dialogram.fr/api/user/video`

#### Query Parameters

NONE


## Update Video

```shell
curl -X PUT \
  https://api.dialogram.fr/api/video/:idVideo \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 5927c68a-c72f-4da5-a1ca-49de4aa6d072' \
  -H 'cache-control: no-cache' \
  -d '{
	"title" : "Chicago records talkshow",
	"description" : "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
	"public" : true,
  "category": "entertainment"
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/video/:idVideo",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "ed9cdbcf-4320-4f60-9a61-e3ca316e941f"
  },
  "processData": false,
  "data": "{\n\t\"title\" : \"Chicago records talkshow\",\n\t\"description\" : \"Marshall Jefferson, the creator of House music tell the story of the sound of chicago\",\n\t\"public\" : true,\n\t\"category\" : \"entertainment\"\n}"
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
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Chicago records talkshow",
            "description": "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
            "public": true,
            "category": "entertainment",
            "publishedAt": "2019-05-19T13:57:28+02:00",
            "tags": [],
            "metadata": [],
            "source": {
                "type": "upload",
                "uri": "/videos/<url>/source"
            },
            "assets": {
                "iframe": "<iframe src=\"https://embed.api.video/vod/<url>\" width=\"100%\" height=\"100%\" frameborder=\"0\" scrolling=\"no\" allowfullscreen=\"\"></iframe>",
                "player": "https://embed.api.video/vod/<url>",
                "hls": "https://cdn.api.video/vod/<url>/hls/manifest.m3u8",
                "thumbnail": "https://cdn.api.video/vod/<url>/thumbnail.jpg"
            },
            "timestamp": 1558267041
        }
    ],
    "includes": []
}
```


This endpoint update the video data specified by ID.

#### HTTP Request

`PUT https://api.dialogram.fr/api/video/:idVideo`

#### Query Parameters
``
{
	"title" : "Chicago records talkshow",
	"description" : "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
	"public" : true,
  "category" : "entertainment",
	"tags" : ["chicago", "jack youor body", "records"],
	"metadata" : ["uno", "dos", "tres"]
}
``

## Delete Video by ID

```shell
curl -X DELETE \
  https://api.dialogram.fr/api/video/:idVideo \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: f2472e62-d64f-496e-8190-a115225d1e94' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/video/:idVideo",
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

This endpoint delete a video by ID.

#### HTTP Request

`DELETE https://api.dialogram.fr/api/video/:idVideo`

#### Query Parameters

NONE
