# Issue

**Title:** Alec context refactor

## Description

## Summary

- Adds a `match_target_sents_only` parameter to `ConText` that restricts modifier matching to only sentences containing target entities, rather than scanning the entire document
- Defaults to `False` to preserve backward compatibility
- On 100 MIMIC discharge summaries with 102 ConText rules and 8 target rules, reduces ConText processing from **3.40s to 0.06s** (~61x speedup)


## Changes

- `medspacy/context/context.py`: New `match_target_sents_only` constructor parameter; when `True`, collects unique sentences containing targets and runs the matcher only on those sentences
- tests/context/test_context_component.py: Two new tests covering both True and False settings; four existing tests updated to explicitly set match_target_sents_only=False because they either check modifier detection without setting target entities, or use a blank model without sentence boundaries

## Usage

```python
import medspacy

nlp = medspacy.load()
# Enabled by default
assert nlp.get_pipe("medspacy_context").match_target_sents_only 

# To disable, set to False
nlp.get_pipe("medspacy_context").match_target_sents_only = False
```

## Test plan

- [x] All 34 context tests pass
- [x] Full test suite: 267 passed, 1 skipped, 1 unrelated failure (numpy binary compat in notebook test)
- [x] Benchmarked on 100 MIMIC discharge summaries with realistic NER pipeline: 61x speedup
EOF

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b5783c60b918`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.