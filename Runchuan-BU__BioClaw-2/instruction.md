# Issue

**Title:** Add Chinese font support for plots

## Description

Install Chinese fonts in the agent image and guide matplotlib to use them to avoid missing glyphs in Chinese labels.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `289f94bef030`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.