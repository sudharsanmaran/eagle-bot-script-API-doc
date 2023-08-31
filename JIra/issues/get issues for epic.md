## HTTP Method : `GET` (***Get issues for epic***)

### Endpoint : `/rest/api/3/epic/{epicIdOrKey}/issue`

Returns a single issue, for a given issue ID or issue key. Issues returned from this resource include Agile fields, like sprint, closedSprints, flagged, and epic.

Connect app scope required: READ

OAuth 2.0 scopes required:
read:issue:jira-software

#### Parameters

| Parameter Name | Value | Description |
|-|-|-|
|***Path parameters***|||
|`epicIdOrKey`| string <span style="font-size: small;color: red;">(***REQUIRED*** )</span>  | The ID or key of the epic that contains the requested issues.|
|***Query parameters***|||
|`startAt`|integer| The starting index of the returned issues. Base index: 0.|
|`maxResults`|integer| The maximum number of issues to return per page. Default: 50.|
|`jql`|string| Filters results using a JQL query. If you define an order in your JQL query, it will override the default order of the returned issues.|
|`validateQuery`|boolean| Specifies whether to validate the JQL query or not. Default: true.|
|`fields`|array of objects| The list of fields to return for each issue. By default, all navigable and Agile fields are returned.|
|`expand`|string| A comma-separated list of the parameters to expand.|

**Notes:**
- This operation returns all issues that belong to the specified epic.
- The returned issues include Agile fields like sprint, closedSprints, flagged, and epic.
- The issues are ordered by rank by default.
- If you are querying a next-gen project, use the "Search for issues using JQL" operation with the parent clause instead of this operation.

**Required Scopes:**
- Connect app scope: `READ`
- OAuth 2.0 scopes: `read:epic:jira-software`, `read:issue-details:jira`, `read:jql:jira`

## Responses

| Status code | Status name | Message |
| - | - | - |
|200|OK|Returns the requested issues, at the specified page of the results. <br> (**contentType**: application/json)|
|400 |Bad Request | Returned if the request is invalid. |
|401| Unauthorized | Returned if the user is not logged in. |
|403|Forbidden|Returned if the user does not a have valid license.|
|404|Not Found|Returned if the epic does not exist or the user does not have permission to view it.|


  ## Example

***200 Response:***
```json
{
  "expand": "names,schema",
  "startAt": 0,
  "maxResults": 50,
  "total": 1,
  "issues": [
    {
      "expand": "",
      "id": "10001",
      "self": "https://your-domain.atlassian.net/rest/agile/1.0/board/92/issue/10001",
      "key": "HSP-1",
      "fields": {
        "flagged": true,
        "sprint": {
          "id": 37,
          "self": "https://your-domain.atlassian.net/rest/agile/1.0/sprint/13",
          "state": "future",
          "name": "sprint 2",
          "goal": "sprint 2 goal"
        },
        "closedSprints": [
          {
            "id": 37,
            "self": "https://your-domain.atlassian.net/rest/agile/1.0/sprint/23",
            "state": "closed",
            "name": "sprint 1",
            "startDate": "2015-04-11T15:22:00.000+10:00",
            "endDate": "2015-04-20T01:22:00.000+10:00",
            "completeDate": "2015-04-20T11:04:00.000+10:00",
            "goal": "sprint 1 goal"
          }
        ],
        "description": "example bug report",
         "project": {
          "self": "https://your-domain.atlassian.net/rest/api/3/project/EX",
          "id": "10000",
          "key": "EX",
          "name": "Example",
          "avatarUrls": {
            "48x48": "https://your-domain.atlassian.net/secure/projectavatar?size=large&pid=10000",
            "24x24": "https://your-domain.atlassian.net/secure/projectavatar?size=small&pid=10000",
            "16x16": "https://your-domain.atlassian.net/secure/projectavatar?size=xsmall&pid=10000",
            "32x32": "https://your-domain.atlassian.net/secure/projectavatar?size=medium&pid=10000"
          },
          "projectCategory": {
            "self": "https://your-domain.atlassian.net/rest/api/3/projectCategory/10000",
            "id": "10000",
            "name": "FIRST",
            "description": "First Project Category"
          },
          "simplified": false,
          "style": "classic",
          "insight": {
            "totalIssueCount": 100,
            "lastIssueUpdateTime": "2022-11-15T23:15:20.052+0000"
          }
        },
        "comment": [
          {
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/10010/comment/10000",
            "id": "10000",
            "author": {
              "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g",
              "accountId": "5b10a2844c20165700ede21g",
              "displayName": "Mia Krystof",
              "active": false
            },
            "body": {
              "type": "doc",
              "version": 1,
              "content": [
                {
                  "type": "paragraph",
                  "content": [
                    {
                      "type": "text",
                      "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eget venenatis elit. Duis eu justo eget augue iaculis fermentum. Sed semper quam laoreet nisi egestas at posuere augue semper."
                    }
                  ]
                }
              ]
            },
            "updateAuthor": {
              "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g",
              "accountId": "5b10a2844c20165700ede21g",
              "displayName": "Mia Krystof",
              "active": false
            },
            "created": "2021-01-17T12:34:00.000+0000",
            "updated": "2021-01-18T23:45:00.000+0000",
            "visibility": {
              "type": "role",
              "value": "Administrators",
              "identifier": "Administrators"
            }
          }
        ],
        "epic": {
          "id": 37,
          "self": "https://your-domain.atlassian.net/rest/agile/1.0/epic/23",
          "name": "epic 1",
          "summary": "epic 1 summary",
          "color": {
            "key": "color_4"
          },
          "done": true
        },
        "worklog": [
          {
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/10010/worklog/10000",
            "author": {
              "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g",
              "accountId": "5b10a2844c20165700ede21g",
              "displayName": "Mia Krystof",
              "active": false
            },
            "updateAuthor": {
              "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g",
              "accountId": "5b10a2844c20165700ede21g",
              "displayName": "Mia Krystof",
              "active": false
            },
            "comment": {
              "type": "doc",
              "version": 1,
              "content": [
                {
                  "type": "paragraph",
                  "content": [
                    {
                      "type": "text",
                      "text": "I did some work here."
                    }
                  ]
                }
              ]
            },
            "updated": "2021-01-18T23:45:00.000+0000",
            "visibility": {
              "type": "group",
              "value": "jira-developers",
              "identifier": "276f955c-63d7-42c8-9520-92d01dca0625"
            },
            "started": "2021-01-17T12:34:00.000+0000",
            "timeSpent": "3h 20m",
            "timeSpentSeconds": 12000,
            "id": "100028",
            "issueId": "10002"
          }
        ],
        "updated": 1,
        "timetracking": {
          "originalEstimate": "10m",
          "remainingEstimate": "3m",
          "timeSpent": "6m",
          "originalEstimateSeconds": 600,
          "remainingEstimateSeconds": 200,
          "timeSpentSeconds": 400
        }
      }
    }
  ]
}
```

***Python:***
```python
# This code sample uses the 'requests' library:
# http://docs.python-requests.org
import requests
import json

url = "https://your-domain.atlassian.com/rest/agile/1.0/epic/{epicIdOrKey}/issue"

headers = {
  "Accept": "application/json",
  "Authorization": "Bearer <access_token>"
}

response = requests.request(
   "GET",
   url,
   headers=headers
)

print(json.dumps(json.loads(response.text), sort_keys=True, indent=4, separators=(",", ": ")))
```