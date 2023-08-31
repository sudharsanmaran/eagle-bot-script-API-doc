## Send Draft

### Example User Prompt:
**Required Parameters**: `draftID` or `latest draft`
**Optional Parameters For Edits**: `to`, `cc`, `bcc`, 

1. **Sending a Draft**:
   - Send the draft with the subject "Meeting Tomorrow" to "john.doe@example.com".
   - Please send the draft I created earlier(latest draft) to "susan@example.com".
   - Can you send the draft with the subject "Important Information" to the recipient "manager@example.com"?

2. **Sending to Contact Names**:
   - Send the latest draft addressed to John.
   - Please forward the latest draft to Sarah.

3. **Specifying the Sender(USER)**:
   - Send the draft from "your.email@example.com" to "support@example.com".
   - Please send the email drafted by "business@example.com" to "customer@example.com".
   - Can you forward the draft from "me@example.com" to "friend@example.com"?

4. **Sending with Modifications**:
   - Edit the draft's body to add a new paragraph and then send it.
   - Before sending, change the recipient to "new@example.com".
   - Make a small change to the subject of the draft and then proceed with sending it.


**HTTP Method**: POST

**Endpoint**: `https://www.googleapis.com/gmail/v1/users/{userId}/drafts/{draftId}/send`

### Path Parameters:

- `{userId}` (required): The user's email address or "me" to indicate the authenticated user.
- `{draftId}` (required): The ID of the draft to be sent.

### Request Body:

The request body should contain a JSON object with the following structure:

```json
{
    "message": {
        "raw": "base64url_encoded_message"
    }
}
```

- `message.raw` (required): The new MIME message content for the draft, encoded as a base64url string. This will replace the content of the draft before sending.
