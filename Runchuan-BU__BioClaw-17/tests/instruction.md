# Issue

**Title:** fix: surface unstructured container stdout in logs

## Description

When a container exits successfully (exit code 0), any stdout content outside the structured OUTPUT markers (e.g. Python print() warnings from scripts) was silently dropped. This made fallback behavior inscripts invisible unless LOG_LEVEL=debug was set.

Fix: after a successful container run, extract orphan stdout and log it at warn level so script warnings surface by default.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2ace84856c73`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.