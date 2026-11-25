# Lot sell-by and eat-by date alerts — Dolibarr module

> You see in time the lots in stock whose sell-by or eat-by date is near or past, and you can prevent the validation of a shipment that contains a lot past its sell-by date.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1)
- **Price:** €39 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3719) or [dolix.fr](https://dolix.fr/en/buy/alertes-dlc/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/alertes-dlc/

## The problem it solves

Dolibarr records the sell-by and eat-by date of each lot, but does not use them: no widget, no alert, and nothing prevents validating the shipment of an expired lot.

## What it does

- A home page widget: the lots in stock whose date falls within the chosen delay (30 days by default) or is past, most urgent first, with the date, its type and the number of days.
- A full list, Products menu → “Lots to watch (dates)”: filter by delay, by warehouse, or past dates only, with the quantity in stock and links to the product, the lot card and the warehouse.
- A daily email to the addresses of your choice, through a scheduled job created disabled. Nothing is sent when there is no lot to report. A “Send the email now” button on the setup page.
- When a shipment is validated, for each shipped lot whose date is past: “Block the validation”, “Warn only” or “Do nothing”, set separately for the sell-by date (block by default) and the eat-by date (warn by default).
- When blocked, the message names the product, the lot and the past date. Nothing is saved: the shipment stays a draft and the stock is not touched.
- The date labels are Dolibarr's, in each user's language: sell-by and eat-by date in English, DLC and DMD/DLUO in French.

## Limits (stated honestly)

- The check covers shipment validation only: not TakePOS, not invoices, not orders.
- The dates used are those of the lots. A lot without a date is never reported.
- A date disabled in the setup of the Product Lots module is ignored.
- Only lots in stock, with a quantity above zero, appear in the widget, the list and the email.
- A date is past from the next day on: on the day itself, the lot is neither blocked nor reported when shipping.
- The daily email needs email sending set up in Dolibarr, a sender address, and the scheduled job enabled.
- The module reports and can block; it does not change or move any lot.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
