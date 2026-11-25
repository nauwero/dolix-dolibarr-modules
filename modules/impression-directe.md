# Direct printing — Dolibarr module

> Print invoices, proposals, orders, shipments and TakePOS receipts on the shop printer, without a print dialog, even with a Dolibarr hosted online.

- **Version:** 1.0.0
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2, 24.0.3)
- **Price:** €79 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/impression-directe/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/impression-directe/

## The problem it solves

With a Dolibarr hosted online, the printer is in the shop and the server somewhere else: the "Receipt printers" method cannot see it, Google Cloud Print closed in 2020, and every invoice or receipt needs a print dialog.

## What it does

- "Print" button on invoices, proposals, orders and shipments: the PDF goes straight to the chosen printer.
- Automatic printing on validation, to be chosen for each type of document. Nothing is printed when the PDF is simply regenerated, and a missing printer never blocks the validation.
- In TakePOS: a "Direct receipt" button for the receipt of the current sale, a "Drawer" button to open the cash drawer, an "open the drawer with each receipt" option.
- Works with a Dolibarr hosted online: printing goes through PrintNode, whose software is installed on the computer connected to the printer (Windows, macOS, Linux, Raspberry Pi).
- PrintNode key checked before saving, then encrypted; list of the printers and of their status in the settings.

## Limits (stated honestly)

- A PrintNode account and its software on the computer connected to the printer are required.
- Receipts and drawer not yet tested on a real thermal printer.
- Interface in French and English.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
