# Issue

**Title:** Fix db and WhatsApp test baseline

## Description

## Summary

Fixes two existing test-baseline issues that were failing unrelated pull requests:

- align the db is_from_me assertion with the current retrieval semantics
- preserve WhatsApp module mocks across test cases

## Changes

- update src/db.test.ts to verify the stored is_from_me flag via recent-message retrieval
- update src/channels/whatsapp.test.ts to clear mocks instead of restoring module mocks between tests

## Testing

Ran locally:

- npx vitest run src/db.test.ts
- npx vitest run src/channels/whatsapp.test.ts
- npx vitest run

All tests passed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `47f710f204f6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.