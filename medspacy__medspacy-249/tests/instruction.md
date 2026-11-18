# Issue

**Title:** Have sectionizer create sentence boundaries around header

## Description

I think that section headers should be considered their own sentence. The text after the header I think makes more sense as its own sentence.

The context pipeline is ordered before the sectionizer. So the context algorithm doesn't respect these new sentence boundaries. It seems like this isn't a problem, but it seems worth considering.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6cd9f61907cc`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.