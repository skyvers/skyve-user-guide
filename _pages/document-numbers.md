---
title: "Document Numbers"
permalink: /document-numbers/
excerpt: "Viewing and updating sequence numbers within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---

Document numbers allow creators of Skyve applications to define unique sequences for fields, for example customer IDs or invoice numbers. These can be numerical or alphanumeric (an alphanumeric sequence keeps its prefix and zero padding when incrementing, e.g. `INV0001` is followed by `INV0002`).

## Viewing a document number

To check the current sequence assigned to an attribute:

1. Login with a user which has the `SecurityAdministrator` role
2. Under the 'Admin' module, select 'Document Numbers'
3. Locate or filter for the sequence using the 'Module Name', 'Document Name' and 'Sequence' columns
4. The 'Number' column contains the current last assigned sequence for the attribute

## Modifying a document number

If a gap needs to be introduced in a sequence, or go back to a previous sequence to close a gap:

1. Login with a user which has the `SecurityAdministrator` role
2. Under the 'Admin' module, select 'Document Numbers'
3. Locate or filter for the sequence using the 'Module Name', 'Document Name' and 'Sequence' columns, and click the row to zoom into the document number
4. Update the `Number` field to the new value
5. Click `OK` to save the changes
6. The next number assigned will be incremented from the saved value