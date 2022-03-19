# task

> TODO list manager.
> More information: <https://manned.org/task>.

- Add new task:

`task add {{thing_to_do}}`

- List tasks:

`task list`

- Mark task as completed:

`task {{task_id}} done`

- Modify task:

`task {{task_id}} modify {{new_thing_to_do}}`

- Delete task:

`task {{task_id}} delete`

- Get list of tasks completed today:

`task completed end:today`

- Get list of tasks completed since start of the week (sow): 

`task completed end.after:sow`

- Get list of tasks due at end of day, week or quarter: (+TODAY, +WEEK, +QUARTER)

`task +TODAY list`

- Get a list of tasks completed between a range of date:

`task end.after:2022-03-01 and end.before:2022-03-31 completed`
