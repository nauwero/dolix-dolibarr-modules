# Landed costs — Dolibarr module

> You spread freight, customs and the other costs of a shipment over the cost of products and their weighted average price.

- **Version:** 1.0.7
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €99 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3701) or [dolix.fr](https://dolix.fr/en/buy/frais-approche/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/frais-approche/

## The problem it solves

The carrier and the forwarder invoice separately, and the weighted average price of your products only reflects the purchase price: stock value and margins are wrong.

## What it does

- A shipment file groups one or more purchase orders, from different suppliers if needed: a truck, a container. Draft orders are not offered.
- Five cost types: freight, customs duties and taxes, insurance, forwarder, other. Each cost has an amount excluding tax and, if you wish, the matching supplier invoice, linked to find the document.
- Four spread keys, cost by cost: by value (net line amount, discount deducted), by quantity, by weight (from the product card, converted to kg from t, g, mg, pound or ounce) or equally between lines.
- Calculation to the cent: rounding cents go to the lines whose share has the largest remainder, and the amount spread always equals the amount of the cost. A negative cost, a credit note for example, is spread the same way.
- Allocation table line by line: quantity, quantity already in stock, net purchase price, unit weight, allocated costs, costs per unit and landed unit cost. A cost that cannot be spread — missing weight, zero basis — blocks the application and the products concerned are named.
- Apply before receiving: the landed cost is written on the lines of the receptions still in draft. When the reception is validated, Dolibarr computes the weighted average price with this cost, using its own formula.
- Apply after receiving: the weighted average price is corrected product by product, on the part still in stock only (current stock / stock right after receiving). The part already gone is not revalued.
- Log of every change and all-or-nothing undo, refused if a reception has been validated, a cost changed or a weighted average price changed since. Option: update the products' cost price as well, undone with the rest. Tab on the purchase order, reminder when an order is also in another file, multi-company respected.

## Limits (stated honestly)

- No accounting entry and no invoice is changed: the module acts on reception costs, the weighted average price and, as an option, the cost price.
- No costs in a foreign currency: costs are entered in the company currency. Orders in a foreign currency, however, are taken at the order's rate, as Dolibarr does.
- No customs tariff by commodity code and no customs value calculation: duties are entered as an amount and spread like the other costs.
- No spreading by lot or serial number. Only products receive costs: service lines and free-text lines are excluded.
- Applying before receiving requires the Receptions module and a draft reception. If stock is updated when the purchase order or the supplier invoice is validated, neither application is possible.
- Quantities not yet received at the time of the application get no costs. A warning says so before you confirm.
- The weighted average price correction after receiving is written directly on the product: no stock movement is created. An applied file can no longer be edited until the application is undone.
- The same order can be in two files: the module reminds you but does not prevent it. Order selection covers the 500 most recent purchase orders, and invoice linking the 300 most recent supplier invoices.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
