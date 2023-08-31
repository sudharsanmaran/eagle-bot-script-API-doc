# Update Event 
Update the properties of the [event](../resources/Event.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission   type                      | Permissions (from least to most privileged) |
|----------------------------------------|---------------------------------------------|
| Delegated (work or school account)     | Calendars.ReadWrite                         |
| Delegated (personal Microsoft account) | Calendars.ReadWrite                         |
| Application	                           | Calendars.ReadWrite                         |

## HTTP request
```http 
PATCH /me/events/{id}
PATCH /users/{id | userPrincipalName}/events/{id}
PATCH /groups/{id}/events/{id}

PATCH /me/calendar/events/{id}
PATCH /users/{id | userPrincipalName}/calendar/events/{id}
PATCH /groups/{id}/calendar/events/{id}

PATCH /me/calendars/{id}/events/{id}
PATCH /users/{id | userPrincipalName}/calendars/{id}/events/{id}

PATCH /me/calendarGroups/{id}/calendars/{id}/events/{id}
PATCH /users/{id | userPrincipalName}/calendarGroups/{id}/calendars/{id}/events/{id}
```

## Request headers

| Name          | Type   | Description               |
|---------------|--------|---------------------------|
| Authorization | string | Bearer {token}. Required. |

## Request body
The request object is [event](../resources/Event.md).



### Examples

- **Updating the `Dinner at NewYork` from 5:30 IST to 5:00 IST**
#### Request
```http request
PATCH  https://graph.microsoft.com/v1.0/me/events/<id>
Authorization: Bearer <Token>
Content-Type: application/json

{
  "end": {
      "dateTime": "2023-09-15T17:00:00",
      "timeZone": "Asia/Kolkata"
  }
}
```

#### Response 
```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('outlook_5096A72EAA569FCB%40outlook.com')/events/$entity",
    "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ61A==\"",
    "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6azAAAA",
    "createdDateTime": "2023-08-31T07:30:26.5374046Z",
    "lastModifiedDateTime": "2023-08-31T07:30:27.3346261Z",
    "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ61A==",
    "categories": [],
    "transactionId": null,
    "originalStartTimeZone": "Asia/Kolkata",
    "originalEndTimeZone": "Asia/Kolkata",
    "iCalUId": "040000008200E00074C5B7101A82E0080000000064C1CB02DDDBD901000000000000000010000000D21AD22100DC964286BB270BE067B565",
    "reminderMinutesBeforeStart": 15,
    "isReminderOn": true,
    "hasAttachments": false,
    "subject": "Dinner at NewYork",
    "bodyPreview": "Will make it happy?",
    "importance": "normal",
    "sensitivity": "normal",
    "isAllDay": false,
    "isCancelled": false,
    "isOrganizer": true,
    "responseRequested": true,
    "seriesMasterId": null,
    "showAs": "busy",
    "type": "singleInstance",
    "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6azAAAA&exvsurl=1&path=/calendar/item",
    "onlineMeetingUrl": null,
    "isOnlineMeeting": false,
    "onlineMeetingProvider": "unknown",
    "allowNewTimeProposals": true,
    "occurrenceId": null,
    "isDraft": false,
    "hideAttendees": false,
    "responseStatus": {
        "response": "organizer",
        "time": "0001-01-01T00:00:00Z"
    },
    "body": {
        "contentType": "html",
        "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nWill make it happy?\r\n</body>\r\n</html>\r\n"
    },
    "start": {
        "dateTime": "2023-09-15T10:00:00.0000000",
        "timeZone": "UTC"
    },
    "end": {
        "dateTime": "2023-09-15T11:30:00.0000000",
        "timeZone": "UTC"
    },
    "location": {
        "displayName": "NewYork",
        "locationUri": "",
        "locationType": "default",
        "uniqueId": "NewYork",
        "uniqueIdType": "private",
        "address": {
            "street": "4567 Main St",
            "city": "Redmond",
            "state": "NY",
            "countryOrRegion": "US",
            "postalCode": "32008"
        },
        "coordinates": {
            "latitude": 47.672,
            "longitude": -102.103
        }
    },
    "locations": [
        {
            "displayName": "NewYork",
            "locationUri": "",
            "locationType": "default",
            "uniqueId": "NewYork",
            "uniqueIdType": "private",
            "address": {
                "street": "4567 Main St",
                "city": "Redmond",
                "state": "NY",
                "countryOrRegion": "US",
                "postalCode": "32008"
            },
            "coordinates": {
                "latitude": 47.672,
                "longitude": -102.103
            }
        }
    ],
    "recurrence": null,
    "attendees": [],
    "organizer": {
        "emailAddress": {
            "name": "Teja Chowdary",
            "address": "outlook_5096A72EAA569FCB@outlook.com"
        }
    },
    "onlineMeeting": null
}
```
		
- **Updating the `Weekly Status` to `Weekly Status Updated!` and updating the content.
#### Request
```http request
PATCH  https://graph.microsoft.com/v1.0/me/events/<id>
Authorization: Bearer <Token>
Content-Type: application/json

{
  "subject": "Weekly Status Updated!",
  "body": {
    "contentType": "HTML",
    "content": "Please confirm if you are joining or not?"
  }
}
```

#### Response
```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('outlook_5096A72EAA569FCB%40outlook.com')/events/$entity",
    "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ9TA==\"",
    "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6a0AAAA",
    "createdDateTime": "2023-08-31T08:02:39.7508489Z",
    "lastModifiedDateTime": "2023-08-31T09:21:36.1238969Z",
    "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ9TA==",
    "categories": [],
    "transactionId": null,
    "originalStartTimeZone": "Asia/Kolkata",
    "originalEndTimeZone": "Asia/Kolkata",
    "iCalUId": "040000008200E00074C5B7101A82E0080000000068791483E1DBD901000000000000000010000000464055E6AC94BB44B4F58BB2F26EAC65",
    "reminderMinutesBeforeStart": 15,
    "isReminderOn": true,
    "hasAttachments": false,
    "subject": "Weekly Status Updated!",
    "bodyPreview": "Please confirm if you are joining or not?",
    "importance": "normal",
    "sensitivity": "normal",
    "isAllDay": false,
    "isCancelled": false,
    "isOrganizer": true,
    "responseRequested": true,
    "seriesMasterId": null,
    "showAs": "busy",
    "type": "seriesMaster",
    "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6a0AAAA&exvsurl=1&path=/calendar/item",
    "onlineMeetingUrl": null,
    "isOnlineMeeting": false,
    "onlineMeetingProvider": "unknown",
    "allowNewTimeProposals": true,
    "occurrenceId": null,
    "isDraft": false,
    "hideAttendees": false,
    "responseStatus": {
        "response": "organizer",
        "time": "0001-01-01T00:00:00Z"
    },
    "body": {
        "contentType": "html",
        "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nPlease confirm if you are joining or not?\r\n</body>\r\n</html>\r\n"
    },
    "start": {
        "dateTime": "2023-09-08T10:00:00.0000000",
        "timeZone": "UTC"
    },
    "end": {
        "dateTime": "2023-09-08T11:30:00.0000000",
        "timeZone": "UTC"
    },
    "location": {
        "displayName": "",
        "locationType": "default",
        "uniqueIdType": "unknown",
        "address": {},
        "coordinates": {}
    },
    "locations": [],
    "recurrence": {
        "pattern": {
            "type": "weekly",
            "interval": 1,
            "month": 0,
            "dayOfMonth": 0,
            "daysOfWeek": [
                "friday"
            ],
            "firstDayOfWeek": "sunday",
            "index": "first"
        },
        "range": {
            "type": "endDate",
            "startDate": "2023-09-08",
            "endDate": "2023-12-31",
            "recurrenceTimeZone": "India Standard Time",
            "numberOfOccurrences": 0
        }
    },
    "attendees": [],
    "organizer": {
        "emailAddress": {
            "name": "Teja Chowdary",
            "address": "outlook_5096A72EAA569FCB@outlook.com"
        }
    },
    "onlineMeeting": null
}
```