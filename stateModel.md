# Requirements

1. A user can view a dashboard that displays a list of contacts
   - Each contact in the list should be displayed as their first and last names
2. A user can click a contact's name to view more details about that contact
   - The view should contain the contact's first and last name, as well as the contact's street and city
3. A user can create a contact via a form, accessed by clicking a "Create a contact" menu link
   - The form should create a contact with a first and last name, as well as a street and city
   - When submitted, the contact data should be sent to an API that saves it
   - The user should then be automatically navigated back to the contact list

# State models

```json
contacts =
{
"firstName": "Ludwig",
"lastName": "Bergstrom",
"street": "The Drive",
"city": "Fort Danial",
"id": 1
},[]
```

```json
form =
{
"firstName": "",
"lastName": "",
"street": "",
"city": "",
}
```

# Component tree

- Root App
  - [contacts, setContacts]
- **Navbar**
  - -> _/contacts_
  - -> _/contacts/create_
- Routes
  - **ContactsListPage** _/contacts_ {contacts, setContacts}
    - (Display a list of all the contacts)
    - **ContactsListItem** {contact}
      - -> ContactDetailsPage
  - **ContactDetailsPage** _/contacts/:id_ {contact}
    - (Display detailed view of the selected contact)
  - **CreateContactPage** _/contacts/create_
    - (Form to post a contact)
    - [form, setForm]
    - on submit -> _/contacts_

### Syntax explanation

- **Component**
- _Route_
- {Props}
- (Comments)
- Navigation -> _route_
- [state, setState]
