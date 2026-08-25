---
title: "Reports"
permalink: /reports/
excerpt: "Running and scheduling reports within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Skyve applications can include pre-built reports which users run on demand, and which administrators can schedule to be generated and emailed automatically. (For ad-hoc exporting and charting of list data, see [List Functionality]({{ site.url }}{{ site.baseurl }}/lists/) instead.)

## Running a report

The `Reports` menu item is available in the default (responsive) interface to users with the `BasicUser` role. The list shows the enabled reports available to you — if a report is restricted to a specific role, it only appears when your user holds that role.

1. Login to your application.
1. Navigate to the `Reports` menu group, and select `Reports`.
1. The list shows the `Name` and `Description` of each report you can run. Zoom into the report you want.
1. On the `Report Details` tab, fill in any values in the `Report Parameters` table (for example a date range, or a record to report on).
1. Click `Download Report`. Your browser will download the generated report in the report's configured output format.

## Scheduling a report

Reports can be scheduled to be generated automatically and emailed to selected users — for example, a weekly summary emailed to managers every Monday morning.

_Prerequisites_: Your application has its SMTP settings configured, and your user has the `DevOps` or `SecurityAdministrator` role. The `Report Schedules` menu item is only available in desktop mode (see [Switching Interfaces]({{ site.url }}{{ site.baseurl }}/#switching-interfaces)).

1. Login with a user which has the `DevOps` or `SecurityAdministrator` role.
1. Switch to desktop mode, then navigate to the `Reports` menu group and select `Report Schedules`.
1. The list shows each enabled report and a plain-English description of its current schedule (if any). Zoom into the report you wish to schedule.
1. On the `Schedule Details` tab, tick `Scheduled` to enable scheduling. The scheduling options will then be displayed.
1. Add the recipients to the `Users to Email` list.
1. Select the user the report should run as in the `Run As` lookup — the report will only include data this user is permitted to see.
1. Select the required frequency in the `When To Execute` section (hours, days, months and weekdays), and optionally a `Date Range To Execute`.
1. Click `Save`.

## Report Manager and Report Designer

The `Report Manager` and `Report Designer` menu items (desktop mode, `DevOps` role) are developer tools for creating and maintaining the report templates themselves, including exporting and importing report specifications between environments. Report design is covered by the <a href="https://skyvers.github.io/skyve-dev-guide/">Skyve developer guide</a>.
