# Issue

**Title:** Integrating span groups, adding custom attributes

## Description

The main purpose of this PR is to:
1. Facilitate better integration of span groups in medspacy (including accommodating span groups in `visualization.py`)
2. Add the ability to view custom attributes in `doc_consumer.py`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3746a941da9e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.