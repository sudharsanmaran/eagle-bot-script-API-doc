# Get issue
Returns the details for an issue.

The issue is identified by its ID or key, however, if the identifier doesn't match an issue, a case-insensitive search and check for moved issues is performed. If a matching issue is found its details are returned, a 302 or other redirect is not returned. The issue key returned in the response is the key of the issue found.

## Request
### Path parameters

| Property     | Type   | Description                 |
|--------------|--------|-----------------------------|
| issueIdOrKey | string | The ID or key of the issue. |

### Properties

| Parameter     | Type    | Description                                                                                            |
|---------------|---------|--------------------------------------------------------------------------------------------------------|
| fields        | array   | A list of fields to return for the issue. This parameter accepts a comma-separated list.               |
| fieldsByKeys  | boolean | Whether fields in fields are referenced by keys rather than IDs.                                       |
| expand        | string  | Use expand to include additional information about the issues in the response.                         |
| properties    | array   | A list of issue properties to return for the issue. This parameter accepts a comma-separated list.     |
| updateHistory | boolean | Whether the project in which the issue is created is added to the user's Recently viewed project list. |

### Request Body
```http request
GET https://your-domain.atlassian.net/rest/api/3/issue/{issueIdOrKey}
Authorization: email@example.com:<api_token>
Accept: application/json
```
## Response
### Response Body
```http 
{
  "expand": "",
  "id": "10002",
  "self": "https://your-domain.atlassian.net/rest/api/3/issue/10002",
  "key": "ED-1",
  "fields": {
    "watcher": {
      "self": "https://your-domain.atlassian.net/rest/api/3/issue/EX-1/watchers",
      "isWatching": false,
      "watchCount": 1,
      "watchers": [
        {
          "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g",
          "accountId": "5b10a2844c20165700ede21g",
          "displayName": "Mia Krystof",
          "active": false
        }
      ]
    },
    "attachment": [
      {
        "id": 10000,
        "self": "https://your-domain.atlassian.net/rest/api/3/attachments/10000",
        "filename": "picture.jpg",
        "author": {
          "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10a2844c20165700ede21g",
          "key": "",
          "accountId": "5b10a2844c20165700ede21g",
          "accountType": "atlassian",
          "name": "",
          "avatarUrls": {
            "48x48": "https://avatar-management--avatars.server-location.prod.public.atl-paas.net/initials/MK-5.png?size=48&s=48",
            "24x24": "https://avatar-management--avatars.server-location.prod.public.atl-paas.net/initials/MK-5.png?size=24&s=24",
            "16x16": "https://avatar-management--avatars.server-location.prod.public.atl-paas.net/initials/MK-5.png?size=16&s=16",
            "32x32": "https://avatar-management--avatars.server-location.prod.public.atl-paas.net/initials/MK-5.png?size=32&s=32"
          },
          "displayName": "Mia Krystof",
          "active": false
        },
        "created": "2023-08-30T05:33:40.269+0000",
        "size": 23123,
        "mimeType": "image/jpeg",
        "content": "https://your-domain.atlassian.net/jira/rest/api/3/attachment/content/10000",
        "thumbnail": "https://your-domain.atlassian.net/jira/rest/api/3/attachment/thumbnail/10000"
      }
    ],
    "sub-tasks": [
      {
        "id": "10000",
        "type": {
          "id": "10000",
          "name": "",
          "inward": "Parent",
          "outward": "Sub-task"
        },
        "outwardIssue": {
          "id": "10003",
          "key": "ED-2",
          "self": "https://your-domain.atlassian.net/rest/api/3/issue/ED-2",
          "fields": {
            "status": {
              "iconUrl": "https://your-domain.atlassian.net/images/icons/statuses/open.png",
              "name": "Open"
            }
          }
        }
      }
    ],
    "description": {
      "type": "doc",
      "version": 1,
      "content": [
        {
          "type": "paragraph",
          "content": [
            {
              "type": "text",
              "text": "Main order flow broken"
            }
          ]
        }
      ]
    },
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
        "lastIssueUpdateTime": "2023-08-30T05:33:38.872+0000"
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
    "issuelinks": [
      {
        "id": "10001",
        "type": {
          "id": "10000",
          "name": "Dependent",
          "inward": "depends on",
          "outward": "is depended by"
        },
        "outwardIssue": {
          "id": "10004L",
          "key": "PR-2",
          "self": "https://your-domain.atlassian.net/rest/api/3/issue/PR-2",
          "fields": {
            "status": {
              "iconUrl": "https://your-domain.atlassian.net/images/icons/statuses/open.png",
              "name": "Open"
            }
          }
        }
      },
      {
        "id": "10002",
        "type": {
          "id": "10000",
          "name": "Dependent",
          "inward": "depends on",
          "outward": "is depended by"
        },
        "inwardIssue": {
          "id": "10004",
          "key": "PR-3",
          "self": "https://your-domain.atlassian.net/rest/api/3/issue/PR-3",
          "fields": {
            "status": {
              "iconUrl": "https://your-domain.atlassian.net/images/icons/statuses/open.png",
              "name": "Open"
            }
          }
        }
      }
    ],
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
```