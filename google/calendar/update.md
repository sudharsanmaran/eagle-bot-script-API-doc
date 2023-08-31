## Calendars: update

This endpoint allows you to update metadata for a calendar.

### Example User Prompts:
1. **Basic Calendar Update**:
   - Update the title of the "Work Projects" calendar to "Work Assignments".
   - Change the name of the "Family Events" calendar to "Family Gatherings".
   - Modify the title of the "Fitness Schedule" calendar to "Workout Plan".

2. **Calendar Description Update**:
   - Update the description of the "Travel Plans" calendar to "Track upcoming trips and itineraries".
   - Add a new description "Stay organized with school tasks" to the "Homework Assignments" calendar.
   - Modify the description of the "Book Club" calendar to "Discuss and schedule book club meetings and reads".

3. **Calendar Location Update**:
   - Update the location of the "Global Meetings" calendar to "Virtual Meetings".
   - Change the location of the "Conference Schedule" calendar to "Meeting Room B".
   - Modify the location of the "Team Events" calendar to "Office Lounge".

4. **Time Zone Update**:
   - Update the time zone of the "Project Deadlines" calendar to "Asia/Tokyo".
   - Change the time zone of the "Health Goals" calendar to "America/Chicago".
   - Modify the time zone of the "Hobby Events" calendar to "Europe/Berlin".

5. **Combined Updates**:
   - Update the "Financial Planning" calendar's description to "Manage financial goals and budgets" and change its time zone to "America/Los_Angeles".
   - Modify the "Recipe Collection" calendar's location to "Kitchen" and update its time zone to "Europe/London".
   - Update the "Home Renovation" calendar's description to "Plan and schedule home improvement projects" and change its location to "Living Room".

In these prompts, you can replace the specific details like calendar names, descriptions, locations, and time zones with the desired information for your use case.

Certainly, here's a solution outline for updating calendar metadata using the Google Calendar API based on the provided example prompts:

Certainly, here are the solution steps for updating calendar metadata with a specific calendar name using the Google Calendar API:

**Solution Steps:**
1. Authenticate and set up access to the Google Calendar API.
2. Retrieve the requested calendar from `calendarList.list` API with filtering.
3. Extract the `calendarId` of the calendar you want to update.
4. Use the `calendars().get` API with the extracted `calendarId` to retrieve the current calendar details.
5. Modify the properties you want to update (such as `summary`, `description`, `location`, `timeZone`) based on the prompt.
6. Use the `calendars().update` API, providing the extracted `calendarId` as a path parameter and the modified `Calendars` resource in the request body to update the calendar.

Remember to adjust the properties, such as `desired_calendar_name`, `summary`, `description`, `location`, and `timeZone`, according to your preferences

### Request

**HTTP Request**

```
PUT https://www.googleapis.com/calendar/v3/calendars/calendarId
```

**Path Parameters**

- `calendarId` (string): Calendar identifier. To retrieve calendar IDs, call the `calendarList.list` method. If you want to access the primary calendar of the currently logged-in user, use the "primary" keyword.

### Authorization

This request requires authorization with the following scope:

- `https://www.googleapis.com/auth/calendar`

For more information, refer to the authentication and authorization documentation.

### Request Body

In the request body, supply a `Calendars` resource with the following properties:

**Optional Properties**

- `description` (string): Description of the calendar. Optional.
- `location` (string): Geographic location of the calendar as free-form text. Optional.
- `summary` (string): Title of the calendar.
- `timeZone` (string): The time zone of the calendar. (Formatted as an IANA Time Zone Database name, e.g. "Europe/Zurich".) Optional.

### Response

If successful, this method returns a `Calendars` resource in the response body.

### Example

Here's an example of how to use this method in Python:

```python
# First retrieve the calendar from the API.
calendar = service.calendars().get(calendarId='primary').execute()

calendar['summary'] = 'New Summary'

updated_calendar = service.calendars().update(calendarId=calendar['id'], body=calendar).execute()

print(updated_calendar['etag'])
```
