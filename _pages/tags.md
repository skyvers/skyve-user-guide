---
title: "Tags"
permalink: /tags/
excerpt: "Working with Tags within Skyve applications"
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Another powerful feature of [List Grids]({{ site.url }}{{ site.baseurl }}/lists) in the power user/desktop 
mode of Skyve applications is Tags. Tags allow you to filter and store the selection of records within a Skyve 
list, or across multiple lists.

To access Tags, switch into power user/desktop mode if not already in there.

![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)

## Creating a Tag

1. To create a new tag, from the list toolbar, click the Tag control
1. Select `New Tag`
1. Enter a name for your tag and click `OK`
1. The `Tag` menu will update to show that you have your new tag selected

![New tag]({{ site.url }}{{ site.baseurl }}/assets/images/tags/new-tag.png)

## Adding records to a Tag

Tags are a re-usable filter that can be used to remember a selection of records. For example, 
if you have a list of Orders that you need to process, you can use a tag to indicate which records 
are still to do, and untag them once complete.

To add a _single_ record to the set of records as part of a tag:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, click the name of the tag you wish to use
1. Click the checkbox in the tag column to apply the tag to individual records

![Tag single record]({{ site.url }}{{ site.baseurl }}/assets/images/tags/tag-one.png)

To add _all_ records to the set of records as part of a tag:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, click the name of the tag you wish to use to select it
1. From the `Tag` menu again, hover over the name of the selected tag and select `Tag all in list`
1. The list will update to show that all records have been tagged

![Tag all records]({{ site.url }}{{ site.baseurl }}/assets/images/tags/tag-all.png)

## Removing records from a Tag

To remove a _single_ record from the set of records as part of a tag:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, click the name of the tag you wish to use
1. Click the checkbox in the tag column for a tagged record to remove the check to remove the tag from individual records

To remove the tag from _all_ records associated with a tag in a particular list:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, click the name of the tag you wish to use to select it
1. From the `Tag` menu again, hover over the name of the selected tag and select `Untag all in list`
1. The list will update to show that all records have been untagged

![Untag all records]({{ site.url }}{{ site.baseurl }}/assets/images/tags/untag-all.png)

## Loading/Restoring a Tag

After you have created a tag, you can load it when returning to the same list with your saved tag(s). 

To restore a saved tag:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, click the name of the tag you wish to restore
1. Skyve will update the list grid with the tagged records in the list

![Restore tag]({{ site.url }}{{ site.baseurl }}/assets/images/tags/restore-tag.png)

## Updating a Tag

To make changes to which records are selected for an existing tag:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, click the name of the tag you wish to update to select it first
1. The `Tag` menu will update to show that you have your new tag selected
1. Make the changes to your selected tag using the Tag column for single records or the tag menu to select/deselect all
1. Tag selection changes are saved immediately, no further action is required

## Deleting a Tag

To delete an existing tag you no longer want to keep:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, hover over the name of the selected tag and select `Delete Tag`
1. Select `Yes` to confirm deletion of the tag

![Delete tag]({{ site.url }}{{ site.baseurl }}/assets/images/tags/delete-tag.png) 

## Performing bulk actions against a tag

![Tag bulk actions]({{ site.url }}{{ site.baseurl }}/assets/images/tags/tag-bulk-actions.png)

One of the most powerful features of tags is the ability to perform bulk actions on all tagged items. 
This allows you to execute server-side actions or default operations across all records associated with a tag.

To perform a bulk action against a tag:

1. Navigate to Admin -> Tags
2. Select a tag from the list of tags that you wish to perform an action on
3. Navigate to the `Action` tab.
4. Configure the action settings:
   - **Module**: Select the module containing the document and action
   - **Document**: Choose the document type for the tagged items
   - **Action**: Select the action to perform on each tagged item
   - **Condition**: Optionally specify a condition that an item must meet for the action to be performed on them
   - **Cache Evict**: Choose cache eviction strategy (None, Bean, or All)
   - **Untag successful documents**: Check to automatically untag successfully processed items
   - **Notify when job is complete**: Check to receive an email notification when finished
5. Click `Run Tag Action Job` to start processing
6. The job will execute the specified action on each tagged item that meets the condition

Available default actions include:
- **Delete Documents** - Untags and permanently deletes the item
- **Save Documents** - Saves the item to the database
- **Upsert (Save Top Level Only) Documents** - Updates or inserts only the top-level item using upsert operation
- **Validate Documents** - Validates the item

You can also select custom document actions that have been defined for the specific document type.

The bulk action runs as a background job, allowing you to continue working while it processes the tagged items. 
Progress is tracked and logged, with detailed results available in the [job](https://skyvers.github.io/skyve-user-guide/jobs/) execution log.
