---
title: "Users"
permalink: /users/
excerpt: "Creating and managing users within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---
## User Management

User management within Skyve applications is accessed from the Admin -> Security Admin -> Users menu. This allows new users to be added, existing users to be marked inactive or deteled, and user permissions to be updated.

### Adding a new User

_Prerequisites:_ You have at least one group created for user permissions.

1. Login with a user which has the `SecurityAdministrator` role
2. Navigate to the Admin module, and select _Users_ under Security Admin
3. From the user list, click the `+` button to open the new user view
4. Click *New Person* 
    1. (alternatively, you can enter a name or email address of an existing Contact in the system and click Search to create a User for a Contact)
6. Enter the full name and email address of the new user and click *Next*
7. Change the generated username if required
8. Enter a matching password and confirm password, then click *Next*
9. Select the groups the new user will be added to by selecting it from the Unassigned list then clicking the right arrow (`>`)
10. Click _OK_ to save the user

### Inviting new users

To have the system send an invitation email to one or multiple new users, you can use the invitation feature. Invited users will receive an email with a link to the application, allowing them to choose their own password on first login.

_Prerequisites:_ 

* Your application has its SMPT settings configured to enable sending email
* You have at least one group created for user permissions

1. Login with a user which has the `SecurityAdministrator` role
2. Navigate to the Admin module, and select `Users` under Security Admin
3. Select the _Invite Users_ tab
4. From the list of Groups, assign any group permissions new users will have after they are invited by selecting the group(s) and clicking the right arrow (`>`)
5. Enter a comma or semicolon separated list of email addresses to be sent invitations into the text area below
6. Click the _Invite Users_ button