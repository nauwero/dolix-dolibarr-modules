# TakePOS wallet — Dolibarr module

> Your customers or members pay an amount in advance, and TakePOS spends it at each visit to the till, until it runs out.

- **Version:** 1.1.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.0, 24.0.1, 24.0.2)
- **Price:** €79 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3687) or [dolix.fr](https://dolix.fr/en/buy/porte-monnaie-takepos/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/porte-monnaie-takepos/

## The problem it solves

Your members pay an amount in advance and draw on it at each visit to the till, but TakePOS offers no way to pay with a prepaid balance.

## What it does

- Top-up from the “Wallet” tab of the third-party or member card: amount, payment method, bank account, note. The balance and the history of top-ups and purchases are shown in the same place.
- A top-up is a one-line down payment invoice at 0% VAT, validated, paid, deposited in the bank if the Banks & Cash module is enabled, then converted into Dolibarr available credit.
- On the member card, the tab shows the wallet of the linked third party. A member with no linked third party has no wallet: the tab says so.
- At the till, the “Wallet (balance)” button appears on the payment screen when the customer has a balance and the sale is not settled.
- The browser sends no amount: the server applies at most the remaining amount, and at most the balance. The oldest credits are used first, and a credit larger than needed is split.
- If the balance covers the sale, it is validated and paid with no other payment. Otherwise the screen shows the remaining amount, to be paid by another method. The “Cancel” link gives the balance back.
- The balance is protected: if a draft sale is edited (line added, modified or deleted), deleted, or changes customer after the wallet was used, the applied amount is given back.
- The receipt keeps its lines and its VAT: the credit is applied as a payment, with no negative line. The customer's ordinary credit notes and down payments are never used.
- From 19 to 22, TakePOS does not display buttons added by modules: the module then prints its button itself.

## Limits (stated honestly)

- The printed receipt shows neither the part paid with the wallet nor the remaining balance.
- Top-ups are made from the third-party or member card, not from the TakePOS screen.
- With the « VAT at top-up » option, one single rate for all top-ups, and the balance only applies to a receipt still in progress.
- One wallet per third party. A member uses the one of its linked third party; there is no separate balance per member.
- No negative balance, no balance expiry, no online top-up, no top-up bonus.
- No manual correction or refund of the balance from the module.
- A cash-type bank account only accepts cash: this is a Dolibarr rule. A top-up by cheque on that account is refused, and the balance stays unchanged.
- The LNE-certified version of Dolibarr has not been tested.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
