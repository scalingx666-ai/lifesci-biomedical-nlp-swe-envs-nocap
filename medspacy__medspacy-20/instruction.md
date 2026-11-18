# Issue

**Title:** add init.py file to fix pytest PYTHONPATH issue

## Description

This fix should change the CI workflow to correctly import modules when testing with pytest in the merged package. This should allow nested testing folders, although if we have multiple folders nested within each other, i am not sure if we will need more inits.

Solution found here https://docs.pytest.org/en/stable/pythonpath.html

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c17553176138`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.