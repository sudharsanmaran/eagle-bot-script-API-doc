## IssueTransition type

### Properties
| Property | Type                  | Description                                                                         |
|----------|-----------------------|-------------------------------------------------------------------------------------|
| id       | string                | The ID of the issue transition. Required when specifying a transition to undertake. |
| looped   | boolean               | Indicates if the transition is looped.                                              |
| 12       | Additional Properties | any                                                                                 | Extra properties of any type may be provided to this object.                 |

### Json Representation
Here is a JSON representation of the resource

```http 
{
  "id": "string",
  "looped": boolean,
  "Additional Properties": {}
}
```