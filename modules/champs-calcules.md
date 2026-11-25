# Stored computed fields — Dolibarr module

> An extra field computed by a formula written without PHP, with its value stored: right in the lists, sortable, filterable and printable on PDFs.

- **Version:** 1.0.1
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.2, 24.0.3)
- **Price:** €49 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/champs-calcules/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/champs-calcules/

## The problem it solves

Dolibarr's computed fields are not stored in the database: a list cannot be sorted or filtered on them, and the value shown in a list can differ from the one on the record. In recent versions, the security rules for formulas prevent sums and reading another record, and the allowed functions are set in conf.php. As for the hidden option that stores these fields, it blocks saving the whole record as soon as a formula is in error.

## What it does

- One rule: the kind of record, the extra field that receives the result (integer, decimal, price, text, date or checkbox) and the formula. Dolibarr's native computed fields are not offered as a target.
- Supported records: products and services, third parties, contacts, members, commercial proposals, sales orders, customer invoices, and the lines of proposals, orders and invoices.
- Formulas without PHP or SQL: operations, comparisons, and / or / not, if(), rounding, min, max, texts, dates (a date plus a number adds days, days_between, today()). Function names in English or French. A list inserts a field or a function at the cursor.
- Linked records: produit.xxx for the product of a line, document.xxx for its document, tiers.xxx for the third party of a contact, a document or a line.
- Sums, counts, averages, minimums and maximums over the lines of a document, with a condition if needed, and over the subscriptions of a member. An order can thus add up an extra field computed on its lines.
- Value stored each time the record is created or modified, from the screen or the REST API; for a document, also when a line is added, modified or deleted; for a member, when a subscription is added, modified or deleted.
- Since the value is in the database, it is the same on the record and in the list, and the list can be sorted and filtered on it. It prints on PDFs like any other extra field (checked with the eratosthene order template).
- Never blocking: a formula in error leaves the field as it is, the record is saved, and the error is noted on the rule and in the log.
- Test before saving: the formula is computed on an existing record, without saving anything, with the result and the values read.
- Recompute all existing records of a rule, by batches, with the “Recompute now” button. Nightly scheduled job, disabled by default, for formulas that read another record.
- Rules of the same kind of record are computed in the order of their position: a rule can read the result of a previous rule.

## Limits (stated honestly)

- After a Dolibarr import, values are not computed: the import writes straight into the database without telling the modules. Click “Recompute now”, or rely on the nightly job if it is enabled.
- When a linked record changes (the product of a line, the third party of a contact), the value is not recomputed immediately: it follows at the next recompute, at the next change of the record or with the nightly job.
- Ten kinds of records only: no supplier orders or invoices, no shipments, no projects, no objects of other modules.
- A formula reads a fixed list of fields per kind of record (offered in the insert list), plus the extra fields. Linked records: the product, the document and the third party only. Sums only cover the lines of the document or the subscriptions of the member.
- The result goes into an extra field you create yourself (integer, decimal, price, text, date or checkbox). Dolibarr's native computed fields cannot be a target.
- The value is written directly to the extra field table, without running Dolibarr's triggers again.
- The log keeps the last 1,000 errors; the tab shows the 200 most recent.
- Interface in French, English, German and Italian. Function names in English or French.
- Not tested: PostgreSQL, multicompany, Firefox and Safari browsers, PDF templates other than eratosthene, export.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
