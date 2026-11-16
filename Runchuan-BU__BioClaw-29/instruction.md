# Issue

**Title:** Align WhatsApp tests with current channel behavior

## Description

## Summary

This PR updates `src/channels/whatsapp.test.ts` to match the current WhatsApp channel implementation.

Specifically, it:

- adds the config mock exports now used by the runtime (`ALLOW_WHATSAPP_SELF_MESSAGES`, `ASSISTANT_NAME`, and `GROUPS_DIR`)
- adds Baileys mocks for media download and version lookup used by the current channel implementation
- updates `onChatMetadata` assertions to the current three-argument callback shape
- updates the image-message assertion to match the current content-building behavior

## Validation

Ran locally:

- `npx vitest run src/channels/whatsapp.test.ts`
- `npx vitest run`

Both passed locally.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `578acf03ac10`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.