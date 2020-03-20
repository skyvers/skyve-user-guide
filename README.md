---
title: "Skyve User Guide"
permalink: /
excerpt: "End user guide for Skyve Enterprise applications"
toc: true
sidebar:
  title: "Index"
  nav: docs
---

<div style="margin: 0 auto; text-align: center">
  <img src="assets/images/skyve-logo.png" width="300" alt="Skyve logo" />
</div>

Welcome to the Sykve User Guide. Use the index on the left to navigate or search.

## Basic Skyve Concepts

### Navigation
				
Navigation within Skyve applications may be slightly different to other web applications as it is designed to feel more like a desktop application rather than a website. Navigation will be explained in three broad categories here: [menu](#menu), [action panel](#action-panel) and [zoom](#zoom).

#### Menu

The main application menu is broken into sections by Module, and then typically shows Documents which have been added to the menu. By default, clicking an item in the menu will navigate you to a list (table) of all records of that type. 

#### Action Panel

Once a record is is opened, the application loads the detail view for that document. This then provides the action panel at the top of the view for interaction with the document. The action panel has the following buttons:

* _OK_ - This performs a Save and Close action when clicked. This will save any 
changes and return you to the view you came from (e.g. the list of this document).
* _Save_ - This saves any changes to the current view when clicked. 
* _Delete_ - This will delete the current document (and any child documents) when clicked and return you to the view you came from. 
* _Cancel_ - This will undo any changes which have been made and return you to the view you came from without saving.
						
If you have "zoomed" into a list within another document, your action panel buttons will change to provide two different options based on your context.

* _Zoom Out_ - This will return you to the parent view of the record you are in. Any changes will be saved or cancelled based on the action you take at the parent level.
* _Remove_ - If you added a new record to a list on the parent document, this will delete the new record and return you to the parent view. An example of this is adding a role to a user in the admin module.

    ![Action panel buttons]({{ site.url }}{{ site.baseurl }}/assets/images/action-panel.png)

#### Zoom

Skyve applications use a zoom in / zoom out concept for navigation which allows complex
interfaces to be broken into discrete sections. Each view has its own fields and validation rules, keeping the interfaces small and light.

By selecting an item from a list, we Zoom into that record. If that record's view has  another table, we can keep zooming in to access more details. We can then Cancel or Zoom Out to return to the level above until we get back to the top.

### Switching Interfaces

Skyve applications feature two separate user interfaces, both with their own advantages depending on the use case. In the default (_normal_) mode, the interface is responsive and mobile and tablet friendly, with larger controls for touch and whitespace for legibility.

The alternate interface, _power user mode_, is great for desktop browsers where lots of data manipulation, reporting or exorting is required.

To switch interfaces, click the switch icon from the top right hand corner. In _normal_ mode, this is accessed by clicking your username, and selecting the switch mode icon from the user menu.

  ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)

In _power user_ mode, the same switch icon is available from the toolbar at the top of the application.

_Note_: the switch mode button may not always be available depending on your application and if it suppports both interfaces.

### List Grids 

#### Column Headings

Column headings control sorting, you can do simple sorting by clicking
on the column heading. Clicking once will sort the list by ascending order, 
each following click will then toggle between descending and ascending. By
clicking the dropdown of a Column heading, you can choose to `Sort Ascending`, 
`Sort Descending`, `Configure Sort`, `Auto Fit` the column or `Auto Fit all columns`.
You can also choose which columns you wish to see using the `Columns` function, and Group
by the column selected.

If you wish to no longer have the list sorted, you can return the list to 
the default configuration by clicking on the menu item on the left hand side
that you clicked to get to your current screen.

To use a more complex sort, you can use the `Configure Sort` tool previously 
mentioned. Click the drop down for any column heading and select `Configure Sort`.
You will now have the option to choose any number of ways to sort, you can 
add and remove levels of sort or rearrange them if you wish. Your configured sort 
will show a superscript number representing its priority in your sort, and the 
arrow will indicate whether the data is ascending or descending.

By clicking `Auto Fit`, the column width will automatically resize to show all 
information in that column. To resize all columns, click the `Auto Fit All Columns` 
button. To gain a little more room to view your query, you can click on the 
`Expand/Shrink Menu` button to minimise the side-menu.

#### Filter Line

The filter line has the ability to filter the list based on `like` or `contains` 
searches. Clicking the `Use Advanced Filtering` displays the `Advanced Filtering` 
section above the list. There are three styles of Advanced Filter: `Flat`, `Nested`
and `Inline`. Each perform the same use, but you may find one style easier to use 
than the others. Click the `Add` button to add new critera to filter by, then 
select the filter operator and enter the data you wish to find. 

#### Export Data

To Export Data you can click on the `Export Table Data` button, the key areas of 
the wizard are; the report format, page formatting, margins and column selector. 
Your file will be generated and will appear in your downloads. To change the 
data shown in the export file, drag and drop between the two columns. If the report
is formatted, you can change the widths on the right hand side of the column.

#### Flags
Flags are a useful tool for setting reminders or alerting others of something of 
note. To set a flag, click in the `Flag` column next to the record, then enter 
the text you wish to show and click `Flag`. The flag icon will show in the list and 
when hovered over will display the message stored. To clear the flag, click the flag
and click `Clear`. If you wish to search by contents in a flag, they can be filtered
just like any other field. 

#### Summary Line
The Summary Line  in the bottom left corner can be applied to enact a number of summary functions on the data. 
There are functions to find the `Count` of the data, the average, the minimum and 
maximum, and the sum of any field.

#### Tags
If you have a set of filters that you wish to reuse, you can use `Tags`. Once 
you have the filters set, click the `Tag` drop-down and click `New Tag`, enter the 
name of your tag and click `OK`. Click the drop-down again and hover over your 
newly created tag, from there you can select `Tag all in list` to tag all the items 
in your filter. At any point you can come back and select the tag you set, and filter 
by your previously set filter or the tags you set. 
