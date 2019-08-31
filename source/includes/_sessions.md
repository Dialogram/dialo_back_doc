# Session

## Create a session

```shell
curl -X POST \
   https://api.dialogram.fr/api/session \
   -H 'Content-Type: application/json' \
   -d '{
      "email" : "usermail@domain.com",
      "password" : "password1234",
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/session",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{\n\t\"nickName\" : \"NewUser\",\n\t\"email\" : \"usermail@domain.com\",\n\t\"password\" : \"JeSuisUnTest\",\n}"
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
            "type": "session",
            "id": "Your Session ID",
            "token": "Your User token",
            "deviceName": "Unknown",
        }
    ],
    "includes": []
}
```

This endpoint create a session linked to the specified user ID.

#### HTTP Request

`POST https://api.dialogram.fr/api/session`

#### Query Parameters

``
   {
      "email" : "usermail@domain.com",
      "password" : "password1234"
   }
``

<aside class="success">
Note that you need to create a user before being able to create its session.
</aside>


## Create Backoffice session

```shell
curl -X POST \
   https://api.dialogram.fr/api/session \
   -H 'Content-Type: application/json' \
   -d '{
      "email" : "usermail@domain.com",
      "password" : "password1234",
}'
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.dialogram.fr/api/session",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
  },
  "processData": false,
   "data": "{\n\t\"nickName\" : \"NewUser\",\n\t\"email\" : \"usermail@domain.com\",\n\t\"password\" : \"JeSuisUnTest\",\n}"
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
            "type": "session",
            "id": "Your Session ID",
            "token": "Your User token",
            "deviceName": "Unknown",
        }
    ],
    "includes": []
}
```

This endpoint create a session linked to the specified user ID.

#### HTTP Request

`POST https://api.dialogram.fr/api/session`

#### Query Parameters

``
   {
      "email" : "usermail@domain.com",
      "password" : "password1234"
   }
``

<aside class="success">
Note that you need to create a user with admin role before being able to create its session.
</aside>
