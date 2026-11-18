# Issue

**Title:** Add a negation rule

## Description

It's a common pattern to say:

fever: none
back pain: none, 

and those are not currently picked up by negations

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `75d144e39511`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.