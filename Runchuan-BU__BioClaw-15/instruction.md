# Issue

**Title:** Add Windows-friendly local web chat and upload flow

## Description

## Summary

This PR adds a Windows-friendly way to use BioClaw without relying on WhatsApp.

## What changed

- added a local web chat channel
- added a simple HTTP webhook entrypoint
- added file upload support for the local web chat
- stored uploaded files in the group workspace so the agent can access them directly
- improved the local chat UI with file cards, preview links, download buttons, and image previews
- added `.env` loading and a local-web example

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `006db5a1988b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.