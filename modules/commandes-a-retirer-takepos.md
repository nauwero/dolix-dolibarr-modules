# Orders to collect in TakePOS — Dolibarr module

> The customer comes to collect a pre-order: one click in TakePOS copies it into the ticket, and after payment the order is classified billed, even if the weight changed.

- **Version:** 1.0.3
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2, 24.0.3)
- **Price:** €49 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/commandes-a-retirer-takepos/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/commandes-a-retirer-takepos/

## The problem it solves

The customer ordered in advance, by phone, on the website or at the previous market. On collection day, TakePOS cannot find the order: the products have to be keyed in again at the till, then the order classified by hand. And if the actual weight changes, the Dolibarr rule that classifies the linked order billed no longer applies, because it requires an identical amount.

## What it does

- “Orders to collect” button in the TakePOS action bar, shown only to cashiers who have the module permission.
- List of validated orders that are not billed and have no linked invoice, whose planned delivery date is past, today or empty; a button shows all dates. Search by reference, customer or customer reference. If the ticket already has a customer, the list is filtered on that customer, with an “All customers” link.
- One click on “Put into the ticket” copies the order into the current ticket: customer, products, quantities, prices, discounts and VAT. If there is no ticket yet, the draft is created the way TakePOS does it, with the same temporary reference.
- The cashier adjusts quantities (actual weight), adds or removes products, then takes payment as usual. The floor plan (restaurant mode) works too.
- On screen only: the order reference, the ordered amount and the difference in the ticket header; “Ordered” under each line, with the quantity of its own order line. The printed ticket is not changed.
- After payment: order linked to the ticket (“Related Objects”), classified billed even if the amount changed, and classified delivered if it has no shipment and the cashier is allowed to close an order (option ticked by default).
- Lots and serial numbers: since TakePOS asks for a lot for each lot-managed product, the module puts on the line the lot that expires first and holds the quantity, in the till warehouse (or in all warehouses if the till does not impose one). If a product is on several lines, each line takes into account what the previous ones already took from a lot.
- Ticket emptied or deleted: the link is removed and the order is back in the list.
- Clear refusal messages: order already linked to an invoice or a ticket, order with a validated shipment, another currency, deposit or credit note discount, title or subtotal line, ticket that already contains an order or products for another customer.

## Limits (stated honestly)

- Only one order per ticket.
- A deposit already paid is not deducted: an order with a deposit or credit note discount is refused, and is invoiced from Dolibarr.
- Orders with a validated shipment, in another currency, or with a title or subtotal line: refused, to be invoiced from Dolibarr.
- One lot per line, as in TakePOS: if no lot in the till warehouse holds the whole quantity and the till takes stock out, the order is refused.
- The list shows at most 100 orders; the search finds the others.
- TakePOS phone screen: no button, because that screen does not show module buttons.
- The module makes no stock movement: the ticket takes stock out, according to the till setting. If Dolibarr already decreases stock when sales orders are validated and the till also takes stock out, the order is refused (otherwise stock would go out twice): invoice it from Dolibarr, or set the till not to take stock out.
- The Multicompany module itself is not tested; the Dolibarr entity isolation it relies on is tested.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
