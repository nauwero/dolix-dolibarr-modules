# Grouped delivery note — Dolibarr module

> One single PDF delivery note for several shipments of the same customer, signed only once.

- **Version:** 1.0.4
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €29 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3706) or [dolix.fr](https://dolix.fr/en/buy/bl-groupe/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/bl-groupe/

## The problem it solves

Dolibarr makes one delivery note per shipment. When several orders of one customer leave together, the customer gets several notes to sign. The “PDF Merge” action puts them one after the other, but they are still separate notes, with no common total.

## What it does

- Created from the shipment list: tick the shipments, choose the “Grouped delivery note (one PDF)” mass action. A screen recalls the customer and the selected shipments, with their order, customer reference, planned delivery date, number of lines and status, and offers an optional note printed on the document.
- Checks at creation: at least one shipment, none in draft (the faulty reference is shown), one customer only. Otherwise the note is not created and the reason is displayed.
- One single PDF: your company name or logo, the title “Grouped delivery note”, the reference BLGyymm-NNNN, the date, the number of shipments and the page number. A “Sender” block with your company address, a “Delivery address” block with the shipping contact of the first shipment, otherwise the customer address.
- One block per shipment, in order of planned delivery date (creation date if none): “Shipment – Order (Customer ref.) – date”, then each line with the reference, the description, the ordered quantity, the shipped quantity and the weight (product weight × shipped quantity).
- At the bottom of the document: the total quantity delivered, the total weight when lines have a weight, your note, then a “Received in good condition on: / Name and signature:” box.
- On several pages, the page header and the table header are repeated, and the shipment cut by the page break is recalled with “(continued)”.
- The PDF is written in the customer's language if it is set on their card, otherwise in the user's language. The module's own labels exist in French, English and German; for other languages they are in English.
- Grouped note card: customer, date, note, link to the PDF and table of shipments, with the “Download the PDF”, “Regenerate the PDF” (after a shipment was changed) and “Delete” buttons. The “Grouped delivery notes” list shows them all, and each shipment card recalls the grouped note(s) that contain it.

## Limits (stated honestly)

- The module neither creates nor changes any shipment: it gathers already validated shipments in one document. No single shipment for several orders, no grouped invoice.
- No configurable PDF template: the layout is fixed. The document follows Dolibarr's paper format and margins.
- The grouped note is not added to the documents of the shipment or the order, and the module sends no email: the PDF is downloaded from the grouped note card.
- A grouped note concerns one customer only. The printed delivery address is the one of the first shipment (shipping contact, otherwise customer address).
- The shipments of a grouped note and its note cannot be changed after creation: delete the grouped note and create a new one.
- The same shipment can appear in several grouped notes: the module does not prevent it, and the shipment card recalls them all.
- The “Grouped delivery notes” list shows the 500 most recent notes, with no filter or search.
- The signature box is filled in on paper: no electronic signature.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
