## ResponseStatus type
Represents the response status of an attendee or organizer for a meeting request.

You can get the response status of an attendee or organizer through the responseStatus property of an event or the status property of an [attendee](Attendee.md).

### Properties

| Index | Property | Type           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------|----------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | response | String         | The response type. Possible values are: none, organizer, tentativelyAccepted, accepted, declined, notResponded.  <br/>To differentiate between none and notResponded:  <br/>none – from organizer's perspective. This value is used when the status of an attendee/participant is reported to the organizer of a meeting.  <br/>notResponded – from attendee's perspective. Indicates the attendee has not responded to the meeting request.  <br/>Clients can treat notResponded == none.   <br/>As an example, if attendee Alex hasn't responded to a meeting request, getting Alex' response status for that event in Alex' calendar returns notResponded. Getting Alex' response from the calendar of any other attendee or the organizer's returns none. Getting the organizer's response for the event in anybody's calendar also returns none. |
| 2     | time     | DateTimeOffset | The date and time when the response was returned. It uses ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is 2014-01-01T00:00:00Z                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

		
### JSON representation
The following is a JSON representation of the resource.
```http 
{
  "response": "String",
  "time": "String (timestamp)"
}
```
		
		
