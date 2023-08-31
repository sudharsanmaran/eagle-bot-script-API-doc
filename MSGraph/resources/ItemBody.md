## ItemBody type
Represents properties of the body of an item, such as a message, event or group post.

### Properties

| Index | Property    | Type     | Description                                                     |
|-------|-------------|----------|-----------------------------------------------------------------|
| 1     | content     | String   | The content of the item.                                        |
| 2     | contentType | bodyType | The type of the content. Possible values are `text` and `html`. |

		
		
		
### JSON representation
Here is a JSON representation of the resource
```http
{
  "emailAddress": {
    "address": "john.doe@example.com",
    "name": "John Doe"
  },
  "status": {
    "response": "accepted",
    "time": "2023-08-28T10:00:00Z"
  },
  "type": "required"
}
```
