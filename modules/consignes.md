# Returnable packaging — Dolibarr module

> You see how many returnable kegs, crates or pallets each customer holds, what those deposits are worth, and which ones have not come back in time.

- **Version:** 1.0.3
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €59 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3704) or [dolix.fr](https://dolix.fr/en/buy/consignes/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/consignes/

## The problem it solves

A brewery, a drinks wholesaler or a supplier delivering on pallets charges a deposit and refunds it when the packaging comes back. Dolibarr invoices and refunds, but does not tell how much packaging each customer still holds, nor since when.

## What it does

- Two fields on the product card: “Returnable packaging”, a checkbox, and “Return delay (days)”. An empty delay uses the module's default delay.
- The register is filled from customer invoices: on validation, each invoiced line of returnable packaging counts the packaging at the customer. A negative line, in quantity or in price, on a later invoice, or a credit note line, counts it as returned.
- The register follows the invoice: movements are removed if it is set back to draft or deleted, and recreated when it is validated again. An invoice replaced by a replacement invoice is no longer counted. Down payment invoices are ignored.
- A “Returnable packaging” tab on the third-party card: for each packaging, the quantity at the customer, the deposit value, the oldest unreturned delivery, the delay and the overdue quantity; then the history of movements, with a link to each invoice.
- An overview in the Products menu: all customers holding packaging, a filter by packaging, the “Overdue packaging only” checkbox and a total line.
- First out, first returned: returns settle the oldest deliveries first. Packaging is overdue when it has been at the customer for longer than its return delay.
- Manual entry on the tab: “Opening balance” for packaging already at the customer before the module, “Correction” for a stock-count difference. A product not marked “Returnable packaging” is refused.
- The “Consider overdue as sold” button, after confirmation, takes the overdue packaging out of the customer's balance and records it in the “Considered as sold” report: date, customer, packaging, quantity, value, note, over the chosen period. No invoice is created.
- “Rebuild the register from invoices”, on the setup page, rereads the validated invoices and credit notes containing returnable packaging, for instance after ticking a product. Opening balances, corrections and packaging considered as sold are kept.
- A negative balance, more packaging returned than invoiced, is flagged in the tab with a warning: check the opening balance or the invoices.

## Limits (stated honestly)

- No tracking of the physical stock of empty packaging: the Dolibarr stock remains the one from your stock movements.
- No tracking of returnable packaging received from your suppliers: only customer invoices and credit notes are read.
- No automatic accounting entry for packaging considered as sold: the report is meant for the accountant, and no invoice is created.
- The module sets no VAT rate and does not choose the tax treatment of the deposit: the rate of the packaging product applies.
- Only lines carrying a product marked “Returnable packaging” are counted. A free line, with no product, is not.
- No separate return entry: a return goes through a negative line on an invoice or a credit note. Manual entry is reserved for the opening balance and corrections.
- One return delay per packaging, with no delay specific to a customer.
- The third-party tab shows the 200 most recent movements.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
