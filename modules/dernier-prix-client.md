# Last customer price — Dolibarr module

> You pick a product on a proposal, order or invoice: the last price and discount granted to that customer are shown, and applied in one click.

- **Version:** 1.0.3
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €59 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3755) or [dolix.fr](https://dolix.fr/en/buy/dernier-prix-client/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/dernier-prix-client/

## The problem it solves

In B2B, prices are negotiated customer by customer. When you add a product to a proposal, order or invoice, Dolibarr suggests the catalogue price, or a customer price entered by hand: it does not show the price you charged that customer last time. To find it, you have to leave the form and reopen their past documents.

## What it does

- Badge below the entry line, as soon as the product is chosen on a draft customer proposal, order or invoice: “Dernier prix : 15,90 € HT (-8,00 %) le 03/09/2026 (Facture FA2609-0030)” (last price, date, source invoice).
- “Appliquer” (Apply) button: the unit price excl. VAT and, if the option is ticked, the line's discount percentage are copied into the current line. The VAT rate is not copied: it is the one Dolibarr suggests today.
- Automatic mode, optional: the last price is copied as soon as the product is chosen, without a click. Dolibarr still enforces the product's minimum price.
- The last price is the one on the most recent line for this customer and product, by document date. The document being entered is not taken into account.
- Sources of your choice: invoices, orders, proposals. By default only validated documents count; credit notes and down payment invoices never count.
- Maximum age adjustable in months; 0, the default, means no limit.
- “Historique des prix” (Price history) tab on the third-party card: the last 100 lines of products or services sold to this customer, with date, document (link), product, unit price excl. VAT, discount, VAT, quantity and total excl. VAT.
- “Prix par client” (Prices by customer) tab on the product card: the last 100 sales of this product, customer by customer, with the same columns.
- Dolibarr permissions applied to the badge, the tabs and automatic mode: readable document types, visible customers (sales representatives, external users).

## Limits (stated honestly)

- Sales only: no vendor proposals, orders or invoices.
- The badge appears when adding a line to a draft document, not when editing an existing line.
- Only lines linked to a product or service are taken into account: free-text lines are ignored.
- A single price: the one from the last sale, whatever the quantity. The quantity sold appears in the tabs, not in the badge.
- Only the line's percentage discount is copied, not a global discount on the document or the customer.
- Amounts in the company's currency: multi-currency is not handled.
- The history tabs show the 100 most recent lines, from validated documents only. The settings (document types, maximum age) apply only to the badge and automatic mode.
- Interface in French, English, German, Spanish and Italian.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
