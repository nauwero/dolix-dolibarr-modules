# Multiple barcodes — Dolibarr module

> Several barcodes for one product: supplier code, old code, in-store label, pack code. Scanned in TakePOS, each code adds the product to the ticket with its quantity: the code of a pack of 6 adds 6 units.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2, 24.0.3)
- **Price:** €49 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/codes-barres-multiples/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/codes-barres-multiples/

## The problem it solves

In Dolibarr, a product has a single barcode. In a shop, the same item often carries several: the new supplier's code, the old code still on the stock, the in-store label, the pack code. Scanned at the till, a code Dolibarr does not know means searching for the product by hand, and the pack of 6 is counted by hand.

## What it does

- “Barcodes” tab on the product card and on the service card: the main barcode is recalled, then the list of additional codes, one-line entry (code, label, quantity) and one-click deletion.
- The code is typed or scanned straight into the field. The label is free text: “Supplier B”, “Old code”, “Pack of 6 boxes”.
- Quantity added when scanned: 1 for a simple code, 6 for a pack of 6. Any quantity greater than 0 is accepted.
- TakePOS till: an additional code scanned or typed in the search adds the product to the ticket with its quantity, at the product's unit price. The till's filters still apply: product for sale, root category of the till, “products in stock only” option.
- Proposals, orders and invoices: the product selection also recognises these codes. With the classic drop-down list, from Dolibarr 19. With the option “search to select a product” (large catalogues), from Dolibarr 22: before that, Dolibarr does not pass the searched term to modules.
- No duplicates: a code already used, as an additional code or as a product's main barcode, is rejected, with the reference of the product that uses it.
- Check digit verified for 8, 12 or 13-digit codes (EAN-8, UPC-A, EAN-13): a typing error is rejected. The check can be disabled in the settings.
- Codes of up to 128 characters, without spaces: alphanumeric in-house codes are accepted.
- No Dolibarr file modified: the module uses the hooks provided by Dolibarr.

## Limits (stated honestly)

- A pack code adds several units of the same product at the unit price: no specific price for the pack or case.
- The module does not print labels for the additional codes, and these codes do not appear on PDF documents.
- The search of Dolibarr's product list does not find a product by an additional code: the codes are recognised in TakePOS and in the product selection of proposals, orders and invoices.
- Before Dolibarr 22, with the option “search to select a product”, only the main code is recognised in documents (a Dolibarr limitation). The classic drop-down list recognises the codes in all versions.
- No bulk import: codes are added one by one in the product's tab (the field accepts input from a scanner).
- Duplicates are checked when an additional code is added; the module does not watch the main barcode entered on the product card.
- Supplier documents (purchase orders and supplier invoices) are not covered by the module's description and have not been tested.
- Not tested: multi-company, PostgreSQL.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
