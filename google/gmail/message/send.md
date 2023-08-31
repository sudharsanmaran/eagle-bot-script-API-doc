## Sending Messages

Once you have created an email message, you can send it by supplying it in the request body of a call to the `messages.send` endpoint, as demonstrated in the following example.


### Example User Prompts:

1. **Sending a Basic Email**:
   - Send a simple email with the subject "Hello" to "john.doe@example.com".
   - Compose an email saying "Meeting Tomorrow at 2 PM" and send it to "team@example.com".
   - Send an email to "friend@example.com" with the subject "Check out this link" and the link to a website.

2. **Sending an Email to Multiple Recipients**:
   - Send an announcement email to both "team@example.com" and "managers@example.com".
   - Email a project update to "project-team@example.com" and "project-manager@example.com".
   - Send a party invitation to "friends@example.com" and "family@example.com".

3. **Sending an Email with CC and BCC**:
   - Send an email to "client@example.com" with a copy to "account-manager@example.com".
   - Email a report to "supervisor@example.com" with a blind copy to "director@example.com".
   - Compose an email with CC to "colleague@example.com" and BCC to "personal-archive@example.com".

Feel free to replace the email addresses, subjects, content, and other details to match your specific use case. Additionally, ensure you have the necessary Gmail API credentials and setup to make these API requests.

### Request

**HTTP Request**

```
POST https://www.googleapis.com/gmail/v1/users/me/messages/send
```

**Path Parameters**

No path parameters are required for this endpoint.

### Authorization

This request requires authorization with one of the following scopes:

- `https://www.googleapis.com/auth/gmail.compose`
- `https://www.googleapis.com/auth/gmail.send`

For more information, see the authentication and authorization documentation.

### Request Body

In the request body, supply a JSON object with the following property:

- `raw` (string): The base64url-encoded MIME message. This is the content of the email message you want to send.

**Example Request Body**

```json
{
  "raw": "base64_encoded_mime_message"
}
```

### Response

If successful, this method returns a response body with a message resource containing information about the sent email.

**Example Response Body**

```json
{
  "id": "message_id",
  "threadId": "thread_id",
  "labelIds": [
    "INBOX"
  ],
  "snippet": "Message snippet",
  "historyId": "history_id",
  "internalDate": "timestamp",
  "payload": {
    "partId": "",
    "mimeType": "multipart/mixed",
    "filename": "",
    "headers": [
      {
        "name": "Header Name",
        "value": "Header Value"
      }
    ],
    "body": {
      "attachmentId": "",
      "size": 0
    },
    "parts": [
      {
        "partId": "part_id",
        "mimeType": "text/plain",
        "filename": "",
        "headers": [
          {
            "name": "Header Name",
            "value": "Header Value"
          }
        ],
        "body": {
          "attachmentId": "",
          "size": 0,
          "data": "base64_encoded_data"
        }
      }
    ]
  },
  "sizeEstimate": 0,
  "raw": "base64_encoded_raw_message"
}
```

Please note that the response structure may include additional fields and details depending on the content of the sent email message.

### Example

Here's an example of how to use this method in Python using the Google API client library:

```python
from googleapiclient.discovery import build
from google.auth import default
import base64
from email.message import EmailMessage

def gmail_send_message():
    creds, _ = default()

    try:
        service = build('gmail', 'v1', credentials=creds)
        message = EmailMessage()

        message.set_content('This is automated draft mail')

        message['To'] = 'gduser1@workspacesamples.dev'
        message['From'] = 'gduser2@workspacesamples.dev'
        message['Subject'] = 'Automated draft'

        # encoded message
        encoded_message = base64.urlsafe_b64encode(message.as_bytes()).decode()

        create_message = {
            'raw': encoded_message
        }

        send_message = service.users().messages().send(userId="me", body=create_message).execute()
        print(F'Message Id: {send_message["id"]}')
    except HttpError as error:
        print(F'An error occurred: {error}')
        send_message = None
    return send_message

if __name__ == '__main__':
    gmail_send_message()
```