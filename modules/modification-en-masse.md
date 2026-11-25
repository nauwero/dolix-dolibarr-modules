# Bulk field update — Dolibarr module

> You change a field across a series of records without writing an SQL query.

- **Version:** 1.0.10
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.0, 24.0.1, 24.0.2)
- **Price:** €25 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3489) or [dolix.fr](https://dolix.fr/en/buy/modification-en-masse/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/modification-en-masse/

## The problem it solves

You need to switch a series of third parties from customer to prospect, and the interface can only do it one record at a time.

## What it does

- Third parties: customer / prospect status (all four values), supplier yes or no, status enabled or disabled.
- Contacts and addresses: status enabled or disabled.
- Two optional filters: the field's current value, and a search on the name or email.
- Before → after preview for each record, with a checkbox to untick to exclude it.
- Closed list of fields and values: the module can only write what is declared in its registry.
- Transactional write, adjustable cap (1 000 records by default) and history of operations.

## Limits (stated honestly)

- Only four fields, on two objects: third parties and contacts. No products, quotes, invoices or projects.
- Does not change complementary attributes, categories, prices or contact details.
- One field at a time. Two fields to change, two operations.
- The update is written directly to the database: Dolibarr's triggers are not run and no event is created in the agenda. The operation is recorded in Dolibarr's logs and in the module's history.
- There is no one-click undo afterwards. The history says what was done, it does not undo it.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
