## PatternedRecurrence type
The recurrence pattern and range. 

### Properties

| Index | Property | Type                                      | Description                                                                                                                                                                                                                                                             |
|-------|----------|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | pattern  | [recurrencePattern](RecurrencePattern.md) | The frequency of an event. <br/>For access reviews: <br/>Do not specify this property for a one-time access review. <br/>Only `interval`, `dayOfMonth`, and `type` (*weekly*, *absoluteMonthly*) properties of [recurrencePattern](RecurrencePattern.md) are supported. |
| 2     | range    | [recurrenceRange](RecurrenceRange.md)     | The duration of an event.                                                                                                                                                                                                                                               |

		
		

		
### JSON representation
Here is a JSON representation of the resource
```http 
{
  "pattern": {"@odata.type": "microsoft.graph.recurrencePattern"},
  "range": {"@odata.type": "microsoft.graph.recurrenceRange"}
}
```

