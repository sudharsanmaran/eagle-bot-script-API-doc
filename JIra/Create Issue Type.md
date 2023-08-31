# Create Issue Type
Creates an issue type and adds it to the default issue type scheme.

## Request
### Properties

| index | Property       | type    | Description                                                                                                                                                                         | Required | Default    |
|-------|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|------------|
| 1     | description    | string  | The description of the issue type.                                                                                                                                                  | No       | -          |
| 2     | hierarchyLevel | integer | The hierarchy level of the issue type. Use:<br/>-1 for Subtask.<br/>0 for Base.                                                                                                     | Yes      | 0          |
| 3     | name           | string  | The unique name for the issue type. The maximum length is 60 characters.                                                                                                            | Yes      | -          |
| 4     | type           | string  | Deprecated. Use hierarchyLevel instead. See the deprecation notice for details.<br/><br/>Whether the issue type is `subtype` or `standard`.<br/>Valid values: `subtask`, `standard` | Yes      | `standard` |

### Request Body
```http request
POST https://your-domain.atlassian.net/rest/api/3/issuetype' 
Authorization:  'email@example.com:<api_token>' 
Accept: application/json' 
Content-Type: application/json' 

{
  "description": "description",
  "name": "name",
  "type": "standard"
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