# USER API SPEC

## Register User

Endpoint: POST /api/users

Request Body :

```json
{
  "username": "nasa",
  "password": "nasapass",
  "name": "nasa"
}
```

Response Body(Success) :

```json
{
  "data": {
    "username": "nasa",
    "name": "nasa"
  }
}
```

Response Body(Failed) :

```json
{
  "errors": "Username must not blank, ..."
}
```

## Login User

Endpoint: POST /api/users/login

Request Body :

```json
{
  "username": "nasa",
  "password": "nasapass"
}
```

Response Body(Success) :

```json
{
  "data": {
    "username": "nasa",
    "name": "nasa",
    "token": "token123456"
  }
}
```

Response Body(Failed) :

```json
{
  "errors": "Username or Password wrong, ..."
}
```

## Get User

Endpoint: GET /api/users/current

Request Header :

- X-API-TOKEN : token

Response Body(Success) :

```json
{
  "data": {
    "username": "nasa",
    "name": "nasa"
  }
}
```

Response Body(Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```

## Update User

Endpoint: PATCH /api/users/current

Request Header :

- X-API-TOKEN : token

Request Body :

```json
{
  "password": "nasapass",
  "name": "nasa"
}
```

Response Body(Success) :

```json
{
  "data": {
    "username": "nasa",
    "name": "nasa"
  }
}
```

Response Body(Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```

## Logout User

Endpoint: DELETE /api/users/current

Request Header :

- X-API-TOKEN : token

Request Body :

```json
{
  "data": "OK"
}
```

Response Body(Failed) :

```json
{
  "errors": "Unauthorized, ..."
}
```
