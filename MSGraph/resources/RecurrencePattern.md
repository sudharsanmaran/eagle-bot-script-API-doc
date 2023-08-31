## RecurrencePattern type
Describes the frequency by which a recurring event repeats.

### Properties

| Index | Property       | Type                  | Description                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------|----------------|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | dayOfMonth     | Int32                 | The day of the month on which the event occurs. Required if type is absoluteMonthly or absoluteYearly.                                                                                                                                                                                                                                                                                                       |
| 2     | daysOfWeek     | dayOfWeek collection  | A collection of the days of the week on which the event occurs. The possible values are: `sunday`, `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`. <br/>If type is relativeMonthly or relativeYearly, and daysOfWeek specifies more than one day, the event falls on the first day that satisfies the pattern.<br/>Required if type is `weekly`, `relativeMonthly`, or `relativeYearly`. |
| 3     | firstDayOfWeek | dayOfWeek             | The first day of the week. The possible values are: `sunday`, `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`. Default is `sunday`. <br/>Required if type is `weekly`.                                                                                                                                                                                                                    |
| 4     | index          | weekIndex             | Specifies on which instance of the allowed days specified in daysOfWeek the event occurs, counted from the first instance in the month. The possible values are: `first`, `second`, `third`, `fourth`, `last`. Default is `first`. Optional and used if type is `relativeMonthly` or `relativeYearly`.                                                                                                       |
| 5     | interval       | Int32                 | The number of units between occurrences, where units can be in days, weeks, months, or years, depending on the type. Required.                                                                                                                                                                                                                                                                               |
| 6     | month          | Int32                 | The month in which the event occurs. This is a number from 1 to 12.                                                                                                                                                                                                                                                                                                                                          |
| 7     | type           | recurrencePatternType | The recurrence pattern type: daily, weekly, absoluteMonthly, relativeMonthly, absoluteYearly, relativeYearly. Required. For more information, see values of type property.                                                                                                                                                                                                                                   |

### Values of type property


| Value of `type` property | Description                                                                                                                                                              | Example                                                                        | Required Properties                                |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|----------------------------------------------------|
| `daily`                  | Event repeats based on the number of days specified by interval between occurrences.                                                                                     | Repeat event every 3 days.                                                     | `type`, `interval`                                 |
| `weekly`                 | Event repeats on the same day or days of the week, based on the number of weeks between each set of occurrences.                                                         | Repeat event Monday and Tuesday of every other week.                           | `type`, `interval`, `daysOfWeek`, `firstDayOfWeek` |
| `absoluteMonthly`        | Event repeats on the specified day of the month (e.g., the 15th), based on the number of months between occurrences.                                                     | Repeat event quarterly (every 3 months) on the 15th.                           | `type`, `interval`, `dayOfMonth`                   |
| `relativeMonthly`        | Event repeats on the specified day or days of the week, in the same relative position in the month, based on the number of months between occurrences.                   | Repeat event on the second Thursday or Friday every three months.              | `type`, `interval`, `daysOfWeek`                   |
| `absoluteYearly`         | Event repeats on the specified day and month, based on the number of years between occurrences.                                                                          | Repeat event on the 15th of March every 3 years.                               | `type`, `interval`, `dayOfMonth`, `month`          |
| `relativeYearly`         | Event repeats on the specified day or days of the week, in the same relative position in a specific month of the year, based on the number of years between occurrences. | Repeat event on the second Thursday or Friday of every November every 3 years. | `type`, `interval`, `daysOfWeek`                   |


### JSON representation
The following is a JSON representation of the resource.
```http 
{
  "dayOfMonth": 1024,
  "daysOfWeek": ["String"],
  "firstDayOfWeek": "String",
  "index": "String",
  "interval": 1024,
  "month": 1024,
  "type": "String"
}
```

		
		
		
		
		
		
		
		