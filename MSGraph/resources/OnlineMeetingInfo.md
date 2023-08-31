## OnlineMeetingInfo type

Details for an attendee to join the meeting online.

### Properties

| Index | Property        | Type                         | Description                                                                                                                                               |
|-------|-----------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | conferenceId    | String                       | The ID of the conference.                                                                                                                                 |
| 2     | joinUrl         | String                       | The external link that launches the online meeting. This is a URL that clients will launch into a browser and will redirect the user to join the meeting. |
| 3     | phones          | [phone](Phone.md) collection | All of the phone numbers associated with this conference.                                                                                                 |
| 4     | quickDial       | String                       | The pre-formatted quickdial for this call.                                                                                                                |
| 5     | tollFreeNumbers | String                       | collection	The toll free numbers that can be used to join the conference.                                                                                 |
| 6     | tollNumber      | String                       | The toll number that can be used to join the conference.                                                                                                  |


### JSON representation
The following is a JSON representation of the resource.
```http 
{
  "conferenceId": "String",
  "joinUrl": "String",
  "phones": [{"@odata.type": "microsoft.graph.phone"}],
  "quickDial": "String",
  "tollFreeNumbers": ["String"],
  "tollNumber": "String"
}
```

