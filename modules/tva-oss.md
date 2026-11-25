# EU VAT OSS – buyer's country VAT rates — Dolibarr module

> For your sales of goods to consumers in other EU countries: the VAT rate of the customer's country, found from the product's customs code and the European Commission's official rates, draft invoices fixed in one click, tracking of the €10,000 threshold and the quarterly OSS return.

- **Version:** 1.0.0
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.2, 24.0.3)
- **Price:** €99 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/tva-oss/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/tva-oss/

## The problem it solves

For goods sold to a consumer in another EU country, Dolibarr does not know which rate applies to that product in the customer's country: its own code says so (“TODO”), and it takes the country's highest rate. A book sold to a German consumer therefore goes out at 19% instead of 7%. The VAT rates dictionary shipped with Dolibarr 24 is also incomplete for the EU (checked on 19 October 2026): no rate at all for Czechia, Estonia, Finland, Latvia and Lithuania, and 20% for Slovakia, whose official standard rate is 23%. Finally, nothing in Dolibarr tracks the €10,000 threshold or prepares the quarterly OSS return.

## What it does

- Official rates of the 27 EU countries, taken from the European Commission's TEDB database: shipped with the module (it works without Internet access) and updated every week by a scheduled job, or with the “Update now” button.
- Expected rate of a line, in this order: the rate you forced for this product and this country; otherwise the longest official customs code matching the product's customs code, if it gives a single rate; otherwise the country's standard rate.
- Sales checked: your company is in the EU and registered for VAT, the customer is in another EU country and is not a business with a valid VAT number (same logic as Dolibarr). Monaco is treated as France.
- Draft customer invoice: a warning lists the lines with a wrong rate (“5.5% → 7% (customs code 4901)”), and the “Apply OSS rates” button fixes them. A setting says whether to keep the net price (default) or the gross price. Validated invoices are never changed.
- The module suggests, you decide: when the official database gives several rates for a customs code, or lists it as exempt or out of scope, the line is flagged “to check” and is not corrected.
- Shipping and packaging: tick “Include this service in the distance sale” on these services. They then follow the rate of the customer's country and count in the threshold and the return, like goods.
- “VAT OSS” tab on the product: for each of the 27 countries, the expected rate, its reason (customs code found, official category and comment) and a field to force a rate.
- €10,000 threshold: net total, for the current and previous year, of goods sold to consumers in other EU countries (validated invoices, credit notes deducted), by country. Alert if the threshold is exceeded while OSS mode is off.
- Quarterly OSS return: net amount and VAT by country and by rate, number of lines, lines whose rate differs from the expected rate, totals and CSV export. By default, the last completed quarter.
- VAT rates dictionary: country-by-country comparison with the official rates (missing rates, rates no longer in force) and one-click addition of the missing rates. No existing rate is disabled, since older invoices use it.

## Limits (stated honestly)

- Only goods are handled, plus the services you include in the distance sale (shipping, packaging). For electronic services, use the Dolibarr option SERVICE_ARE_ECOMMERCE_200238EC.
- The module suggests, you decide: reduced rates subject to conditions must still be checked, and a line with several possible rates, or listed as exempt or out of scope, is flagged, not corrected.
- The return is not filed on the tax portal: you check the amounts and enter them yourself; the return remains yours.
- Customer invoices only: quotes and orders are not checked.
- When a line is entered, the VAT rate list still offers Dolibarr's rate: the warning and the button on the draft make the correction.
- Without a customs code on the product, the country's standard rate is expected.
- The threshold only counts goods and included services. The regulatory threshold also counts telecommunications, broadcasting and electronic services sold to EU consumers: add them yourself if you sell any.
- Amounts are in your company's currency; the threshold is set in euros.
- Rates are those of the official TEDB database on the date shown in the settings. The weekly update needs the Scheduled jobs module and Internet access; otherwise, the rates shipped with the module (20 October 2026) stay in place.
- In the product tab, the category shown is that of the first official entry found (sometimes “LOAN_LIBRARIES” for a book), and the official comments are in English.
- No effect for a company outside the EU or not registered for VAT.
- Not tested: PostgreSQL, multi-company. On 20, 21 and 23, no visual check in a browser.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
