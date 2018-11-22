---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Ulotky API! You can use our API to access Ulotky API endpoints, which can get information on Klienci, lokacje, rezerwacje in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

## Get Access token

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
	"access_token": "abc"
    "token_type": "bearer",
    "expires_in": 14399,
    "userName": "e1@e1.e1",
    ".issued": "Thu, 22 Nov 2018 10:32:50 GMT",
    ".expires":"Thu, 22 Nov 2018 14:32:50 GMT"
  }
]
```

This endpoint retrieves access token for user.

### HTTP Request

`POST http://ulotkyyy.gear.host/token`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
grant_type | - | password.
username | - | e1%40e1.e1.
password | - | Qq1;qq.

<aside class="success">
Remember — content-type: application/x-www-form-urlencoded
</aside>

# Klienci

## Get Klient info

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "Email":"e1@e1.e1",
  "HasRegistered":true,
  "LoginProvider":null
}
```

This endpoint retrieves Klient info based on authorization.

<aside class="warning">authorization: bearer abc....</aside>

### HTTP Request

`GET http://ulotkyyy.gear.host/api/Account/UserInfo`

### URL Parameters

Parameter | Description
--------- | -----------

## Delete a Specific Klient

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

# Lokacje

## Get all Lokacje

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "Id":4,
  "Latitude":123.123,
  "Longitude":456.46778
},
{
  "Id":5,
  "Latitude":13.13,
  "Longitude":56.4678
}
```

This endpoint retrieves all Lokacje.

### HTTP Request

`GET http://ulotkyyy.gear.host/api/lokacja`

### URL Parameters

Parameter | Description
--------- | -----------

## Get all Lokacje pomiedzy x1,y1 - x2,y2

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "Id":4,
  "Latitude":123.123,
  "Longitude":456.46778
},
{
  "Id":5,
  "Latitude":13.13,
  "Longitude":56.4678
}
```

This endpoint retrieves Lokacje pomiedzy x1,y1 - x2,y2.

<aside class="warning">authorization: bearer abc....</aside>

### HTTP Request

`GET http://ulotkyyy.gear.host/api/lokacja`

### URL Parameters

Parameter | Description
--------- | -----------
lat1 | 1.0
lng1 | 1.0
lat2 | 100.0
lng2 | 100.0
