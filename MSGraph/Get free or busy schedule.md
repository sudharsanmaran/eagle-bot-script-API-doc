# Retrieving Free/Busy Schedule using Microsoft Graph


## Request Headers

- **Authorization**: Bearer {token}. (Required)
- **Content-Type**: application/json. (Required)
- **Prefer: outlook.timezone**: Use this to specify the time zone for start and end times in the response. If not specified, those time values are returned in UTC. (Optional)

## Request Body

In the request body, provide a JSON object with the following parameters:

| Index | Property                 | type                                              | Description                                                                                                                              | Optional |
|-------|--------------------------|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 1     | availabilityViewInterval | Int32                                             | Represents the duration of a time slot in an availabilityView in the response. The default is 30 minutes, minimum is 5, maximum is 1440. | Yes      |
| 2     | endTime                  | [dateTimeTimeZone](resources/DateTimeTimeZone.md) | The date, time, and time zone that the period ends.                                                                                      | No       |
| 3     | schedules                | String collection.                                | A collection of SMTP addresses of users, distribution lists, or resources to get availability information for.                           | No       |
|       | startTime                | [dateTimeTimeZone](resources/DateTimeTimeZone.md) | The date, time, and time zone that the period starts.                                                                                    | No       |




### Example


A simple example is to find the free/busy schedule of a coworker, Alex, on a specific day, from 9am to 6pm, Pacific Standard Time:
```http
POST https://graph.microsoft.com/v1.0/me/calendar/getschedule 
Prefer: outlook.timezone="Pacific Standard Time"
Content-Type: application/json

{        
    "Schedules": ["AlexW@contoso.OnMicrosoft.com"],
    "StartTime": {
        "dateTime": "2018-08-06T09:00:00",
        "timeZone": "Pacific Standard Time"
    },
    "EndTime": {
        "dateTime": "2018-08-06T18:00:00",
        "timeZone": "Pacific Standard Time"
    },
    "availabilityViewInterval": "15"
}
```

***getSchedule*** returns two schedule items that match existing events in Alex default calendar, showing the start and end times of each event and its free/busy status. You can assume Alex is free for the remaining time in that date/time range.

## Response

If successful, this method returns a 200 OK response code and a collection of scheduleInformation objects for each object in the schedules' parameter.

**Note**: When the user's calendar has a time slot that contains more than 1000 entries, a 5006 response code with the message "The result set contains too many calendar entries. The allowed size is 1000; the actual size is ..." will be returned.

**HTTP Response:**

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context":"https://graph.microsoft.com/v1.0/$metadata#Collection(microsoft.graph.scheduleInformation)",
    "value":[
        {
            "scheduleId":"AlexW@contoso.OnMicrosoft.com",
            "availabilityView":"111111002222222200000000000000000000",
            "scheduleItems":[
                {
                    "status":"Tentative",
                    "start":{
                        "dateTime":"2018-08-06T09:00:00.0000000",
                        "timeZone":"Pacific Standard Time"
                    },
                    "end":{
                        "dateTime":"2018-08-06T10:30:00.0000000",
                        "timeZone":"Pacific Standard Time"
                    }
                },
                {
                    "status":"Busy",
                    "start":{
                        "dateTime":"2018-08-06T11:00:00.0000000",
                        "timeZone":"Pacific Standard Time"
                    },
                    "end":{
                        "dateTime":"2018-08-06T13:00:00.0000000",
                        "timeZone":"Pacific Standard Time"
                    }
                }
            ],
            "workingHours":{
                "daysOfWeek":[
                    "monday",
                    "tuesday",
                    "wednesday",
                    "thursday",
                    "friday"
                ],
                "startTime":"08:00:00.0000000",
                "endTime":"17:00:00.0000000",
                "timeZone":{
                    "@odata.type":"#microsoft.graph.customTimeZone",
                    "bias":480,
                    "name":"Customized Time Zone",
                    "standardOffset":{
                        "time":"02:00:00.0000000",
                        "dayOccurrence":1,
                        "dayOfWeek":"sunday",
                        "month":11,
                        "year":0
                    },
                    "daylightOffset":{
                        "daylightBias":-60,
                        "time":"02:00:00.0000000",
                        "dayOccurrence":2,
                        "dayOfWeek":"sunday",
                        "month":3,
                        "year":0
                    }
                }
            }
        }
    ]
}
```
In this example, we send a POST request to retrieve Alex's free/busy schedule for a specific day and time range. The response includes information about Alex's schedule, availability, and working hours.

Note: The availability view uses the following convention:

0: Free  
1: Tentative  
2: Busy  
3: Out of Office  
4: Working Elsewhere.
