# Issue

**Title:** CI workflow updates

## Description

1. Externalize dependency configuration to requirements/requirements.txt (for installation only) and requirements/requirements_test.txt (for extra dependencies ) to run pytest.
2. Dynamicalize the medspacy version in pyproject.toml
3. Set up dependency cache for the "manual_test_pip" and "medspacy" workflows
4. Add "prerelease" argument in the "manual_test_pip" workflow. 
5. Double-check the installed medspacy version and location.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2799ffaf0b9a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.