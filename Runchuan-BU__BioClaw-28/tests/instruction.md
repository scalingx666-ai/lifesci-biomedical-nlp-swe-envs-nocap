# Issue

**Title:** Clarify skills contribution path in README

## Description

## Summary

This PR updates the English and Chinese README headers to clarify the BioClaw skill contribution path.

Specifically, it adds a short note near the top of both README files stating that:

- new BioClaw-compatible skills should first be contributed to [Bioclaw_Skills_Hub](https://github.com/zongtingwei/Bioclaw_Skills_Hub)
- skills can be iterated and tested there before being promoted into the main BioClaw repository
- users can pull the latest BioClaw updates with `git pull`

## Files

- `README.md`
- `README.zh-CN.md`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `578acf03ac10`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.