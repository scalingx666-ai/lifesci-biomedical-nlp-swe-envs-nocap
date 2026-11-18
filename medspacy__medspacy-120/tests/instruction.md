# Issue

**Title:** Updated Adding Sections notebook to not include a dependency for anot…

## Description

…her model.  This notebook does not currently appear to do anything meaningful with entities, but rather it shows how sections are detected and accessible at a Doc level.  As such, I've changed this to use the simple English spacy model.  The notebook now runs.  Re-enabling this notebook for execution in our tests.  while I was looking at this, I found another section related notebook which was being skipped in our automated tests.  I verified that this other notebook currently runs successfully, so I have enabled this one as well for our automated testing.

NOTE:  Since there did not appear to be anything in the notebook which required certain entities, I changed the text to make the text very simple and allow the entities in the visualization to be simple DATE entities from a out of the box (non-clinical) English spacy model.

This resolves issue #116

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `923b90700667`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.