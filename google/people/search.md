## Method: people.searchContacts

Provides a list of contacts in the authenticated user's grouped contacts that matches the search query. The query matches on a contact's names, nickNames, emailAddresses, phoneNumbers, and organizations fields that are from the CONTACT source.

**IMPORTANT:** Before searching, clients should send a warmup request with an empty query to update the cache. See [here](https://developers.google.com/people/v1/contacts#search_the_users_contacts) for more information.

### HTTP request

```
GET https://people.googleapis.com/v1/people:searchContacts
```

The URL uses gRPC Transcoding syntax.

### Query parameters

| Parameter | Type   | Description                                                                                                 |
|-----------|--------|-------------------------------------------------------------------------------------------------------------|
| `query`   | string | **Required.** The plain-text query for the request. The query is used to match prefix phrases of the fields on a person. For example, a person with name "foo name" matches queries such as "f", "fo", "foo", "foo n", "nam", etc., but not "oo n". |
| `pageSize`| integer| **Optional.** The number of results to return. Defaults to 10 if the field is not set, or set to 0. Values greater than 30 will be capped to 30. |
| `readMask`| string | **Required.** A field mask to restrict which fields on each person are returned. Multiple fields can be specified by separating them with commas. Valid values are specified fields such as: addresses, ageRanges, biographies, birthdays, calendarUrls, clientData, coverPhotos, emailAddresses, events, externalIds, genders, imClients, interests, locales, locations, memberships, metadata, miscKeywords, names, nicknames, occupations, organizations, phoneNumbers, photos, relations, sipAddresses, skills, urls, userDefined. |
| `sources[]`| enum  | **Optional.** A mask of what source types to return. Defaults to READ_SOURCE_TYPE_CONTACT if not set. |

### Request body

The request body must be empty.

### Response body

If successful, the response body contains an instance of SearchResponse.

### Authorization Scopes

Requires one of the following OAuth scopes:

- `https://www.googleapis.com/auth/contacts`
- `https://www.googleapis.com/auth/contacts.readonly`
