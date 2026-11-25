# Google Contacts two-way sync — Dolibarr module

> Dolibarr contacts and Google Contacts synced both ways, for each user. Only the contacts with the “Dolibarr” label in Google are involved, and a field changed on both sides is settled by the rule you chose.

- **Version:** 1.0.0
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.2)
- **Price:** €59 excl. VAT — buy: [dolix.fr](https://dolix.fr/en/buy/synchro-google-contacts/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/synchro-google-contacts/

## The problem it solves

The company's contacts are in Dolibarr; the ones users look up on their phone or in Gmail are in Google Contacts. Sending Dolibarr contacts to Google is not enough: a number corrected on the phone, or a contact added in Google, must also come back to Dolibarr. Without a two-way sync, the two address books drift apart and someone has to copy by hand.

## What it does

- One Google account per user: each one connects it from Third parties > Google Contacts sync, through Google's consent page. Access tokens are stored encrypted.
- Only the contacts with the “Dolibarr” label in Google are synced (the name can be changed): the other Google contacts never come into Dolibarr.
- Dolibarr to Google: as chosen, all the contacts the user can see, those of the third parties they are sales representative of, or the contacts of one category.
- Google to Dolibarr, optional: a contact put under the label in Google is created in Dolibarr and attached to the third party whose name is the company given in Google, if there is exactly one.
- Conflicts settled field by field against the last sync: changed on one side only, that side wins; changed on both sides, the chosen rule decides (most recent by default, or Dolibarr always, or Google always) and the log keeps both values.
- No duplicates: before creating a contact, the module looks for the same email address on the other side and links the two records.
- Configurable deletions. By default, a contact deleted in Google is disabled in Dolibarr, and a contact deleted in Dolibarr is removed from the label in Google, where it stays.
- Synced fields: first name, last name, job title, email, work, mobile and home phones, address, zip code, town, country, birthday. The third party name is sent to Google as the company.
- Google data that Dolibarr does not know (other emails, other numbers, notes, photo) is kept.
- Every 15 minutes through the scheduled job, or with the “Sync now” button. A log per user, and a general log for the administrator.
- Number of writes per run limited (300 by default): beyond that, the rest is done at the next run.

## Limits (stated honestly)

- Only contacts (Contact/Address records) are synced, not the third parties themselves. The third party name goes to Google as the company, but does not come back: it is changed in Dolibarr.
- No calendar, no other Google data: contacts only.
- One Google account per Dolibarr user.
- You create an OAuth client yourself in the Google Cloud console (once for the instance). With Gmail accounts, Google shows an “unverified app” warning when connecting.
- A birthday without a year, possible in Google, is not copied into Dolibarr.
- Other emails, other numbers, notes and photo from Google are kept in Google, but do not come into Dolibarr.
- Writes limited per run (300 by default): a large address book is synced over several runs.
- The log is not purged by the module.
- Not tested: Google Workspace account, PostgreSQL, multi-company, Firefox and Safari browsers, address books of more than a few dozen contacts.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
