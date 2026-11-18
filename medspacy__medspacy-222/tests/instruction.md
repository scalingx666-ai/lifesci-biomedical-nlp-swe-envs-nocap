# Issue

**Title:** Fix json issue context_rules

## Description

1. Added `to_json()` to context_rule.py
2. Added `test_to_json()` to test_context_rule.py
3. Fixed error in `to_dict()` to return a list instead of a set

@abchapman93

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b4ba5c050ff4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.