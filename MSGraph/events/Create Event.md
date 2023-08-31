# Create Event

Create the [event](../resources/Event.md) object.

### Request:
The request is [event](../resources/Event.md).




### Examples:

- **Create an event in my primary calendar called `Meeting with Team` on 2023-09-15 at 15:00 for an hour.**

#### Request

```http request
POST https://graph.microsoft.com/v1.0/me/events
Authorization: Bearer <Token>
Content-Type: application/json

{
  "subject": "Meeting with Team",
  "body": {
    "contentType": "HTML",
    "content": "Are you ready to join?"
  },
  "start": {
      "dateTime": "2023-09-15T15:30:00",
      "timeZone": "Asia/Kolkata"
  },
  "end": {
      "dateTime": "2023-09-15T17:00:00",
      "timeZone": "Asia/Kolkata"
  },
  "allowNewTimeProposals": true
}
```  

#### Response
```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('outlook_5096A72EAA569FCB%40outlook.com')/events/$entity",
    "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ6vw==\"",
    "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6ayAAAA",
    "createdDateTime": "2023-08-31T07:01:35.9638528Z",
    "lastModifiedDateTime": "2023-08-31T07:01:35.9975931Z",
    "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ6vw==",
    "categories": [],
    "transactionId": null,
    "originalStartTimeZone": "Asia/Kolkata",
    "originalEndTimeZone": "Asia/Kolkata",
    "iCalUId": "040000008200E00074C5B7101A82E008000000000D514CFBD8DBD901000000000000000010000000BB14E86A6C8A004FA282BF214885BBE7",
    "reminderMinutesBeforeStart": 15,
    "isReminderOn": true,
    "hasAttachments": false,
    "subject": "Meeting with Team",
    "bodyPreview": "Are you ready to join?",
    "importance": "normal",
    "sensitivity": "normal",
    "isAllDay": false,
    "isCancelled": false,
    "isOrganizer": true,
    "responseRequested": true,
    "seriesMasterId": null,
    "showAs": "busy",
    "type": "singleInstance",
    "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6ayAAAA&exvsurl=1&path=/calendar/item",
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
        "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nAre you ready to join?\r\n</body>\r\n</html>\r\n"
    },
    "start": {
        "dateTime": "2023-09-15T15:30:00.0000000",
        "timeZone": "Asia/Kolkata"
    },
    "end": {
        "dateTime": "2023-09-15T17:00:00.0000000",
        "timeZone": "Asia/Kolkata"
    },
    "location": {
        "displayName": "",
        "locationType": "default",
        "uniqueIdType": "unknown",
        "address": {},
        "coordinates": {}
    },
    "locations": [],
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

- **Create an event in my primary calendar called `Dinner at NewYork` with "Adele Vance" on 2023-10-01 at 20:00 for two hours.**
#### Request
```http request
POST https://graph.microsoft.com/v1.0/me/events
Authorization: Bearer <Token>
Content-Type: application/json

{
  "subject": "Dinner at NewYork",
  "body": {
    "contentType": "HTML",
    "content": "Will make it happy?"
  },
  "start": {
      "dateTime": "2023-10-01T20:00:00",
      "timeZone": "Asia/Kolkata"
  },
  "end": {
      "dateTime": "2023-10-01T22:00:00",
      "timeZone": "Asia/Kolkata"
  },
  "attendees": [
    {
      "emailAddress": {
        "address":"AdeleV@contoso.onmicrosoft.com",
        "name": "Adele Vance"
      },
      "type": "required"
    }
  ],
  "location":{
      "displayName": "NewYork",
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
  "allowNewTimeProposals": true
}
```  
#### Response
```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('outlook_5096A72EAA569FCB%40outlook.com')/events/$entity",
    "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ60g==\"",
    "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6azAAAA",
    "createdDateTime": "2023-08-31T07:30:26.5374046Z",
    "lastModifiedDateTime": "2023-08-31T07:30:26.5927114Z",
    "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ60g==",
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
        "dateTime": "2023-10-01T20:00:00.0000000",
        "timeZone": "Asia/Kolkata"
    },
    "end": {
        "dateTime": "2023-10-01T22:00:00.0000000",
        "timeZone": "Asia/Kolkata"
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



- ** Create an event with recurring date for every friday `Weekly status` for 30min
#### Request
```http request
POST https://graph.microsoft.com/v1.0/me/events
Authorization: Bearer <Token>
Content-Type: application/json

{
  "subject": "Weekly Status",
  "body": {
    "contentType": "HTML",
    "content": "Are you ready to join?"
  },
  "start": {
      "dateTime": "2023-09-01T15:00:00",
      "timeZone": "Asia/Kolkata"
  },
  "end": {
      "dateTime": "2023-09-01T15:30:00",
      "timeZone": "Asia/Kolkata"
  },
  "allowNewTimeProposals": true,
  "recurrence": {
    "pattern": {
      "type": "weekly",
      "interval": 1,
      "daysOfWeek": [ "Friday" ]
    },
    "range": {
      "type": "endDate",
      "startDate": "2023-09-04",
      "endDate": "2023-12-31"
    }
  }
}
```

#### Response
```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('outlook_5096A72EAA569FCB%40outlook.com')/events/$entity",
    "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ7Aw==\"",
    "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6a0AAAA",
    "createdDateTime": "2023-08-31T08:02:39.7508489Z",
    "lastModifiedDateTime": "2023-08-31T08:02:39.7987856Z",
    "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ7Aw==",
    "categories": [],
    "transactionId": null,
    "originalStartTimeZone": "Asia/Kolkata",
    "originalEndTimeZone": "Asia/Kolkata",
    "iCalUId": "040000008200E00074C5B7101A82E0080000000068791483E1DBD901000000000000000010000000464055E6AC94BB44B4F58BB2F26EAC65",
    "reminderMinutesBeforeStart": 15,
    "isReminderOn": true,
    "hasAttachments": false,
    "subject": "Weekly Status",
    "bodyPreview": "Are you ready to join?",
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
        "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nAre you ready to join?\r\n</body>\r\n</html>\r\n"
    },
    "start": {
        "dateTime": "2023-09-01T15:00:00.0000000",
        "timeZone": "Asia/Kolkata"
    },
    "end": {
        "dateTime": "2023-09-01T15:30:00.0000000",
        "timeZone": "Asia/Kolkata"
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
            "recurrenceTimeZone": "Asia/Kolkata",
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