## HTTP Method : `POST` (***Move issues to sprint and rank***)

### Endpoint : `/rest/agile/1.0/sprint/{sprintId}/issue`
Moves issues to a sprint, for a given sprint ID. Issues can only be moved to open or active sprints. The maximum number of issues that can be moved in one operation is 50.

Connect app scope required: WRITE

OAuth 2.0 scopes required:
write:sprint:jira-software
## Request

#### Parameters

- `sprintId`: ***integer*** <span style="font-size: small;color: red;">( ***REQUIRED*** )</span> 
    - The ID of the sprint that you want to assign issues to.
    - `Format` (***int64***)

## Request body ***( application/json )***
- `issues`
array<string>

- `rankBeforeIssue` (***string***)

- `rankAfterIssue` (***string***)

- `rankCustomFieldId` (***integer***) 
    - `Format`: (***int64***)

## Responses

| Status code | Status name | Message |
| - | - | - |
|200|OK|Empty response is returned if operation was successful. <br> (**contentType**: application/json)|
|400 |Bad Request | Returned if the request is invalid. |
|401| Unauthorized | Returned if the user is not logged in. |
|403|Forbidden|Returned if the user does not a have valid license or does not have permission to assign issues.|
|404|Not Found|Returned if the epic does not exist or the user does not have permission to view it.|

## Example

***200 Response:***
```
Empty response is returned if operation was successful.
```
***Python:***
```python
// This code sample uses the 'Unirest' library:
// http://unirest.io/php.html
$headers = array(
  'Content-Type' => 'application/json',
  'Authorization' => 'Bearer <access_token>'
);

$body = <<<REQUESTBODY
{
  "rankBeforeIssue": "PR-4",
  "rankCustomFieldId": 10521,
  "issues": [
    "PR-1",
    "10001",
    "PR-3"
  ]
}
REQUESTBODY;

$response = Unirest\Request::post(
  'https://your-domain.atlassian.com/rest/agile/1.0/sprint/{sprintId}/issue',
  $headers,
  $body
);

var_dump($response)
```