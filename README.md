# Dolix — Dolibarr modules

Modules for [Dolibarr ERP/CRM](https://www.dolibarr.org/), the open-source ERP: TakePOS point of sale, logistics, sales, administration. Each module is tested by installing its zip on Dolibarr 19 to 24, and its page states what it does **and what it does not do**.

- Website, screenshots and online demo: https://dolix.fr/en/modules/
- Bought on the [DoliStore](https://www.dolistore.com/) (official Dolibarr marketplace) or directly on [dolix.fr](https://dolix.fr/en/modules/) by businesses and associations in any country. [Dolix Pass](https://dolix.fr/en/pass/): every module and its updates for €249 a year.
- Licence: GPL v3 or later. Support by email: support@dolix.fr (English, French, German).

This repository is a catalogue (descriptions only). The module code is delivered with each purchase.

## Point of sale (TakePOS)

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [TakePOS cash closing](modules/cloture-caisse-takepos.md) | Bank deposits, withdrawals to the safe, cash in and cash expenses recorded from TakePOS, a count by notes and coins, and the discrepancy booked so that the cash account matches the drawer. | Dolibarr 19 to 24 | €49 excl. VAT |
| [Multiple barcodes](modules/codes-barres-multiples.md) | Several barcodes for one product: supplier code, old code, in-store label, pack code. Scanned in TakePOS, each code adds the product to the ticket with its quantity: the code of a pack of 6 adds 6 units. | Dolibarr 19 to 24 | €49 excl. VAT |
| [Orders to collect in TakePOS](modules/commandes-a-retirer-takepos.md) | The customer comes to collect a pre-order: one click in TakePOS copies it into the ticket, and after payment the order is classified billed, even if the weight changed. | Dolibarr 19 to 24 | €49 excl. VAT |
| [Dolix Coop](modules/dolix-coop.md) | For cooperative and community grocery stores: shelf labels with the price per kilo or per litre, the customer's membership status in the TakePOS checkout, a simplified home page and menu for volunteers, a quick inventory on the phone. | Dolibarr 19 to 24 | €79 excl. VAT |
| [TakePOS Look](modules/habillage-takepos.md) | Make TakePOS look like a modern till: category tabs, large product grid, basket on the right, Charge button, trade looks or your logo colours. | Dolibarr 19 to 24 | €79 excl. VAT |
| [TakePOS wallet](modules/porte-monnaie-takepos.md) | Your customers or members pay an amount in advance, and TakePOS spends it at each visit to the till, until it runs out. | Dolibarr 19 to 24 | €79 excl. VAT |

## Logistics

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Lot sell-by and eat-by date alerts](modules/alertes-dlc.md) | You see in time the lots in stock whose sell-by or eat-by date is near or past, and you can prevent the validation of a shipment that contains a lot past its sell-by date. | Dolibarr 19 to 24 | €39 excl. VAT |
| [Grouped delivery note](modules/bl-groupe.md) | One single PDF delivery note for several shipments of the same customer, signed only once. | Dolibarr 19 to 24 | €29 excl. VAT |
| [Mondial Relay labels (Sendcloud)](modules/etiquettes-mondial-relay.md) | You choose the recipient's Point Relais® or Locker on the shipment, and the module creates the Mondial Relay label with your Sendcloud account. | Dolibarr 19 to 24 | €79 excl. VAT |

## Sales and invoicing

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Direct printing](modules/impression-directe.md) | Print invoices, proposals, orders, shipments and TakePOS receipts on the shop printer, without a print dialog, even with a Dolibarr hosted online. | Dolibarr 19 to 24 | €79 excl. VAT |
| [EU VAT Mentions](modules/mentions-tva-europe.md) | The mandatory VAT statement is printed on your invoices by itself: small business exemption, intra-Community supply, reverse charge, export. | Dolibarr 19 to 24 | €79 excl. VAT |
| [Remaining to bill](modules/reste-a-facturer.md) | You see what remains to be invoiced on each customer order, line by line, in quantity and in amount excluding tax. | Dolibarr 19 to 24 | €39 excl. VAT |
| [EU VAT OSS – buyer's country VAT rates](modules/tva-oss.md) | For your sales of goods to consumers in other EU countries: the VAT rate of the customer's country, found from the product's customs code and the European Commission's official rates, draft invoices fixed in one click, tracking of the €10,000 threshold and the quarterly OSS return. | Dolibarr 19 to 24 | €99 excl. VAT |

## Quotes and pricing

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Update prices on quotes and template invoices](modules/actualiser-les-prix.md) | Your draft quotes and template invoices pick up the catalogue prices, one by one or all at once. | Dolibarr 19 to 24 | €49 excl. VAT |
| [Last customer price](modules/dernier-prix-client.md) | You pick a product on a proposal, order or invoice: the last price and discount granted to that customer are shown, and applied in one click. | Dolibarr 19 to 24 | €59 excl. VAT |
| [Margin per day](modules/marge-par-jour.md) | You see what a working day brings in before you accept the quote. | Dolibarr 19 to 24 | €19 excl. VAT |

