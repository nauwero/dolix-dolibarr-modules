# Consignment sales — Dolibarr module

> For each consignor, you see what was sold and your commission, and the statement prepares the invoices as drafts.

- **Version:** 1.0.5
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €49 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3705) or [dolix.fr](https://dolix.fr/en/buy/depot-vente/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/depot-vente/

## The problem it solves

In a farm shop or a makers' shop, consigned products belong to their consignors. Dolibarr sells them easily, but does not tell you what was sold for each of them: the statement, the commission and the invoices are done in a spreadsheet.

## What it does

- A “Consignor (consignment)” field on each product: the third party who owns it. Left empty, the product is a regular one and the module ignores it.
- Commission rate: the product's if set, otherwise the consignor's, otherwise the module's default rate. The commission is computed on sales excluding or including tax, as you choose.
- Sales are read from validated customer invoices, TakePOS receipts included. Credit notes and negative lines are deducted; draft invoices, replaced invoices and down payments are ignored.
- Products → Consignment sales, “Sales to settle” tab: per consignor, the number of lines, quantity sold, sales excluding and including tax, the commission and the amount due to the consignor, up to the chosen date, with a total.
- “Create the statement” takes all of the consignor's sales not yet settled up to that date, including an older invoice validated late. The statement gets a DVyymm-NNNN reference.
- “Two invoices” mode, the default: the consignor's supplier invoice, one line per product, and your commission invoice addressed to the consignor. “One invoice” mode: the supplier invoice for the sales minus the commission. Everything is created as a draft.
- Each invoice line sold is settled only once: a unique key in the database prevents it, even when two statements are created at the same time.
- Statement card: consignor, period, mode, links to the invoices with their status, detail of each sale (date, invoice, product, quantity, amounts, rate, commission) and amount due to the consignor. Print view.
- A statement can be deleted while its invoices are drafts: they are deleted with it and its sales become to settle again. If an invoice is validated, deletion is refused.
- “Consignment” tab on the consignor's card: their products with selling price, stock and rate, their sales to settle as of today and their statements.
- If your company's country is not set, the page says so: without it, Dolibarr suggests no VAT on statement invoices.

## Limits (stated honestly)

- No separate stock for the consignor's products: stock remains Dolibarr's, and goods coming in or going back use the usual stock movements.
- No automatic payment of the consignor: statement invoices are paid like any invoice.
- No margin scheme for second-hand goods.
- The module validates no invoice. Their VAT is the one Dolibarr suggests; the VAT treatment of your consignment business is to be checked with your accountant.
- The commission invoice has a single line, at the VAT rate Dolibarr suggests by default for your company.
- One consignor per product.
- PDFs and data import have not been tested. Tests were run with MariaDB and PHP 8.2; PostgreSQL has not been tested.
- On Dolibarr 21, the CSV export of products and third parties shows the key DolDvFieldCommission as a column header instead of the label: the version 21 core does not translate these headers. This is fixed in the core from version 22.
- The “Statements” tab shows the 500 most recent statements.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
