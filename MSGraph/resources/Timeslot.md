## Timeslot type
Represents a time slot for a meeting.

### Properties

| Property | Type                                    | Description                                         |
|----------|-----------------------------------------|-----------------------------------------------------|
| end      | [dateTimeTimeZone](DateTimeTimeZone.md) | The date, time, and time zone that a period ends.   |
| start    | [dateTimeTimeZone](DateTimeTimeZone.md) | The date, time, and time zone that a period begins. |
		
### JSON representation
Here is a JSON representation of the resource
```http
{
  "end": {"@odata.type": "DateTimeTimeZone"},
  "start": {"@odata.type": "DateTimeTimeZone"}
}

```
		