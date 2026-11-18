# Issue

**Title:** bumping to python 3.7 in CI

## Description

Changed github workflow to use python 3.7 to avoid pip issues. Will possibly add 3.6 back to build system with further testing later, but most users will use python 3.7+

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e9869e2acf43`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.