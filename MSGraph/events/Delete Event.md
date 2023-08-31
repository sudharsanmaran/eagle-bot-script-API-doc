# Delete Event
Removes the specified event from the containing calendar.

If the event is a meeting, deleting the event on the organizer's calendar sends a cancellation message to the meeting attendees.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type                        | Permissions (from least to most privileged) |
|----------------------------------------|---------------------------------------------|
| Delegated (work or school account)     | Calendars.ReadWrite                         |
| Delegated (personal Microsoft account) | Calendars.ReadWrite                         |
| Application                            | Calendars.ReadWrite                         |

## HTTP request

```http 
DELETE /me/events/{id}
DELETE /users/{id | userPrincipalName}/events/{id}
DELETE /groups/{id}/events/{id}

DELETE /me/calendar/events/{id}
DELETE /users/{id | userPrincipalName}/calendar/events/{id}
DELETE /groups/{id}/calendar/events/{id}/

DELETE /me/calendars/{id}/events/{id}
DELETE /users/{id | userPrincipalName}/calendars/{id}/events/{id}

DELETE /me/calendarGroups/{id}/calendars/{id}/events/{id}
DELETE /users/{id | userPrincipalName}/calendarGroups/{id}/calendars/{id}/events/{id}
```

## Request headers

| Name          | Type   | Description               |
|---------------|--------|---------------------------|
| Authorization | string | Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns 204 No Content response code. It does not return anything in the response body.

## Example
### Request
Here is an example of the request.
```http
DELETE https://graph.microsoft.com/v1.0/me/events/{id}\
```
Response
Here is an example of the response.
```http
HTTP/1.1 204 No Content
```