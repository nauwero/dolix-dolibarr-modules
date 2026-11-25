# TakePOS cash closing — Dolibarr module

> Bank deposits, withdrawals to the safe, cash in and cash expenses recorded from TakePOS, a count by notes and coins, and the discrepancy booked so that the cash account matches the drawer.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.1, 24.0.2)
- **Price:** €49 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/cloture-caisse-takepos/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/cloture-caisse-takepos/

## The problem it solves

In Dolibarr, the TakePOS cash control computes the expected amount from the terminal's invoice payments only. Bank deposits, withdrawals to the safe and expenses paid in cash during the day are not included, and the discrepancy found when counting is recorded nowhere: the Dolibarr cash account ends up no longer matching the drawer.

## What it does

- A “Cash” button in the TakePOS action bar opens a window with two tabs: Movement and Count. The terminal is the one of the open till.
- Four cash movements: bank deposit (drawer to a bank account), withdrawal to the safe, cash in (float, change, from the safe or another account) and expense paid with money from the drawer, with a required label.
- Deposit, withdrawal and cash in are internal transfers, written like those of the Bank menu (two linked entries). An expense is a miscellaneous payment debited from the cash account.
- Expected amount = actual balance of the terminal's cash account: sales, movements and any other entry included. The window shows the detail since the last count (or since the start of the day): payments received, transfers, expenses and discrepancies, other entries.
- Opening or closing count by notes and coins. The counted total and the discrepancy are shown while you type; the server recalculates them when saving.
- “Record the discrepancy in the cash account” box, ticked by default: the discrepancy becomes a “Cash discrepancy” miscellaneous payment, credited for a surplus, debited for a shortage. The cash account matches the drawer again.
- Several counts per day are possible, for example at each change of cashier. Each count keeps its cashier and the detail of notes and coins.
- After a closing count, the window reminds you of the cash amount to declare and offers “Do the Dolibarr cash control”: the core form opens with the terminal already selected. If today's cash control is already done, the window says so.
- Amounts typed are read the same way in every language: “12,50” means €12.50, even in an English interface.
- History in the Bank menu: a Counts tab and a Movements tab, filters by terminal and dates, link to each bank entry.
- Settings: safe account, deposit account, accounting accounts for shortages, surpluses and expenses (optional), list of notes and coins (euros by default).

## Limits (stated honestly)

- Only cash is counted. Cheques and bank cards are still handled by Dolibarr; no cheque deposit slips.
- The Dolibarr cash control is not modified: its own calculation still ignores movements. The module shows its own expected amount, then sends you to the Dolibarr cash control with the counted amount to declare.
- Each terminal needs a cash account in the TakePOS setup, and the window opens from the till (it reads the current terminal).
- The accounts used must be in the company currency: accounts in another currency are refused.
- No bank category is set on the module's entries.
- The history shows at most 500 lines; by default, the last 30 days.
- From version 19 to 23, expenses and discrepancies, like any miscellaneous payment, are written by Dolibarr to the unalterable log. Under 19.0.4, Dolibarr also writes PHP warnings to its log for each miscellaneous payment, whether entered by the module or by hand (a core defect).
- The module alone gives no guarantee of compliance with cash register software regulations and has not been reviewed by any body.
- Not tested: multicompany, browsers other than Chrome, and a mouse walkthrough in TakePOS on versions other than 24.0.2.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
