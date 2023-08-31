# Event type
## Properties

Here are the properties that you can use when creating or updating an event in an Outlook calendar. Some of these properties are optional and can be included in the request body to customize your event.
### Required Fields:

| Index | Property              | Type                                                       | Description                                                          |
|-------|-----------------------|------------------------------------------------------------|----------------------------------------------------------------------|
| 1     | allowNewTimeProposals | Boolean                                                    | True if the meeting organizer allows invitees to propose a new time. |
| 3     | body                  | [ItemBody](../resources/ItemBody.md)                       | The body of the message associated with the event.                   |
| 5     | end                   | [DateTimeTimeZone](../resources/DateTimeTimeZone.md)       | The date, time, and time zone that the event ends.                   |
| 11    | start                 | [DateTimeTimeZone](../resources/DateTimeTimeZone.md)       | The start date, time, and time zone of the event.                    |
| 12    | subject               | string                                                     | The text of the event's subject line.                                |

### Optional Fields:

| Index | Property                   | Type                                                       | Description                                                                  |
|-------|----------------------------|------------------------------------------------------------|------------------------------------------------------------------------------|
| 1     | bodyPreview                | string                                                     | The preview of the message associated with the event.                        |
| 2     | changeKey                  | string                                                     | Identifies the version of the event object.                                  |
| 3     | createdDateTime            | DateTimeOffset                                             | The timestamp when the event was created.                                    |
| 4     | hasAttachments             | Boolean                                                    | Set to true if the event has attachments.                                    |
| 5     | hideAttendees              | Boolean                                                    | When set to true, each attendee only sees themselves in the meeting request. |
| 6     | importance                 | string                                                     | The importance of the event.                                                 |
| 7     | isAllDay                   | Boolean                                                    | Set to true if the event lasts all day.                                      |
| 8     | isDraft                    | Boolean                                                    | Set to true if the user has updated the meeting but not sent updates.        |
| 9     | isOnlineMeeting            | Boolean                                                    | True if the event has online meeting information.                            |
| 10    | isOrganizer                | Boolean                                                    | Set to true if the calendar owner is the organizer of the event.             |
| 11    | isReminderOn               | Boolean                                                    | Set to true if an alert is set to remind the user of the event.              |
| 12    | lastModifiedDateTime       | DateTimeOffset                                             | The timestamp when the event was last modified.                              |
| 13    | location                   | [Location](../resources/Location.md)                       | The location of the event.                                                   |
| 14    | locations                  | [Location](../resources/Location.md) collection            | The locations where the event is held or attended from.                      |
| 15    | onlineMeeting              | [OnlineMeetingInfo](../resources/OnlineMeetingInfo.md)     | Details for an attendee to join the meeting online.                          |
| 16    | onlineMeetingProvider      | onlineMeetingProviderType                                  | Represents the online meeting service provider.                              |
| 17    | onlineMeetingUrl           | string                                                     | A URL for an online meeting.                                                 |
| 18    | originalEndTimeZone        | string                                                     | The end time zone when the event was created.                                |
| 19    | originalStart              | DateTimeOffset                                             | The start time of an event initially created in a recurring series.          |
| 20    | originalStartTimeZone      | string                                                     | The start time zone when the event was created.                              |
| 21    | reminderMinutesBeforeStart | Int32                                                      | The number of minutes before the event start time for the reminder.          |
| 22    | responseRequested          | Boolean                                                    | True if the organizer wants an invitee to send a response.                   |
| 23    | responseStatus             | [ResponseStatus](../resources/ResponseStatus.md)           | Indicates the type of response sent for an event message.                    |
| 24    | sensitivity                | string                                                     | Possible values: normal, personal, private, confidential.                    |
| 25    | seriesMasterId             | string                                                     | The ID for the recurring series master item.                                 |
| 26    | showAs                     | string                                                     | The status to show.                                                          |
| 27    | transactionId              | string                                                     | A custom identifier specified by a client app.                               |
| 28    | webLink                    | string                                                     | The URL to open the event in Outlook on the web.                             |
| 29    | iCalUId                    | string                                                     | A unique identifier for an event across calendars.                           |
| 30    | id                         | string                                                     | Unique identifier for the event.                                             |
| 31    | isCancelled                | Boolean                                                    | Set to true if the event has been canceled.                                  |
| 32    | type                       | string                                                     | The event type.                                                              |
| 33    | originalStartTimeZone      | string                                                     | The start time zone that was set when the event was created.                 |
| 34    | recurrence                 | [PatternedRecurrence](../resources/PatternedRecurrence.md) | The recurrence pattern for the event.                                        |
| 35    | categories                 | string collection                                          | The categories associated with the event.                                    |
| 36    | attendees                  | [Attendee](../resources/Attendee.md) collection            | The collection of attendees for the event.                                   |

## JSON representation
Here is a JSON representation of the resource

```http 
{
  "allowNewTimeProposals": "Boolean",
  "attendees": [{"@odata.type": "Attendee"}],
  "body": {"@odata.type": "microsoft.graph.itemBody"},
  "bodyPreview": "string",
  "categories": ["string"],
  "changeKey": "string",
  "createdDateTime": "string (timestamp)",
  "end": {"@odata.type": "DateTimeTimeZone"},
  "hasAttachments": true,
  "hideAttendees": false,
  "id": "string (identifier)",
  "importance": "string",
  "isAllDay": true,
  "isCancelled": true,
  "isDraft": false,
  "isOnlineMeeting": true,
  "isOrganizer": true,
  "isReminderOn": true,
  "lastModifiedDateTime": "string (timestamp)",
  "location": {"@odata.type": "Location"},
  "locations": [{"@odata.type": "Location"}],
  "onlineMeeting": {"@odata.type": "OnlineMeetingInfo"},
  "onlineMeetingProvider": "string",
  "onlineMeetingUrl": "string",
  "organizer": {"@odata.type": "Recipient"},
  "originalEndTimeZone": "string",
  "originalStart": "string (timestamp)",
  "originalStartTimeZone": "string",
  "recurrence": {"@odata.type": "PatternedRecurrence"},
  "reminderMinutesBeforeStart": 1024,
  "responseRequested": true,
  "responseStatus": {"@odata.type": "ResponseStatus"},
  "sensitivity": "string",
  "seriesMasterId": "string",
  "showAs": "string",
  "start": {"@odata.type": "DateTimeTimeZone"},
  "subject": "string",
  "type": "string",
  "webLink": "string"
}
```
