# List Events
Get the event list from the containing calendar.


## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type                        | Permissions (from least to most privileged) |
|----------------------------------------|---------------------------------------------|
| Delegated (work or school account)     | Calendars.ReadWrite                         |
| Delegated (personal Microsoft account) | Calendars.ReadWrite                         |
| Application                            | Calendars.ReadWrite                         |

## Request 

```http 
GET https://graph.microsoft.com/v1.0/me/events
```

### Request headers

| Name          | Type   | Description               |
|---------------|--------|---------------------------|
| Authorization | string | Bearer {token}. Required. |

### Request body
Do not supply a request body for this method.

## Response
If successful, this method returns 200 and returns full list.

### Response Body
```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('outlook_5096A72EAA569FCB%40outlook.com')/events",
    "value": [
        {
            "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ7BQ==\"",
            "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6a0AAAA",
            "createdDateTime": "2023-08-31T08:02:39.7508489Z",
            "lastModifiedDateTime": "2023-08-31T08:02:43.3694799Z",
            "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ7BQ==",
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
            "onlineMeeting": null,
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        },
        {
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
            "onlineMeeting": null,
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        },
        {
            "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ6ug==\"",
            "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6axAAAA",
            "createdDateTime": "2023-08-31T06:54:21.3383513Z",
            "lastModifiedDateTime": "2023-08-31T06:54:22.5345558Z",
            "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ6ug==",
            "categories": [],
            "transactionId": null,
            "originalStartTimeZone": "Asia/Kolkata",
            "originalEndTimeZone": "Asia/Kolkata",
            "iCalUId": "040000008200E00074C5B7101A82E008000000003D2C3CF8D7DBD901000000000000000010000000620513B35CF3D04E949850A286FD1550",
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
            "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6axAAAA&exvsurl=1&path=/calendar/item",
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
                "dateTime": "2023-09-15T10:00:00.0000000",
                "timeZone": "UTC"
            },
            "end": {
                "dateTime": "2023-09-15T11:30:00.0000000",
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
            "recurrence": null,
            "attendees": [],
            "organizer": {
                "emailAddress": {
                    "name": "Teja Chowdary",
                    "address": "outlook_5096A72EAA569FCB@outlook.com"
                }
            },
            "onlineMeeting": null,
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        },
        {
            "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ6pw==\"",
            "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6awAAAA",
            "createdDateTime": "2023-08-31T06:33:23.3241073Z",
            "lastModifiedDateTime": "2023-08-31T06:33:24.9433211Z",
            "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ6pw==",
            "categories": [],
            "transactionId": null,
            "originalStartTimeZone": "Asia/Kolkata",
            "originalEndTimeZone": "Asia/Kolkata",
            "iCalUId": "040000008200E00074C5B7101A82E00800000000E336680AD5DBD9010000000000000000100000002B624DF06274EF41ADEEE653C988B2F6",
            "reminderMinutesBeforeStart": 15,
            "isReminderOn": true,
            "hasAttachments": false,
            "subject": "Let's go for lunch",
            "bodyPreview": "Does noon work for you?",
            "importance": "normal",
            "sensitivity": "normal",
            "isAllDay": false,
            "isCancelled": false,
            "isOrganizer": true,
            "responseRequested": true,
            "seriesMasterId": null,
            "showAs": "busy",
            "type": "singleInstance",
            "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6awAAAA&exvsurl=1&path=/calendar/item",
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
                "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nDoes noon work for you?\r\n</body>\r\n</html>\r\n"
            },
            "start": {
                "dateTime": "2023-08-31T09:30:00.0000000",
                "timeZone": "UTC"
            },
            "end": {
                "dateTime": "2023-08-31T10:30:00.0000000",
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
            "recurrence": null,
            "attendees": [
                {
                    "type": "required",
                    "status": {
                        "response": "none",
                        "time": "0001-01-01T00:00:00Z"
                    },
                    "emailAddress": {
                        "name": "Samantha Booth",
                        "address": "samanthab@contoso.onmicrosoft.com"
                    }
                }
            ],
            "organizer": {
                "emailAddress": {
                    "name": "Teja Chowdary",
                    "address": "outlook_5096A72EAA569FCB@outlook.com"
                }
            },
            "onlineMeeting": null,
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        },
        {
            "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ6jg==\"",
            "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6avAAAA",
            "createdDateTime": "2023-08-31T06:31:49.0140609Z",
            "lastModifiedDateTime": "2023-08-31T06:31:50.4536057Z",
            "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ6jg==",
            "categories": [],
            "transactionId": "7E163156-7762-4BEB-A1C6-729EA81755A7",
            "originalStartTimeZone": "Pacific Standard Time",
            "originalEndTimeZone": "Pacific Standard Time",
            "iCalUId": "040000008200E00074C5B7101A82E00800000000B5792FD2D4DBD9010000000000000000100000001A4CD2FC97312041B967516384911270",
            "reminderMinutesBeforeStart": 15,
            "isReminderOn": true,
            "hasAttachments": false,
            "subject": "Let's go for lunch",
            "bodyPreview": "Does noon work for you?",
            "importance": "normal",
            "sensitivity": "normal",
            "isAllDay": false,
            "isCancelled": false,
            "isOrganizer": true,
            "responseRequested": true,
            "seriesMasterId": null,
            "showAs": "busy",
            "type": "singleInstance",
            "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6avAAAA&exvsurl=1&path=/calendar/item",
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
                "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nDoes noon work for you?\r\n</body>\r\n</html>\r\n"
            },
            "start": {
                "dateTime": "2017-04-15T19:00:00.0000000",
                "timeZone": "UTC"
            },
            "end": {
                "dateTime": "2017-04-15T21:00:00.0000000",
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
            "recurrence": null,
            "attendees": [
                {
                    "type": "required",
                    "status": {
                        "response": "none",
                        "time": "0001-01-01T00:00:00Z"
                    },
                    "emailAddress": {
                        "name": "Samantha Booth",
                        "address": "samanthab@contoso.onmicrosoft.com"
                    }
                }
            ],
            "organizer": {
                "emailAddress": {
                    "name": "Teja Chowdary",
                    "address": "outlook_5096A72EAA569FCB@outlook.com"
                }
            },
            "onlineMeeting": null,
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        },
        {
            "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ6+g==\"",
            "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6atAAAA",
            "createdDateTime": "2023-08-31T06:17:53.1737632Z",
            "lastModifiedDateTime": "2023-08-31T07:58:27.5027652Z",
            "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ6+g==",
            "categories": [],
            "transactionId": null,
            "originalStartTimeZone": "Pacific Standard Time",
            "originalEndTimeZone": "Pacific Standard Time",
            "iCalUId": "040000008200E00074C5B7101A82E00800000000F1EBFDDFD2DBD901000000000000000010000000C715E113149CA341937C78A61533CD86",
            "reminderMinutesBeforeStart": 15,
            "isReminderOn": true,
            "hasAttachments": false,
            "subject": "Let's go for lunch",
            "bodyPreview": "Does noon work for you?\r\n.........................................................................................................................................\r\nJoin online meeting\r\n......................................................................",
            "importance": "normal",
            "sensitivity": "normal",
            "isAllDay": false,
            "isCancelled": false,
            "isOrganizer": true,
            "responseRequested": true,
            "seriesMasterId": null,
            "showAs": "busy",
            "type": "singleInstance",
            "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6atAAAA&exvsurl=1&path=/calendar/item",
            "onlineMeetingUrl": "https://join.skype.com/r5UHzBJzAXyC",
            "isOnlineMeeting": true,
            "onlineMeetingProvider": "skypeForConsumer",
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
                "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nDoes noon work for you?<br>\r\n<font face=\"Calibri\" size=\"1\" color=\"#404040\"><span style=\"\">.........................................................................................................................................</span></font><br>\r\n<font face=\"Calibri\" size=\"4\"><span style=\"font-size:16pt\"><a href=\"https://join.skype.com/r5UHzBJzAXyC\">Join online meeting</a></span></font><br>\r\n<font face=\"Calibri\" size=\"1\" color=\"#404040\"><span style=\"font-size:8pt\">.........................................................................................................................................</span></font><br>\r\n</body>\r\n</html>\r\n"
            },
            "start": {
                "dateTime": "2017-04-15T19:00:00.0000000",
                "timeZone": "UTC"
            },
            "end": {
                "dateTime": "2017-04-15T21:00:00.0000000",
                "timeZone": "UTC"
            },
            "location": {
                "displayName": "Harry's Bar",
                "locationType": "default",
                "uniqueId": "Harry's Bar",
                "uniqueIdType": "private"
            },
            "locations": [
                {
                    "displayName": "Harry's Bar",
                    "locationType": "default",
                    "uniqueId": "Harry's Bar",
                    "uniqueIdType": "private"
                }
            ],
            "recurrence": null,
            "attendees": [
                {
                    "type": "required",
                    "status": {
                        "response": "none",
                        "time": "0001-01-01T00:00:00Z"
                    },
                    "emailAddress": {
                        "name": "Samantha Booth",
                        "address": "samanthab@contoso.onmicrosoft.com"
                    }
                }
            ],
            "organizer": {
                "emailAddress": {
                    "name": "Teja Chowdary",
                    "address": "outlook_5096A72EAA569FCB@outlook.com"
                }
            },
            "onlineMeeting": {
                "joinUrl": "https://join.skype.com/r5UHzBJzAXyC"
            },
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        },
        {
            "@odata.etag": "W/\"gpsXXHw/S0y+QrVrhMZE5AAFYHZ3WA==\"",
            "id": "AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6arAAAA",
            "createdDateTime": "2023-08-31T06:06:25.4078478Z",
            "lastModifiedDateTime": "2023-08-31T06:06:25.9552271Z",
            "changeKey": "gpsXXHw/S0y+QrVrhMZE5AAFYHZ3WA==",
            "categories": [],
            "transactionId": null,
            "originalStartTimeZone": "Pacific Standard Time",
            "originalEndTimeZone": "Pacific Standard Time",
            "iCalUId": "040000008200E00074C5B7101A82E0080000000025460C46D1DBD901000000000000000010000000990AC43CD2EE48429FED8761B4565BE1",
            "reminderMinutesBeforeStart": 15,
            "isReminderOn": true,
            "hasAttachments": false,
            "subject": "Let's go for lunch",
            "bodyPreview": "Does noon time work for you?",
            "importance": "normal",
            "sensitivity": "normal",
            "isAllDay": false,
            "isCancelled": false,
            "isOrganizer": true,
            "responseRequested": true,
            "seriesMasterId": null,
            "showAs": "busy",
            "type": "seriesMaster",
            "webLink": "https://outlook.live.com/owa/?itemid=AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn%2Bc6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQ0AAACCmxdcfD9LTL5CtWuExkTkAAVge6arAAAA&exvsurl=1&path=/calendar/item",
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
                "content": "<html>\r\n<head>\r\n<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\">\r\n</head>\r\n<body>\r\nDoes noon time work for you?\r\n</body>\r\n</html>\r\n"
            },
            "start": {
                "dateTime": "2017-09-04T19:00:00.0000000",
                "timeZone": "UTC"
            },
            "end": {
                "dateTime": "2017-09-04T21:00:00.0000000",
                "timeZone": "UTC"
            },
            "location": {
                "displayName": "Harry's Bar",
                "locationType": "default",
                "uniqueId": "Harry's Bar",
                "uniqueIdType": "private"
            },
            "locations": [
                {
                    "displayName": "Harry's Bar",
                    "locationType": "default",
                    "uniqueId": "Harry's Bar",
                    "uniqueIdType": "private"
                }
            ],
            "recurrence": {
                "pattern": {
                    "type": "weekly",
                    "interval": 1,
                    "month": 0,
                    "dayOfMonth": 0,
                    "daysOfWeek": [
                        "monday"
                    ],
                    "firstDayOfWeek": "sunday",
                    "index": "first"
                },
                "range": {
                    "type": "endDate",
                    "startDate": "2017-09-04",
                    "endDate": "2017-12-31",
                    "recurrenceTimeZone": "Pacific Standard Time",
                    "numberOfOccurrences": 0
                }
            },
            "attendees": [
                {
                    "type": "required",
                    "status": {
                        "response": "none",
                        "time": "0001-01-01T00:00:00Z"
                    },
                    "emailAddress": {
                        "name": "Teja Chowdary",
                        "address": "outlook_5096A72EAA569FCB@outlook.com"
                    }
                }
            ],
            "organizer": {
                "emailAddress": {
                    "name": "Teja Chowdary",
                    "address": "outlook_5096A72EAA569FCB@outlook.com"
                }
            },
            "onlineMeeting": null,
            "calendar@odata.associationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')/$ref",
            "calendar@odata.navigationLink": "https://graph.microsoft.com/v1.0/users('outlook_5096A72EAA569FCB@outlook.com')/calendars('AQMkADAwATNiZmYAZC0wYWEAZi0xODEwLTAwAi0wMAoARgAAAzn_c6J10qVLiXAeHgCFnNGWBwCCmxdcfD9LTL5CtWuExkTkAAACAQYAAACCmxdcfD9LTL5CtWuExkTkAAACM4oAAAA=')"
        }
    ]
}
```