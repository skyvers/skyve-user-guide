---
title: "Audits"
permalink: /audits/
excerpt: "Reviewing the change history of records within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Skyve applications automatically keep an audit trail of data changes — every insert, update and delete is recorded with who made the change and when. Audits answer the common administrative question: *"who changed this record, and what did it look like before?"*

To view audits, your user requires the `SecurityAdministrator` or `AuditManager` role.

## Viewing audits

1. Login with a user which has the `SecurityAdministrator` or `AuditManager` role.
1. Navigate to the `Admin` module, and select `Audits`.
1. On the `Audits` tab, the list shows the `Timestamp`, `User`, `Operation` (`Insert`, `Update` or `Delete`), `Module`, `Document` and `Description` of each audited change, most recent first.
1. Use the column filters to narrow the list — for example, filter on `Document` and `Description` to find all changes to a particular record, or on `User` to review one person's activity.
1. Zoom into an audit to see the details of that version.

## Comparing versions

In desktop mode, zooming into an audit additionally provides a comparison view. Select the `Source Version To Compare` and the `Other Version To Compare` from the drop-downs to see a field-by-field comparison of the record between any two audited versions, highlighting what changed.

## Archived Audits

To keep the database lean, applications can be configured to archive older audit records out of the database into archive files on the server. When archiving is enabled, the Audits view shows an additional `Archived Audits` tab, which lets you browse and search the archived records in the same way as the `Audits` tab.

Audit archiving and audit log maintenance (such as truncating old audits) are administrative operations performed via the `Data Maintenance` function and scheduled jobs — if you need audits archived or trimmed, contact your system administrator or Skyve provider.
