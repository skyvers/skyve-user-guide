---
title: "Snapshots"
permalink: /snapshots/
excerpt: "Working with Snapshots within Skyve applications"
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Another powerful feature of [List Grids]({{ site.url }}{{ site.baseurl }}/lists) in the power user/desktop 
mode of Skyve applications is Snapshots. Snapshots allow you to save customisations to a list grid, such as 
advanced filters, custom sorting or column configuration.

To access Snapshots, switch into power user/desktop mode if not already in there.

![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)

## Creating a Snapshot

1. To create a snapshot, perform some customisations to a list grid, such as applying a custom filter.
1. From the `Snapshot` menu, select `New Snapshot`
1. Enter a name for your snapshot and click `OK`
1. Your `Snapshot` menu will update to show that you have your new snapshot selected

![New snapshot]({{ site.url }}{{ site.baseurl }}/assets/images/snapshots/new-shapshot.png)

## Loading/Restoring a Snapshot

After you have created a snapshot, you can load it when returning to the same list with your saved snapshot(s). 
To restore a saved snapshot:

1. Navigate to a list grid with a saved snapshot
1. From the Snapshot menu, click the name of the snapshot you wish to restore
1. Skyve will update the list grid with the settings in your saved snapshot

![Restore snapshot]({{ site.url }}{{ site.baseurl }}/assets/images/snapshots/restore-snapshot.png)

## Updating a Snapshot

To make changes to an existing snapshot:

1. Navigate to a list grid with a saved snapshot
1. From the `Snapshot` menu, click the name of the snapshot you wish to update to select it first
1. Make the changes to your selected snapshot that you wish to apply and save
1. From the `Snapshot` menu again, hover over the name of the selected snapshot and select `Update snapshot`
1. Your snapshot will be updated to reflect the current list grid configuration

![Update snapshot]({{ site.url }}{{ site.baseurl }}/assets/images/snapshots/update-snapshot.png)

## Deleting a Snapshot

To delete an existing snapshot you no longer want to keep:

1. Navigate to a list grid with a saved snapshot
1. From the `Snapshot` menu, hover over the name of the selected snapshot and select `Delete Snapshot`
1. Select `Yes` to confirm deletion of the snapshot

![Delete snapshot]({{ site.url }}{{ site.baseurl }}/assets/images/snapshots/delete-snapshot.png)

## Sharing a Snapshot

Snapshots are private to the user that created them, but if you have a useful snapshot you would like to share 
to others in your team, they can be copied. Note, if the recipient makes changes to the snapshot, it will 
not be reflected in your snapshot.

1. Login to the application with a user with the `Basic User` role
1. Navigate to `admin -> Snapshots`
1. Double click or zoom into the snapshot you wish to share with another user
1. Select a user from the `Copy to user` picker
1. Enter a name fo the snapshot
1. Click `Make Copy`