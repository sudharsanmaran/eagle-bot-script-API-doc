## Attendee type
An event attendee. This can be a person or resource such as a meeting room or equipment, that has been set up as a resource on the Exchange server for the tenant.

### Properties
#### Required properties
| Index | Property        | Type	                               | Description                                         |
|:-----:|-----------------|-------------------------------------|-----------------------------------------------------|
|   1   | emailAddress    | [emailAddress](EmailAddress.md)     | Includes the name and SMTP address of the attendee. |
|   2   | status          | [ResponseStatus](ResponseStatus.md) | The attendee's response for the event.              |
|   3   | type            | String                              | The attendee type: required, optional, resource.    |

#### Optional properties
| Index | Property        | Type	                   | Description                                      |
|-------|-----------------|-------------------------|--------------------------------------------------|
| 1     | proposedNewTime | [timeSlot](Timeslot.md) | An alternate date/time proposed by the attendee. |


### Json Representation
Here is a JSON representation of the resource

```http 
{
  "emailAddress": {"@odata.type": "EmailAddress"},
  "proposedNewTime": {"@odata.type": "TimeSlot"},
  "status": {"@odata.type": "ResponseStatus"},
  "type": "String"
}
```