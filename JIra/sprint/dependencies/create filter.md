## HTTP Method : `POST` (***Create filter***)

### Endpoint : `/rest/api/3/filter`

Creates a filter. The filter is shared according to the default share scope. The filter is not selected as a favorite.

**Permissions** required: Permission to access Jira.

**Connect app scope** required: WRITE

OAuth 2.0 scopes required:

ClassicRECOMMENDED:write:jira-work

**Granular**: `read:filter:jira`, `read:group:jira`, `read:project:jira`, `read:project-role:jira`, `read:user:jira`, `write:filter:jira`, `read:application-role:jira`, `read:avatar:jira`, `read:issue-type-hierarchy:jira`, `read:issue-type:jira`, `read:project-category:jira`, `read:project-version:jira`, `read:project.component:jira`

## Request
### Query parameters
|Property name	|Value	|Description|
| - | - | - |
|expand|string|Use expand to include additional information about filter in the response. This parameter accepts a comma-separated list. **Expand options include:** <br><br> &#8226; `sharedUsers` Returns the users that the filter is shared with. This includes users that can browse projects that the filter is shared with. If you don't specify `sharedUsers`, then the `sharedUsers` object is returned but it doesn't list any users. The list of users returned is limited to 1000, to access additional users append `[start-index:end-index]` to the expand request. For example, to access the next 1000 users, use `?expand=sharedUsers[1001:2000]`. <br><br> &#8226; `subscriptions` Returns the users that are subscribed to the filter. If you don't specify `subscriptions`, the `subscriptions` object is returned but it doesn't list any subscriptions. The list of subscriptions returned is limited to 1000, to access additional subscriptions append `[start-index:end-index]` to the expand request. For example, to access the next 1000 subscriptions, use `?expand=subscriptions[1001:2000]`.
|overrideSharePermissions|boolean|EXPERIMENTAL: Whether share permissions are overridden to enable filters with any share permissions to be created. Available to users with Administer Jira global permission. `Default` (**false**)

## Request body (***application/json***)
The filter to create.

|Property name	|Value	|Description|
|-|-|-|
|`description`| string|A description of the filter.|
|`editPermissions`|array < SharePermission >|The groups and projects that can edit the filter.|
|`favourite`|boolean|Whether the filter is selected as a favorite.|
|`jql`|string|The JQL query for the filter. For example, project = SSP AND issuetype = Bug.|
|`name`|string <span style="font-size: small;color: red;">( ***REQUIRED*** )</span>|The name of the filter. Must be unique.|
|`sharePermissions`|array < SharePermission >|The groups and projects that the filter is shared with.|

## Responses

| Status code | Status name | Message |
| - | - | - |
|200|OK|Returned if the request is successful. <br> (**contentType**: application/json) <br> ***Filter:***<br> &#8226; Details about a filter.|
|400 |Bad Request | Returned if the request object is invalid. For example, the `name` is not unique or the project ID is not specified for a project role share permission. |
|401| Unauthorized | Returned if the authentication credentials are incorrect or missing. |