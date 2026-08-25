---
title: "Import and export"
permalink: /data-maintenance/
excerpt: "Import and Exporting data within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Skyve comes with a few different options for bulk importing and exporting of data out of the box. Some of these options are available in the Admin module. To access those described below, navigate to Admin -> DevOps -> Data Maintenance.

## Bizport

**Desktop mode required**: Bizport is only available in _desktop mode_ — the responsive interface does not include it. In the default (responsive) interface, use [Quick Import/Export](#quick-importexport) below instead. To switch modes, click your username in the top right hand corner and choose `Switch Mode` — see [Switching Interfaces]({{ site.url }}{{ site.baseurl }}/#switching-interfaces).
{: .notice--info}

Bizport is a powerful feature to allow sophisticated bulk data manipulation and offline data maintenance. If existing data is exported, the internal UUIDs will be exported in an Excel workbook, in the bizId column and also where references between records exist.

On import, if the bizId of the row of data is recognised by the system, the system interprets this as an attempt to update the data row. If the UUID is not recognised, the system assumes that the value in the bizId is actually a business key which will need to be replaced with a UUID to guarantee uniqueness.

### Export Data

To use Bizport to export data:

1. Login with a user which has the `DevOps` role
2. Switch to desktop mode if not already in it, by clicking your username in the top right hand corner and choosing `Switch Mode`
3. Navigate to the Admin module, and select `DevOps` -> `Data Maintenance`
4. From the Import/Export tab, select the Document to be exported in the Bizport form
5. Click `Export Data`
6. Your browser will download the data as a Microsoft Excel file

### Import Data

To use Bizport to bulk import new data into an application, first follow the instructions to Export Data so that you have a spreadsheet in the correct format
with the expected columns and tabs defined.

If the ID values provided in the sheet are found in your existing Skyve data, Bizport will update the existing record. If the ID value is not found, Bizport will insert the data.
For new data, ID values for references between sheets need to be consistent for related data to be inserted correctly.

1. Using your export file, add new data into the spreadsheet. Add your own id values to insert new records (e.g. 1,2,3... or any other values or legacy key values - using excel's drag-down feature is an easy way to set these if you don't have IDs from a legacy system), or modify existing exported data by re-using the exported ID. If adding records which are related (i.e. in multiple sheets), use the corresponding ID for the reference ID columns - each reference will have an ID column and a lookup column - drag down the lookup formula to check that your reference ID is referencing the correct record from the other sheet.
2. Login with a user which has the `DevOps` role
3. Switch to desktop mode if not already in it, by clicking your username in the top right hand corner and choosing `Switch Mode`
4. Navigate to the Admin module, and select `DevOps` -> `Data Maintenance`
5. From the Import/Export tab, select the destination Document for the import in the Bizport form
6. Click `Import Data`
7. Click `Choose` to select the file to import
8. Click `Upload`
9. You will get a message that the import completed successfully if everything works, or the Problems table will highlight any issues if the import fails 

## Quick Import/Export

While Bizport allows import and export of complex relationships, a simpler option to bulk load data into or out of Skyve is to use the Quick Import/Export option.

### Export Data

To export existing data from a Skyve application using the Quick Import/Export function:

1. Login with a user which has the `DevOps` role
2. Navigate to the Admin module, and select `DevOps` -> `Data Maintenance`
3. From the Import/Export tab, click the `+` button in the Quick Import/Export table
4. Change the Mode to `Export Data`
5. Select the Module and Document you wish to export in the Configure Options section
6. Click the `Download Data` button
7. Your browser will download the data as a Microsoft Excel file
8. You can either Save this configuration to re-use it again, or click Cancel

### Import Data

To import new data into a Skyve application using the Quick Import/Export function:

1. Login with a user which has the `DevOps` role
2. Navigate to the Admin module, and select `DevOps` -> `Data Maintenance`
3. From the Import/Export tab, click the `+` button in the Quick Import/Export table
4. Leave the Mode as `Import Data`
5. Select the destination Module and Document for the import in the Configure Options section
6. Click `Upload file`
7. Click `Choose` and use the file browser to locate your import spreadsheet. You can click `Get Template for Import` to download a correctly-formatted spreadsheet to fill in, or select your own `.xlsx` file.
8. Click `Upload`
9. Click the `x` in the top right corner to close the upload dialog
10. If the upload was successful, the Configure Import Columns table should be populated with the column headings from the spreadsheet.
11. Modify any bindings in the Configure Import Columns table to match the correct attributes of the destination Document
12. Click `Import data from file` to load the data from the spreadsheet
13. You can either Save this configuration to re-use it again, or click Cancel