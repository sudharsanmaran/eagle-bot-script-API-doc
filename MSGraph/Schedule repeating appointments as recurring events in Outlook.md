# Schedule repeating appointments as recurring events in Outlook

<br>In this there are  

- ***[Recurrence patterns](#recurrence-patterns)***  
- ***[Recurrence ranges](#recurrence-ranges)***  


## Recurrence patterns
The first part of a recurrence is the pattern. This specifies how often the event repeats. For example, an event could repeat "every 3 days," "every Thursday," or "on July 22 every year." A pattern is represented in the API by the [recurrencePattern](resources/RecurrencePattern.md) resource.

Depending on the type of pattern, certain fields of the recurrencePattern are required, optional, or ignored.

 
Let's take a look at each of the possible pattern types.
### Daily
The daily recurrence pattern causes an event to repeat based on a number of days between each occurrence.

#### Properties

| Index | Property | Type   | Description                                           | Required |
|-------|----------|--------|-------------------------------------------------------|----------|
| 1     | interval | int    | Specifies the number of days between each occurrence. | Yes      |
| 2     | type     | String | Must be set to daily.                                 | Yes      |

	
#### Examples
- Repeat this event every day
```http
  "pattern": {
    "type": "daily",
    "interval": 1
  }
```

- Repeat this event every three days
```http 
  "pattern": {
    "type": "daily",
    "interval": 3
  }
```
  
### Weekly
The weekly recurrence pattern causes an event to repeat on the same day or days of the week, based on the number of weeks between each set of occurrences.

#### Properties

| Index | Property       | Type              | Description                                                                         | Required |
|-------|----------------|-------------------|-------------------------------------------------------------------------------------|----------|
| 1     | daysOfWeek     | String collection | Specifies on which day(s) of the week the event occurs.                             | Yes      |
| 2     | firstDayOfWeek | String            | Specifies which day is considered the first day of the week. Default value: Sunday. | No       |
| 3     | interval       | int               | Specifies the number of weeks between each set of occurrences.                      | Yes      |
| 4     | type           | String            | Must be set to weekly.                                                              | Yes      |

#### Examples
- Repeat this event every Thursday
```http 
  "pattern": {
    "type": "weekly",
    "interval": 1,
    "daysOfWeek": [ "Thursday" ]
  }
```
  
- Repeat this event every other Monday and Tuesday
```http 
  "pattern": {
    "type": "weekly",
    "interval": 2,
    "daysOfWeek": [
      "Monday",
      "Tuesday"
    ]
  }
```
 
### Absolute monthly
The absolute monthly pattern causes an event to repeat on the same day of the month (for example, the 15th), based on the number of months between each occurrence.

#### Properties

| Index | Property   | Type   | Description                                           | Required |
|-------|------------|--------|-------------------------------------------------------|----------|
| 1     | dayOfMonth | int    | Specifies on which day of the month the event occurs. | Yes      |
| 2     | interval   | int    | Specifies the number of days between each occurrence. | Yes      |
| 3     | type       | String | Must be set to absoluteMonthly.                       | Yes      |

#### Examples
- Repeat this event on the 15th of every month
```http
  "pattern": {
    "type": "absoluteMonthly",
    "interval": 1,
    "dayOfMonth": 15
  }
 ```
- Repeat this event quarterly (every 3 months) on the 7th
```http 
  "pattern": {
    "type": "absoluteMonthly",
    "interval": 3,
    "dayOfMonth": 7
  }
```

### Relative monthly
The relative monthly pattern causes an event to repeat on the same day of the week in the same relative position in the month, based on the number of months between each occurrence. For example, "every second Wednesday of the month."

#### Properties

| Index | Property   | Type              | Description                                                                                                                                                                                                             | Required |
|-------|------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 1     | daysOfWeek | String collection | Specifies on which day(s) of the week the event can occur. Relative monthly events only occur once per month, so if more than one value is specified, the event falls on the first day that satisfies the pattern.      | Yes      |
| 2     | index      | String            | Specifies on which instance of the allowed days specified in daysOfsWeek the event occurs, counted from the first instance in the month. Possible values: first, second, third, fourth, and last. Default value: first. | No       |
| 3     | interval   | int               | Specifies the number of days between each occurrence.                                                                                                                                                                   | Yes      |
| 4     | type       | String            | Must be set to relativeMonthly.                                                                                                                                                                                         | Yes      |

	
#### Examples
- Repeat this event on the second Wednesday of every month
````http 
  "pattern": {
    "type": "relativeMonthly",
    "interval": 1,
    "daysOfWeek": [ "Wednesday" ],
    "index": "second"
  }
````

- Repeat this event on the first Thursday or Friday of every month
```http 
  "pattern": {
    "type": "relativeMonthly",
    "interval": 1,
    "daysOfWeek": [ "Thursday", "Friday" ],
    "index": "first"
  }
```

### Absolute yearly
The absolute yearly pattern causes an event to repeat on the same month and day (for example, April 15), based on the number of years between each occurrence.

#### Properties

| Index | Property   | Type   | Description                                           | Required |
|-------|------------|--------|-------------------------------------------------------|----------|
| 1     | dayOfMonth | int    | Specifies on which day of the month the event occurs. | Yes      |
| 2     | month      | int    | Specifies in which month the event occurs.            | Yes      |
| 3     | interval   | int    | Specifies the number of days between each occurrence. | Yes      |
| 4     | type       | String | Must be set to daily.                                 | Yes      |


#### Example
Repeat this event on April 15 every year
```http 
  "pattern": {
    "type": "absoluteYearly",
    "interval": 1,
    "dayOfMonth": 15,
    "month": 4
  }
```

### Relative yearly
The relative yearly pattern causes an event to repeat on the same day of the week in the same relative position in a specific month, based on the number of years between each occurrence. For example, "every last Wednesday of November."

#### Properties

| Index | Property   | Type              | Description                                                                                                                                                                                                             | Required |
|-------|------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 1     | daysOfWeek | String collection | Specifies on which day(s) of the week the event can occur. Relative yearly events only occur once per year, so if more than one value is specified, the event falls on the first day that satisfies the pattern.        | Yes      |
| 2     | index      | String            | Specifies on which instance of the allowed days specified in daysOfsWeek the event occurs, counted from the first instance in the month. Possible values: first, second, third, fourth, and last. Default value: first. | No       |
| 3     | month      | int               | Specifies in which month the event occurs.                                                                                                                                                                              | Yes      |
| 4     | interval   | int               | Specifies the number of days between each occurrence.                                                                                                                                                                   | Yes      |
| 5     | type       | String            | Must be set to daily.                                                                                                                                                                                                   | Yes      |

#### Examples
Repeat this event on the last Wednesday of November every year
```http 
  "pattern": {
    "type": "relativeYearly",
    "interval": 1,
    "daysOfWeek": [ "Wednesday" ],
    "index": "last",
    "month": 11
  }
```
## Recurrence ranges
The second part of a recurrence is the range. This specifies how long the pattern repeats. For example, an event could end after 10 occurrences, by a specific date, or could have no end. A range is represented in the API by the [recurrenceRange](resources/RecurrenceRange.md) resource.

Depending on the type of range, certain fields of recurrenceRange are required or ignored.

Let's take a look at each of the possible range types.

### Numbered range
The numbered range causes an event to occur a fixed number of times (based on the pattern) from a start date.

#### Properties

| Index | Property            | Type   | Description                                                                                                                                                                                                                                                      | Required |
|-------|---------------------|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 1     | numberOfOccurrences | int    | Specifies the number of occurrences. Must be a positive integer.                                                                                                                                                                                                 | Yes      |
| 2     | recurrenceTimeZone  | String | Specifies the time zone for the startDate property. If not specified, the time zone of the event is used.                                                                                                                                                        | No       |
| 3     | startDate           | String | Specifies the date to start applying the pattern. The value of startDate MUST correspond to the date value of the start property on the event resource. Note that the first occurrence of the meeting may not occur on this date if it does not fit the pattern. | Yes      |
| 4     | type                | String | Must be set to daily.                                                                                                                                                                                                                                            | Yes      |


#### Examples
Repeat this event 10 times
```http 
  "range": {
    "type": "numbered",
    "startDate": "2017-04-02",
    "numberOfOccurrences": 10
  }
```

### End date range
The end date range causes an event to occur on all days that fit the applicable pattern between a start date and an end date.

Properties

| Index | Property           | Type   | Description                                                                                                                                                                                                                                                      | Required |
|-------|--------------------|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 1     | endDate            | String | Specifies the date to stop applying the pattern. Note that the last occurrence of the meeting may not occur on this date if it does not fit the pattern.                                                                                                         | Yes      |
| 2     | recurrenceTimeZone | String | Specifies the time zone for the startDate and endDate properties. If not specified, the time zone of the event is used.                                                                                                                                          | No       |
| 3     | startDate          | String | Specifies the date to start applying the pattern. The value of startDate MUST correspond to the date value of the start property on the event resource. Note that the first occurrence of the meeting may not occur on this date if it does not fit the pattern. | Yes      |
| 4     | type               | String | Must be set to daily.                                                                                                                                                                                                                                            | Yes      |


#### Examples
Repeat this event from July 1, 2017, to July 31, 2017
```http 
  "range": {
    "type": "endDate",
    "startDate": "2017-07-01",
    "endDate": "2017-07-31"
  }
```

### No end range
The no end range causes an event to occur on all days that fit the applicable pattern after a start date.

#### Properties

| Index | Property           | Type   | Description                                                                                                                                                                                                                                                      | Required |
|-------|--------------------|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| 1     | recurrenceTimeZone | String | Specifies the time zone for the startDate property. If not specified, the time zone of the event is used.                                                                                                                                                        | No       |
| 2     | startDate          | String | Specifies the date to start applying the pattern. The value of startDate MUST correspond to the date value of the start property on the event resource. Note that the first occurrence of the meeting may not occur on this date if it does not fit the pattern. | Yes      |
| 3     | type               | String | Must be set to daily.                                                                                                                                                                                                                                            | Yes      |

#### Examples
Repeat this event from May 15, 2017, forever
```http 
  "range": {
    "type": "noEnd",
    "startDate": "2017-05-15"
  }
```
