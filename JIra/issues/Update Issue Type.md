# Update Issue Type
Updates the issue type.


## Request

### Path parameters
| Property | type   | Description               |
|----------|--------|---------------------------|
| id       | string | The ID of the issue type. |

### Properties
| index | Property    | type    | Description                                                              |
|-------|-------------|---------|--------------------------------------------------------------------------|
| 1     | avatarId    | integer | The ID of an issue type avatar.                                          |
| 2     | description | string  | The description of the issue type.                                       |
| 3     | name        | string  | The unique name for the issue type. The maximum length is 60 characters. |


### Request Body
```http request
PUT https://your-domain.atlassian.net/rest/api/3/issuetype/{id}
Authorization: email@example.com:<api_token>
Accept: application/json
Content-Type: application/json

{
  "avatarId": 1,
  "description": "description",
  "name": "name"
}
```

## Response
### Response Body
```http 
{
  "avatarId": 34,
  "description": "<string>",
  "entityId": "<string>",
  "hierarchyLevel": 34,
  "iconUrl": "<string>",
  "id": "<string>",
  "name": "<string>",
  "scope": {
    "project": {
      "avatarUrls": {},
      "id": "<string>",
      "key": "<string>",
      "name": "<string>",
      "projectCategory": {},
      "projectTypeKey": "software",
      "self": "<string>",
      "simplified": true
    },
    "type": "PROJECT"
  },
  "self": "<string>",
  "subtask": true
}
```