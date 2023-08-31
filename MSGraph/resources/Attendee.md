## Attendee type
An event attendee. This can be a person or resource such as a meeting room or equipment, that has been set up as a resource on the Exchange server for the tenant.

### Properties
| Index | Property        | Type	                               | Description                                         | Required properties |
|:-----:|-----------------|-------------------------------------|-----------------------------------------------------|---------------------|
|   1   | emailAddress    | [emailAddress](EmailAddress.md)     | Includes the name and SMTP address of the attendee. | Yes                 |
|   2   | proposedNewTime | [timeSlot](Timeslot.md)             | An alternate date/time proposed by the attendee.    | No                  |
|   3   | status          | [ResponseStatus](ResponseStatus.md) | The attendee's response for the event.              | Yes                 |
|   4   | type            | String                              | The attendee type: required, optional, resource.    | Yes                 |

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