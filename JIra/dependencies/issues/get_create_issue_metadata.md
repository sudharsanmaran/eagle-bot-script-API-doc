# Get Create Issue Metadata

Retrieve details about projects, issue types within those projects, and create screen fields for each issue type. This information is valuable for populating requests when creating issues using the Create Issue and Create Issues APIs.

## Request

### Query Parameters

- **projectIds** (array of strings): A list of project IDs. This parameter accepts a comma-separated list or multiple project IDs provided using an ampersand-separated list. For example, `projectIds=10000,10001&projectIds=10020,10021`. This parameter may be provided with `projectKeys`.

- **projectKeys** (array of strings): A list of project keys. This parameter accepts a comma-separated list or multiple project keys provided using an ampersand-separated list. For example, `projectKeys=proj1,proj2&projectKeys=proj3`. This parameter may be provided with `projectIds`.

- **issuetypeIds** (array of strings): A list of issue type IDs. This parameter accepts a comma-separated list or multiple issue type IDs provided using an ampersand-separated list. For example, `issuetypeIds=10000,10001&issuetypeIds=10020,10021`. This parameter may be provided with `issuetypeNames`.

- **issuetypeNames** (array of strings): A list of issue type names. This parameter accepts a comma-separated list or multiple issue type names provided using an ampersand-separated list. For example, `issuetypeNames=name1,name2&issuetypeNames=name3`. This parameter may be provided with `issuetypeIds`.

- **expand** (string): Use the `expand` parameter to include additional information about issue metadata in the response. This parameter accepts `projects.issuetypes.fields`, which returns information about the fields in the issue creation screen for each issue type. Fields hidden from the screen are not returned. You can use this information to populate fields and update fields in Create Issue and Create Issues requests.

## Responses

### 200 OK

- **Content Type**: application/json

- **Body**: The response body contains information about projects, issue types, and create screen fields, based on the provided query parameters. This information can be used for creating and configuring issues.

### 401 Unauthorized

- Returned if the request lacks proper authorization.

---

**Example Request:**

```http
GET https://your-domain.atlassian.net/rest/api/3/issue/createmeta?projectIds=10000,10001&issuetypeNames=Bug,Task&expand=projects.issuetypes.fields
Authorization: Bearer <access_token>
Accept: application/json
```

**Example Response (200 OK):**

```json
{
  "projects": [
    {
      "id": "10000",
      "key": "PROJ1",
      "name": "Project One",
      "issuetypes": [
        {
          "id": "10001",
          "name": "Bug",
          "fields": {
            "summary": {
              "name": "Summary",
              "key": "summary",
              "required": true,
              "schema": {
                "type": "string",
                "system": "summary"
              }
            },
            "description": {
              "name": "Description",
              "key": "description",
              "required": false,
              "schema": {
                "type": "string",
                "system": "description"
              }
            },
            "priority": {
              "name": "Priority",
              "key": "priority",
              "required": true,
              "schema": {
                "type": "priority",
                "system": "priority"
              }
            }
          }
        },
        {
          "id": "10002",
          "name": "Task",
          "fields": {
            "summary": {
              "name": "Summary",
              "key": "summary",
              "required": true,
              "schema": {
                "type": "string",
                "system": "summary"
              }
            },
            "description": {
              "name": "Description",
              "key": "description",
              "required": false,
              "schema": {
                "type": "string",
                "system": "description"
              }
            },
            "assignee": {
              "name": "Assignee",
              "key": "assignee",
              "required": false,
              "schema": {
                "type": "user",
                "system": "assignee"
              }
            }
          }
        }
      ]
    },
    {
      "id": "10001",
      "key": "PROJ2",
      "name": "Project Two",
      "issuetypes": [
        {
          "id": "10003",
          "name": "Bug",
          "fields": {
            // ...
          }
        },
        {
          "id": "10004",
          "name": "Task",
          "fields": {
            // ...
          }
        }
      ]
    }
  ]
}
```

This response provides details about projects, issue types, and create screen fields based on the provided query parameters. The information can be used to configure and populate fields when creating or editing issues.