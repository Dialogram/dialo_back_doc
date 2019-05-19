# API Video

## API Video Auth

```shell
curl -X GET \
  http://api.dialogram.fr/api/apiVideo/auth \ \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 701b451b-a5a6-4ab0-b262-80413d7e5fd0' \
  -H 'cache-control: no-cache'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr/api/apiVideo/auth",
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
            "type": "videosApi",
            "accessToken": "<ACESS_TOKEN>",
            "expiresIn": 3600
        }
    ],
    "includes": []
}
```

This endpoint authenticate you to the video API

#### HTTP Request

`GET http://api.dialogram.fr/api/apiVideo/auth`

#### Query Parameters

NONE
