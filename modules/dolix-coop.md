# Dolix Coop — Dolibarr module

> For cooperative and community grocery stores: shelf labels with the price per kilo or per litre, the customer's membership status in the TakePOS checkout, a simplified home page and menu for volunteers, a quick inventory on the phone.

- **Version:** 1.0.1
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.3)
- **Price:** €79 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/dolix-coop/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/dolix-coop/

## The problem it solves

A community grocery store runs with volunteers who change every week. In Dolibarr, the TakePOS checkout does not say whether the customer has paid their membership fee, product labels do not show the price per kilo or per litre, and a volunteer sees every menu of the software when they only need the checkout, deliveries and stock.

## What it does

- Shelf labels as PDF on A4 sheets: 24, 21, 14 or 8 labels per page. On each one: the label, the price including VAT in large print, the price per kilo or per litre, and optionally the reference, the origin and the barcode.
- The price per kilo or per litre is computed from the weight or volume on the product card. For bulk sold per kilo or per litre, enter a weight of 1 kg or a volume of 1 L: the price including VAT is then the price per kilo or per litre. Products with no weight or volume are flagged.
- A "price changed since" filter to reprint only the labels whose price has changed, search by reference, label or barcode, number of copies per product.
- In the TakePOS checkout, the payment screen shows the customer's membership status at the top: "up to date until…" in green, "expired since…" or "not a member" in red, "default customer" in grey.
- Three settings: show nothing, show the status without blocking (on activation), or refuse the sale. In refuse mode, the check is made by the server when the ticket is validated: it cannot be bypassed from the checkout. Credit notes are never blocked; sales to the default customer (non-members) stay allowed if you choose.
- A membership is up to date if the member is validated and their subscription covers today, or if their member type requires no subscription. The ticket's customer is linked to the member through the third party of the member card, as in Dolibarr.
- One button creates the "Volunteers" group with only the permissions needed in the store. Another sets the volunteer home page for its members: large tiles Checkout, Deliveries, Inventory, Supplier orders, Shelf labels and Members, according to each person's permissions.
- For volunteers, the top menu keeps only Home, Products, Members and Checkout. Administrators keep the full menu; the box can be unticked in the settings.
- Quick inventory, usable on a phone: scan or type a product, the current stock is shown, enter the counted quantity. The difference becomes an ordinary stock movement, labelled "Inventaire rapide (Dolix Coop)".
- Shipped with a command-line import script: products, members and suppliers from CSV files (Odoo headers recognised), dry run, all or nothing.

## Limits (stated honestly)

- The membership check happens in the TakePOS checkout only, not on invoices entered outside the checkout.
- A customer without a member card linked to their third party is "not a member", even if they paid a fee elsewhere.
- Labels on A4 sheets only (4 formats): no roll label printer, no electronic shelf label.
- Products tracked by lot or serial number do not go through the quick inventory: they keep Dolibarr's inventory screen.
- The simplified menu only concerns the top menu, and only non-administrator members of the "Volunteers" group.
- The import script needs command-line access to the server.
- The module does not make the checkout compliant with French anti-fraud law: that remains a matter for Dolibarr and your installation.
- Not tested: PostgreSQL, multicompany, browsers other than Chromium.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
