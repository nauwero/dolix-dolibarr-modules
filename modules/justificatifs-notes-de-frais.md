# Receipts in expense reports — Dolibarr module

> The expense report PDF also contains its receipts, photos and PDFs, page by page: one single document to hand over.

- **Version:** 1.0.2
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21, 22, 23.0.4, 24.0.1)
- **Price:** €49 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3686) or [dolix.fr](https://dolix.fr/en/buy/justificatifs-notes-de-frais/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/justificatifs-notes-de-frais/

## The problem it solves

In Dolibarr, each expense report line can be linked to a receipt, but the report PDF only contains the table of expenses. Receipts stay apart and have to be downloaded one by one.

## What it does

- Fixed order: first the receipts attached to the lines, in line order. A file attached to several lines appears only once.
- As an option, enabled by default: the other files in the report's “Linked files” tab, except documents produced by Dolibarr.
- JPG, PNG and GIF photos: straightened according to the EXIF orientation, read directly from the file, without the PHP “exif” extension; transparency replaced with white; image centred and fitted to the page, in portrait or landscape depending on its shape.
- PDFs: added page by page, each page in its original format, portrait or landscape.
- Marker at the top of each receipt page, can be switched off: “Receipt — report reference — line, date, amount incl. tax — file name”. A file not attached to a line carries the mention “not attached to a line”.
- Check before reading: empty file, maximum size (20 MB by default, adjustable from 1 to 200 MB), format, complete PDF, non-encrypted PDF. A rejected file is listed on a last page, “Receipts not included in this document”, with the reason, and reported on screen.
- Merging is written to a separate file. Dolibarr's PDF is only replaced if it succeeds.
- On Dolibarr 19 to 23, the core PDF library can stop PHP on some damaged PDFs. The module then sets the file aside and displays an explanation page with a link back to the expense report, instead of a blank page. On the next generation, the file is listed as not included. The list of files set aside can be viewed and cleared in the setup page.
- No table, no permission, no menu. The three settings are specific to each entity in multi-company.

## Limits (stated honestly)

- Accepted formats: PDF, JPG, PNG and GIF. iPhone HEIC photos, Word documents and other formats are not converted: they are listed as not included.
- A protected (encrypted) PDF is left out, even if it opens without a password. It has to be uploaded without protection.
- Without the PHP GD extension, only JPEGs are included, without straightening.
- In the PDF, photos are re-saved as JPEG and limited to 2,400 pixels on the longest side. An image of more than 60 million pixels is left out. The uploaded file is not changed.
- The module does not check that each line has a receipt: a line with no attached file is not reported.
- Only the expense report PDF is completed. The module acts at the end of generation, through the afterPDFCreation hook; it has only been tried with the core expense report template.
- If PDF merging is disabled in Dolibarr (MAIN_DISABLE_TCPDI constant), the PDF is left as it is, with no receipt and no message.
- A file set aside is recognised by its content: it stays left out until the list has been cleared in the setup page.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
