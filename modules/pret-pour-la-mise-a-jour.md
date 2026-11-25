# Upgrade readiness check — Dolibarr module

> Before upgrading Dolibarr, you know how far you can go, what will stop working and what to do first. The module changes nothing.

- **Version:** 1.1.3
- **Compatibility:** Dolibarr 16 to 24 (tested on 16.0.5, 17.0.4, 18.0.9, 18.0.10, 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.0, 24.0.1, 24.0.2, 24.0.3)
- **Price:** Free — buy: [Download](https://www.dolistore.com/product.php?id=3650)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/pret-pour-la-mise-a-jour/

## The problem it solves

You keep putting off the Dolibarr upgrade because you do not know what will break: an external module, the PHP version, a customisation.

## What it does

- You choose the target version, from the next major version up to 24.0, and the PHP version planned after the upgrade. The check changes nothing: not the database, not the files, not the modules.
- The code of every external module is read file by file, without being run, and compared with every version on the path: removed functions, classes, methods, files, columns, hooks and events; overridden methods that became incompatible; functions and syntax refused by the planned PHP. Each finding gives the file, the line, the version from which it stops working and, when known, the replacement.
- New in 1.1.0: the module also reads your settings and data, and reports what the official migration does not carry over, such as contact titles erased on 24.0.0 to 24.0.2 or negative stock transfers forbidden by the 22 migration. Each case is verified on a real migration from 18 to 24.0.3, or in the code of the official releases.
- For each module, a coverage rate: the share of calls actually verified. Encrypted code (ionCube, SourceGuardian, Zend Guard) is reported as impossible to verify.
- The other checks: files and database at different versions, latest maintenance release of your branch, PHP at every step and when to switch, PHP extensions and memory_limit, mixed encodings and MyISAM tables, enabled core modules that disappear, modified, missing or extra core files, overridden translations, ODT templates, extrafield formulas refused from 23, recent backup, unalterable log key for 24, install lock, conf.php permissions.
- The report starts with a one-line answer, the highest version you can reach without changing anything, the path step by step and the plan in order. It also tells you whether the installed and target versions still receive security fixes, what to back up, and which step rewrites the most data.
- Each finding has a level — no problem, to check, blocking or cannot be verified — with what to do and the source of the rule.
- Report downloadable as HTML or Markdown. The “anonymise” option hides the domain, the paths, the company name and the user's login. For each module at fault, a “Report for the publisher” to send to them: files, lines, known fix, nothing about your company or your server.
- No password or key is ever displayed or exported: for conf.php, the module only says whether a key is present.
- Only one possible connection: the “Integrity of core files” box is ticked by default only when the official signature of your version is already in install/, and the comparison then needs no network. Otherwise it stays unticked: ticking it allows the signature to be downloaded from dolibarr.org. With the box unticked, the module connects to nothing.
- Interface in French, English, German, Spanish and Italian. Works on MySQL/MariaDB and PostgreSQL.

## Limits (stated honestly)

- The module does not perform the upgrade. It runs no script, repairs nothing, disables no module: repair commands are given, never run.
- The target versions are the major versions known to its data, up to 24.0. A version released after 15 November 2026 is not known: a new version of the module is needed. On a 24, no target version is offered.
- The analysis reads the code without running it. Dynamic calls and encrypted code cannot be verified: the coverage rate shows this, module by module. Only a test on a copy proves that a module works.
- Limited duration: 60 seconds in total for the code analysis, 30 seconds at most per module. Files over 2 MB and the vendor, node_modules and includes folders of modules are not analysed. What was not read is reported.
- For backups, the module looks for a recent file in documents/admin/backup. It does not check that it can be restored, and does not see a backup made elsewhere, at your host for example.
- It does not foresee bugs in the target version, how the migration scripts will handle your data, or business effects: PDF layout, VAT, external integrations.
- If Dolibarr no longer starts, the module cannot open either.
- Administrators only: no permission makes it available to another user.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
