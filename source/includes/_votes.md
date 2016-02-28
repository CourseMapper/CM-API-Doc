# Votes 
  
## Get Vote Based on Object
```shell
curl "https://coursemapper/api/votes/<voteType>/id/<voteTypeId>"
  -H "Authorization: Bearer <accessToken>"

e.g.:
curl "https://coursemapper/api/votes/discussion/id/5530bef8e5a9e0dd261059b8"
  -H "Authorization: Bearer 2ksjow2039ze_18jaszxvnKLJlsfHUHfsjklmvoiay9146fah"
```
> The above command returns JSON structured like this:

```json
{
  "result": true,
  "vote": {
    "_id": "5530bef8e5a9e0dd261059b8",
    "total": "12"
  }
}
```
`GET /api/votes/<voteType>/id/<voteTypeId>`

This endpoint will return the summary of votes of an object. A vote is casted on an object by a user, based on its object type and object Id. An object can be a discussion topic, discussion reply, annotations and many others as long as it has an id as its identifiers.

### URL Parameter
Key    | Value
-----  | -----
voteType | string (discussion, reply, link, pdf-annotation, video-annotation)
voteTypeId | ObjectId

### Response
Key    | Value
-----  | -----
result | boolean
{vote:{total:int}} | int

## Insert Vote
`POST /api/votes/<voteType>/id/<voteTypeId>/<operation>`

This endpoint can be used to vote up, vote down, and unvote.

### URL Parameter
Key    | Value
-----  | -----
voteType | string ("discussion", "reply", "link", "pdf-annotation", "video-annotation")
voteTypeId | ObjectId
operation  | string ("up" or "down"). Send the same value if unvote.