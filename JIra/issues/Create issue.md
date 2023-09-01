# Create issue

Creates an issue or, where the option to create subtasks is enabled in Jira, a subtask. A transition may be applied, to move the issue or subtask to a workflow step other than the default start step, and issue properties set.

## example user prompts:

1. **Creating a Bug Report in Project XYZ**:
   - Create a new bug report in project "XYZ" with the summary "UI Bug on Homepage".
   - I need to log a bug in project "XYZ" for a critical issue with the summary "Broken Login Button".
   - Please create an issue in project "XYZ" to track the bug "404 Error on Product Page".

2. **Adding a New Task in Project ABC**:
   - Add a task to project "ABC" with the title "Implement User Authentication".
   - I want to create a task in project "ABC" called "Design Landing Page".
   - Create an issue type "Task" in project "ABC" with the description "Backend Development for User Registration".

3. **Reporting an Epic in Project QRS**:
   - Report an epic in project "QRS" with the name "Project Redesign".
   - I'd like to create an epic in project "QRS" called "Mobile App Enhancement".
   - Please help me create an epic for project "QRS" titled "New Feature Development".

4. **Raising a Story in Project PQR**:
   - Raise a user story in project "PQR" with the title "User Profile Page".
   - I need to add a story in project "PQR" for "Shopping Cart Checkout".
   - Create a new user story in project "PQR" named "Integration with Payment Gateway".

Feel free to customize the project names, issue types, summaries, and descriptions to match your specific Jira setup and requirements. You can also specify additional details like assignees, due dates, and labels depending on your Jira project's configuration.

## Request
### Query parameters

| Property      | Type    | Description                                                                                                                                                                                                                                                                                                                          |
|---------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| updateHistory | boolean | Whether the project in which the issue is created is added to the user's Recently viewed project list, as shown under Projects in Jira. When provided, the issue type and request type are added to the user's history for a project. These values are then used to provide defaults on the issue create screen. <br/>Default: false |

### Properties

**Required body properties:**
| Property      | Type    | Description    
|---------------|---------|----------------|
project_id |string |The ID or key of the project the issue or subtask is to be created in.
summary |string | The summary description for the new issue or subtask.
issuetype | string | The ID or name of the issue type for the new issue or subtask.

**Optional body properties:**
| Index | Property              | Type                                                 | Description                                                                                                                                                                                                                                                                                                 |
|-------|-----------------------|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | fields                | object                                               | List of issue screen fields to update, specifying the sub-field to update and its value for each field. This field provides a straightforward option when setting a sub-field. When multiple sub-fields or other operations are required, use update. Fields included in here cannot be included in update. |
| 2     | historyMetadata       | [HistoryMetadata](resources/HistoryMetadata.md)      | Additional issue history details.                                                                                                                                                                                                                                                                           |
| 3     | properties            | array<[EntityProperty](resources/EntityProperty.md)> | Details of issue properties to be add or update.                                                                                                                                                                                                                                                            |
| 4     | transition            | [IssueTransition](resources/IssueTransition.md)      | Details of a transition. Required when performing a transition, optional when creating or editing an issue.                                                                                                                                                                                                 |
| 5     | update                | object                                               | A Map containing the field field name and a list of operations to perform on the issue screen field. Note that fields included in here cannot be included in fields.                                                                                                                                        |
| 6     | Additional Properties | any                                                  | Extra properties of any type may be provided to this object.                                                                                                                                                                                                                                                |


### Request Body
```http request
POST https://your-domain.atlassian.net/rest/api/3/issue
Authorization: email@example.com:<api_token>
Accept: application/json
Content-Type: application/json

{
  "fields": {
    "assignee": {
      "id": "5b109f2e9729b51b54dc274d"
    },
    "components": [
      {
        "id": "10000"
      }
    ],
    "customfield_10000": "09/Jun/19",
    "customfield_20000": "06/Jul/19 3:25 PM",
    "customfield_30000": [
      "10000",
      "10002"
    ],
    "customfield_40000": {
      "content": [
        {
          "content": [
            {
              "text": "Occurs on all orders",
              "type": "text"
            }
          ],
          "type": "paragraph"
        }
      ],
      "type": "doc",
      "version": 1
    },
    "customfield_50000": {
      "content": [
        {
          "content": [
            {
              "text": "Could impact day-to-day work.",
              "type": "text"
            }
          ],
          "type": "paragraph"
        }
      ],
      "type": "doc",
      "version": 1
    },
    "customfield_60000": "jira-software-users",
    "customfield_70000": [
      "jira-administrators",
      "jira-software-users"
    ],
    "customfield_80000": {
      "value": "red"
    },
    "description": {
      "content": [
        {
          "content": [
            {
              "text": "Order entry fails when selecting supplier.",
              "type": "text"
            }
          ],
          "type": "paragraph"
        }
      ],
      "type": "doc",
      "version": 1
    },
    "duedate": "2019-05-11",
    "environment": {
      "content": [
        {
          "content": [
            {
              "text": "UAT",
              "type": "text"
            }
          ],
          "type": "paragraph"
        }
      ],
      "type": "doc",
      "version": 1
    },
    "fixVersions": [
      {
        "id": "10001"
      }
    ],
    "issuetype": {
      "id": "10000"
    },
    "labels": [
      "bugfix",
      "blitz_test"
    ],
    "parent": {
      "key": "PROJ-123"
    },
    "priority": {
      "id": "20000"
    },
    "project": {
      "id": "10000"
    },
    "reporter": {
      "id": "5b10a2844c20165700ede21g"
    },
    "security": {
      "id": "10000"
    },
    "summary": "Main order flow broken",
    "timetracking": {
      "originalEstimate": "10",
      "remainingEstimate": "5"
    },
    "versions": [
      {
        "id": "10000"
      }
    ]
  },
  "update": {}
}
```
## Response
### Response Body
```http
{
  "id": "10000",
  "key": "ED-24",
  "self": "https://your-domain.atlassian.net/rest/api/3/issue/10000",
  "transition": {
    "status": 200,
    "errorCollection": {
      "errorMessages": [],
      "errors": {}
    }
  }
}
```