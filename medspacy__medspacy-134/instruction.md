# Issue

**Title:** Add serialization to medspacy.

## Description

I had to remove some back-linking from objects to get rid of circularity for the serialization to work. 
The downside is - after serialization sections don't have the .doc property but I refactored the `__repr__` you can still access everything else.

Tackles #125

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `923b90700667`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.