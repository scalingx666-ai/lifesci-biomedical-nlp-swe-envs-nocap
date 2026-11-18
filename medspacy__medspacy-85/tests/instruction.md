# Issue

**Title:** CI debug

## Description

merging in the fix to our CI

new environment
`python setup.py install` creates `error: click 8.0.1 is installed but click<7.2.0,>=7.1.1 is required by {'typer'}`

pip install spacy (before setup.py) creates no conflict

the problem is a version conflict created by typer/click. Spacy has not yet updated to the latest version of typer and it is unclear why this error occurs ONLY when setuptools installs spacy, not when pip installs spacy. We will clean up our requirements in other packages and wait for a spacy incremental update. in the meantime, spacy needs to be installed before medspacy.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `98ae900b9e03`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.