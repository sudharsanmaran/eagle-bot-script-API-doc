## HistoryMetadata type

### Properties 

| Index | Property               | Type                                                        | Description                                                                  |
|-------|------------------------|-------------------------------------------------------------|------------------------------------------------------------------------------|
| 1     | activityDescription    | string                                                      | The activity described in the history record.                                |
| 2     | activityDescriptionKey | string                                                      | The key of the activity described in the history record.                     |
| 3     | actor                  | [HistoryMetadataParticipant](HistoryMetadataParticipant.md) | Details of the user whose action created the history record.                 |
| 4     | cause                  | [HistoryMetadataParticipant](HistoryMetadataParticipant.md) | Details of the cause that triggered the creation of the history record.      |
| 5     | description            | string                                                      | The description of the history record.                                       |
| 6     | descriptionKey         | string                                                      | The description key of the history record.                                   |
| 7     | emailDescription       | string                                                      | The description of the email address associated with the history record.     |
| 8     | emailDescriptionKey    | string                                                      | The description key of the email address associated with the history record. |
| 9     | extraData              | object                                                      | Additional arbitrary information about the history record.                   |
| 10    | generator              | [HistoryMetadataParticipant](HistoryMetadataParticipant.md) | Details of the system that generated the history record.                     |
| 11    | type                   | string                                                      | The type of the history record.                                              |
| 12    | Additional Properties  | any                                                         | Extra properties of any type may be provided to this object.                 |

### Json Representation
Here is a JSON representation of the resource

```http 
{
  "activityDescription": "string",
  "activityDescriptionKey": "string",
  "actor": {
    "@odata.type": "HistoryMetadataParticipant"
  },
  "cause": {
    "@odata.type": "HistoryMetadataParticipant"
  },
  "description": "string",
  "descriptionKey": "string",
  "emailDescription": "string",
  "emailDescriptionKey": "string",
  "extraData": {},
  "generator": {
    "@odata.type": "HistoryMetadataParticipant"
  },
  "type": "string",
  "Additional Properties": {}
}
```
