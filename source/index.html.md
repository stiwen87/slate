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

`POST http://ulotky.azurewebsites.net/token`

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

`GET http://ulotky.azurewebsites.net/api/Account/UserInfo`

### URL Parameters

Parameter | Description
--------- | -----------

# Lokacje

## Get all Lokacje

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

`GET http://ulotky.azurewebsites.net/api/lokacja`

### URL Parameters

Parameter | Description
--------- | -----------

## Get all Lokacje pomiedzy x1,y1 - x2,y2



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

`GET http://ulotky.azurewebsites.net/api/lokacja`

### URL Parameters

Parameter | Description
--------- | -----------
lat1 | 1.0
lng1 | 1.0
lat2 | 100.0
lng2 | 100.0

# Ulotki

## Get all Ulotki

> The above command returns JSON structured like this:

```json
{
  "Id":1,
  "Url":123.jpg
},
{
  "Id":2,
  "Url":456.jpg
}
```

This endpoint retrieves all Ulotki.

### HTTP Request

`GET http://ulotky.azurewebsites.net/api/ulotka`

### URL Parameters

Parameter | Description
--------- | -----------

## Get Ulotka url

> The above command returns JSON structured like this:

```json
"http://ulotky.azurewebsites.net/Ulotky/123.JPG"
```

This endpoint retrieves Ulotka url.

### HTTP Request

`GET http://ulotky.azurewebsites.net/api/ulotka/{id}`

### URL Parameters

Parameter | Description
id | 1

# Dashboard

## Get ilosc obejrzen w lokacjach

> The above command returns JSON structured like this:

```json
{
  "ilosc":21,
  "LokacjaId":14
},
{
  "ilosc":10,
  "LokacjaId":15
}
```

This endpoint retrieves ilosc obejrzen w lokacjach.

### HTTP Request

`GET http://ulotky.azurewebsites.net/api/dashboard/lokacje`

### URL Parameters

Parameter | Description
--------- | -----------

## Get ilosc obejrzen przez mezczyzn

> The above command returns JSON structured like this:

```json
{
  "1":0.625
}
```

This endpoint retrieves ilosc obejrzen przez mezczyzn.

### HTTP Request

`GET http://ulotky.azurewebsites.net/api/dashboard/men`

### URL Parameters

Parameter | Description
--------- | -----------

## Get ilosc obejrzen danej ulotki w kolejnych dniach

> The above command returns JSON structured like this:

```json
{
  "Data":"2018-12-23T00:00:00",
  "ilosc":"20"
},
{
  "Data":"2018-12-24T00:00:00",
  "ilosc":"15"
}
```

This endpoint retrieves ilosc obejrzen danej ulotki w kolejnych dniach.

### HTTP Request

`GET http://ulotky.azurewebsites.net/api/dashboard/dni/{id}`

### URL Parameters

Parameter | Description
id | 1

## Get ilosc obejrzen w kampaniach autoryzowanego usera

> The above command returns JSON structured like this:

```json
{
  "id":1,
  "total":71,
  "zostalo":39
},
{
  "id":2,
  "total":1000,
  "zostalo":1000
}
```

This endpoint retrieves ilosc obejrzen w kampaniach autoryzowanego usera.

### HTTP Request

`GET http://ulotky.azurewebsites.net/api/dashboard/kampanie`

### URL Parameters

Parameter | Description
--------- | -----------

# Rezerwacja lokacji (kampania)

## Get kampanie autoryzowanego usera

## Post nowa kampanie

# Sklep

## Get itemy w sklepie

## Post kup item w sklepie
