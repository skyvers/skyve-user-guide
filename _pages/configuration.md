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

_Prerequisites_: Your application has its SMTP settings configured to enable sending a test email.

1. Login with a user which has the `SecurityAdministrator` role
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`
1. On the `General` tab, specify the `Test Email` recipient, subject and email body
1. Click `Send Mail`

## Specify the Password Reset Message

Skyve applications come with a default password reset email message. This can be customised to provide specific instructions for users of your application.

_Prerequisites_: Your application has its SMTP settings configured to configure the password reset email.

1. Login with a user which has the `SecurityAdministrator` role
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`
1. On the `General` tab, specify the `Password Reset` sender email address, subject and body.
1. Optionally specify the `Password Reset Token Expiry (minutes)` to limit how long password reset links remain valid after they are requested. Clear this setting to have tokens that never expire.
1. Click `Save`

## Two-Factor Authentication

Two-Factor Authentication (2FA) enhances security by requiring an additional step to verify a user's identity. When email 2FA is enabled, users must enter a one-time code sent to their email address each time they log in, in addition to their password.

Email 2FA must first be activated for your application by your Skyve provider before it can be configured, and is available to customers covered by a support agreement. If it has not yet been activated, selecting `Email` as the Two-Factor Type will display a message advising you to contact [info@skyve.org](mailto:info@skyve.org) to enquire about enabling it.

Once activated, the following configuration options are available:

- **Two-Factor Type**: This can be set to one of the following values:
  - **Off**: Disables 2FA.
  - **Email**: Enables 2FA via email. A one-time code is sent to the user's email address and will be required to log in.
- **Two-factor Email Subject**: Customise the email subject for the 2FA email sent to users.
- **Two-factor Body**: Customise the email body text for the 2FA email sent to users. The body must include the `{tfaCode}` placeholder, which is replaced with the user's one-time code when the email is sent.
- **Two Factor Code Timeout (seconds)**: Specify the duration (in seconds) for which the 2FA email code remains valid. The default is 300 seconds (5 minutes).

### Configuring Email Two-Factor Authentication

_Prerequisites_: Email 2FA has been activated for your application, your application has its SMTP settings configured, and your users have email addresses recorded against their contact details.

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `General` tab, navigate to the `Two Factor Authentication` section.
1. Set the `Two-Factor Type` to `Email`. A default email subject, body and code timeout will be pre-filled for you.
1. Customise the email subject, body and code timeout as required, ensuring the body retains the `{tfaCode}` placeholder.
1. Click `Save`.

### What Users Will Experience

Once email 2FA is enabled, it applies to all users of the application. After entering their username and password at the login page, users will be emailed a one-time verification code and prompted to enter it before they can access the application. If the code is not entered before the timeout elapses, they will need to log in again to be sent a new code.

Users who do not receive their code should check their spam/junk folder, and confirm with an administrator that the email address recorded against their user account is correct.

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

_Prerequisites_: Your application has its SMTP settings configured to send the disk space alarm email.

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
1. On the `Startup Configuration` tab, navigate to the `Mail Settings` section.
1. Enter the server url for your mail server, port, username and password.
1. The default sender should be modified to match the domain of your application.
1. Ensure `Test Mode` is unchecked.
1. If a `Test Mail Recipient` is set, all email will be sent to this address. Clear this to send to the intended recipient.
1. Click `Save`
1. To test that the entered configuration is working, select the `General` tab of the `Configuration` page
1. In the `Test Email` section, enter your email address and a test subject and email body and click `Send Mail`
1. Verify you received the email

_Note_: To prevent issues with email being sent from your Skyve application being flagged as spam, ensure the `General` tab's `Password Reset` -> `Send/From Email Address` and the `Startup` tab's `Configuration` -> `Mail Settings` -> `Default Sender` match that of your SMTP server or your application.

## Map Settings

Map settings define the mapping capabilities for your Skyve application:

- **Type**: Which map technology would you like to use for this Skyve application? Either Google Maps or Open Street Map. Note: Google Maps requires an API key and a credit card.
- **Zoom**: What should the default zoom level be when opening a new map (value between 1-19)? This determines how zoomed in or out the map is when showing a map with a location set.
- **Layers**: Google Map or Leaflet layer to show the map backdrop.
- **Centre**: Where to centre a new map by default when it opens.

