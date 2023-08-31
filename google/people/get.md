## Get Person Information

This API provides information about a person by specifying a resource name.

### Request

**HTTP Request**

```
GET https://people.googleapis.com/v1/{resourceName}
```

| Parameter Name | Value | Description |
|-|-|-|
|***Path parameters***|||
|`resourceName` |string| The resource name of the person to provide information about. To get information about the authenticated user, specify `people/me`. To get information about a Google account, specify `people/{account_id}`. To get information about a contact, specify the resource name that identifies the contact as returned by `people.connections.list`.|
|***Optional Query Parameters***|||
|`personFields`|string| A field mask to restrict which fields on the person are returned. Multiple fields can be specified by separating them with commas. <br> ***Valid values are specified fields such as:*** <br> &#8226; addresses <br> &#8226; ageRanges <br> &#8226; biographies <br> &#8226; birthdays <br> &#8226; calendarUrls <br> &#8226; clientData <br> &#8226; coverPhotos <br> &#8226; emailAddresses <br> &#8226; events <br> &#8226; externalIds <br> &#8226; genders <br> &#8226; imClients <br> &#8226; interests <br> &#8226; locales <br> &#8226; locations <br> &#8226; memberships <br> &#8226; metadata <br> &#8226; miscKeywords <br> &#8226; names <br> &#8226; nicknames <br> &#8226; occupations <br> &#8226; organizations <br> &#8226; phoneNumbers <br> &#8226; photos <br> &#8226; relations <br> &#8226; sipAddresses <br> &#8226; skills <br> &#8226; urls <br> &#8226; userDefined|
|`sources[]`|enum| A mask of what source types to return. Defaults to `READ_SOURCE_TYPE_PROFILE` and `READ_SOURCE_TYPE_CONTACT` if not set.|

### Response

If successful, the response body contains an instance of `Person` with information about the requested person.

### Authorization Scopes

No authorization is required to access public data. For private data, one of the following OAuth scopes is required:

- `https://www.googleapis.com/auth/contacts`
- `https://www.googleapis.com/auth/contacts.readonly`
- `https://www.googleapis.com/auth/directory.readonly`
- `https://www.googleapis.com/auth/profile.agerange.read`
- `https://www.googleapis.com/auth/profile.emails.read`
- `https://www.googleapis.com/auth/profile.language.read`
- `https://www.googleapis.com/auth/user.addresses.read`
- `https://www.googleapis.com/auth/user.birthday.read`
- `https://www.googleapis.com/auth/user.emails.read`
- `https://www.googleapis.com/auth/user.gender.read`
- `https://www.googleapis.com/auth/user.organization.read`
- `https://www.googleapis.com/auth/user.phonenumbers.read`
- `https://www.googleapis.com/auth/userinfo.email`
- `https://www.googleapis.com/auth/userinfo.profile`

For more information, see the Authorization guide.

### Example

To get information about the authenticated user, you can use the following URL:

```
GET https://people.googleapis.com/v1/people/me?personFields=names,emailAddresses
```

This will return a JSON response with information about the authenticated user's name and email addresses.