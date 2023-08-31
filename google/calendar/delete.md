## Calendars: delete

This endpoint allows you to delete a secondary calendar.

## Example User Prompts:
1. **Basic Calendar Deletion**:
   - Delete the "Work Projects" calendar.
   - Remove the "Family Events" calendar from the list.
   - Cancel the "Fitness Schedule" calendar.

2. **Confirm Deletion**:
   - Are you sure you want to delete the "Travel Plans" calendar? (Yes/No)
   - Confirm the deletion of the "Homework Assignments" calendar. (Yes/No)
   - Please confirm the deletion of the "Book Club" calendar. (Yes/No)

3. **Calendar Deletion with Notification**:
   - Delete the "Project Deadlines" calendar and send notifications to all collaborators.
   - Remove the "Health Goals" calendar and notify all participants about the deletion.
   - Cancel the "Hobby Events" calendar and notify attendees accordingly.

Remember to adjust the details like calendar names, IDs, and confirmation prompts based on your use case. Additionally, make sure to handle user input for confirmation and notifications as needed before proceeding with the deletion process.

## Solution Steps:
1. Authenticate and set up access to the Google Calendar API.
2. For each delete prompt:
   - Display the calendar name you intend to delete.
   - Optionally, ask for user confirmation before proceeding with the deletion.
   - If the user confirms, retrieve the list of calendars using the `calendarList.list` API.
   - Loop through the list of calendars and find the one with the specified name.
   - Extract the `calendarId` of the calendar you want to delete.
   - Use the `calendars().delete` API, providing the extracted `calendarId` as a path parameter, to delete the calendar.
   - Execute the API call to delete the calendar.

### Request

**HTTP Request**

```
DELETE https://www.googleapis.com/calendar/v3/calendars/calendarId
```

**Path Parameters**

- `calendarId` (string): Calendar identifier. To retrieve calendar IDs, call the `calendarList.list` method. If you want to access the primary calendar of the currently logged-in user, use the "primary" keyword.

### Authorization

This request requires authorization with the following scope:

- `https://www.googleapis.com/auth/calendar`

For more information, refer to the authentication and authorization documentation.

### Request Body

Do not supply a request body with this method.

### Response

If successful, this method returns an empty response body.

### Example

Here's an example of how to use this method in Python using the Python client library:

```python
service.calendars().delete(calendarId='secondaryCalendarId').execute()
```

