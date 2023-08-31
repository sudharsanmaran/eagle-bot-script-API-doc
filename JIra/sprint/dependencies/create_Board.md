## HTTP Method : `POST` (***Create board***)

### Endpoint : `/rest/agile/1.0/board`

Creates a new board. Board name, type and filter ID is required.
## Parameters
- `name` - Must be less than 255 characters.
- `type` - Valid values: scrum, kanban
- `filterId` - ID of a filter that the user has permissions to view. Note, if the user does not have the 'Create shared objects' permission and tries to create a shared board, a private board will be created instead (remember that board sharing depends on the filter sharing).
- `location` - The container that the board will be located in. location must include the type property (Valid values: project, user). If choosing 'project', then a project must be specified by a projectKeyOrId property in location. If choosing 'user', the current user is chosen by default. The projectKeyOrId property should not be provided.

`Note`:
If you want to create a new project with an associated board, use the Jira platform REST API. For more information, see the Create project method. The projectTypeKey for software boards must be 'software' and the projectTemplateKey must be either com.pyxis.greenhopper.jira:gh-kanban-template or com.pyxis.greenhopper.jira:gh-scrum-template.
You can create a filter using the Jira REST API. For more information, see the Create filter method.
If you do not ORDER BY the Rank field for the filter of your board, you will not be able to reorder issues on the board.

Connect app scope required: WRITE

OAuth 2.0 scopes required:
write:board-scope:jira-software

## Request
### Request body (***application/json***)

- `name` (***string***)

- `type` (***string***)
    - `Valid values` (***kanban, scrum, agility***)

- `filterId` (***integer***)
    - `Format` (***int64***)

- `location` (***object***)
    - `type` (***string***)
    - `projectKeyOrId` (***string***)

## Responses

| Status code | Status name | Message |
| - | - | - |
|200|OK|Returns the created board. <br> (**contentType**: application/json)|
|400 |Bad Request | Returned if the request is invalid. |
|401| Unauthorized | Returned if the user is not logged in. |
|403|Forbidden|Returned if the user does not a have valid license.|

## Example

***Python:***
```python
# This code sample uses the 'requests' library:
# http://docs.python-requests.org
import requests
import json

url = "https://your-domain.atlassian.com/rest/agile/1.0/board"

headers = {
  "Accept": "application/json",
  "Content-Type": "application/json",
  "Authorization": "Bearer <access_token>"
}

payload = json.dumps( {
  "filterId": 10040,
  "name": "scrum board",
  "location": {
    "projectKeyOrId": "10000",
    "type": "project"
  },
  "type": "scrum"
} )

response = requests.request(
   "POST",
   url,
   data=payload,
   headers=headers
)

print(json.dumps(json.loads(response.text), sort_keys=True, indent=4, separators=(",", ": ")))
```

