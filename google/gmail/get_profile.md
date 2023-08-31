## HTTP Request

**GET** `https://gmail.googleapis.com/gmail/v1/users/{userId}/profile`

*The URL uses gRPC Transcoding syntax.*

### Path Parameters

#### Parameters

- `userId`: string
  - The user's email address. The special value `me` can be used to indicate the authenticated user.

### Request Body

The request body must be empty.

### Response Body

Profile for a Gmail user.

If successful, the response body contains data with the following structure:

```json
{
  "emailAddress": string,
  "messagesTotal": integer,
  "threadsTotal": integer,
  "historyId": string
}
```

**Fields**

- `emailAddress`: string
  - The user's email address.
- `messagesTotal`: integer
  - The total number of messages in the mailbox.
- `threadsTotal`: integer
  - The total number of threads in the mailbox.
- `historyId`: string
  - The ID of the mailbox's current history record.

### Authorization Scopes

Requires one of the following OAuth scopes:

- `https://mail.google.com/`
- `https://www.googleapis.com/auth/gmail.modify`
- `https://www.googleapis.com/auth/gmail.compose`
- `https://www.googleapis.com/auth/gmail.readonly`
- `https://www.googleapis.com/auth/gmail.metadata`