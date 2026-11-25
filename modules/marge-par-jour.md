# Margin per day — Dolibarr module

> You see what a working day brings in before you accept the quote.

- **Version:** 1.0.3
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 23.0.4, 24.0.0)
- **Price:** €19 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3487) or [dolix.fr](https://dolix.fr/en/buy/marge-par-jour/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/marge-par-jour/

## The problem it solves

You accept a job without knowing whether it brings in more or less than another one of the same duration.

## What it does

- Adds a “Planned days” field on the quote, decimals allowed.
- Shows “Margin per day” on the quote card, with the detail: total margin and number of days.
- Adds a sortable “Margin / day” column in the quote list, as well as the “Planned days” column.
- Uses Dolibarr's official calculation (FormMargin::getMarginInfosArray): same figures as the “Margins” block of the card.
- As long as the days are not filled in, the card shows “Fill in ‘Planned days’ to get the margin per day” instead of a wrong figure.
- Creates no table in your database.

## Limits (stated honestly)

- Only handles commercial proposals. Not orders, not invoices, not projects.
- The margin depends on the cost prices entered on the quote lines. Without a cost price, the margin shown is the amount sold.
- The number of days is entered by hand. The module does not work it out from the tasks, from the time consumed or from the quantities.
- No dedicated permission: anyone who can open a quote sees the margin per day.
- Does not add the margin per day to PDF documents.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
