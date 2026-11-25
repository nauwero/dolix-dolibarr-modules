# Duplicate finder — Dolibarr module

> You find records entered twice and merge them: third parties, contacts and members.

- **Version:** 1.1.9
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.0, 24.0.1, 24.0.2)
- **Price:** €79 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3493) or [dolix.fr](https://dolix.fr/en/buy/detection-doublons/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/detection-doublons/

## The problem it solves

The same company exists twice in your database, under two spellings, and you no longer know which one is up to date.

## What it does

- Four criteria for third parties: same email, same name, same phone, same SIRET / SIREN / VAT number. Three for contacts and members: email, first and last name, phone.
- Normalisation before matching: case, spaces, accents and punctuation ignored; legal forms removed from the name; phone numbers reduced to their last nine digits, whatever the format; first and last name in any order.
- The scan is read-only. Empty fields never form a group.
- Merging of all three scanned objects. Third parties are merged through Dolibarr's native method; contacts and members through a merge written in the module, since the Dolibarr core does not merge contacts, and has only merged members since version 23.
- Merging a third party: quotes, orders, invoices, contacts, categories and attached documents are moved to the kept record, whose empty fields are filled in, then the duplicate is deleted.
- Merging a contact or a member: roles on quotes, orders, invoices and projects, links to third parties, categories, agenda events, notifications, mass emailing targets, complementary attributes, contributions and partnerships, and any linked user account, are moved to the kept record. Its empty fields are filled in with those of the duplicate and the notes are joined end to end. All in a transaction: if a single step fails, nothing is applied.
- Two safeguards: maximum number of records scanned (20 000 by default) and maximum group size (10 by default). A value shared by too many records is reported and set aside: it is a switchboard number or a generic address, not a duplicate.
- Multi-company respected, external users confined to their own third party, viewable merge history, including the type of object merged.

## Limits (stated honestly)

- The module detects, it does not correct on its own: you choose the record to keep, merge by merge.
- Matching is exact after normalisation. Two genuinely different spellings — a typo in a name, one letter too many in an email — are not matched.
- No detection on products, projects, invoices or documents.
- A merge permanently deletes the merged record. There is no button to go back.
- Merging a contact or a member writes directly to the database: Dolibarr's triggers are not run and no event is created in the agenda. Merging a third party, on the other hand, goes through the core method.
- If the kept record already carries the same link as the duplicate — same category, same link to a third party, contribution with the same date, partnership of the same type and with the same date — the duplicate's redundant row is set aside instead of being moved.
- Files attached to the record of a merged contact or member do not follow: they stay in the deleted record's folder, on the server. For third parties, Dolibarr's native merge moves them.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
