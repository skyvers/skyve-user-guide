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

## Two-Factor Authentication

Two-Factor Authentication (2FA) enhances security by requiring an additional step to verify a user's identity. The configuration options are:

- **Two-Factor Type**: This can be set to one of the following values:
  - **Off**: Disables 2FA.
  - **Email**: Enables 2FA via email. A one-time code is sent to the user's email address and will be required to log in.
- **Code Expiry Timeout**: Specify the duration (in minutes) for which the 2FA email code remains valid. 
- **Two-factor Email subject**: Customise the email subject for the 2FA email sent to users.
- **Two-factor body**: Customise the email body text for the 2FA email sent to users.

_Note:_ Activating 2FA incurs an additional fee. Please contact info@skyve.org to enquire about enabling two factor email authentication for your application.

## User Self-Registration

User Self-Registration allows new users to sign-up to have an account in your Skyve application. The following options are available:

- **User Self-Registration Enabled**: Enable this feature from the Startup page. When enabled, users can sign up through a registration form.
- **User Self-Registration Group**: Select a default group that defines the permissions assigned to newly registered users. 
- **Activation Code Expiry**: Specify the number of hours the self-registration activation link remains valid after a user registers. Leaving this field empty allows activation links to remain active indefinitely.

## Anonymous Public User

If your application has public pages accessible to non-logged-in users, you can configure which permissions apply to such interactions:

- **Anonymous Public User**: Select a user account to represent anonymous users. Permissions assigned to this user will determine which records can be created, updated or deleted anonymously. For example, this may limit access to support table records or restrict the ability to create new records.

Ensure proper permissions and security settings are configured for the selected user to avoid unintended access or exposure of sensitive data.

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

## Environment Settings

Environment settings allow you to define key attributes for your application's environment:

- **Identifier**: The description of this environment, e.g., Test, UAT. Leave this blank for production. This will display a red bar at the top and bottom of every page in the application to signal to users they are in a non-production environment.
- **Support Email Address**: This is the email address that will be shown to users if there is an error on who to contact for support. This email will also receive automatic notifications for system alerts.

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

## Map Settings

Map settings define the mapping capabilities for your Skyve application:

- **Type**: Which map technology would you like to use for this Skyve application? Either Google Maps or Open Street Map. Note: Google Maps requires an API key and a credit card.
- **Zoom**: What should the default zoom level be when opening a new map (value between 1-19)? This determines how zoomed in or out the map is when showing a map with a location set.
- **Layers**: Google Map or Leaflet layer to show the map backdrop.
- **Centre**: Where to centre a new map by default when it opens.

## Security Settings

Security settings enhance user safety and protect against unauthorized access:

- **Check for Breached Password**: When users try to create or change a password, this checks whether the new password has been compromised in known data breaches (requires internet access).
- **CAPTCHA Type**: Which CAPTCHA service to use for the self-registration and self-service password reset (forgot password) function. You may choose between Cloudflare Turnstile and Google Recaptcha or leave blank to not enable a CAPTCHA.
- **Site and Secret Keys**: These are required if using either CAPTCHA service and can be obtained from the Google Recaptcha console or Cloudflare Turnstile console.
- **Geo IP Key/Token**: By supplying a Geo IP API token (one can be obtained from [ipinfo.io](https://ipinfo.io/)), you can create a list of allowed or disalled countries for registration and password reset.