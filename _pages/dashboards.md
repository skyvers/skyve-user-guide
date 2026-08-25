---
title: "Dashboards"
permalink: /dashboards/
excerpt: "The User Dashboard and System Dashboard within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Skyve applications include two built-in dashboards: the *User Dashboard*, the personal landing page for every user, and the *System Dashboard*, an at-a-glance health and security view for administrators.

## User Dashboard

The User Dashboard is the default home page of the admin module — it is the first screen users see after signing in, and can also be reached from the `User Dashboard` menu item in the `Admin` module.

It contains:

- **Favourites** — shortcut tiles (up to six) to records you have recently or frequently worked with, generated automatically from your activity. Click a tile to go straight to that record.
- **My Details** — your own user name (read-only), full name, email address and mobile number. Update the details and click `Save` to change them — no administrator required.
- **My Activity** — charts summarising your recent activity in the application over the last fortnight.
- **My Jobs** — the background jobs you have run and their status (only shown if your permissions allow you to view jobs).

### Updating your own details

1. Login to your application — the User Dashboard is shown (or select `User Dashboard` from the `Admin` module menu).
1. In the `My Details` section, update your name, email address and/or mobile number.
1. Click `Save`.

_Note_: your email address is where the application will send password reset emails, two-factor authentication codes and notifications, so keep it up to date.

## System Dashboard

The System Dashboard gives administrators an at-a-glance view of system health, activity and security. To access it, your user requires the `SecurityAdministrator` role.

1. Login with a user which has the `SecurityAdministrator` role.
1. Navigate to the `Admin` module, and select `System Dashboard`.

The dashboard contains:

- **System Activity** — a chart of activity in the application over time.
- **System Status** — a checklist of recommended configuration items and whether each is in place, such as backups configured and scheduled, the available disk space alarm scheduled, and the anonymous public user configured. Items that are not configured include a suggestion of where to fix them.
- **Activity Breakdown** — charts showing where the recent activity in the application has occurred.
- **System Jobs** — recent background jobs across all users.
- **Recent Security Logs** — the most recent entries from the [Security Log]({{ site.url }}{{ site.baseurl }}/security-log/).

The System Status checklist is a useful first stop after standing up a new application — work through any unconfigured items it lists, using the [Configuration]({{ site.url }}{{ site.baseurl }}/configuration/) and [Backup and restore]({{ site.url }}{{ site.baseurl }}/backup-restore/) guides.
