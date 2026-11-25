# Remaining to bill — Dolibarr module

> You see what remains to be invoiced on each customer order, line by line, in quantity and in amount excluding tax.

- **Version:** 1.0.4
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €39 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3702) or [dolix.fr](https://dolix.fr/en/buy/reste-a-facturer/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/reste-a-facturer/

## The problem it solves

In Dolibarr, an order only has a yes/no “Billed” status. As soon as you invoice it in several steps, nothing tells you what is left to invoice: you have to open the order and add up its invoices by hand.

## What it does

- A “Remaining to bill on orders” list with three views. By order: total excl. tax, billed excl. tax, remaining to bill excl. tax, share billed, number of invoices, status, alerts. By line: quantity ordered, billed, remaining, and amounts. By customer: number of orders, totals and number of orders to check.
- Filters: reference, third party, status, order dates, “Only with an amount remaining”, “Include orders classified billed”. Sorting on the columns and a grand total of all filtered rows, not just the current page.
- CSV export of the view displayed, with all filtered rows. Semicolon separator, UTF-8 encoding, decimals in the format of the language.
- A “Remaining to bill” tab on the sales order: summary, detail by line, invoices examined with the reason when they are not counted, and invoice lines without a matching order line.
- Partial invoices and percentage invoices deducted line by line. Credit notes attached to an invoice of the order counted as negative. Invoices created from a shipment attached to the order of the shipment (option, on by default).
- Down payments: a down payment invoice reduces the remaining amount until it is deducted; the deduction line on the final invoice offsets it. With the core option <code>FACTURE_DEPOSITS_ARE_JUST_PAYMENTS</code>, a down payment consumed as a payment is not counted twice.
- An invoice shared by several orders is spread between them in sequence (date, then reference), each order line capped at its quantity. The same rule applies to a product present on several lines of one order. No double counting.
- Six alerts: “Situation invoice”, “Shared invoice”, “Free line to check”, “Over-billed”, “Classified billed”, “Draft invoice”. Draft invoices are not counted by default (option); abandoned invoices never are.

## Limits (stated honestly)

- Amounts excluding tax only, in the company currency: no amounts including tax, and multi-currency is not taken into account.
- Situation invoices are not computed. They are flagged by an alert: the remaining amount has to be checked by hand.
- Only invoices linked to the order, or to one of its shipments, are seen. An invoice entered without a link to the order is not counted.
- Matching is done by product, and by start of label and unit price for free lines. A free line edited on the invoice, or an invoice line whose product is not on the order, does not reduce the remaining amount: it is listed separately in the tab.
- The module shows, it does not act: no button to invoice the remainder, no column added to the native order list, and the order's “Billed” status is not changed.
- Customer orders only, validated, in progress or closed. No draft or cancelled orders, and no supplier orders or invoices.
- In the by-line view, down payments not yet deducted are not spread over lines: they only appear in the by-order view.
- Beyond 5,000 orders matching the filters, only the 5,000 most recent are computed. A message then asks you to narrow the filters.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
