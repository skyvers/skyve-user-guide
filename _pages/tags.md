---
title: "Tags"
permalink: /tags/
excerpt: "Working with Tags within Skyve applications"
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Another powerful feature of [List Grids]({{ site.url }}{{ site.baseurl }}/lists) in the desktop
mode of Skyve applications is Tags. Tags allow you to store a selection of records within a Skyve
list, or across multiple lists, and act on that selection later — including [filtering a list to just
the tagged records](#filtering-a-list-by-tag) and [performing bulk actions](#performing-bulk-actions-against-a-tag).

Tags are private to the user that created them — other users cannot see your tags, but you can [copy a tag to another user](#sharing-a-tag).

**Desktop mode required**: Tags are only available in _desktop mode_, including the `Admin -> Tags` menu item used later on this page. To switch modes, click your username in the top right hand corner and choose `Switch Mode` — see [Switching Interfaces]({{ site.url }}{{ site.baseurl }}/#switching-interfaces).
{: .notice--info}

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

The `Tag` menu also provides two further items:

- **No Tag** — deselects the current tag, hiding the tag column again without changing which records are tagged.
- **Clear all tagged** — removes _every_ record from the tag, across all lists, not just the records in the current list. Use `Untag all in list` if you only want to untag the records shown in the current list.

## Filtering a list by Tag

Selecting a tag does not filter the list — it shows the tag column so you can see and change which records are tagged. To reduce the list to only the tagged (or only the untagged) records, use the [advanced filter]({{ site.url }}{{ site.baseurl }}/lists/#advanced-filtering): add a criterion on the `Tag` field with the value `true` (tagged) or `false` (untagged).

## Deleting a Tag

To delete an existing tag you no longer want to keep:

1. Navigate to a list grid with a saved tag
1. From the `Tag` menu, hover over the name of the selected tag and select `Delete Tag`
1. Select `Yes` to confirm deletion of the tag

![Delete tag]({{ site.url }}{{ site.baseurl }}/assets/images/tags/delete-tag.png)

## Tagging records from a file

The `Load` tab of a Tag lets you tag (or untag) records in bulk by uploading a spreadsheet or CSV file of matching values — for example, a list of customer numbers extracted from another system.

1. Navigate to Admin -> Tags and zoom into the tag
1. Select the `Load` tab
1. In the `Load` section, select the `Module` and `Document` whose records you wish to tag. From here you can also use `Tag All` to tag every record of that document, or `Clear Tag` to untag everything
1. In the `Match` section, select the `Attribute` of the document to match your file values against, the `Filter Operator` (equals or like), and the `Column (first column is 1)` your values appear in within the file
1. If your file's first row is a heading row, tick `Upload File has Column Headers`
1. Click `Upload Tag Criteria` and choose your file
1. Once processed, the result counts show how many rows were uploaded, how many matched, and how many records are now tagged

## Combining Tags

The `Combinations` tab lets you combine two tags using set operations — useful for questions like "tagged in last month's campaign but not this month's".

1. Navigate to Admin -> Tags and zoom into the tag you wish to modify
1. Select the `Combinations` tab
1. Select the other tag to combine with, and the `Operator`:
   - **Union** — add the other tag's records to this tag
   - **Except** — remove the other tag's records from this tag
   - **Intersect** — keep only records that are in both tags
1. Click `Explain` to preview a description of what the combination will do
1. Click `Perform Combination` to apply it to this tag

## Sharing a Tag

Tags are private to the user that created them, but a tag can be copied to another user:

1. Navigate to Admin -> Tags and zoom into the tag
1. In the `Copy` section, select the recipient in `Copy to user`
1. Click `Make Copy`

The copy is owned by the recipient and appears in their `Tag` menu — subsequent changes to your tag are not reflected in their copy.

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
   - **Condition**: Optionally specify a condition that an item must meet for the action to be performed on it
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
Progress is tracked and logged, with detailed results available in the [job]({{ site.url }}{{ site.baseurl }}/jobs/) execution log.

Tags are also used to select the recipients of a [Communication]({{ site.url }}{{ site.baseurl }}/communication/).
