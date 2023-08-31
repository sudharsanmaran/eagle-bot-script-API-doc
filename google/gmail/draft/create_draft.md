## Create Draft

### Example User Prompt:
**Required Parameters**: `subject`, `body`
**Optional Parameters**: `from`, `to`, `cc`, `bcc`


1. **Simplest Form**:
   - Create a draft email with the subject "Meeting Tomorrow" and the body "Hi, just a reminder about our meeting tomorrow."
   - Draft an email with subject "Quick Update" and body "Hey, I wanted to give you a quick update on the project."

2. **Specifying Recipient**:
   - Create a draft email addressed to "john.doe@example.com" with subject "Important Information" and body "John, please review the attached document."
   - Draft an email to "susan@example.com" with subject "Party Invitation" and body "Susan, you're invited to my birthday party!"

3. **Using Contact Names**:
   - Create a draft email for John with subject "Catch-up" and body "Hey John, long time no chat. How's everything going?"
   - Draft an email with subject "Hiking Trip" and body "Hi Sarah, are you up for a hiking trip this weekend?"

4. **Sender's Email Address**:
   - Create a draft email from "your.email@example.com" to "support@example.com" with subject "Query" and body "Hello, I have a question about your services."
   - Draft an email from "business@example.com" with subject "Product Order" and body "Dear customer, your order has been processed."

5. **Subject-Centric**:
   - Create a draft email with the subject "Lunch Tomorrow" and body "Hi, let's have lunch together tomorrow. What do you think?"
   - Draft an email with subject "Feedback Needed" and body "Hello team, I'd appreciate your feedback on the recent presentation."

6. **Combining Recipients**:
   - Create a draft email to "partners@example.com" and "colleague@example.com" with subject "Collaboration" and body "Dear partners and colleagues, let's discuss the upcoming project."
   - Draft an email from "me@example.com" to "friend@example.com" with subject "Weekend Plans" and body "Hey, any plans for the weekend?"

**HTTP Method**: POST

**Endpoint**: `https://www.googleapis.com/gmail/v1/users/{userId}/drafts`

### Path Parameters:

- `{userId}` (required): The user's email address or "me" to indicate the authenticated user.

### Request Body:

The request body should contain a JSON object with the following structure:

```json
{
    "message": {
        "raw": "base64url_encoded_message"
    }
}
```

- `message.raw` (required): The MIME message content of the draft, encoded as a base64url string. The MIME message must comply with RFC 2822.

### Response:

The response will contain the created draft object, including its ID and message metadata.
