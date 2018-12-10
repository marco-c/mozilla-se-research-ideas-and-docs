## Bugs / Regressions / Tasks
There is, at the time of writing, no way to tell whether a bug on Bugzilla is an actual bug or a task (e.g. refactoring, or addition of a feature). Bugzilla is indeed used not only to track features, but also for development purposes.
Also, there is a `regression` keyword to mark regressions, but since it is not mandatory, one can not assume that its absence means that the bug is not a regression. The same applies to all other keywords (e.g. `feature`).

## Product and Component
The "Product" and "Component" are two levels of categories used to classify bugs. It's a hierarchical categorization system.

## Status and Resolution
Confusing, but there are two fields to specify the status of a bug ("status" and "resolution"). 

### Resolution
RESOLVED means that the bug has been closed (not necessarily fixed). VERIFIED means that someone (QA, or the reporter, or somebody who could reproduce) has verified that the bug no longer exists.

### Status
The "status" can be one of FIXED, INVALID, WONTFIX, INACTIVE, DUPLICATE, WORKSFORME, INCOMPLETE.
FIXED means the bug has been fixed by a developer.
INVALID means that the bug was not valid.
WONTFIX means that the developers don't intend to fix the bug.
INACTIVE means that the bug has been open for too long and will unlikely receive a fix.
DUPLICATE means that the bug has been duplicated.
WORKSFORME means that the bug was reproducible at first but is no longer reproducible.
INCOMPLETE means that the bug doesn't have enough information to be actionable and there seems to be no way to retrieve the missing information (e.g. the reporter stops responding after a request for additional information).

## Priority
The priority field on Bugzilla is not, at the time of writing, used consistently between different teams. It can't be used to answer questions about priority of bugs.
An approximation of priority might be to consider tracked bugs or blocking bugs as high priority bugs, and non-tracked ones as lower-priority ones.

## Bug Tracking
Tracking flags are set to manage a list of release critical bugs but also the bugs / features that the Release Management Team wants to keep on their radar. If the tracking flag for a given Firefox version is '+', it means that the bug is being tracked for that version; if the flag is 'blocking', it means that the bug is blocking the release of that version.

## Needinfo
The needinfo? flag can be used to request more information from one of the actors involved in Bugzilla. E.g. a developer might request more information from the reporter of a bug, or a release manager might ask something to a developer.

## Link between bugs and commits
When a patch lands for a given bug, an automated bot submits a comment to the bug to note the commits that landed. See the VCS.md file for the opposite link (commit -> bug).
