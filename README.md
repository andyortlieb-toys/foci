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

`foci --global-config [--user-email=<email@address.example.com>] [--user-display=<First Last|Last, First|Nickname>]`
 * Override your user info for a particular project

## Doing tasks

foci start <task-name> [--time|-t <time_input>]

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


