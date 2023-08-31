## List Events

This API returns events on the specified calendar.

### Request

**HTTP Request**

```
GET https://www.googleapis.com/calendar/v3/calendars/{calendarId}/events
```

**Path Parameters**

- `calendarId` (string, required): Calendar identifier. To retrieve calendar IDs, you can call the `calendarList.list` method. If you want to access the primary calendar of the currently logged-in user, use the "primary" keyword.

**Optional Query Parameters**

- `alwaysIncludeEmail` (boolean): Deprecated and ignored. A value will always be returned in the email field for the organizer, creator, and attendees, even if no real email address is available (i.e. a generated, non-working value will be provided).
- `eventTypes` (string): Event types to return. Optional. Possible values are:
  - "default"
  - "focusTime"
  - "outOfOffice"
  - "workingLocation"
  
  This parameter can be repeated multiple times to return events of different types. The default is ["default", "focusTime", "outOfOffice"].
- `iCalUID` (string): Specifies an event ID in the iCalendar format to be provided in the response. Optional. Use this if you want to search for an event by its iCalendar ID.
- `maxAttendees` (integer): The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.
- `maxResults` (integer): Maximum number of events returned on one result page. The number of events in the resulting page may be less than this value, or none at all, even if there are more events matching the query. Incomplete pages can be detected by a non-empty `nextPageToken` field in the response. By default, the value is 250 events. The page size can never be larger than 2500 events. Optional.
- `orderBy` (string): The order of the events returned in the result. Optional. The default is an unspecified, stable order. Acceptable values are:
  - "startTime": Order by the start date/time (ascending). This is only available when querying single events.
  - "updated": Order by last modification time (ascending).
- `pageToken` (string): Token specifying which result page to return. Optional.
- ... and more

For the complete list of optional query parameters and their descriptions, please refer to the official Google Calendar API documentation.

### Authorization

This request allows authorization with at least one of the following scopes:

- `https://www.googleapis.com/auth/calendar.readonly`
- `https://www.googleapis.com/auth/calendar`
- `https://www.googleapis.com/auth/calendar.events.readonly`
- `https://www.googleapis.com/auth/calendar.events`

### Request Body

Do not supply a request body with this method.

### Response

If successful, this method returns a response body with the following structure:

```json
{
  "kind": "calendar#events",
  "etag": "etag",
  "summary": "string",
  "description": "string",
  "updated": "datetime",
  "timeZone": "string",
  "accessRole": "string",
  "defaultReminders": [
    {
      "method": "string",
      "minutes": "integer"
    }
  ],
  "nextPageToken": "string",
  "nextSyncToken": "string",
  "items": [
    {
      "event": "Resource"
    }
  ]
}
```