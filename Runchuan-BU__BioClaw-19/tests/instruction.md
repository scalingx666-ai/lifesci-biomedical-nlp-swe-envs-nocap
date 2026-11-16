# Issue

**Title:** fix: satisfy IPC syncGroupMetadata promise type

## Description

## Summary

Fixes a TypeScript type error in `src/index.ts` that breaks the `Test` workflow on PRs.

The `startIpcWatcher` dependency contract requires `syncGroupMetadata: (force: boolean) => Promise<void>`, but the current callback uses optional chaining:

```ts
syncGroupMetadata: (force) => whatsapp?.syncGroupMetadata(force)
```

That expression returns `Promise<void> | undefined`, which causes `npx tsc --noEmit` to fail.

This PR changes it to an explicit async no-op when WhatsApp is unavailable, preserving the existing interface contract.

## Change

```ts
syncGroupMetadata: async (force) => {
  if (!whatsapp) return;
  await whatsapp.syncGroupMetadata(force);
},
```

## Testing

Confirmed from GitHub Actions logs that the failing job was caused by:

```text
src/index.ts(603,35): error TS2322: Type 'Promise<void> | undefined' is not assignable to type 'Promise<void>'.\n```\n\nThis fix is separated from the skill PR to comply with `CONTRIBUTING.md`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `79ce6f25e6cc`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.