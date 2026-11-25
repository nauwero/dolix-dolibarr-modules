# EU VAT Mentions — Dolibarr module

> The mandatory VAT statement is printed on your invoices by itself: small business exemption, intra-Community supply, reverse charge, export.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21, 22, 23.0.4, 24.0.1)
- **Price:** €79 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3685) or [dolix.fr](https://dolix.fr/en/buy/mentions-tva-europe/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/mentions-tva-europe/

## The problem it solves

Your company is German, Austrian, Belgian or Luxembourgish: Dolibarr prints no VAT statement, and you type it by hand, invoice after invoice.

## What it does

- Six situations: small business VAT exemption, intra-EU supply of goods (exempt), services to an EU business (reverse charge), export of goods outside the EU, services to a customer outside the EU, domestic reverse charge (construction…).
- Automatic detection: company not liable for VAT, exemption statement. Otherwise, only lines at 0% count. Customer in another EU country with a VAT number: intra-Community supply for goods, reverse charge for services. Customer outside the EU: export, or services outside the EU.
- Mixed invoice, goods and services at 0%: both statements are printed.
- The statement is the one of your company's country, in the language of the invoice. Example for a German company supplying an Austrian customer: “Steuerfreie innergemeinschaftliche Lieferung (§ 4 Nr. 1 Buchst. b, § 6a UStG).”
- On the invoice card, the “Printed VAT statement” line shows the statement in advance, or explains why there is none. Warning if the EU customer has no VAT number, or if their country is not set.
- “VAT statement” attribute on each invoice: left empty, the module chooses by itself; otherwise you force a situation, or “No statement”. It can still be changed on a validated invoice, to regenerate its PDF.
- Two placements to choose from: the notes area of the PDF (core templates sponge, crabe and octopus), or the __DOLIXTVA_MENTION__ variable, to be placed in the invoice footer free text or in an ODT template.
- French company under the small business exemption: an option corrects the statement Dolibarr has printed since version 21, “article L. 223-3 du CIBS”, to “TVA non applicable, art. 293 B du CGI”. A translation already customised by the administrator is left untouched.
- The setup page shows, for your company's country, the text of each situation in French, German and English. The official sources are listed in the SOURCES.md file shipped with the module.

## Limits (stated honestly)

- Only companies established in France, Belgium, Luxembourg, Germany and Austria are covered. For a company in another country, the module prints nothing and says so.
- Customer invoices and credit notes only: nothing on quotes, orders or supplier invoices.
- The module neither calculates nor changes any VAT rate or amount. You set the line to 0%; the module prints the matching statement.
- The customer's VAT number is only checked as filled in, not validated with the European Commission. EU customer without a number: no statement, and a warning on the invoice card.
- Sale at 0% to a customer in the same country: no automatic statement. Domestic reverse charge is chosen by hand.
- Not covered: distance sales to consumers (OSS one-stop shop), margin scheme, special schemes.
- Statements in French, German and English, and in Dutch for a Belgian company. For a Belgian company, on an invoice in German or English, the mandatory domestic reverse charge text stays in French, and so does the exemption text, followed by a translation in brackets.
- The notes area only works with a PDF template that prints the public note; the core templates sponge, crabe and octopus have been checked. For another template, use the variable.
- The “Printed VAT statement” line on the invoice card is displayed in the user's language, not necessarily in the PDF's.
- The statements for services to a customer outside the EU, and the export statement for a French company, are customary wordings: no official text imposes their wording. The texts follow the official sources listed with the module; they are no substitute for your accountant's advice.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
