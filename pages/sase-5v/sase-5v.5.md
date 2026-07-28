# Bead: sase-5v.5 — First release: v0.2.0 on PyPI

[Bead Pages](../README.md) / [sase-5v](README.md) / sase-5v.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5v.5`
**Created:** 2026-07-12 23:21:48 UTC
**Plan:** [202607/basher\_extraction.md](https://github.com/sase-org/sase--plans/blob/main/202607/basher_extraction.md)

## Description

Work directly in ~/projects/github/bbugyi200/basher/. USER CHECKPOINT: before this phase runs, confirm the existing basher PyPI project has trusted publisher owner bbugyi200, repository basher, workflow publish.yml, environment pypi; stop with a clear notification if it is missing. Then merge and independently verify the v0.2.0 release.

## Notes

Merged release-please PR #1 as ab1a14a. Publish workflow 29243509776 succeeded end-to-end (release, build/twine validation, wheel install smoke, PyPI OIDC publish). Verified GitHub v0.2.0 tag/release at ab1a14a; PyPI JSON reports 0.2.0 with wheel and sdist; isolated uv tool install resolved basher==0.2.0 and passed --version, cat/bash -n, export/provenance/BUGYI_VERSION, and sourced log::info smoke checks.

## Dependencies

- **Depends on:** [sase-5v.4](sase-5v.4.md) ✓
- **Blocks:** [sase-5v.6](sase-5v.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5v.5--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-5v.5.md#member-1) | [sase-5v.5](sase-5v.5.md) | 0 |
