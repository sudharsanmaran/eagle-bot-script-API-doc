# Edit Issue

Edit an existing issue in Jira, allowing you to make changes to various fields, apply transitions, and update issue properties. This API operation is useful for modifying existing issues to reflect changes in your project's workflow or data.

## Request

### Path Parameter

- **issueIdOrKey** (string, required): The ID or key of the issue you want to edit.

**note:** issue id can be fetched from [issue picker API](../dependencies/issues/issue_picker.md) if user give matched issue properties.

### Query Parameters

- **notifyUsers** (boolean): Indicates whether a notification email about the issue update should be sent to all watchers. To disable the notification, the user must have the "administer Jira" or "administer project" permissions. Default is true.

- **overrideScreenSecurity** (boolean): Specifies whether screen security should be overridden to enable hidden fields to be edited. This option is available to Connect app users with the "Administer Jira global" permission and Forge apps acting on behalf of users with the same permission. Default is false.

- **overrideEditableFlag** (boolean): Determines whether screen security should be overridden to enable uneditable fields to be edited. Like the previous parameter, this is available to Connect app users with the "Administer Jira global" permission and Forge apps acting on behalf of such users. Default is false.

- **returnIssue** (boolean): Indicates whether the response should contain the edited issue with the updated fields. The returned issue will have the same format as in the "Get issue" API. Default is false.

- **expand** (string): The "Get issue" API expand parameter to use in the response if the "returnIssue" parameter is true.

### Request Body
**Required body properties:**
- **fields** (object): A list of issue screen fields to update, specifying the sub-field to update and its value for each field. Fields included here cannot be included in the "update" field.

**Optional body properties:**

- **historyMetadata** ([HistoryMetadata](resources/HistoryMetadata.md)): Additional issue history details.

- **properties** (array of [EntityProperty](resources/EntityProperty.md)): Details of issue properties to add or update.

- **transition** ([IssueTransition](resources/IssueTransition.md)): Details of a transition. This field is required when performing a transition and optional when creating or editing an issue.

- **update** (object): A map containing the field name and a list of operations to perform on the issue screen field. Fields included here cannot be included in the "fields" field.

- **Additional Properties** (any): Extra properties of any type that may be provided.

Sure, here are example user prompts and possible values to re-prompt if required fails for the "Edit Issue" API:

### Example User Prompts:

1. **Editing an Issue**:
   - I want to update an existing issue in Jira with the issue key "PROJ-123".
   - Edit issue "BUG-456" to change the assignee.
   - Please modify the description of issue "TASK-789".
   - Make changes to issue "FEATURE-101" to reflect the latest status.

2. **Applying a Transition to an Issue**:
   - Transition issue "PROJ-234" to the "In Progress" status.
   - Change the status of issue "BUG-789" to "Resolved".
   - I need to move issue "TASK-567" to the "Testing" phase.
   - Apply a transition to issue "EPIC-123" to mark it as "Done".

3. **Updating Issue Properties**:
   - Add a property to issue "BUG-123" to track additional information.
   - Set a custom property for issue "TASK-456" to store special data.
   - I want to add a property to issue "STORY-789" to store release notes.
   - Please update the properties of issue "EPIC-456" with the latest details.

### Possible Information to Re-prompt Users if Required Fails:

1. **Issue ID/Key Not Found:** If the provided issue ID or key cannot be found, prompt the user to verify the ID/key or provide another one.

2. **Permission Issues:** If the user lacks permission to edit the issue or override screen security, inform them about the permission requirements and offer to retry with appropriate permissions.

3. **Invalid Data:** If the request is malformed or contains invalid data, provide guidance on the required format and prompt the user to correct the input.

4. **Notification Options:** If the user wants to disable notification emails but lacks the necessary permissions, explain the permissions required and offer to proceed with notifications enabled or help them grant the necessary permissions.

5. **Expand Parameter:** If the "returnIssue" parameter is set to true and the user wants to use the "expand" parameter but provides an invalid value, inform them of the correct options for the "expand" parameter.

6. **Screen Security Overrides:** If the user wants to override screen security (either for hidden or uneditable fields), ensure they have the necessary permissions and explain the available options.

By addressing these potential issues and providing clear instructions, you can ensure a smoother interaction with the "Edit Issue" API in Jira.

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
