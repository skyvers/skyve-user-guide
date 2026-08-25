---
title: "Security Log"
permalink: /security-log/
excerpt: "Monitoring security events and sign in history within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Skyve applications record security-related events as they happen, so that suspicious activity and intrusions can be detected in near real time. This page covers the two places an administrator can review this activity: the *Security Log* and the *Sign In History*.

## Security Log

The Security Log is a list of security events recorded by the application. An event is recorded automatically whenever an access or security exception occurs (for example, a user attempting to reach a record or feature they do not have permission for), and for security-relevant activity such as:

- Geo IP blocks (see [Geographical IP Restrictions]({{ site.url }}{{ site.baseurl }}/configuration/#geographical-ip-restrictions))
- Logins from a new IP address or a different country
- Concurrent session warnings (a second session started from another device)
- Password changes

### Viewing the Security Log

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Security Log`.
1. The list shows the `Timestamp`, `Username`, `Event Type` and `Event Message` for each event, most recent first.
1. Zoom into an event to see its full details, including the `Source IP` address the request came from and the `Logged In User ID`.

Security Log records are read-only — they are created by the system and cannot be edited.

The most recent security events are also shown at the bottom of the [System Dashboard]({{ site.url }}{{ site.baseurl }}/dashboards/#system-dashboard).

### Email notifications for security events

Skyve can email an administrator as security events occur. Notifications are sent to the `Security Notifications Email Address` if one is specified on the `Startup Configuration` tab of the Configuration page, otherwise to the application's `Support Email Address`.

Which events generate an email is controlled by the checkboxes in the `Notifications` section of the `Startup Configuration` tab — for example `Geo IP Block Notifications`, `Different Country Login Notifications`, `IP Address Change Notifications`, `Access Exception Notifications` and `Security Exception Notifications`. See [Configuration]({{ site.url }}{{ site.baseurl }}/configuration/) for details.

## Sign In History

The Sign In History lists every login to the application — successful and failed — so an administrator can review who has been accessing the system, and from where.

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and under `Security Admin`, select `Sign In History`.
1. The list shows the `User Name`, `Login Date/Time`, whether the attempt `Failed`, and the `IP Address` the login came from, most recent first.
1. If Geo IP is configured (see [Geographical IP Restrictions]({{ site.url }}{{ site.baseurl }}/configuration/#geographical-ip-restrictions)), the `Country Code` and `Country Name` columns show which country each login came from.

When `Enable IP Address Checks` is enabled on the `Startup Configuration` tab, Skyve compares each login against the user's previous sign in records — a login from a new IP address or a different country is recorded in the Security Log, and can trigger a notification email as described above.
