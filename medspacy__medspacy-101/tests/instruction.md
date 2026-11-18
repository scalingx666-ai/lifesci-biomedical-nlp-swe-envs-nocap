# Issue

**Title:** Adds ConText running on non-entity iterables of spans (via custom doc extension attrs)

## Description

Would be specified via

component_cfg = {"medspacy_context": {"targets": <custom_attr_name>}}

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d96c2bf2636e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.