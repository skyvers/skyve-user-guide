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

_Prerequisites:_ Your application has its SMTP settings configured to enable sending email. If SMTP is not configured, a warning banner is shown at the top of the Communication view.

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

22. Attachments can be added from the `Attachments` tab if required (see [Attachments and calendar invites](#attachments-and-calendar-invites))
23. Optionally, click `Test Send to yourself` first — this sends the email to your own email address, using the first tagged record for expression substitution, so you can check the result before sending to everyone. At least one record must be tagged or the test will fail with an error.
24. Click `Send Now`
25. A new background job will be initiated to send your email immediately in the background. The results of the job can be checked from the `Jobs` screen, or by clicking `Run Result Check Job` on the `Manage` tab.

Two further options on the `Manage` tab affect the send:

- **Untag successful documents**: each record is removed from the tag as its email sends successfully, so after a partial failure the tag contains only the records still to send.
- **Notify when job is complete**: sends you a notification email when the send job finishes.

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

_Note_: communications marked `Used for System communications` (such as the built-in password reset and user invitation emails) have their Description, Module and Document locked and cannot be deleted — you can still edit the subject and body. Untick the system flag first if you really need to change or remove one.

## Embedding an image

To embed an image in the email body without hosting it externally, use the `Add Uploaded Image` button in the `Options` section of the `Contents` tab. Upload an image file and Skyve will append it to the body as an embedded image.

## Attachments and calendar invites

The `Attachments` tab allows up to three files to be attached to the email.

The `Attachments` tab also provides a `Calendar` section for sending calendar invites. Tick `Include Calendar Item` on the `Contents` tab, then specify the `Title (expression)`, `Start Time`, `End Time` and `Description (expression)` — recipients receive Google and Yahoo calendar links in the email body along with an `.ics` attachment for Outlook and Apple Calendar.

## Unsubscribe links and Subscriptions

For bulk communications, recipients should be given a way to opt out:

1. On the `Contents` tab, click `Add Unsubscribe Link` in the `Options` section — this appends an unsubscribe link to the email body (using the `{unsubscribeUrl}` token, which is substituted per recipient).
2. When a recipient clicks the link, a declined *Subscription* record is created for them for this communication.
3. Declined recipients are shown on the communication's `Subscriptions` tab (visible once the communication has been saved), and are automatically excluded from future sends of that communication.

## Generating files instead of sending

Instead of emailing directly, a communication can generate the messages as `.eml` files on the server — useful for review, archiving, or processing by another system:

1. On the `Manage` tab, click `Generate File Batch` — a batch of files is generated, one per tagged recipient.
2. Each batch appears in the `Batches` list on the `Manage` tab.
3. Select a batch and use `Download Zip` to download the generated files, or `Delete` to remove the batch from the server.