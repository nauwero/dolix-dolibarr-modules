# Keyboard shortcuts — Dolibarr module

> Ctrl+S (Cmd+S on Mac) saves the record you are filling in, without scrolling down to the button. g then a letter opens third parties, proposals, orders, invoices or products. ? shows the help.

- **Version:** 1.0.1
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.2, 24.0.3)
- **Price:** €39 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/raccourcis-clavier/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/raccourcis-clavier/

## The problem it solves

In Dolibarr, every record ends with a “Save” or “Create” button at the very bottom of the page. On a third party or product card, you have to scroll down for it every time. And the Ctrl+S reflex opens the browser's “Save page” window instead of saving the record.

## What it does

- Ctrl+S (Cmd+S on Mac) saves the form holding the cursor, like a click on its “Save” or “Create” button: creating or editing a third party, creating a product, a setup page. Never a “Cancel” button.
- Required fields are still checked as with a click. Holding the key down or pressing it repeatedly sends the form only once.
- Never the wrong form: only the one holding the cursor is sent. With no cursor, the module saves the only form of the page that has a save button; if there are several, a message asks you to click in the right one first.
- Nothing to save (card displayed read-only, draft proposal, “add a line” field): the message “Nothing to save on this page.” appears and nothing is sent, so no empty line is added by mistake.
- Also works in the rich text editor, for example a product description.
- g then a letter opens a list: h home, t third parties, d proposals, c sales orders, f customer invoices, p products. The letter must be typed within a second and a half after the g, outside an input field.
- Only the lists whose module is enabled and which the user may see are offered: a sales representative limited to third parties only gets home and third parties.
- ? shows the help with every shortcut available to the user, Esc closes it.
- Two settings: Ctrl+S and navigation can be switched on or off separately, for the whole instance.
- No table, no permission to hand out, no Dolibarr file modified. Module disabled: nothing is loaded any more.

## Limits (stated honestly)

- Ctrl+S acts on Dolibarr's standard save buttons (“Save”, “Create”). A page without them, for example a page of another module, is not covered.
- On a page with several forms, you first have to click in the one to save.
- Only six lists for navigation: home, third parties, proposals, sales orders, customer invoices, products. No suppliers, projects or other lists.
- The keys cannot be changed, and the settings apply to the whole instance: no per-user choice.
- While Ctrl+S is enabled, the browser's “Save page” shortcut no longer works in Dolibarr.
- External users, linked to a third party, do not get the shortcuts.
- Interface in French, English, German and Italian only.
- Not tested: Firefox and Safari browsers (Chromium only), PostgreSQL, multi-company.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
