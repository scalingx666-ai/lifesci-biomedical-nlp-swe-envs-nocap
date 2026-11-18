# Issue

**Title:** 213 postprocessor does not currently run all rules

## Description

@turbosheep  Could you look over this fix I just made for Issue #213 ?  2 of these 3 tests failed before my fix, and now they pass.

Also @abchapman93  you can review as well, but I'll tag you here so that you are aware that the Postprocessor is not working correctly in 1.0.1 of medspacy.  I encountered this on a current project once I updated medspacy.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d64663e8f9fe`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.