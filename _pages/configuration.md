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