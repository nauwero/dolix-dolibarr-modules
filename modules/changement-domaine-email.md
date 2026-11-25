# Email domain changer — Dolibarr module

> A customer changes its name: its addresses move to the new domain in a single operation.

- **Version:** 1.0.9
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.0, 24.0.1, 24.0.2)
- **Price:** €25 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3488) or [dolix.fr](https://dolix.fr/en/buy/changement-domaine-email/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/changement-domaine-email/

## The problem it solves

Your customer has changed its name and you have dozens of addresses to correct record by record.

## What it does

- You enter the old and the new domain, without the @ sign; the module lists all third parties and contacts whose address ends with the old domain.
- Old address → new address preview, row by row, with a checkbox to untick to exclude a record.
- The part before the @ sign is never changed.
- Transactional write: in the event of an error, the entire operation is cancelled.
- Setup option: also include members, if the Members module is enabled.
- Adjustable safety cap (1 000 records by default) and history of operations viewable in the module's setup.

## Limits (stated honestly)

- Only handles third parties, their contacts and, optionally, members. Not user accounts, nor addresses written in documents, events or mass emailing campaigns.
- Matching is exact: only addresses ending with @ancien-domaine are offered. An address at @service.ancien-domaine is not affected by a search on ancien-domaine.
- One domain at a time. For three domains, three operations.
- The update is written directly to the database: Dolibarr's triggers are not run and no event is created in the agenda. The operation is, however, recorded in Dolibarr's logs and in the module's history.
- The module does not check that the new domain exists: it only checks that what was entered has the form of a domain name.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
