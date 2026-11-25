# Mondial Relay labels (Sendcloud) — Dolibarr module

> You choose the recipient's Point Relais® or Locker on the shipment, and the module creates the Mondial Relay label with your Sendcloud account.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1)
- **Price:** €79 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3718) or [dolix.fr](https://dolix.fr/en/buy/etiquettes-mondial-relay/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/etiquettes-mondial-relay/

## The problem it solves

Dolibarr does not know Mondial Relay: no shipping method of that name, no Point Relais search, no label. The label is prepared outside Dolibarr, and the tracking number has to be copied into the shipment by hand.

## What it does

- On the shipment card, a “Mondial Relay Point Relais®” line: search for Points Relais and Lockers around the delivery postcode, with name, address, distance and opening hours. The chosen point is read again from Sendcloud before it is saved.
- “Create the Mondial Relay label” on a validated shipment: the module keeps the Mondial Relay option matching the point (Point Relais, Locker, or home delivery if you allow it), the cheapest offered by your Sendcloud account, and never an option without a printed label.
- The PDF label is stored in the shipment documents. The tracking number and the “Mondial Relay” shipping method are written on the shipment.
- Sendcloud status of the parcel on demand, and cancellation of the label with a confirmation request.
- In the shipment list, the “Mondial Relay labels” mass action creates one label per ready shipment and gathers the PDFs in a zip file.
- Checks before any request to Sendcloud: validated shipment, weight (the shipment's, otherwise the sum of the products, 10 g minimum), sender and recipient addresses, phone number for home delivery.
- Recipient: the “delivery” contact of the shipment or of its order, otherwise the third party. Sender: your company address in Dolibarr.
- Test mode, ticked by default: free Sendcloud test labels, without a carrier, to try the whole process. Nothing is sent to Mondial Relay and the tracking number is not written on the shipment.

## Limits (stated honestly)

- Mondial Relay only, through Sendcloud: you need a Sendcloud account (the business account opened on mondialrelay.fr is one) and its API keys.
- Real labels are charged by Sendcloud, at your account's rates, and require a payment method registered at Sendcloud. The module does not show the price before creation.
- One parcel per shipment. No returns, no multi-parcel shipments.
- The Point Relais is chosen in Dolibarr, not by the customer on your website.
- The labels of a batch are gathered in a zip, not merged into a single PDF.
- A cancelled label is refunded only if Sendcloud accepts the cancellation before the carrier's deadline.
- Tests covered shipments from France to France.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
