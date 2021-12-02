---
title: "Document Numbers"
permalink: /document-numbers/
excerpt: "Viewing and updateing sequence numbers within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Document numbers allow creators of Skyve applications to define unique sequences for fields, for example customer IDs or invoice numbers. These can be numberical or alphanumeric.

## Viewing a document number

To check the current sequence assigned to an attribute:

1. Login with a user which has the `SecurityAdministrator` role
2. Under the 'Admin' module, select 'Document Numbers'
3. Locate or filter for the document and attribute
4. The 'Number' column contains the current last assigned sequence for the attribute

## Modifying a document number

If a gap needs to be introduced in a sequence, or go back to a previous sequence to close a gap:

1. Login with a user which has the `SecurityAdministrator` role
2. Under the 'Admin' module, select 'Document Numbers'
3. Locate or filter for the document and attribute and click the row to zoom into the document number
4. Update the `number` attribute to the new value
5. Click `OK` to save the changes
6. The next number assigned will be incremented from the saved value