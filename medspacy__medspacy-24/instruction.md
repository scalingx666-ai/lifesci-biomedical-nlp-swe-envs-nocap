# Issue

**Title:** fixing an extension typo

## Description

`Span.set_extension("section_parent", getter=lambda x: x[0]._.section_header, force=True)` 
is now
`Span.set_extension("section_parent", getter=lambda x: x[0]._.section_parent, force=True)`

This was not tested. Will add more tests in the future about this.

Also reformatting the code to be wider with black/flake8. previously set to 80, now github width of 127

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `edcd99cdb4ca`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.