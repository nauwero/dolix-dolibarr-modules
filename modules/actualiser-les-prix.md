# Update prices on quotes and template invoices — Dolibarr module

> Your draft quotes and template invoices pick up the catalogue prices, one by one or all at once.

- **Version:** 1.1.5
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €49 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3498) or [dolix.fr](https://dolix.fr/en/buy/actualiser-les-prix/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/actualiser-les-prix/

## The problem it solves

Your catalogue prices have gone up, but your draft quotes and subscription invoices still go out at the old prices.

## What it does

- “Update prices” button on the card of a draft quote and of a template invoice.
- Bulk update screen for template invoices: customer, next invoice, lines affected, current total, up-to-date total and difference, with customer and product filters.
- Only the next generated invoices carry the new prices: invoices already issued are never touched.
- Line-by-line preview: current price, up-to-date price, VAT, discount, difference in euros including the discount, and a total after applying that follows the boxes you check.
- The price follows the order of the Dolibarr core: base price, price-level price, customer-specific price.
- Discounts entered on the lines are kept by default; each price is recalculated on the server when applying.

## Limits (stated honestly)

- Only handles draft quotes and template invoices.
- Handles neither orders nor issued invoices. An order is a commitment: its price is agreed.
- Does not touch free lines, those not linked to any product. They appear in the preview, marked as unchanged.
- Changes neither the quantities, nor the descriptions, nor the dates, nor the line extra fields.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
