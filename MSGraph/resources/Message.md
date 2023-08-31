# Message type
A message in a mailFolder.

The maximum total number of recipients included in the `toRecipients`, `ccRecipients`, and `bccRecipients` properties for a single email message sent from an Exchange Online mailbox is 500. For more information, see sending limits.

## Parameters
| Property                   | Type                                                         | Description                                                                                            |
|----------------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| bccRecipients              | [recipient](Recipient.md) collection                         | The Bcc: recipients for the message.                                                                   |
| body                       | [itemBody](ItemBody.md)                                      | The body of the message. It can be in HTML or text format. Find out about safe HTML in a message body. |
| bodyPreview                | String                                                       | The first 255 characters of the message body. It is in text format.                                    |
| categories                 | String collection                                            | The categories associated with the message.                                                            |
| ccRecipients               | [recipient](Recipient.md) collection                         | The Cc: recipients for the message.                                                                    |
| changeKey                  | String                                                       | The version of the message.                                                                            |
| conversationId             | String                                                       | The ID of the conversation the email belongs to.                                                       |
| conversationIndex          | Edm.Binary                                                   | Indicates the position of the message within the conversation.                                         |
| createdDateTime            | DateTimeOffset                                               | The date and time the message was created.                                                             |
| flag                       | [followupFlag](FollowupFlag.md)                              | The flag value that indicates the status, start date, due date, or completion date for the message.    |
| from                       | [recipient](Recipient.md)                                    | The owner of the mailbox from which the message is sent.                                               |
| hasAttachments             | Boolean                                                      | Indicates whether the message has attachments.                                                         |
| id                         | String                                                       | Unique identifier for the message.                                                                     |
| importance                 | importance                                                   | The importance of the message.                                                                         |
| inferenceClassification    | inferenceClassificationType                                  | The classification of the message for the user.                                                        |
| internetMessageHeaders     | [internetMessageHeader](InternetMessageHeader.md) collection | A collection of message headers defined by RFC5322.                                                    |
| internetMessageId          | String                                                       | The message ID in the format specified by RFC2822.                                                     |
| isDeliveryReceiptRequested | Boolean                                                      | Indicates whether a read receipt is requested for the message.                                         |
| isDraft                    | Boolean                                                      | Indicates whether the message is a draft.                                                              |
| isRead                     | Boolean                                                      | Indicates whether the message has been read.                                                           |
| isReadReceiptRequested     | Boolean                                                      | Indicates whether a read receipt is requested for the message.                                         |
| lastModifiedDateTime       | DateTimeOffset                                               | The date and time the message was last changed.                                                        |
| parentFolderId             | String                                                       | The unique identifier for the message's parent mailFolder.                                             |
| receivedDateTime           | DateTimeOffset                                               | The date and time the message was received.                                                            |
| replyTo                    | [recipient](Recipient.md) collection                         | The email addresses to use when replying.                                                              |
| sender                     | [recipient](Recipient.md)                                    | The account that is actually used to generate the message.                                             |
| sentDateTime               | DateTimeOffset                                               | The date and time the message was sent.                                                                |
| subject                    | String                                                       | The subject of the message.                                                                            |
| toRecipients               | [recipient](Recipient.md) collection                         | The To: recipients for the message.                                                                    |
| uniqueBody                 | [itemBody](ItemBody.md)                                      | The part of the body of the message that is unique to the current message.                             |
| webLink                    | String                                                       | The URL to open the message in Outlook on the web.                                                     |

## JSON representation
Here is a JSON representation of the resource

```http 
{
  "bccRecipients": [{"@odata.type": "microsoft.graph.recipient"}],
  "body": {"@odata.type": "microsoft.graph.itemBody"},
  "bodyPreview": "string",
  "categories": ["string"],
  "ccRecipients": [{"@odata.type": "microsoft.graph.recipient"}],
  "changeKey": "string",
  "conversationId": "string",
  "conversationIndex": "String (binary)",
  "createdDateTime": "String (timestamp)",
  "flag": {"@odata.type": "microsoft.graph.followupFlag"},
  "from": {"@odata.type": "microsoft.graph.recipient"},
  "hasAttachments": true,
  "id": "string (identifier)",
  "importance": "String",
  "inferenceClassification": "String",
  "internetMessageHeaders": [{"@odata.type": "microsoft.graph.internetMessageHeader"}],
  "internetMessageId": "String",
  "isDeliveryReceiptRequested": true,
  "isDraft": true,
  "isRead": true,
  "isReadReceiptRequested": true,
  "lastModifiedDateTime": "String (timestamp)",
  "parentFolderId": "string",
  "receivedDateTime": "String (timestamp)",
  "replyTo": [{"@odata.type": "microsoft.graph.recipient"}],
  "sender": {"@odata.type": "microsoft.graph.recipient"},
  "sentDateTime": "String (timestamp)",
  "subject": "string",
  "toRecipients": [{"@odata.type": "microsoft.graph.recipient"}],
  "uniqueBody": {"@odata.type": "microsoft.graph.itemBody"},
  "webLink": "string",

  "attachments": [{"@odata.type": "microsoft.graph.attachment"}],
  "extensions": [{"@odata.type": "microsoft.graph.extension"}],
  "multiValueExtendedProperties": [{"@odata.type": "microsoft.graph.multiValueLegacyExtendedProperty"}],
  "singleValueExtendedProperties": [{"@odata.type": "microsoft.graph.singleValueLegacyExtendedProperty"}]
}

```
