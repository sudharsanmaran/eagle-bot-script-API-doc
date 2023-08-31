## HTTP Method : `POST` (***Create sprint***)

### Endpoint : `/rest/agile/1.0/sprint`


Connect app scope required: WRITE

OAuth 2.0 scopes required:
write:epic:jira-software

## Request
### Request body (***application/json***)

- ***name*** (`string`) <span style="font-size: small;color: red;">( ***REQUIRED*** )</span>

- ***startDate***
(`string`)

- ***endDate***
(`string`)

- ***originBoardId*** (`integer`) <span style="font-size: small;color: red;">( ***REQUIRED*** )</span>
  - ***Format*** (`int64`)

- ***goal*** (`string`)

## Responses

| Status code | Status name | Message |
| - | - | - |
|200|OK|Created sprint <br> (**contentType**: application/json)|
|400 |Bad Request | Returned if the request is invalid. |
|401| Unauthorized | Returned if the user is not logged in. |
|403|Forbidden|Returned if the user does not a have valid license.|
|404|Not Found|Returned if the epic does not exist or the user does not have permission to view it.|

## Example

***Python:***
```python
# This code sample uses the 'requests' library:
# http://docs.python-requests.org
import requests
import json

url = "https://your-domain.atlassian.com/rest/agile/1.0/sprint"

headers = {
  "Accept": "application/json",
  "Content-Type": "application/json",
  "Authorization": "Bearer <access_token>"
}

payload = json.dumps( {
  "originBoardId": 5,
  "goal": "sprint 1 goal",
  "endDate": "2015-04-20T01:22:00.000+10:00",
  "name": "sprint 1",
  "startDate": "2015-04-11T15:22:00.000+10:00"
} )

response = requests.request(
   "POST",
   url,
   data=payload,
   headers=headers
)

print(json.dumps(json.loads(response.text), sort_keys=True, indent=4, separators=(",", ": ")))
```