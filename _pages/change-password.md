---
title: "Change Password"
permalink: /change-password/
excerpt: "Changing your own password within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Every user of a Skyve application can change their own password at any time — no administrator required. (If you have forgotten your password and can't sign in, use the *Forgot password* link on the sign in page instead. If an administrator needs to reset another user's password, see [Resetting a password]({{ site.url }}{{ site.baseurl }}/users/#resetting-a-password).)

## Changing your password

1. Login to your application.
1. Navigate to the `Admin` module, and select `Password`.
1. Enter your current password into `Old Password`.
1. Enter your new password into `New Password`, and again into `Confirm Password`. As you enter your new password, the application provides feedback on whether it meets requirements.
1. Click `Change Password`.

A confirmation message is shown once your password has been changed.

## Notes

- Your new password must meet the application's password complexity rules (minimum length and required character types), which are set by your administrator — see [Password Complexity]({{ site.url }}{{ site.baseurl }}/configuration/#password-complexity).
- If the *Check for Breached Password* security setting is enabled, passwords that have appeared in known data breaches will be rejected — choose something unique.
- If *Password Change Notifications* are enabled, you will receive an email confirming the change — see [Password Change Notifications]({{ site.url }}{{ site.baseurl }}/configuration/#password-change-notifications). If you receive one of these emails without having changed your password, contact your administrator immediately.
