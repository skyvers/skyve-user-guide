---
title: "Contacts"
permalink: /contacts/
excerpt: "Managing contacts within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Contacts are the shared register of people and organisations in a Skyve application. Other admin module features are built on contacts — every [user account]({{ site.url }}{{ site.baseurl }}/users/) is linked to a contact (which provides the user's name and email address), and [Communications]({{ site.url }}{{ site.baseurl }}/communication/) are typically sent to tagged contacts.

Access to contacts is controlled by two dedicated roles:

- **ContactViewer** — view-only access to contact details.
- **ContactManager** — create, edit and delete contacts.

Users with the `SecurityAdministrator` role also have access.

## Viewing contacts

1. Login with a user which has the `ContactViewer`, `ContactManager` or `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and select `Contacts`.
1. The list shows the `Name`, `Contact Type`, `Email` and `Mobile` of each contact. Use the column filters to find a contact, and zoom in to see their details.

## Adding or editing a contact

1. Login with a user which has the `ContactManager` or `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and select `Contacts`.
1. Click the `+` button to add a new contact, or zoom into an existing contact to edit it.
1. Enter or update the `Name`, `Contact Type` (`Person` or `Organisation`), `Email` and `Mobile`, and optionally upload an `Image`.
1. Click `OK` to save.

_Note_: take care when deleting a contact — if the contact is linked to a user account or referenced by other records, it should be retained. For users, the best practice is to [deactivate the user]({{ site.url }}{{ site.baseurl }}/users/#deactivating-a-user) rather than delete their contact.
