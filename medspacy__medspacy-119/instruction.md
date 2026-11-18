# Issue

**Title:** Issue 118 fix ci

## Description

Bumping continuous integration to Python 3.8.  Currently numpy 1.22.0 is being attempted for installation, but it has dropped Python 3.7 support.

This is likely the first of at least 2 pull requests to fix our CI.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ef151ac163e4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.