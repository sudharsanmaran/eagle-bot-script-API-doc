# Create Event

Create the [event](../resources/Event.md) object.

### Request:
The request is [event](../resources/Event.md).

```http 
POST https://graph.microsoft.com/v1.0/me/events
Prefer: outlook.timezone="Pacific Standard Time"
Content-type: application/json

{
  "subject": "Prep for customer meeting",
  "body": {
    "contentType": "HTML",
    "content": "Does this time work for you?"
  },
  "start": {
      "dateTime": "2019-11-20T13:00:00",
      "timeZone": "Pacific Standard Time"
  },
  "end": {
      "dateTime": "2019-11-20T14:00:00",
      "timeZone": "Pacific Standard Time"
  },
  "location":{
      "displayName":"Cordova conference room"
  },
  "attendees": [
    {
      "emailAddress": {
        "address":"AdeleV@contoso.OnMicrosoft.com",
        "name": "Adele Vance"
      },
      "type": "required"
    }
  ],
  "isOnlineMeeting": true,
  "onlineMeetingProvider": "teamsForBusiness"
}
```

## Response

```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('64339082-ed84-4b0b-b4ab-004ae54f3747')/events/$entity",
    "@odata.etag": "W/\"NEXywgsVrkeNsFsyVyRrtAAASBUEsA==\"",
    "id": "AAMkADAAABIGYDZAAA=",
    "createdDateTime": "2019-11-15T01:55:54.8022848Z",
    "lastModifiedDateTime": "2019-11-15T01:55:56.5162924Z",
    "changeKey": "NEXywgsVrkeNsFsyVyRrtAAASBUEsA==",
    "categories": [],
    "originalStartTimeZone": "Pacific Standard Time",
    "originalEndTimeZone": "Pacific Standard Time",
    "iCalUId": "040000008200E00074C5B7101A82E0080000000076B29D94B32CD6010000000000000000100000005F31C591C3C328459653D025BD277439",
    "reminderMinutesBeforeStart": 15,
    "isReminderOn": true,
    "hasAttachments": false,
    "subject": "Prep for customer meeting",
    "bodyPreview": "Does this time work for you?\r\n________________________________________________________________________________\r\nJoin Microsoft Teams Meeting\r\n+1 323-555-0166   United States, Los Angeles (Toll)\r\nConference ID: 291 633 251#\r\nLocal numbers | Reset PIN | Lea",
    "importance": "normal",
    "sensitivity": "normal",
    "isAllDay": false,
    "isCancelled": false,
    "isOrganizer": true,
    "responseRequested": true,
    "seriesMasterId": null,
    "showAs": "busy",
    "type": "singleInstance",
    "webLink": "https://outlook.office365.com/owa/?itemid=AAMkADAABIGYDZAAA%3D&exvsurl=1&path=/calendar/item",
    "onlineMeetingUrl": null,
    "isOnlineMeeting": true,
    "onlineMeetingProvider": "teamsForBusiness",
    "allowNewTimeProposals": true,
    "recurrence": null,
    "responseStatus": {
        "response": "organizer",
        "time": "0001-01-01T00:00:00Z"
    },
    "body": {
        "contentType": "html",
        "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n<meta content=\"text/html; charset=us-ascii\">\r\n</head>\r\n<body>\r\nDoes this time work for you?\r\n<div style=\"width:100%; height:20px\"><span style=\"white-space:nowrap; color:gray; opacity:.36\">________________________________________________________________________________</span>\r\n</div>\r\n<div class=\"me-email-text\" style=\"color:#252424; font-family:'Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif\">\r\n<div style=\"margin-top:24px; margin-bottom:10px\"><a class=\"me-email-headline\" href=\"https://teams.microsoft.com/l/meetup-join/19%3ameeting_ODkyNWFmNGYtZjBjYS00MDdlLTllOWQtN2E3MzJlNjM0ZWRj%40thread.v2/0?context=%7b%22Tid%22%3a%2298a79ebe-74bf-4e07-a017-7b410848cb32%22%2c%22Oid%22%3a%2264339082-ed84-4b0b-b4ab-004ae54f3747%22%7d\" target=\"_blank\" rel=\"noreferrer noopener\" style=\"font-size:18px; font-family:'Segoe UI Semibold','Segoe UI','Helvetica Neue',Helvetica,Arial,sans-serif; text-decoration:underline; color:#6264a7\">Join\r\n Microsoft Teams Meeting</a> </div>\r\n<div>\r\n<div><a class=\"me-email-link\" href=\"tel:&#43;1 323-886-7531,,291633251# \" target=\"_blank\" rel=\"noreferrer noopener\" style=\"font-size:14px; text-decoration:none; color:#6264a7\">&#43;1 323-886-7531</a>\r\n<span style=\"font-size:12px\">&nbsp; United States, Los Angeles (Toll) </span></div>\r\n</div>\r\n<div style=\"margin-top:10px; margin-bottom:20px\"><span style=\"font-size:12px\">Conference ID:\r\n</span><span style=\"font-size:14px\">291 633 251# </span></div>\r\n<div style=\"margin-bottom:24px\"><a class=\"me-email-link\" target=\"_blank\" href=\"https://dialin.teams.microsoft.com/1f9a0550-737c-41bd-8c7d-4c81dc1c4070?id=291633251\" rel=\"noreferrer noopener\" style=\"font-size:12px; text-decoration:none; color:#6264a7\">Local\r\n numbers</a> | <a class=\"me-email-link\" target=\"_blank\" href=\"https://mysettings.lync.com/pstnconferencing\" rel=\"noreferrer noopener\" style=\"font-size:12px; text-decoration:none; color:#6264a7\">\r\nReset PIN</a> | <a class=\"me-email-link\" target=\"_blank\" href=\"https://aka.ms/JoinTeamsMeeting\" rel=\"noreferrer noopener\" style=\"font-size:12px; text-decoration:none; color:#6264a7\">\r\nLearn more about Teams</a> | <a class=\"me-email-link\" target=\"_blank\" href=\"https://teams.microsoft.com/meetingOptions/?organizerId=64339082-ed84-4b0b-b4ab-004ae54f3747&amp;tenantId=98a79ebe-74bf-4e07-a017-7b410848cb32&amp;threadId=19_meeting_ODkyNWFmNGYtZjBjYS00MDdlLTllOWQtN2E3MzJlNjM0ZWRj@thread.v2&amp;messageId=0&amp;language=en-US\" rel=\"noreferrer noopener\" style=\"font-size:12px; text-decoration:none; color:#6264a7\">\r\nMeeting options</a> </div>\r\n<div style=\"font-size:14px; margin-bottom:4px\"></div>\r\n<div style=\"font-size:12px\"></div>\r\n</div>\r\n<div style=\"width:100%; height:20px\"><span style=\"white-space:nowrap; color:gray; opacity:.36\">________________________________________________________________________________</span>\r\n</div>\r\n</body>\r\n</html>\r\n"
    },
    "start": {
        "dateTime": "2019-11-20T13:00:00.0000000",
        "timeZone": "Pacific Standard Time"
    },
    "end": {
        "dateTime": "2019-11-20T14:00:00.0000000",
        "timeZone": "Pacific Standard Time"
    },
    "location": {
        "displayName": "Cordova conference room",
        "locationType": "default",
        "uniqueId": "Cordova conference room",
        "uniqueIdType": "private"
    },
    "locations": [
        {
            "displayName": "Cordova conference room",
            "locationType": "default",
            "uniqueId": "Cordova conference room",
            "uniqueIdType": "private"
        }
    ],
    "attendees": [
        {
            "type": "required",
            "status": {
                "response": "none",
                "time": "0001-01-01T00:00:00Z"
            },
            "emailAddress": {
                "name": "Adele Vance",
                "address": "AdeleV@contoso.OnMicrosoft.com"
            }
        }
    ],
    "organizer": {
        "emailAddress": {
            "name": "Alex Wilber",
            "address": "AlexW@contoso.OnMicrosoft.com"
        }
    },
    "onlineMeeting": {
        "joinUrl": "https://teams.microsoft.com/l/meetup-join/19%3ameeting_ODkyNWFmNGYtZjBjYS00MDdlLTllOWQtN2E3MzJlNjM0ZWRj%40thread.v2/0?context=%7b%22Tid%22%3a%2298a79ebe-74bf-4e07-a017-7b410848cb32%22%2c%22Oid%22%3a%2264339082-ed84-4b0b-b4ab-004ae54f3747%22%7d",
        "conferenceId": "291633251",
        "tollNumber": "+1 323-555-0166"
    }
}
```


