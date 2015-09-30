# foci
Stay focused no matter how spread out you are.

# CLI Usage Specification

It's called "Specification" because it is not yet implemented.

All features are intended for version 1.1 unless specified otherwise.

## Multiple project management

`foci establish <project name> [-f <path-to-file>]`
 * Establish & track a new project

`foci track -f <path-to-file>`
`foci track -s <scheme>://[user[:pass]@]<server>` (v1.3)
 * Track an existing project

`foci project [-v]`
 * Display current project

`foci project <project-name>`
 * Set which project to assume as main

`foci projects [-v]`
 * List all projects

## User identifier

In open source projects, it may be convenient for project files to be shared.  You ought to know who you are.

`foci --global-config [--user-email=<email@address.example.com>] [--user-display=<First Last|Last, First|Nickname>]`
 * Set your default user info for your system

`foci --project-config <project-name> [--user-email=<email@address.example.com>] [--user-display=<First Last|Last, First|Nickname>]`
 * Override your user info for a particular project

## Doing tasks

Notes:
* All of these commands will assume your current project, unless you pass in -p/--project=<project-name>
* Any task change will allow you to specify a time with -s/--timestamp=<time_input>
* Any operation that creates a task will accept -b/--base=<other_task_name> indicating a task is based on another task
* Any operation creating or editing a task will accept -x/--external-ticket=<external-id>, for relating to external ticket systems.

`foci task [-v]`
* Display your current task

`foci tasks [-v]
* Display all tasks

`foci task <task-name>`
* Create a task or task type

`foci todo [-v]`
* Display the to-do list.

`foci todo add <task-name> [<int>]`
* Insert a new task to-do 

`foci todo move <task-name> to <int>|+[<int>]|-[<int>]`
* Move a priority to a specific position, or relatively up or down.

`foci note [-t/--task <task-name>] [<text>]`
* Attach a note to a task.  If not not in arguments, an editor will be invoked. If -t not specified, current task will be targeted.

`foci start [<task-name>]`
* Switch focus to a new or existing task. If matching task-name does not exist, or is resolved, a new one will be created.

`foci resolve [<task-name>]`
* Mark a task as resolved.  Automatically return your focus to the most recent unresolved task.

`foci break`
* Indicate that you are not working on anything.  Come back with simple `foci start`.

## Notes:

<time_input> can be any as follows:
* HH:mm
* DD HH:mm
  * DD Will refer to the most-recent in-the-past DAY, meaning if you say 20 on Feb 2, it will assume January 20
* MM-DD HH:mm
  * Like DD by itself, MM-DD will assume the most recent date in the past, up to and including today. For example if it's November 5 1974, and you say "11-06" it will assume the year 1973
* YY-MM-DD HH:mm
  * Non-Millenium compliant date will always assume most-recent past date, like other styles above.
* CCYY-MM-DD HH:mm
  * Will never make assumptions


