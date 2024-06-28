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

_Prerequisites:_ Your application has its SMPT settings configured to enable sending email.

The following example will walk through using the built in Communication feature from the admin module to send an email from within a Skyve application. In this example, we will use the Tag feature to select some Contacts as the recipients of the test email.

1. Login with a user which has the `ContactManager` or `SecurityAdministrator` role
2. From the top right hand corner, switch to power user mode if not already in there

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
12. Enter `test email` into Description
13. Select `Admin` as the Module from the drop-down
14. Select `Contact` as the Document from the drop-down
13. Select the tag we just created, `email contacts`, from the Tag drop-down
14. Click `Save` to save your Communication
15. Click `Get Count` and it should show the number of tagged Contacts in the Reulsts section

    ![Communication results]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-4.png)

16. Select the `Contents` tab
17. In the `To:` address, we are going to enter an expression to use a field from the tagged contacts. This operates similarly to a mail merge, and Skyve will substitue the expression value with the contact value for each tagged record. Enter `{email1}`, which is the name of the contact *email address* field.
18. Enter `test email` into Subject (this can also be an expression)
19. Click the `Edit` button to the right of Body to open the HTML editor
20. Enter some text into the email body and click `Apply`

    ![communication properties]({{ site.url }}{{ site.baseurl }}/assets/images/communication/comm-5.png)

21. Attachments can be added from the `Options` tab, but for now return to the `Manage` tab
22. Click `Send Now`
23. A new background job will be initiated to send your email immediately in the background. The results of the job can be checked from the `Jobs` screen.

## Editing an existing Communication

When you have existing Communcations in your application and wish to make changes to the content of the email.

_Prerequisites:_ Your application has at least one ad-hoc or system communication defined

1. Login with a user which has the `ContactManager` or `SecurityAdministrator` role
2. From the admin menu, select Communication->`Communications`
3. Open the communication you wish to edit
4. Select the `Contents` tab
5. Modify the `To` or `CC To` fields if you would like to change who receives the communication. This can be an expression.
5. Modify the `Subject` and/or the `Body` with any desired changes. These can contain expressions.
6. Click `OK` to save the modifications 