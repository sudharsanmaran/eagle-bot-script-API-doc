# Get Issue Picker Suggestions

Retrieve issue picker suggestions to provide auto-completion when users are searching for issues using specific keywords or strings. This API operation returns two lists: one from the user's history and another based on a JQL query.

## Request

### Query Parameters

- **query** (string): A string used to match against text fields in the issue, such as title, description, or comments.

- **currentJQL** (string): A JQL query that defines a list of issues to search for based on the query term. Note that usernames and userkeys cannot be used as search terms for this parameter due to privacy reasons; instead, use the `accountId` parameter.

- **currentIssueKey** (string): The key of an issue to exclude from the search results. For example, this could be the issue the user is currently viewing when they perform the query.

- **currentProjectId** (string): The ID of a project that suggested issues must belong to.

- **showSubTasks** (boolean): Indicates whether to include subtasks in the suggestions list.

- **showSubTaskParent** (boolean): When `currentIssueKey` refers to a subtask, this parameter determines whether to include the parent issue in the suggestions if it matches the query.

### Permissions

- No specific permissions are required to access this operation.

### OAuth 2.0 Scopes

- Classic: `read:jira-work`
- Granular: `read:issue-details:jira`

## Response

### 200 OK

- **Content Type**: application/json

#### IssuePickerSuggestions

A list of issues suggested for use in auto-completion. This list includes two sections:

- **History Search**: Contains issues from the user's history of created, edited, or viewed issues that contain the string specified in the `query` parameter.

- **Current Search**: Includes issues that match the JQL expression in `currentJQL` and also contain the string specified in the `query` parameter.

### 401 Unauthorized

- Returned if the request lacks proper authorization.

     