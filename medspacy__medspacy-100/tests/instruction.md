# Issue

**Title:** Add multilingual tests

## Description

Tests that we can load models (with parser disabled):
* spanish
* polish
* german
* multilingual

And process a string of text that contains some non-English (Polish) special characters without erroring out. 

If the user does not have the language models downloaded, it passes the test.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d96c2bf2636e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.