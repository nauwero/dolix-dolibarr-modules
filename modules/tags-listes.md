# Tags column in lists — Dolibarr module

> The tags of your proposals, orders, invoices, third parties, contacts, products and projects are shown in colour in a column of the list, without opening each card.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 21 to 24 (tested on 21.0.4, 22.0.5, 23.0.4, 24.0.0, 24.0.2)
- **Price:** €15 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3700) or [dolix.fr](https://dolix.fr/en/buy/tags-listes/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/tags-listes/

## The problem it solves

Dolibarr can filter a list by tag, but it does not show tags in the list: to see which tags an order or a customer has, you have to open its card.

## What it does

- A “Tags/categories” column in nine lists: commercial proposals, customer orders, customer invoices, supplier orders, supplier invoices, third parties, contacts, products and services, projects.
- Each tag is shown as a pill, in its own colour, with black or white text depending on contrast, like on the cards. A click on the pill opens the tag page.
- On the third-party list, the column brings together customer tags and supplier tags.
- Dolibarr's tag filter stays above the list: you filter with it, and the column shows the tags of each row.
- One checkbox per list in the settings page. All nine are ticked on first activation; a setting already saved is not overwritten when the module is enabled again.
- Where the list allows it, the column appears in Dolibarr's column selector: each user can hide it for themselves.
- The module follows the Dolibarr version: a tag type that does not exist in the version is ignored, and the settings page says so on the line of the list.
- The column is only shown to users who have the Dolibarr permission “Read categories”.

## Limits (stated honestly)

- Nine lists only. Dolibarr's other lists that have tags — supplier price requests, members, users, warehouses, events, tickets, interventions, bank accounts — do not get the column.
- On Dolibarr 21, no column on orders, invoices and proposals; on Dolibarr 22, none on proposals: those tags do not exist yet in these versions. Dolibarr 19 and 20 are not supported.
- The column cannot be sorted and has no filter of its own: you filter with Dolibarr's tag filter, above the list.
- Hiding per user only exists on lists where the column appears in the column selector. Elsewhere, the per-list setting applies to all users.
- The column only exists on screen, in the lists: the module adds tags neither to exports nor to PDF documents.
- The module shows tags, it does not change them: you can neither add nor remove a tag from the column.
- Without the “Read categories” permission, the user does not see the column.
- Use with the Multicompany module has not been tested.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
