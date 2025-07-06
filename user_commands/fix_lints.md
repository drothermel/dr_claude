Please run `lint_fix`, then apply unsafe fixes and review them to be sure they’re fine before accepting.  Next run `lint_group` to get a grouped list of lint error counts per file.

Systematically fix the errors by asigning a single task per file, even if the file only has one lint error.  Assign the task to first read the *whole* file and then systematically resolve the lint errors.  If there's anything that is done intentionally, use noqa instead of just leaving the lint error. These tasks can run in parallel. 

At the end you'll just have to clean up anything the tasks missed, then commit your changes.
