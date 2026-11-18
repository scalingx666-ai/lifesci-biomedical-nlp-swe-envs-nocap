# Issue

**Title:** Fix span-relative index bug in MedspacyMatcher and add tests

## Description

## Summary

Adds a `match_target_sents_only` parameter to `ConText` that restricts modifier matching to only sentences containing target entities, rather than scanning the entire document. Defaults to `True` for faster processing out of the box.

On 100 MIMIC discharge summaries with 102 ConText rules and 8 target rules, this reduces ConText processing from **2.7s to 0.05s** (~54x speedup).

## Changes

### New feature: `match_target_sents_only`
- `medspacy/context/context.py`: New `match_target_sents_only` constructor parameter. When `True`, collects unique sentences containing targets and runs the matcher only on those sentences instead of the full document. Defaults to `True`.

### Bug fix: normalize Matcher indices to doc-relative
- `medspacy/common/medspacy_matcher.py`: When `MedspacyMatcher` is called on a `Span` (e.g., a sentence), spaCy's `Matcher` returns span-relative indices while `PhraseMatcher` and `RegexMatcher` return doc-relative indices. This inconsistency caused modifiers in later sentences to be mapped to wrong document positions. Fixed by offsetting `Matcher` results by the span's start index.

### Tests
- `tests/common/test_medspacy_matcher.py`:
  - `TestSpacyMatcherSpanIndices` (3 tests) -- documents the index coordinate systems of spaCy's `Matcher`, `PhraseMatcher`, and medspaCy's `RegexMatcher` when called on a Span. These will catch upstream behavior changes in future spaCy versions.
  - `TestMedspacyMatcherSpanIndices` (6 tests) -- verifies that `MedspacyMatcher` normalizes all three rule types to doc-relative indices when called on a Span.
- `tests/context/test_context_component.py`:
  - `test_match_target_sents_only_multi_sentence` -- regression test for the index bug: verifies that modifiers in later sentences get the correct category assignment.
  - 4 existing tests updated to explicitly set `match_target_sents_only=False` because they either check modifier detection without setting target entities or use a blank model without sentence boundaries.

## Usage

```python
import medspacy

nlp = medspacy.load()

# Enabled by default -- to disable:
nlp.get_pipe("medspacy_context").match_target_sents_only = False
```

## Test plan

- [x] All 276 tests pass (1 skipped, 1 unrelated notebook failure from numpy binary compat)
- [x] Benchmarked on 100 MIMIC discharge summaries with realistic NER pipeline: ~54x speedup
- [x] Verified that entity-level assertions (is_negated, is_historical, etc.) are identical between `True` and `False` on all 100 benchmark documents

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `832fd4c30094`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.