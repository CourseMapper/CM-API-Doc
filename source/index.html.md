---
title: CourseMapper API Reference

language_tabs:
  - shell
  - javascript

toc_footers: 
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the CourseMapper API! You can use our API to access CourseMapper API endpoints, which can let you use many functions available in CourseMapper.

We have language bindings in Javascript. You can view code examples in the dark area to the right.

This API documentation page was created with [Slate](https://github.com/tripit/slate).  

# Authentication
 
CourseMapper uses standard OAuth2 to allow access to the API. You can register a new application to obtain the clientId and clientSecret [here](http://coursemapper/settings/apps).

## 1. Authorization.

Your mobile or web application should provide a button that opens a popup box or a webview to visit this URL:

`https://coursemapper/api/oauth2/authorize?client_id=<client_id>&response_type=code`

### URL Parameters

Parameter | Description
--------- | -----------
client_id | The Client ID 
response_type | "code" (the only supported)

Once users are logged in, they will be redirected to the URL provided in `redirect_uri` that the application provides, or if this field was set to be empty, then it will be redirected to an empty page 

`https://coursemapper/api/oauth2/app?code=<temporary_token>` 

### Response URL Parameters

Parameter | Description
--------- | -----------
code | Contains the temporary token

that contains the temporary token. 

## 2. Obtain Temporary Token when user is authenticated.
Your application will have to parse this URL above and grab the `temporary_token` for the next step.

## 3. Exchange for Access Token
Once the application has obtained a temporary token, now it has to exchange it for an access token. To do that, the application needs to send a request to:

POST `http or https://coursemapper/api/oauth2/token`

### POST Parameters

Parameter | Description
--------- | -----------
code | Temporary Token 
grant_type| "authorization_code" (the only supported)


### Response 
```json
{
  "result": true,
  "access_token": {
    "accessToken": "random-string",
    "userId": "mongo-objectId",
    "email": "email@email.com"
  }
}
```
The result from the exchange contains this json:

Parameter | Description
--------- | -----------
result | boolean 
access_token | object
access_token.accessToken | random string
access_token.userId | mongo object id
access_token.email | email
 

## Finally
CourseMapper expects for the access token to be included in all API requests to the server in a header that looks like the following:

`Bearer <accessToken>`

`Bearer 2ksjow2039z=_18jaszxvnKLJlsfHUHfsjklmvoiay9146fah`

# Categories

## Get All Categories
  
```shell
curl "https://coursemapper/api/categories"
  -H "Authorization: Bearer <accessToken>"

e.g.:
curl "https://coursemapper/api/categories"
  -H "Authorization: Bearer 2ksjow2039z=_18jaszxvnKLJlsfHUHfsjklmvoiay9146fah"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all Categories.

### HTTP Request

`GET /api/categories`
   
 
