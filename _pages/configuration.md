---
title: "Configuration"
permalink: /configuration/
excerpt: "Configuring settings within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Skyve applications come with several settings and options which allow the application to be configured at runtime.

## Password Complexity

Application password complexity can be customised based on your organisation's security requirements. Some options are restricted and require access to the application server for security reasons so they cannot be disabled.

1. Login with a user which has the `SecurityAdministrator` role
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`
1. On the `General` tab, configure the application password complexity options
1. Click `Save`

## Send a Test Email

Send a test email to confirm that email configuration has been entered successfully in your application.

_Prerequisites_: Your application has its SMPT settings configured to enable sending a test email.

1. Login with a user which has the `SecurityAdministrator` role
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`
1. On the `General` tab, specify the `Test Email` recipient, subject and email body
1. Click `Send Mail`

## Specify the Password Reset Message

Skyve applications come with a default password reset email message. This can be customised to provide specific instructions for users of your application.

_Prerequisites_: Your application has its SMPT settings configured to configure the password reset email.

1. Login with a user which has the `SecurityAdministrator` role
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`
1. On the `General` tab, specify the `Password Reset` sender email address, subject and body.
1. Click `Save`

## Configure Email Settings

Allow your Skyve application to send notifications and messages via email.

_Prerequisites_: Access to a SMTP server or email relay service (e.g. [Postmark](https://postmarkapp.com/) or [SendGrid](https://sendgrid.com/)).

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `Startup` tab, navigate to the `Mail Settings` section.
1. Enter the server url for your mail server, port, username and password.
1. The default sender should be modified to match the domain of your application.
1. Ensure `Test Mode` is unchecked.
1. If a `Test Mail Recipient` is set, all email will be sent to this address. Clear this to send to the intended recipient.
1. Click `Save`
1. To test that the entered configuration is working, select the `General` tab of the `Configuration` page
1. In the `Test Email` section, enter your email address and a test subject and email body and click `Send Mail`
1. Verify you received the email

_Note_: To prevent issues with email being sent from your Skyve application being flagged as spam, ensure the `General` tab's `Password Reset` -> `Send/From Email Address` and the `Startup` tab's `Configuration` -> `Mail Settings` -> `Default Sender` match the of your SMPT server or that of your application.

## Scheduling the disk space alarm

Skyve has the ability to monitor the available disk space of the server it is running on, however this is not enabled by default.

To schedule a disk space check which will email the system support user if disk falls below  a specified threshold, the user must have the *JobMaintainer* role in the admin module and have email configured.

_Prerequisites_: Your application has its SMPT settings configured to send the disk space alarm email.

To schedule the disk space alarm job:

1. Login with a user which has the `JobMaintainer` role
1. Navigate to the Admin module, and select the *Jobs* menu item
1. Switch to the *Schedule* tab
1. Click the `+` symbol to create a new schedule
1. Select *admin - Available Disk Space Alarm* as the *Job To Run*
1. Select an appropriate user as the *Run As* user (e.g. a system user or administrator)
1. Select the required frequency by specifying the minutes, hours, days, months and/or weekdays and a date range (if required)
    1. E.g. to schedule to run every day at 6am, change _Minutes_ to `Selected` and tick `00`, change _Hours_ to `Selected` and tick `06`
1. Click `Save` to save your schedule, or press `OK` to save and return to the schedule list.

### Configure Thresholds

_Prerequisites_: Your user has the *System Administrator* role.

By default, the disk space alarm will send an email to the Support Email Address configured in Configuration -> Startup Configuration when the available disk space reaches less than 10%.

To modify the threshold when the disk space alarm is set, navigate to the Configuration page, General tab. Under the _Available Disk Space Alarm_ section, you can enter a new percentage or alarm level in MB.