## Location type
Represents location information of an event.

### Properties
| Index | Property             | Type                                              | Description                                               | Required Property |
|-------|----------------------|---------------------------------------------------|-----------------------------------------------------------|-------------------|
| 1     | address              | [physicalAddress](PhysicalAddress.md)             | The street address of the location.                       | Yes               |
| 2     | coordinates          | [outlookGeoCoordinates](OutlookGeoCoordinates.md) | The geographic coordinates and elevation of the location. | No                |
| 3     | displayName          | String                                            | The name associated with the location.                    | Yes               |
| 4     | locationEmailAddress | String                                            | Optional email address of the location.                   | No                |
| 5     | locationUri          | String                                            | Optional URI representing the location.                   | No                |
| 6     | locationType         | locationType                                      | The type of location.                                     | Yes               |
| 7     | uniqueId             | String                                            | For internal use only.                                    | No                |
| 8     | uniqueIdType         | locationUniqueIdType                              | For internal use only.                                    | No                |
	


### JSON representation
```http
{
  "address": {"@odata.type": "PhysicalAddress"},
  "coordinates": {"@odata.type": "OutlookGeoCoordinates"},
  "displayName": "string",
  "locationEmailAddress": "string",
  "locationUri": "string",
  "locationType": "string",
  "uniqueId": "string",
  "uniqueIdType": "string"
}
```




