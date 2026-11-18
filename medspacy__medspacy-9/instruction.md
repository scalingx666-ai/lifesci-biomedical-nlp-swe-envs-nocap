# Issue

**Title:** Adding a custom tokenizer to medspacy

## Description

But this is not one of the default pipes.  Since one of the current default pipes conflict with this ('preprocessor') this must currently be manually enabled as seen in the notebook.

This is to address #7

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7eaa16705cf6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.