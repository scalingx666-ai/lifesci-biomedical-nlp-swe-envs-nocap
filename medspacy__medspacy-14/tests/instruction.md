# Issue

**Title:** Subsections

## Description

If we accept the subsection change to the sectionizer, then we need to merge this into medspacy as well. It fixes an issue where the visualizer no longer works for section headers because the sections are now a 4-tuple instead of a 3-tuple. It currently does not add functionality for visualizing subsection structure in a document, this is something that requires more work/brainstorming.

I also went over the code with black and flake8 for style purposes and made a handful of minor changes, mostly to line length.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f59bbace422d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.