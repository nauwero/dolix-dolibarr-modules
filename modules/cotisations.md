# Bulk membership renewal — Dolibarr module

> A membership fee for each member, and all subscriptions renewed at once, with invoice, payment and email.

- **Version:** 1.0.5
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €29 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3703) or [dolix.fr](https://dolix.fr/en/buy/cotisations/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/cotisations/

## The problem it solves

In Dolibarr, the amount suggested for a subscription is the member type's amount, and subscriptions have to be renewed one member card after another.

## What it does

- A “Custom membership fee” field on the member card. Dolibarr's “New subscription” form suggests it instead of the member type's amount. Left empty, the type's amount is still suggested.
- With no custom amount, the member's last subscription amount is suggested (setting enabled by default), otherwise the amount of their type.
- “Bulk renewal” page: validated members selected by type, by tag, by “membership ended before” and, as an option, members without any subscription. Or a mass action from the member list.
- For each member: current end date, linked third party or not, suggested amount and where it comes from (the member, their last subscription, their type), editable amount, new period.
- The new subscription starts after the previous one, with the native form's rules (first day of the month or year, end on 31 December), or on a fixed date for everyone.
- Complementary action, as on the native form: direct bank entry, invoice only, or invoice with payment. Optional creation of the third party for members who have none.
- Confirmation email with the template chosen in the members setup, invoice attached if the template says so.
- Summary before running (number, total, action), then a member-by-member report with links to the subscriptions and invoices created.
- All or nothing per member, members already up to date skipped, negative amount refused, and a renewal runs only once (double click, browser back).

## Limits (stated honestly)

- No direct debit or online payment: the module records payments already received, like the native form.
- No automatic reminders for late subscriptions, no tax receipts, no family memberships, no pro rata calculation.
- Only validated members are offered. The list shows at most 2,000 of them at a time.
- One bank account, one payment method and one payment date for the whole selection.
- An invoice requires a third party linked to the member: without one, tick the creation of the third party.
- The confirmation email requires a subscription email template and a sender address in the members setup; otherwise the checkbox is disabled.
- To attach the invoice to the email, Dolibarr must generate the invoice PDF during the renewal. The case where this generation is turned off has not been tested.
- Tested with MariaDB only; PostgreSQL has not been tested.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
