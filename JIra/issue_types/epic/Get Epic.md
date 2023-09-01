# Get Epic

Returns the epic for a given epic ID. This epic will only be returned if the user has permission to view it. 

## Path Parameters

| Property    | type   | Description                          | Required |
|-------------|--------|--------------------------------------|----------|
| epicIdOrKey | string | The id or key of the requested epic. | Yes      |

## Request 
```http request
GET https://your-domain.atlassian.com/rest/agile/1.0/epic/{epicIdOrKey}
Authorization: Bearer <access_token>
Accept: application/json
```
## Response
```http 
{
  "id": 37,
  "self": "https://your-domain.atlassian.net/rest/agile/1.0/epic/23",
  "name": "epic 1",
  "summary": "epic 1 summary",
  "color": {
    "key": "color_4"
  },
  "done": true
}
```