## Purchasing and stock

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Returnable packaging](modules/consignes.md) | You see how many returnable kegs, crates or pallets each customer holds, what those deposits are worth, and which ones have not come back in time. | Dolibarr 19 to 24 | €59 excl. VAT |
| [Consignment sales](modules/depot-vente.md) | For each consignor, you see what was sold and your commission, and the statement prepares the invoices as drafts. | Dolibarr 19 to 24 | €49 excl. VAT |
| [Landed costs](modules/frais-approche.md) | You spread freight, customs and the other costs of a shipment over the cost of products and their weighted average price. | Dolibarr 19 to 24 | €99 excl. VAT |

## Contacts and CRM

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Google Contacts two-way sync](modules/synchro-google-contacts.md) | Dolibarr contacts and Google Contacts synced both ways, for each user. Only the contacts with the “Dolibarr” label in Google are involved, and a field changed on both sides is settled by the rule you chose. | Dolibarr 19 to 24 | €59 excl. VAT |

## Projects

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Move tasks between projects](modules/deplacer-des-taches.md) | A task was created in the wrong project: you move it, with its subtasks, its time spent and its documents. | Dolibarr 19 to 24 | €49 excl. VAT |

## Expense reports

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Receipts in expense reports](modules/justificatifs-notes-de-frais.md) | The expense report PDF also contains its receipts, photos and PDFs, page by page: one single document to hand over. | Dolibarr 19 to 24 | €49 excl. VAT |

## Data quality

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Duplicate finder](modules/detection-doublons.md) | You find records entered twice and merge them: third parties, contacts and members. | Dolibarr 19 to 24 | €79 excl. VAT |

## Administration

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Stored computed fields](modules/champs-calcules.md) | An extra field computed by a formula written without PHP, with its value stored: right in the lists, sortable, filterable and printable on PDFs. | Dolibarr 19 to 24 | €49 excl. VAT |
| [Email domain changer](modules/changement-domaine-email.md) | A customer changes its name: its addresses move to the new domain in a single operation. | Dolibarr 19 to 24 | €25 excl. VAT |
| [Bulk field update](modules/modification-en-masse.md) | You change a field across a series of records without writing an SQL query. | Dolibarr 19 to 24 | €25 excl. VAT |
| [Upgrade readiness check](modules/pret-pour-la-mise-a-jour.md) | Before upgrading Dolibarr, you know how far you can go, what will stop working and what to do first. The module changes nothing. | Dolibarr 16 to 24 | Free |

## Members and everyday use

| Module | What it does | Dolibarr | Price |
|---|---|---|---|
| [Bulk membership renewal](modules/cotisations.md) | A membership fee for each member, and all subscriptions renewed at once, with invoice, payment and email. | Dolibarr 19 to 24 | €29 excl. VAT |
| [Keyboard shortcuts](modules/raccourcis-clavier.md) | Ctrl+S (Cmd+S on Mac) saves the record you are filling in, without scrolling down to the button. g then a letter opens third parties, proposals, orders, invoices or products. ? shows the help. | Dolibarr 19 to 24 | €39 excl. VAT |
| [Tags column in lists](modules/tags-listes.md) | The tags of your proposals, orders, invoices, third parties, contacts, products and projects are shown in colour in a column of the list, without opening each card. | Dolibarr 21 to 24 | €15 excl. VAT |

## Free guides

Tested guides on installing, upgrading and troubleshooting Dolibarr: https://dolix.fr/en/notes/
