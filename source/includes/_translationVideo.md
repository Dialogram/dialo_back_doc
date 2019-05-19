# Translation Videos

## Upload A Translation Video

```shell
curl -X POST \
  http://api.dialogram.fr/api/translationVideo \
  --header 'Authorization: Bearer <your_access_token>' \
  --header 'Content-Type: application/json' \
  --header 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
  --header 'cache-control: no-cache' \
  --form 'video=@/path/to/my/video.mp4' \
  --form 'title=Title of the Video' \
  --form 'description=Description of the video' \
  --form public=true
```

```javascript
var form = new FormData();
form.append("video", "/path/of/my/video.mp4");
form.append("title", "Title of the Video");
form.append("description", "Description of the video");
form.append("public", "true");

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/translationVideo",
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
            "type": "translation_videos",
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the translation video",
            "description": "Description of the translation video",
            "public": true,
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

This endpoint upload a video translation for the document or video to be translated.

#### HTTP Request

`POST http://api.dialogram.fr/api/translationVideo`

#### Query Parameters

Key naming | Content
---------- | -------
file (type: file) | Your video file
title (type: string) | Your video title
description (type: string) | Your video description
public (type: boolean) | Your video privacy


## Get Translation Video

```shell
curl -X GET \
  http://api.dialogram.fr/api/translationVideo/:idApiVideo \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Postman-Token: f2472e62-d64f-496e-8190-a115225d1e94' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/translationVideo/:idApiVideo",
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
            "type": "translation_videos",
            "id": "<video_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the translation video",
            "description": "Description of the translation video",
            "public": true,
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

This endpoint get the translation video by ID.

#### HTTP Request

`GET http://api.dialogram.fr/api/translationVideo/:idApiVideo`

#### Query Parameters

NONE

## Get User Translation Videos

```shell
curl -X GET \
  http://api.dialogram.fr/api/user/videos \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/user/videos",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "12d3b36d-52b0-4831-929c-5651e628b753"
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
            "type": "translation_videos",
            "id": "<translation_videos_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the first video",
            "description": "Description of the first video",
            "public": true,
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
            "type": "translation_videos",
            "id": "<translation_videos_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Title of the second video",
            "description": "Description of the second video",
            "public": true,
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

This endpoint get all the user translation videos.

#### HTTP Request

`GET http://api.dialogram.fr/api/user/translationVideos`

#### Query Parameters

NONE


## Update Translation Video

```shell
curl -X PUT \
  http://api.dialogram.fr/api/translationVideo/:idApiVideo \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 5927c68a-c72f-4da5-a1ca-49de4aa6d072' \
  -H 'cache-control: no-cache' \
  -d '{
	"title" : "Chicago records talkshow",
	"description" : "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
	"public" : true
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/translationVideo/:idApiVideo",
  "method": "PUT",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer <your_access_token>",
    "cache-control": "no-cache",
    "Postman-Token": "ed9cdbcf-4320-4f60-9a61-e3ca316e941f"
  },
  "processData": false,
  "data": "{\n\t\"title\" : \"Chicago records talkshow\",\n\t\"description\" : \"Marshall Jefferson, the creator of House music tell the story of the sound of chicago\",\n\t\"public\" : true\n}"
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
            "type": "translation_videos",
            "id": "<translation_videos_id>",
            "idOwner": "<owner_id>",
            "idApiVideo": "<video_api_id>",
            "title": "Chicago records talkshow",
            "description": "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
            "public": true,
            "publishedAt": "2019-05-19T14:57:28+02:00",
            "tags": [],
            "metadata": [],
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

This endpoint update the translation video data specified by ID.

#### HTTP Request

`PUT http://api.dialogram.fr/api/video/:idApiVideo`

#### Query Parameters
``
{
	"title" : "Chicago records talkshow",
	"description" : "Marshall Jefferson, the creator of House music tell the story of the sound of chicago",
	"public" : true
}
``

## Delete Video by ID

```shell
curl -X DELETE \
  http://api.dialogram.fr/api/video/:idApiVideo \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/video/:idApiVideo",
  "method": "DELETE",
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
    "data": [],
    "includes": []
}
```

This endpoint delete a translation video by ID.

#### HTTP Request

`DELETE http://api.dialogram.fr/api/translationVideo/:idApiVideo`

#### Query Parameters

NONE
