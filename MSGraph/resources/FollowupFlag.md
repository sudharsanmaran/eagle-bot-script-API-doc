## FollowupFlag type
Allows setting a flag in an item for the user to follow up on later.

## Properties

| Property          | Type                                    | Description                                                                                                                                                                     |
|-------------------|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| completedDateTime | [dateTimeTimeZone](DateTimeTimeZone.md) | The date and time that the follow-up was finished.                                                                                                                              |
| dueDateTime       | [dateTimeTimeZone](DateTimeTimeZone.md) | The date and time that the follow up is to be finished. Note: To set the due date, you must also specify the startDateTime; otherwise, you will get a 400 Bad Request response. |
| flagStatus        | followupFlagStatus                      | The status for follow-up for an item. Possible values are notFlagged, complete, and flagged.                                                                                    |
| startDateTime     | [dateTimeTimeZone](DateTimeTimeZone.md) | The date and time that the follow-up is to begin.                                                                                                                               |
	

## JSON representation
Here is a JSON representation of the resource.
```http 
{
  "completedDateTime": {"@odata.type": "DateTimeTimeZone"},
  "dueDateTime": {"@odata.type": "DateTimeTimeZone"},
  "flagStatus": "String",
  "startDateTime": {"@odata.type": "DateTimeTimeZone"}
}
```

