# Issue

**Title:** Release: CI/CD Improvements and Scaling Features

## Description

## Overview
This PR merges the latest improvements from the `develop` branch into `master`, including enhanced CI/CD workflows, new scaling capabilities, and improved Python version support.

### What's Changed

####  CI/CD Enhancements
- Updated GitHub Actions workflows to use `windows-latest` runner (replacing deprecated `windows-2019`)
- Added support for Python 3.12 and 3.13 testing
- Enhanced manual test workflow with configurable Python version selection
- Included `develop` branch in CI pipeline for continuous testing

####  New Features: Scaling Support
- **Multiprocessing**: Added support and tests for parallel processing using Python's multiprocessing module
- **Multithreading**: Added threading support for concurrent text processing
- **Benchmarking**: New notebooks for performance testing and comparison between single-process, multiprocess, and multithread approaches

####  Bug Fixes & Compatibility
- Fixed deprecated IPython function in visualization module for compatibility with older spaCy versions
- Updated test dependencies to ensure compatibility (ipython<9.0)
- Improved spaCy version constraints for Python 3.12+ support

####  Documentation & Testing
- Updated README with latest language support information
- Enhanced test coverage for scaling features
- Configured pytest to skip benchmark notebooks

### Files Changed
- `.github/workflows/ci.yml` - Added develop branch support
- `.github/workflows/manual_test_pip.yml` - Made Python versions configurable
- `.github/workflows/python-app.yml` - Updated Windows runner
- `README.md` - Documentation updates
- `requirements/requirements_tests.txt` - Updated dependencies
- `notebooks/benchmark_scaling/` - New benchmark notebooks (2 files)
- `tests/scaling/` - New scaling tests (2 files)
- `tests/test_notebooks.py` - Updated to skip benchmarks
- `notebooks/03-Information-Extraction.ipynb` - Minor updates

### Testing
All CI tests passing with Python 3.8, 3.9, 3.10, 3.11, 3.12, and 3.13 across Ubuntu, macOS, and Windows platforms.

### Breaking Changes
None. All changes are backward compatible.

### Commits Included
This PR includes 30 commits from the develop branch with the following major changes:
- CI workflow improvements and Python version updates
- New multiprocessing and multithreading functionality
- Documentation and dependency updates
- Bug fixes for IPython and spaCy compatibility

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `34dbfc3c4a75`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.