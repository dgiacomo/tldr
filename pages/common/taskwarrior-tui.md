# taskwarrior-tui

> **s** - start/stop task
> **m** - modify task
> **x** - delete task
> **d** - complete task 
> **u** - undo
> **!** - shell
> **z** - zoom : toggle detail popup
> **A** - annotate
> **/** - filter : {project:, tag:, due:} 
> **c** - switch context : work / personal
> **]** - next tab : access **project** or **calendar** tabs
> **[** - prev tab : access **project** or **calendar** tabs
> **tab** - Tab completion maintains history! useful for due dates

- modify task to set specific due date and time:

`m due:2022-03-15T15:00`

- set due date to today at 3pm:

`m due:15:00`

- search for things with partial letters:

`/project project:<project-name>`

- get a list of tasks completed today:

`/status:completed end:today`

- get a list of tasks completed since the start of the week:

`/status:completed end.after:sow`

- Get list of tasks due at end of day, week or quarter (+TODAY, +WEEK, +QUARTER):

`/+TODAY`