## Examples with required data

### Request
```http 
{
  "allowNewTimeProposals": true,
  "attendees": [{
  "emailAddress": {
    "address": "john.doe@example.com",
    "name": "John Doe"
  },
  "status": {
    "response": "accepted",
    "time": "2023-08-28T10:00:00Z"
  },
  "type": "required"
}],
  "body": {
  "emailAddress": {
    "address": "john.doe@example.com",
    "name": "John Doe"
  },
  "status": {
    "response": "accepted",
    "time": "2023-08-28T10:00:00Z"
  },
  "type": "required"
},
  "categories": [],
  "end": {
  "dateTime": "2017-08-29T04:00:00.0000000",
  "timeZone": "Asia/Kolkata"
},
  "iCalUId": "unique_id_here",
  "id": "1",
  "isCancelled": false,
  "originalStartTimeZone": "Asia/Kolkata",
  "recurrence": {
    "pattern": {
      "type": "weekly",
      "interval": 1,
      "daysOfWeek": [ "Monday" ]
    },
    "range": {
      "type": "endDate",
      "startDate": "2017-09-04",
      "endDate": "2017-12-31"
    }
  },
  "start": {
  "dateTime": "2017-08-27T04:00:00.0000000",
  "timeZone": "Asia/Kolkata"
},
  "subject": "Event Subject Here",
  "type": "event_type_here"
}
```



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

- **Create an event in my primary calendar called `Dinner at NewYork` with "Adele Vance" on 2023-10-00 at 20:00 for two hours.**
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
      "dateTime": "2023-09-15T15:30:00",
      "timeZone": "Asia/Kolkata"
  },
  "end": {
      "dateTime": "2023-09-15T17:00:00",
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
        "dateTime": "2023-09-15T15:30:00.0000000",
        "timeZone": "Asia/Kolkata"
    },
    "end": {
        "dateTime": "2023-09-15T17:00:00.0000000",
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
      "dateTime": "2023-09-15T15:30:00",
      "timeZone": "Asia/Kolkata"
  },
  "end": {
      "dateTime": "2023-09-15T17:00:00",
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
        "dateTime": "2023-09-08T15:30:00.0000000",
        "timeZone": "Asia/Kolkata"
    },
    "end": {
        "dateTime": "2023-09-08T17:00:00.0000000",
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