---
title: "Backup and restore"
permalink: /backup-restore/
excerpt: "Using Skyve backupa and restore."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

## Backup and restore

Skyve provides a powerful backup and restore facility that offers a unique range of features.

![Backup and restore](./../_pages/backup-restore/backup-tab.png "Backup and restore")

Feature | Description
--------|------------
platform independent | e.g. backups taken on Windows systems can be restored to Linux systems and vice versa  
database independent | e.g. backups taken from a system using one database provider (e.g. MS SQL Server) can be restored to systems using another provider (e.g. Oracle, H2 or MySQL) and vice versa
includes structured and non-structured data | backups include both SQL/relational/structured database data as well as non-structured/non-sql content items (note that structured and non-structured data are not necessarily guaranteed to be synchronised)

Skyve also offers a range of restore *Pre-Process* options to handle cases where a backup was taken from an application with v1 domain model or schema and is restored to an application running v2, or vice versa.

*NOTE* that Skyve backup and restore is an application wide function - across all customer data segments. If your application is a multi-tenant SaaS application, you should consider carefully both backup and restore options.

### Scheduling backups

To schedule backups the user must have the *JobMaintainer* role in the admin module.

To schedule the job:

1. Login with a user which has the `JobMaintainer` role
2. From the top right hand corner, switch to power user/desktop mode if not already in there

    ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)
    
3. Navigate to the Admin module, and select the *Jobs* menu item
4. Switch to the *Schedule* tab
5. Click the `+` symbol to create a new schedule
6. Select *admin - Scheduled Backup all data and content* as the *Job To Run*
7. Select an appropriately credentialled user as the *Run As* user
8. Select the required frequency by specifying the minutes, hours, days, months and/or weekdays and a date range (if required)
9. Click `Save` to save your schedule, or press `OK` to save and return to the schedule list.

An example configuration is shown for daily backups.

![Daily backup schedule](./../_pages/backup-restore/daily-backup-schedule.png "Daily backup schedule")

### Cyclic retention

The Skyve platform includes cyclic retention settings to allow you to control how many backups are kept.

To access the cyclic retention settings:

1. Login with a user which has the `DevOps` role
2. From the top right hand corner, switch to power user/desktop mode if not already in there

    ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)
    
3. Navigate to the Admin module, and select the *Data Maintenance* menu item
4. Switch to the *Backups* tab
5. The cyclic retention settings are located at the top of the tab as shown below.

![Cyclic backup retention](./../_pages/backup-restore/cyclic-period-schedule.png "Cyclic backup retention")

### Restoring a Skyve backup

Skyve offers a number of *Pre-Process* options to handle cases where the application domain model may have progresses since the backup was taken - this situation is not typically handled by other platforms. 

![Restore options](./../_pages/backup-restore/restore-options.png "Restore options")

#### Content Option

The *Content Option* allows control over whether content items which may have been orphaned in the backup are restored.

Skyve stores the ID of "attachments" or content items in the `content` type attribute.

Consider the situation where developers have modified the application since the backup was taken, and `content` type attributes may have been deprecated resulting in the associated content items becoming *orphaned* (or disconnected). 

In this situation, the options provide are as follows:

Option | Description
-------|-----------
Clear Orphaned Content IDs | With this option selected, the restore will clear any orphaned content IDs leaving the associated `content` type attributes `null`. 
Save Orphaned Content IDs | With this option selected, the restore will preserve orphaned content IDs, which may be useful if an attempt will alter be made to reunite content items with the structure data store.
Error | (*Recommended*) With this options set, if orphaned content items are discovered during the restore, the restore will fail (error) and roll-back. 

The recommended setting is *Error*.

#### Indexing Option

Skyve maintains an index to long text items and content items in a consolidated index that supports federated (i.e system-wide) searching (See [Content Search](./../_pages/content-search.md))

While indexing is not critical to the restore process, content searching will be invalid after a restore until the indexing process is completed.

If the backup being restored is large, or the restore process is taking a large amount of time for other reasons, you may wish to decide to complete only a partial indexing or none (and perform the index at a later time).

Option | Description
-------|-----------
Data | Index only the sql/structure/relational data during the restore.
Content | Index only content/non-sql/non-structured data during the restore.
Both | (*Recommended*) Index both data items flagged for indexing *and* content items during the restore.
None | Use this option if you intend to perform indexing at another time.

The recommended setting is *Both*.

To perform indexing after the restore is complete, use the *Reindex* action on the *Content* tab.

#### Restore Pre-Process

To handle situations where there is a mismatch between the domain/schema of the backup and the system being restored, Skyve provides a number of *Pre-Process* options.

To provide more options for recovery and resolving of schema mismatches, the Skyve backup format includes sql scripts to create (create.sql) and delete tables (delete.sql) for the schema of the backup. 

Some options are only available for single-tenant applications - that is, where only one customer is declared.

Option | Availability | Description 
-------|--------------|-------------
*None* | All | Perform no processing prior to the restore, existing data will remain in place and data from the restore will be added to the system | Use this if you are restoring to an empty system, or if the intention is to add data from the backup to the current system data. Use this option when you've created your database from scratch (or with the bootstrap) and you've let the Skyve create all DDL. You know the backup is from the same version and the schema is synchronised (matches the metadata). Drop tables using metadata & recreate tables from backup create.sql | Use this option when your backup is from a different version of the application, you want the schema to be dropped (the schema matches the metadata) using the system metadata deployed, but you need the schema to look like it did when the backup was taken. (Part of the restore post-process is to sync the schema and reindex content.)
*Drop tables using backup drop.sql & recreate tables from backup create.sql* | Single tenant | Use this option when your schema matches the application version of the backup (maybe your previous attempt to restore failed). You cant drop the schema without stopping the server and if you do that, you can't log in any more without restoring. Since the backup/restore only looks after tables under Skyve control, it could be that extra tables have constraints that you need to drop or other issues that you only find after trying to restore.
*Drop tables using metadata & recreate tables from metadata* | Single tenant | Use this option when you know the backup is from the same version of the application. You have a large amount of data that you want to delete and the quickest way is drop and recreate the schema.
*Drop tables using backup drop.sql & recreate tables from metadata* | Single tenant | Use this option when you've tried a restore before and your database is now in the shape of the backup application version.
*Create tables from backup* | Single tenant | Use this option when you've created a empty schema (manually or scripted).
*Create tables from metadata* | Single tenant | Use this option when you have a empty schema but the backup application version doesn't match your version.
*Delete existing table data using metadata* | All | Use this option when the backup is from the same version of the application and your data size is not large (i.e. just delete the data and then run the restore.)

The recommended setting is *Delete existing table data using metadata*.
