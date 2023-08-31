## RecurrenceRange type
Describes a date range over which a recurring event. 

### Properties
| Index | Property            | Type                | Description                                                                                                                                                                                                                                | Example                                                   | Required Properties                        |
|-------|---------------------|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------------------------------------|
| 1     | endDate             | Date                | The date to stop applying the recurrence pattern. The last occurrence of the meeting may not be on this date.                                                                                                                              | Repeat event between June 1, 2017 and June 15, 2017.      | `type`, `startDate`, `endDate`             |
| 2     | numberOfOccurrences | Int32               | The number of times to repeat the event. Must be positive if `type` is `numbered`.                                                                                                                                                         | Repeat event starting on June 1, 2017 for 10 occurrences. | `type`, `startDate`, `numberOfOccurrences` |
| 3     | recurrenceTimeZone  | String              | Time zone for the `startDate` and `endDate` properties. Optional.                                                                                                                                                                          | -                                                         | Optional                                   |
| 4     | startDate           | Date                | The date to start applying the recurrence pattern. The first occurrence of the meeting may be this date or later, depending on the recurrence pattern of the event. Must be the same value as the `start` property of the recurring event. | -                                                         | Required                                   |
| 5     | type                | recurrenceRangeType | The recurrence range. The possible values are: `endDate`, `noEnd`, `numbered`.                                                                                                                                                             | -                                                         | -                                          |

Use the **type** property to specify the different types of recurrenceRange. Note the required properties for each type, as described in the following table.

| Type     | Description                                                                                                                                  | Example                                                   | Required Properties                        |
|----------|----------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------------------------------------|
| endDate  | Range with end date. Event repeats on all days that fit the corresponding recurrence pattern between `startDate` and `endDate` inclusive.    | Repeat event between June 1, 2017 and June 15, 2017.      | `type`, `startDate`, `endDate`             |
| noEnd    | Range without end date. Event repeats on all days that fit the corresponding recurrence pattern beginning on `startDate`.                    | Repeat event starting on June 1, 2017 indefinitely.       | `type`, `startDate`                        |
| numbered | Range with specific number of occurrences. Event repeats for `numberOfOccurrences` based on the recurrence pattern beginning on `startDate`. | Repeat event starting on June 1, 2017 for 10 occurrences. | `type`, `startDate`, `numberOfOccurrences` |


### JSON representation
Here is a JSON representation of the resource
```http 
{
  "endDate": "String (timestamp)",
  "numberOfOccurrences": 1024,
  "recurrenceTimeZone": "string",
  "startDate": "String (timestamp)",
  "type": "String"
}
```
