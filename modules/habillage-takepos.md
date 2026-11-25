# TakePOS Look — Dolibarr module

> Make TakePOS look like a modern till: category tabs, large product grid, basket on the right, Charge button, trade looks or your logo colours.

- **Version:** 1.0.4
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.2)
- **Price:** €79 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3754) or [dolix.fr](https://dolix.fr/en/buy/habillage-takepos/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/habillage-takepos/

## The problem it solves

TakePOS works well, but its screen looks dated: small boxes, a crossed-out camera on every product without a picture, half of the screen empty.

## What it does

- Modern till layout, the default on screens 900 px wide or more: category tabs at the top, large product grid (name at the top, price at the bottom), basket on the right at full height. The active tab takes the colour of its category.
- “Charge 7.30 €” button at the bottom right, with the amount of the sale. It is disabled when the basket is empty, shows the remaining amount after a partial payment and becomes “New sale” once paid.
- Keypad on demand: it opens with the calculator button, or when you tap a basket line (quantity, price, discount). Page arrows are hidden when they are of no use.
- 4 trade looks: Grocery, Bakery, Bar-café (dark), Boutique. Or your logo colours: the dominant colour of the company logo is worked out, then darkened until it reaches a contrast ratio of 4.5:1.
- Readable products without pictures: the name replaces the crossed-out camera, and each category has its colour, also shown on its products. Products with a picture keep it.
- Bars and restaurants: the floor plan takes the colours of the look, each table is marked “Free” or “Occupied”. In the modern till, the bottom button becomes “Tables” when the basket is empty and once paid.
- Payment screen in the same colours. Large total, big keys (touch screens) and high contrast options.
- The original layout is still available: the “Classic TakePOS” setting keeps the TakePOS zones and only changes the colours.
- Only the position and the look of the zones change. Buttons and calculations are still those of TakePOS: sales, payments, receipts and stock are recorded as before. No table, no core file modified, no outside connection.

## Limits (stated honestly)

- The modern layout needs a screen 900 px wide or more. Below that, and on the TakePOS phone screen (phone.php), the layout stays the original one: only the colours change.
- The floor plan keeps the layout of your tables: only its look changes. It shows neither the amount nor the time of an occupied table, because TakePOS does not provide them.
- The payment screen and the floor plan need a recent browser (Chrome or Edge 105, Safari 15.4, Firefox 121 or later). On an older browser, they keep their original look.
- From 20 to 24 under PHP 8, TakePOS opens the floor plan on floor 0. This is a Dolibarr bug, seen with the module disabled: a room created in 19 on floor 1 looks empty after the upgrade.
- In 20, 21 and 22, TakePOS records a partial cash payment as a full payment and closes the sale (core bug, seen without the module): the button then cannot show a remaining amount.
- Some action button labels remain cut off (“Free-text pro…”): TakePOS already cuts them without the module.
- Empty basket: TakePOS shows “Empty”. This is a core text, not translated in French or German.
- The logo colour is worked out when you save the setup page: after changing the logo, save it again. Without the PHP GD extension, no colour is found and the Grocery look is used.
- With the native TakePOS colour theme (TAKEPOS_COLOR_THEME), some colours may take precedence over those of the module: not tested.
- Tests were run in Google Chrome. Safari and Firefox have not been tried.
- The LNE-certified version of Dolibarr has not been tested.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
