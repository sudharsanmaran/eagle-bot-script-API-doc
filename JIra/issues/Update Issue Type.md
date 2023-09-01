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

## Examples
- **1: Updating Issue Type Description**
#### Request
The JSON payload includes the following attributes:

`description` (string): The updated description for the issue type.
`name` (string): The updated name for the issue type.

```http
PUT {{protocol}}://{{host}}/{{basePath}}rest/api/3/issuetype/10006
Content-Type: application/json
Authorization: Bearer <your-access-token>

{
  "description": "Updated description",
  "name": "Bug"
}
```

#### Response
```
HTTP/1.1 200 OK
Content-Type: application/json

{
  "self": "https://test-jira-rest-api.atlassian.net/rest/api/3/issuetype/10006",
  "id": "10006",
  "description": "Updated description",
  "iconUrl": "https://test-jira-rest-api.atlassian.net/rest/api/2/universal_avatar/view/type/issuetype/avatar/10300?size=medium",
  "name": "Bug",
  "untranslatedName": "Bug",
  "subtask": false,
  "avatarId": 10300,
  "hierarchyLevel": 0
}
```

#### Description
This is the response you will receive when successfully updating the issue type with ID "10006." It reflects the updated description and name of the issue type.

- **Updating Issue Type Name and Description**
### Request
The JSON payload includes the following attributes:

`description` (string): The updated description for the issue type.
`name` (string): The updated name for the issue type.

```http 
PUT {{protocol}}://{{host}}/{{basePath}}rest/api/3/issuetype/10007
Content-Type: application/json
Authorization: Bearer <your-access-token>

{
  "description": "Updated sub-task description",
  "name": "Sub-task Updated"
}
```

#### Response
```http 
HTTP/1.1 200 OK
Content-Type: application/json

{
  "self": "https://test-jira-rest-api.atlassian.net/rest/api/3/issuetype/10007",
  "id": "10007",
  "description": "Updated sub-task description",
  "iconUrl": "https://test-jira-rest-api.atlassian.net/rest/api/2/universal_avatar/view/type/issuetype/avatar/10301?size=medium",
  "name": "Sub-task Updated",
  "untranslatedName": "Sub-task Updated",
  "subtask": true,
  "avatarId": 10301,
  "hierarchyLevel": 1
}
```

#### Description
This is the response you will receive when successfully updating the issue type with ID "10007." It reflects the updated description and name of the issue type.