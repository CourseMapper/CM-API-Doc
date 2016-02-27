# Discussions 
  

## Get Links Based on Node Id
```shell
curl "https://coursemapper/api/links/<nodeId>"
  -H "Authorization: Bearer <accessToken>"

e.g.:
curl "https://coursemapper/api/links/56b0efc1309953f719610aaa"
  -H "Authorization: Bearer 2ksjow2039ze_18jaszxvnKLJlsfHUHfsjklmvoiay9146fah"
```
> The above command returns JSON structured like this:

```json
{
  "result": true,
  "posts": [
    {
      "_id": "56b1fe60a526d27803559a19",
      "dateAdded": "2016-02-03T13:19:28.639Z",
      "dateUpdated": "2016-02-03T13:19:28.639Z",
      "slug": "Electron-Desktop-Bridge-to-Web-Technologies",
      "title": "Electron Desktop Bridge to Web Technologies",
      "content": "http://electron.atom.io/",
      "createdBy": {
        "_id": "5530bef8e5a9e0dd261059b8",
        "username": "rpl",
        "displayName": "akana abaca"
      },
      "description": "Electron library to create desktop app using web technologies", 
      "contentNode": "56b12452309953f719610f67", 
      "totalVotes": 0
    },  
    {
      "_id": "56b1fd5ba526d27803559a17",
      "dateAdded": "2016-02-03T13:15:07.213Z",
      "dateUpdated": "2016-02-03T13:15:07.213Z",
      "slug": "w3c",
      "title": "w3c",
      "content": "http://www.w3.org/",
      "createdBy": {
        "_id": "5530bef8e5a9e0dd261059b8",
        "username": "rpl",
        "displayName": "akana abaca"
      },
      "description": "w3c website", 
      "contentNode": "56b12452309953f719610f67",  
      "totalVotes": 0
    }
  ]
}
```
`GET /api/links/<nodeId>`

### Response
Key    | Value
-----  | -----
result | boolean
posts  | [Post]

 