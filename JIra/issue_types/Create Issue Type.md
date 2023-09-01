# Create Issue Type
Creates an issue type and adds it to the default issue type scheme.

## Request
### Properties

#### Required Parameters
| index | Property       | type    | Description                                                                                                                                                                         | Required | Default    |
|-------|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|------------|
| 1     | name           | string  | The unique name for the issue type. The maximum length is 60 characters.                                                                                                            | Yes      | -          |

#### Optional Parameters

| index | Property       | type    | Description                                                                                                                                                                         | Required | Default    |
|-------|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|------------|
| 1     | description    | string  | The description of the issue type.                                                                                                                                                  | No       | -          |
| 2     | hierarchyLevel | integer | The hierarchy level of the issue type. Use:<br/>-1 for Subtask.<br/>0 for Base.                                                                                                     | Yes      | 0          |
| 3     | type           | string  | Deprecated. Use hierarchyLevel instead. See the deprecation notice for details.<br/><br/>Whether the issue type is `subtype` or `standard`.<br/>Valid values: `subtask`, `standard` | Yes      | `standard` |

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

## Examples 
### Add Standard Issue Type

#### Request

The JSON payload includes the following attributes:

- `name` (string): The name of the issue type, which is "Bug" in this example.
- `description` (string): A description of the issue type, indicating that it represents a software bug or defect.
- `type` (string): Specifies that this is a standard issue type.

```http
POST https://your-jira-instance/rest/api/3/issuetype
Content-Type: application/json
Authorization: Bearer <your-access-token>

{
  "name": "Bug",
  "description": "Represents a software bug or defect",
  "type": "standard"
}


```
#### Response

```
HTTP/1.1 201 Created
Content-Type: application/json

{
  "self": "https://your-jira-instance/rest/api/3/issuetype/10006",
  "id": "10006",
  "description": "Represents a software bug or defect",
  "iconUrl": "https://your-jira-instance/rest/api/2/universal_avatar/view/type/issuetype/avatar/10300?size=medium",
  "name": "Bug",
  "untranslatedName": "Bug",
  "subtask": false,
  "avatarId": 10300,
  "hierarchyLevel": 0
}
```

## Add Subtask Issue Type

### Request
The JSON payload includes the following attributes:

- `name` (string): The name of the issue type, which is "Sub-task" in this example.
- `description` (string): A description of the issue type, indicating that it represents a sub-task within a larger task.
- `type` (string): Specifies that this is a subtask issue type.

```http
POST https://your-jira-instance/rest/api/3/issuetype
Content-Type: application/json
Authorization: Bearer <your-access-token>

{
  "name": "Sub-task",
  "description": "Represents a sub-task within a larger task",
  "type": "subtask"
}
```

### Response
```
HTTP/1.1 201 Created
Content-Type: application/json

{
  "self": "https://your-jira-instance/rest/api/3/issuetype/10007",
  "id": "10007",
  "description": "Represents a sub-task within a larger task",
  "iconUrl": "https://your-jira-instance/rest/api/2/universal_avatar/view/type/issuetype/avatar/10301?size=medium",
  "name": "Sub-task",
  "untranslatedName": "Sub-task",
  "subtask": true,
  "avatarId": 10301,
  "hierarchyLevel": 1
}
```