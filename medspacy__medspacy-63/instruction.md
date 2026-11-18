# Issue

**Title:** Adding a bunch of section patterns

## Description

A couple of notes:

* Is this on purpose that all section patterns end with a ":" ? 

* I think it would be a good idea to detect sections of all kinds by: 
    * ends with a ":"
    * ends with a newline
    * starts with a newline
 I only briefly took a glance and it seemed to me like this is an either-or option right now.

* Should these be case-insensitive? (internally I would say - probably yes, but I might not have all the details)

Overall this seems like it would really benefit from working similarly to the CoNText component - with stopping rules as well (e.g. on double newlines or ______ lines of various kinds) 

* I am not 100% sold on the "TECHNIQUE" being just an imaging section header

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b6265a8baaa3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.