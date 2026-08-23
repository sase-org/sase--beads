# Bead: sase-s9.1 — Bare boolean flags and host bound keys in the shared flat grammar

[Bead Pages](../README.md) / [sase-s9](README.md) / sase-s9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bh.md) · **Assignee:** `sase-s9.1` · **Size:** medium
**Created:** 2026-08-23 08:01:35 EDT · **Closed:** 2026-08-23 08:52:17 EDT
**Plan:** [202608/procs\_filter.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_filter.md)

## Description

grammar: teach the shared profile-driven flat query grammar two closed, digest-stable extensions -- a bare `key` shorthand for boolean fields and a host registry of directional date/duration bound keys -- across the flat parser, canonicalizer, value normalizer, evaluator, and highlighter.

## Notes

[2026-08-23T12:52:17Z · sase-s9.1] Implemented bare boolean flag parsing/canonicalization/evaluation/highlighting plus host date/duration bound-key normalization/evaluation; added regression coverage for quoted boolean-key free text, non-repeatable/negation guards, Stitches sidecar shorthand, date/duration directions, and highlighting. Verified with .venv/bin/pytest tests/test_query_profile_reference.py tests/test_profile_highlighting.py tests/test_query_profile.py -q; targeted launch/LSP regressions; and just check (full-suite escalation) passing.

## Dependencies

- **Blocks:** [sase-s9.2](sase-s9.2.md) ◐ · ⧖ 2026-08-23
- **Blocks:** [sase-s9.6](sase-s9.6.md) ◐ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.1/README.md) | [sase-s9.1](sase-s9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dcbf570`](https://github.com/sase-org/sase/commit/dcbf570d53a3b8e705955b9729df84672f1abb7c) | feat(query): add flat boolean flags and bounds | [sase-s9.1](sase-s9.1.md) | 2026-08-23 08:55:48 EDT |