To modify the map settings for your application:

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `Startup Configuration` tab, navigate to the `Map Settings` section.
1. Modify the map settings as required.
1. Click `Save`.

## Security Settings

Security settings enhance user safety and protect against unauthorized access:

- **Check for Breached Password**: When users try to create or change a password, this checks whether the new password has been compromised in known data breaches (requires internet access).
- **CAPTCHA Type**: Which CAPTCHA service to use for the self-registration and self-service password reset (forgot password) function. You may choose between Cloudflare Turnstile and Google Recaptcha or leave blank to not enable a CAPTCHA.
- **Site and Secret Keys**: These are required if using either CAPTCHA service and can be obtained from the Google Recaptcha console or Cloudflare Turnstile console.
- **Geo IP Key/Token**: By supplying a Geo IP API token (one can be obtained from [ipinfo.io](https://ipinfo.io/)), you can create a list of allowed or disallowed countries for registration and password reset. See [Geographical IP Restrictions](#geographical-ip-restrictions) below for detailed setup instructions.

To modify the security settings for your application:

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `Startup Configuration` tab, navigate to the `Security Settings` section.
1. Modify the security settings as required.
1. Click `Save`.

## Geographical IP Restrictions

Introduced in Skyve 9.2, geographical IP (Geo IP) restrictions allow your application to allow or deny user self-registration and self-service password reset (forgot password) requests based on the country the request originates from. This can help protect your application from bot submissions and suspicious activity from unexpected locations.

Geo IP restrictions are disabled by default. Skyve uses [ipinfo.io](https://ipinfo.io/) as the geolocation provider, so you will need to register for an account with ipinfo.io to obtain an API token before enabling this feature.

The following options are available:

- **Geo IP Key/Token**: The API token obtained from ipinfo.io. Entering a token enables the feature and reveals the remaining options below.
- **Country List Type**: Determines how the selected countries are treated:
  - **Whitelist**: Only requests from the selected countries are allowed; all other countries are denied.
  - **Blacklist**: Requests from the selected countries are denied; all other countries are allowed.
- **Countries**: The list of countries to allow (whitelist) or deny (blacklist).

### Enabling Geographical IP Restrictions

1. Register for an account at [ipinfo.io](https://ipinfo.io/) and obtain an API token.
1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `Startup Configuration` tab, navigate to the `Security Settings` section.
1. Enter your API token into the `GEO IP Key/Token` field. The country selection options will then be displayed.
1. Select the desired `Country List Type` (`Whitelist` or `Blacklist`).
1. Move the applicable countries from `Available Countries` to `Selected Countries`.
1. Click `Save`.

Once enabled, self-registration and password reset requests from denied countries will be silently rejected (the requester receives no indication that they were blocked) and a `GEO IP Block` security event will be recorded against the affected user.

### Geo IP Block Notifications

To be notified by email when a Geo IP block occurs:

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `Startup Configuration` tab, navigate to the `Notifications` section.
1. Check `Geo IP Block Notifications`.
1. Optionally specify a `Security Notifications Email Address`. If not specified, notifications will be sent to the support email address.
1. Click `Save`.

_Related_: When `Enable IP Address Checks` is enabled in the `Security Settings` section, Skyve also uses geolocation to log a security event when a user logs in from a different country than their previous logins. Check `Different Country Login Notifications` in the `Notifications` section to receive an email when this occurs.

## Password Change Notifications

Skyve applications can notify users by email whenever their password is changed, so they can alert support if the change was not made by them. When Geo IP is configured (see [Geographical IP Restrictions](#geographical-ip-restrictions)), the notification email also includes the location the password change was made from.

_Prerequisites_: Your application has its SMTP settings configured, and a `Support Email Address` is specified in the `Environment Settings` (the notification invites users to contact this address if they suspect malicious activity, and is not sent without it).

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Configuration`.
1. On the `Startup Configuration` tab, navigate to the `Notifications` section.
1. Check `Password Change Notifications`.
1. Click `Save`.