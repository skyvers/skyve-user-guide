---
title: "Communication"
permalink: /communication/
excerpt: "Configuring and sending communications within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Communications within a Skyve application is where ad-hoc and system email messages are created and edited. New email messages can be created and use data from within the system as the recipient and/or the body of the email. System messages can also be maintained here if notifications need to be updated over time, for example signatures or contact details. 

## Create and send a new Communication

_Prerequisites:_ Your application has its SMTP settings configured to enable sending email.

The following example will walk through using the built in Communication feature from the admin module to send an email from within a Skyve application. In this example, we will use the Tag feature to select some Contacts as the recipients of the test email.

1. Login with a user which has the `ContactManager` or `SecurityAdministrator` role
2. Switch to desktop mode if not already in it, by clicking your username in the top right hand corner and choosing `Switch Mode` — see [Switching Interfaces]({{ site.url }}{{ site.baseurl }}/#switching-interfaces). Tagging records from a list is only available in desktop mode.

    ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)
    
3. Navigate to the Admin module, and select `Contacts`
4. From the toolbar Tag dropdown, select `New Tag`

    ![Create new tag]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-1.png)

5. Name your tag `email contacts`
6. Click `OK`
7. The toolbar now shows we have the new tag active

    ![Active tag]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-2.png)

8. Tag some contacts by clicking the checkbox next to contacts in the first column (Tag)
9. The tagged contacts will update to be marked in bold

    ![Tagged contacts]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-3.png)

10. From the admin menu, select Communication->`Communications`
11. Click the `+` symbol to create a new Communication
12. On the `Contents` tab, enter `test email` into Description
13. In the `To` field, we are going to enter an expression to use a field from the tagged contacts. This operates similarly to a mail merge, and Skyve will substitute the expression value with the contact value for each tagged record. Enter `{email1}`, which is the name of the contact *email address* field.
14. Enter `test email` into `Subject (expression)` (this can also contain expressions)
15. Enter some text into `Body (expression)`. In the default (responsive) interface this is a plain text field — type your message, or paste in HTML directly. In desktop mode, an `Edit` button opens a rich HTML editor instead — enter your text and click `Apply`.

    ![communication properties]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-5.png)

16. Select the `Manage` tab
17. Select `Admin` as the Module from the drop-down
18. Select `Contact` as the Document from the drop-down
19. Select the tag we just created, `email contacts`, from the Tag drop-down
20. Click `Save` to save your Communication
21. Click `Get Count` and it should show the number of tagged Contacts in the Results section

    ![Communication results]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-4.png)

22. Attachments can be added from the `Attachments` tab if required
23. Click `Send Now`
24. A new background job will be initiated to send your email immediately in the background. The results of the job can be checked from the `Jobs` screen.

## Editing an existing Communication

When you have existing Communcations in your application and wish to make changes to the content of the email.

_Prerequisites:_ Your application has at least one ad-hoc or system communication defined

1. Login with a user which has the `ContactManager` or `SecurityAdministrator` role
2. From the admin menu, select Communication->`Communications`
3. Open the communication you wish to edit
4. Select the `Contents` tab
5. Modify the `To` or `CC To` fields if you would like to change who receives the communication. This can be an expression.
6. Modify the `Subject (expression)` and/or the `Body (expression)` with any desired changes. These can contain expressions.
7. Click `OK` to save the modifications