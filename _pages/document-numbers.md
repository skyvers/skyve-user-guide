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
## Notes on how sequences behave

- **Sequences appear on first use** — a document number record is created automatically the first time a number is allocated. If you can't find a sequence in the list, it simply hasn't been used yet.
- **Sequences are per customer** — in a multi-tenant application, each customer has their own independent sequences. Each combination of Module Name, Document Name and Sequence must be unique; attempting to add a duplicate row will produce an error.
- **Take care decreasing a number** — Skyve allocates numbers by incrementing the stored value, so winding a sequence back risks re-issuing numbers that are already in use, which will fail if the target field must be unique. Only decrease a sequence if you are certain the numbers in the gap were never used.
- **Seeding a starting number** — you can create a document number row up-front (for example to start invoices at `INV1000`) by adding a row with the exact Module Name, Document Name and Sequence values your application uses, and the desired starting value in Number. If the names do not match exactly, the application will create and use a second sequence and ignore yours.
