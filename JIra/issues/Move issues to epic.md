
## HTTP Method : `POSt` (***Move issues to epic***)

### Endpoint : `/rest/agile/1.0/epic/{epicIdOrKey}/issue`
Moves issues to an epic, for a given epic id. Issues can be only in a single epic at the same time. That means that already assigned issues to an epic, will not be assigned to the previous epic anymore. The user needs to have the edit issue permission for all issue they want to move and to the epic. The maximum number of issues that can be moved in one operation is 50. 
`Note`: This operation does not work for epics in next-gen projects.

Connect app scope required: WRITE

OAuth 2.0 scopes required:
write:epic:jira-software

## Request
### Path parameters
- `epicIdOrKey` (***string***) <span style="font-size: small;color: red;">( ***REQUIRED*** )</span> 

## Request body (***application/json***)
- `issues` (***array  < string >***)

## Responses

| Status code | Status name | Message |
| - | - | - |
|204|No Content|Empty response is returned if operation was successful.|
|400 |Bad Request | Returned if the request is invalid. |
|401| Unauthorized | Returned if the user is not logged in. |
|403|Forbidden|Returned if the user does not a have valid license or does not have edit issue permission for all issues to assign or for the epic.|
|404|Not Found|Returned if the epic does not exist or the user does not have permission to view it.|

## Example

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
  "issues": [
    "PR-1",
    "10001",
    "PR-3"
  ]
}
REQUESTBODY;

$response = Unirest\Request::post(
  'https://your-domain.atlassian.com/rest/agile/1.0/epic/{epicIdOrKey}/issue',
  $headers,
  $body
);

var_dump($response)
```