## Calendars: insert

This endpoint allows you to create a secondary calendar.

## Example User Prompts:

1. **Basic Calendar Creation**:
   - Create a new calendar named "Work Projects".
   - Set up a secondary calendar called "Family Events".
   - Make a new calendar with the title "Fitness Schedule".

2. **Calendar with Description**:
   - Create a calendar for "Travel Plans" with the description "Keep track of upcoming trips".
   - Set up a calendar called "Homework Assignments" with the description "Manage all school-related tasks".
   - Make a calendar titled "Book Club" and add the description "Discuss and schedule book club meetings".

3. **Setting Time Zone**:
   - Create a new calendar named "Global Meetings" with the time zone set to "UTC".
   - Set up a calendar called "Conference Schedule" using the time zone "America/Los_Angeles".
   - Make a new calendar for "Team Events" and set the time zone to "Europe/London".

4. **Full Details Calendar**:
   - Create a calendar for "Project Deadlines" with the description "Track project due dates" and the time zone "Asia/Tokyo".
   - Set up a calendar named "Health Goals" with the description "Monitor fitness and wellness objectives" and the time zone "America/Chicago".
   - Make a new calendar for "Hobby Events" with the description "Keep up with hobby-related activities" and the time zone "Europe/Berlin".

5. **Customized Calendar**:
   - Create a calendar named "Financial Planning" with the description "Organize financial goals and budgets" and the time zone "America/New_York".
   - Set up a calendar called "Recipe Collection" with the description "Curate favorite recipes and meal plans" and the time zone "America/Los_Angeles".
   - Make a new calendar for "Home Renovation" with the description "Plan and schedule home improvement projects" and the time zone "Europe/London".

In these prompts, you'll need to replace the specific details like calendar names, descriptions, and time zones with the desired information for your use case.

## Solution Steps:
1. Authenticate and set up access to the Google Calendar API.
2. Create a dictionary containing the necessary properties for the new calendar:
   - `summary` (string): Title of the calendar.
   - `description` (string): Description of the calendar (optional).
   - `location` (string): Geographic location of the calendar (optional).
   - `timeZone` (string): The time zone of the calendar (optional).
3. Use the `calendars().insert` API, providing the dictionary as the `body` parameter, to create the new calendar.

### Request

**HTTP Request**

```
POST https://www.googleapis.com/calendar/v3/calendars
```

### Authorization

This request requires authorization with the following scope:

- `https://www.googleapis.com/auth/calendar`

For more information, refer to the authentication and authorization documentation.

### Request Body

In the request body, supply a `Calendars` resource with the following properties:

**Required Properties**

- `summary` (string): Title of the calendar.


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
calendar = {
    'summary': 'calendarSummary',
    'timeZone': 'America/Los_Angeles'
}

created_calendar = service.calendars().insert(body=calendar).execute()

print(created_calendar['id'])
```

### Calendars Resource Representation

The response contains a `Calendars` resource with the following properties:

- `kind` (string): Type of the resource ("calendar#calendar").
- `etag` (etag): ETag of the resource.
- `id` (string): Identifier of the calendar. To retrieve IDs, call the `calendarList.list()` method.
- `summary` (string): Title of the calendar.
- `description` (string): Description of the calendar. Optional.
- `location` (string): Geographic location of the calendar as free-form text. Optional.
- `timeZone` (string): The time zone of the calendar. (Formatted as an IANA Time Zone Database name, e.g. "Europe/Zurich".) Optional.
- `conferenceProperties` (nested object): Conferencing properties for this calendar, such as allowed conference solution types. Optional.
  - `allowedConferenceSolutionTypes` (list): The types of conference solutions that are supported for this calendar. Possible values are "eventHangout", "eventNamedHangout", and "hangoutsMeet". Optional.

