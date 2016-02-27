# Accounts 
  

## Get Account Based on Username
```shell
curl "https://coursemapper/api/account/<username>"
  -H "Authorization: Bearer <accessToken>"

e.g.:
curl "https://coursemapper/api/account/rpl"
  -H "Authorization: Bearer 2ksjow2039ze_18jaszxvnKLJlsfHUHfsjklmvoiay9146fah"
```
> The above command returns JSON structured like this:

```json
{
  "result": true,
  "user": {
    "_id": "5530bef8e5a9e0dd261059b8",
    "updatedAt": "2015-04-17T08:06:16.743Z",
    "username": "rpl",
    "email": "r@emailo.im",
    "dateAdded": "2015-08-17T14:44:04.167Z",
    "displayName": "akana abaca",
    "image": "//www.gravatar.com/avatar/57a6e733c1a82f02e5d95114e77217a4?s=200&r=pg&d=mm",
    "role": "admin"
  }
}
```
`GET /api/account/<username>`

This endpoint will only able to get the logged in username based on the obtained access token.

### Response
Key    | Value
-----  | -----
result | boolean
user  | User

 