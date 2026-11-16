# Issue

**Title:** Add pigz tabix sra-tools salmon kallisto

## Description

Add pigz, tabix, sra-tools, salmon, and kallisto to the default container image for faster compression, indexing, SRA downloads, and RNA-seq quantification.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c7e8c24f33f7`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.