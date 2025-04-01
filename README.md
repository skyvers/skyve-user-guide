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
  <img src="assets/images/skyve-logo.png" width="300" style="margin: 10 0;" alt="Skyve logo" />
</div>

Welcome to the Skyve User Guide. Please use the index on the left to navigate, or begin a search.

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

Skyve applications feature two separate user interfaces, both with their own advantages depending on the use case. In the default (_responsive_) mode, the interface is responsive and mobile and tablet friendly, with larger controls for touch and whitespace for legibility.

The alternate interface, _power user_ mode, is great for desktop browsers where lots of data manipulation, reporting or exporting is required.

To switch interfaces, click the switch icon from the top right hand corner. In _responsive_ mode, this is accessed by clicking your username, and selecting the switch mode icon from the user menu.

  ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)

In _power user_ mode, the same switch icon is available from the toolbar at the top of the application.

_Note_: the switch mode button may not always be available depending on your application permissions and if it supports both interfaces.
