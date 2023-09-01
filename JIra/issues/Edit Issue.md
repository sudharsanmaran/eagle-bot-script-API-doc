# Edit Issue

Edit an existing issue in Jira, allowing you to make changes to various fields, apply transitions, and update issue properties. This API operation is useful for modifying existing issues to reflect changes in your project's workflow or data.

## Request

### Path Parameter

- **issueIdOrKey** (string, required): The ID or key of the issue you want to edit.

### Query Parameters

- **notifyUsers** (boolean): Indicates whether a notification email about the issue update should be sent to all watchers. To disable the notification, the user must have the "administer Jira" or "administer project" permissions. Default is true.

- **overrideScreenSecurity** (boolean): Specifies whether screen security should be overridden to enable hidden fields to be edited. This option is available to Connect app users with the "Administer Jira global" permission and Forge apps acting on behalf of users with the same permission. Default is false.

- **overrideEditableFlag** (boolean): Determines whether screen security should be overridden to enable uneditable fields to be edited. Like the previous parameter, this is available to Connect app users with the "Administer Jira global" permission and Forge apps acting on behalf of such users. Default is false.

- **returnIssue** (boolean): Indicates whether the response should contain the edited issue with the updated fields. The returned issue will have the same format as in the "Get issue" API. Default is false.

- **expand** (string): The "Get issue" API expand parameter to use in the response if the "returnIssue" parameter is true.

### Request Body
**Required body properties:**
| Property      | Type    | Description    
|---------------|---------|----------------|
project_id |string |The ID or key of the project the issue or subtask is to be created in.
summary |string | The summary description for the new issue or subtask.
issuetype | string | The ID or name of the issue type for the new issue or subtask.

**Optional body properties:**

- **fields** (object): A list of issue screen fields to update, specifying the sub-field to update and its value for each field. Fields included here cannot be included in the "update" field.

- **historyMetadata** ([HistoryMetadata](resources/HistoryMetadata.md)): Additional issue history details.

- **properties** (array of [EntityProperty](resources/EntityProperty.md)): Details of issue properties to add or update.

- **transition** ([IssueTransition](resources/IssueTransition.md)): Details of a transition. This field is required when performing a transition and optional when creating or editing an issue.

- **update** (object): A map containing the field name and a list of operations to perform on the issue screen field. Fields included here cannot be included in the "fields" field.

- **Additional Properties** (any): Extra properties of any type that may be provided.

## Responses

### 200 OK

- **Content Type**: application/json

- **Body**: The response body contains the edited issue if the "returnIssue" parameter is set to true.

### 204 No Content

- Returned if the request is successful, but no content is included in the response body.

### 400 Bad Request

- Returned if the request is malformed or contains invalid data.

### 401 Unauthorized

- Returned if the request lacks proper authorization.

### 403 Forbidden

- Returned if the user does not have permission to edit the issue or override screen security.

### 404 Not Found

- Returned if the specified issue (via ID or key) does not exist.
