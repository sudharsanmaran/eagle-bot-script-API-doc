# Update Epic

Performs a partial update of the epic. A partial update means that fields not present in the request JSON will not be updated. Valid values for color are color_1 to color_9. 
## Path Parameters

| Property    | type   | Description                          | Required |
|-------------|--------|--------------------------------------|----------|
| epicIdOrKey | string | The id or key of the epic to update. | Yes      |
## Properties

| Property | type    |
|----------|---------|
| name     | string  |
| summary  | string  |
| color    | object  |
| done     | boolean |

## Request 


```http 
POST https://your-domain.atlassian.com/rest/agile/1.0/epic/{epicIdOrKey}
Authorization: Bearer <access_token>
Accept: application/json
Content-Type: application/json
{
  "summary": "epic 2 summary",
  "color":{
    "key": "color_6"
  },
  "name": "epic 2",
  "done": true
}
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