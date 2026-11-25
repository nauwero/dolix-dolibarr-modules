# Move tasks between projects — Dolibarr module

> A task was created in the wrong project: you move it, with its subtasks, its time spent and its documents.

- **Version:** 1.0.6
- **Compatibility:** Dolibarr 19 to 24 (tested on 19.0.4, 20.0.4, 21.0.4, 22.0.5, 23.0.4, 24.0.0)
- **Price:** €49 excl. VAT — buy: [DoliStore](https://www.dolistore.com/product.php?id=3494) or [dolix.fr](https://dolix.fr/en/buy/deplacer-des-taches/)
- **Licence:** GPL v3 or later
- **Full page, screenshots and demo:** https://dolix.fr/en/modules/deplacer-des-taches/

## The problem it solves

A task was opened under the wrong project, and Dolibarr cannot move it: you have to recreate it by hand and lose the time already logged, or clone it and keep a duplicate.

## What it does

- You choose a source project and a target project; the module lists the tasks of the source project with their hierarchy, subtasks indented under their parent.
- Preview before writing: each row shows the source project struck through followed by the target project in green, and you tick the tasks one by one, or all at once.
- Subtasks follow their parent task without you having to tick them. A task whose parent stays in the source project becomes a top-level task.
- Time spent and assignees follow the task: they are recorded on the task itself and not on the project, so nothing needs to be re-entered.
- Attached documents are moved to the target project's folder. A setting lets you leave them where they are.
- Transactional move: at the first error, no task is moved. A move history can be viewed on the module setup page.

## Limits (stated honestly)

- Only moves tasks, and only from one project to another. Does not move a project, does not merge two projects, does not rename anything and does not change the reference of the tasks.
- The move is written directly to the database: Dolibarr triggers are not run and no event is created in the agenda. Each task moved is, however, recorded in the Dolibarr logs and in the module history.
- The screen lists all the tasks of the source project, with no pagination, no search and no safety cap. On a project with several hundred tasks, the page is long.
- Moving the files is not covered by the rollback. The transaction protects the tasks and the history; a folder already moved on disk stays moved even if a later task fails. And if a folder with the same name already exists in the target project, the files stay where they are with no message to say so — the “Documents moved” counter in the final message simply does not count them.
- The files are moved on disk, but the Dolibarr document index is not updated: it keeps the old path. The task's “Documents” tab, which reads the disk, shows the files normally.
- A task's visibility follows that of its project, in Dolibarr as in the module. A task moved to a project that a user is not allowed to see disappears from their lists. You yourself can only move between projects that you can see.
- No automatic undo: the history says what was moved, it does not undo it. To go back, you make the move again in the other direction.
- The module does not check that the two projects belong to the same third party, and time already invoiced follows the task, keeping its link to the invoice. A move to another customer's project is possible: it is up to you to know what you are doing.

---

Made and tested by [Dolix](https://dolix.fr/en/). Support: support@dolix.fr (English, French, German).
