## Delete Event

### Example User Prompt:

1. **Basic Delete**:
   - Delete the event titled "Team Meeting" scheduled for 2023-09-15 at 2:00 PM.
   - Remove the "Conference Call" event that is set for 10:30 AM on 2023-09-20.
   - Cancel the "Lunch with Clients" event scheduled at 12:00 PM on 2023-09-25.

2. **Specific Deletion**:
   - Delete the event with ID "abc12345" from the calendar.
   - Remove the event titled "Weekly Review" (event ID: "xyz98765") from the calendar.
   - Cancel the event with event ID "pqr54321" from the calendar.

3. **Notifications on Deletion**:
   - Delete the "Project Presentation" event and send notifications to all guests about the cancellation.
   - Remove the "Marketing Workshop" event from the calendar and notify external guests only.
   - Cancel the "Client Meeting" event and do not send any notifications about the deletion.

4. **Calendar-Specific Delete**:
   - Remove the event "Training Session" from the secondary calendar "Training Schedule".
   - Delete the event "Monthly Review" from the primary calendar "My Calendar".
   - Cancel the "Workshop" event from the shared calendar "Team Events".

In these prompts, you need to specify the `calendarId` and `eventId` as required path parameters for the delete request. Additionally, you can use the optional query parameters `sendNotifications` or `sendUpdates` to control whether notifications are sent to attendees when the event is deleted.

## Solution Steps:
1. Authenticate and set up access to the Google Calendar API.
2. For each delete prompt:
   - Retrieve the list of events from the calendar using the `events.list` API. Filter the events based on the provided event title or event ID.
   - Extract the `eventId` from the list of events that match the event title or event ID.
   - Use the `events.delete` API, providing the `calendarId` and `eventId` as path parameters, to delete the event from the calendar.
   - Optionally, use the `sendNotifications` query parameter to control whether notifications are sent to attendees about the event deletion.

### HTTP Request

DELETE `https://www.googleapis.com/calendar/v3/calendars/calendarId/events/eventId`

#### Parameters

| Parameter Name | Value | Description |
|-|-|-|
|***Path parameters***|||
|`calendarId`| string |Calendar identifier. To retrieve calendar IDs, call the `calendarList.list` method. If you want to access the primary calendar of the currently logged-in user, use the "primary" keyword.|
|`eventId`| string| Event identifier.|
|***Optional query parameters***|||
|`sendNotifications`| boolean |Deprecated. Please use `sendUpdates` instead. <br>&#8226;  Whether to send notifications about the deletion of the event. Note that some emails might still be sent even if you set the value to false. The default is false.|
|`sendUpdates`| string|Guests who should receive notifications about the deletion of the event. <br> **Acceptable values are:** <br>&#8226; `all` - Notifications are sent to all guests.<br>&#8226; `externalOnly` - Notifications are sent to non-Google Calendar guests only. <br>&#8226; `none` - No notifications are sent. For calendar migration tasks, consider using `Events.import` method instead.

#### Authorization

This request requires authorization with at least one of the following scopes:

- Scope: `https://www.googleapis.com/auth/calendar`
- Scope: `https://www.googleapis.com/auth/calendar.events`

For more information, see the authentication and authorization page.

#### Request Body

Do not supply a request body with this method.

## Response

If successful, this method returns an empty response body.

## Examples

**Python:**
```python
service.events().delete(calendarId='primary', eventId='eventId').execute()
```