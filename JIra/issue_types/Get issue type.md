# Get issue type
Returns an issue type.

## Request

### Path parameters

| Property | type   | Description               |
|----------|--------|---------------------------|
| id       | string | The ID of the issue type. |

### Request Body
```http request
GET https://your-domain.atlassian.net/rest/api/3/issuetype/{id}
Authorization: email@example.com:<api_token>
Accept: application/json
```

## Response
### Response Body
```http 
{
  "self": "https://your-domain.atlassian.net/rest/api/3/issueType/3",
  "id": "3",
  "description": "A task that needs to be done.",
  "iconUrl": "https://your-domain.atlassian.net/secure/viewavatar?size=xsmall&avatarId=10299&avatarType=issuetype\",",
  "name": "Task",
  "subtask": false,
  "avatarId": 1,
  "hierarchyLevel": 0
}
```
