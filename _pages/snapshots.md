---
title: "Snapshots"
permalink: /snapshots/
excerpt: "Working with Snapshots within Skyve applications"
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Another powerful feature of [List Grids]({{ site.url }}{{ site.baseurl }}/lists) in the desktop
mode of Skyve applications is Snapshots. Snapshots allow you to save customisations to a list grid — 
advanced filters, sorting, column selection and widths, grouping, and the [summary line]({{ site.url }}{{ site.baseurl }}/lists/#summary-line) selection.

A snapshot belongs to the list it was created on — it appears in the `Snapshot` menu of that list only.

**Desktop mode required**: Snapshots are only available in _desktop mode_, including the `admin -> Snapshots` menu item used later on this page. To switch modes, click your username in the top right hand corner and choose `Switch Mode` — see [Switching Interfaces]({{ site.url }}{{ site.baseurl }}/#switching-interfaces).
{: .notice--info}

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

To return the list to its default configuration, select `No Snapshot` from the `Snapshot` menu.

## Updating a Snapshot

To make changes to an existing snapshot:

1. Navigate to a list grid with a saved snapshot
1. From the `Snapshot` menu, click the name of the snapshot you wish to update to select it first
1. Make the changes to your selected snapshot that you wish to apply and save
1. From the `Snapshot` menu again, hover over the name of the selected snapshot and select `Update Snapshot`
1. Your snapshot will be updated to reflect the current list grid configuration

_Note_: the `Update Snapshot` menu item is disabled (shown as "Update Snapshot (Select the Snapshot first)") until the snapshot is the currently selected one.

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
1. In desktop mode, you can also enter a name for the copied snapshot (in the default responsive interface, the copy keeps the original name)
1. Click `Make Copy`

The copy is owned by the recipient — it appears in _their_ `Snapshot` menu on the same list.

## Reordering Snapshots

If you have several snapshots on one list, you can control the order they appear in the `Snapshot` menu:

1. Navigate to `admin -> Snapshots`
1. Select the `Reorder Snapshots` tab
1. Select the module and list your snapshots belong to
1. Drag and drop the snapshots into the desired order
1. Click `Reorder` to save the new order