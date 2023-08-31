
## Update Draft

### Example User Prompt:

**Required Parameters**: `draftID` or `latest draft`

1. **Updating Draft Content**:
   - Update the body of the draft with the following information: "Hello, I wanted to provide you with some additional details about the project."
   - Please modify the content of the draft to include the latest figures and statistics.
   - Can you make changes to the draft's body text? Add the new section at the beginning.

2. **Changing Recipients**:
   - Update the recipient of the draft to "partners@example.com".
   - Please change the recipient to "manager@example.com".
   - Can you modify the recipient list to include "team@example.com" as well?

3. **Modifying Subject**:
   - Change the subject of the draft to "Important Announcement".
   - Please update the subject to reflect the new product name.
   - Can you modify the subject line to make it more engaging?


**HTTP Method**: PUT

**Endpoint**: `https://www.googleapis.com/gmail/v1/users/{userId}/drafts/{draftId}`

### Path Parameters:

- `{userId}` (required): The user's email address or "me" to indicate the authenticated user.
- `{draftId}` (required): The ID of the draft to be updated.

### Request Body:

The request body should contain a JSON object with the following structure:

```json
{
    "message": {
        "raw": "base64url_encoded_updated_message"
    }
}
```

- `message.raw` (required): The new MIME message content for the draft, encoded as a base64url string. The existing message in the draft will be replaced with the new content.

### Response:

The response will contain the updated draft object, including its ID and message metadata.