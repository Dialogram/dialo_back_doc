# Permissions

## Promote/Switch user role

```shell
curl -X PUT \
  http://api.dialogram.fr:8080/api/document/<idDocument>/editAccess/<idUser>/<userRole> \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer <your_bearer_token>' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Host: api.dialogram.fr:8080' \
  -H 'accept-encoding: gzip, deflate' \
  -H 'cache-control: no-cache' \
  -H 'content-length: '
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/<idDocument>/editAccess/<idUser>/<userRole>",
  "method": "PUT",
  "headers": {
    "Authorization": "Bearer <your_bearer_token>",
    "Accept": "*/*",
    "Cache-Control": "no-cache",
    "Host": "api.dialogram.fr:8080",
    "accept-encoding": "gzip, deflate",
    "content-length": "",
    "Connection": "keep-alive",
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

This endpoint allow the owner/moderator of a document to give a new role to another one. Note that a user cannot be at moderator and collaborator at the same time.

For more informations about role, see the section below this sub-section.

#### HTTP Request

`PUT http://api.dialogram.fr:8080/api/document/:idDocument/editAccess/:idUser/:role`

#### Query Parameters

Key naming | Content
---------- | -------
idDocument | The id of the target document.
idUser | the user you want grant permission to.
role | the role you want to give to the target user.

## Deprive user role

```shell
curl -X DELETE \
  http://api.dialogram.fr:8080/api/document/<idDocument>/editAccess/<idUser>/<userRole> \
  -H 'Accept: */*' \
  -H 'Authorization: Bearer <your_bearer_token>' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Host: api.dialogram.fr:8080' \
  -H 'accept-encoding: gzip, deflate' \
  -H 'cache-control: no-cache' \
  -H 'content-length: '
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.dialogram.fr:8080/api/document/<idDocument>/editAccess/<idUser>/<userRole>",
  "method": "DELETE",
  "headers": {
    "Authorization": "Bearer <your_bearer_token>",
    "Accept": "*/*",
    "Cache-Control": "no-cache",
    "Host": "api.dialogram.fr:8080",
    "accept-encoding": "gzip, deflate",
    "content-length": "",
    "Connection": "keep-alive",
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

This endpoint allow the owner/moderator of a document to deprive a role to another user. Note that you cannot deprive a document owner of any rights.

For more informations about role, see the section below this sub-section.

#### HTTP Request

`DELETE http://api.dialogram.fr:8080/api/document/:idDocument/editAccess/:idUser/:role`

#### Query Parameters

Key naming | Content
---------- | -------
idDocument | The id of the target document.
idUser | the user you want grant permission to.
role | the role you want to give to the target user.

## Role definitions

Name | Meaning
---------- | -------
owner | The user that uploadead the document. Cannot loose this status and have all rights on his document.
moderator | This user have the rights of edition, deletion on the documents; he can also affect other user's role.
collaborator | Have edition/reading access on private document.