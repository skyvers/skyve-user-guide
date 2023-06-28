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

If you have a set of filters that you wish to reuse, you can use `Tags`. Once 
you have the filters set, click the `Tag` drop-down and click `New Tag`, enter the 
name of your tag and click `OK`. Click the drop-down again and hover over your 
newly created tag, from there you can select `Tag all in list` to tag all the items 
in your filter. At any point you can come back and select the tag you set, and filter 
by your previously set filter or the tags you set. 


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
