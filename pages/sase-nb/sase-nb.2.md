# Bead: sase-nb.2 — The typed registry, resolver, and snapshot

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.2` · **Size:** large
**Created:** 2026-08-16 12:24:35 EDT · **Closed:** 2026-08-16 13:49:19 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

registry: build the code-owned flag registry, the layered resolver and its immutable per-process snapshot, the strict SASE_FEATURE_FLAGS transport, and the generated feature_flags block in the config JSON Schema.

## Notes

[2026-08-16T16:49:43Z · sase-nb.2] PROPOSED FOLLOW-UP: project-scoped flags are pinned by the launching process — epic decision 7 exports the full resolved snapshot in SASE_FEATURE_FLAGS, so an agent runner inherits the launcher ACE process resolution (which excludes project-local config) instead of resolving scope:"project" flags against its own workspace; harmless while consumer ships only scope:"global" flags, but needs a decision before the first project-scoped flag

[2026-08-16T17:49:19Z · sase-nb.2] Implemented the approved feature flag registry plan. Verified with just install, focused feature flag tests, mypy, schema drift check, symvision, and just check through the known unrelated artifact-index schema-version blocker.

## Dependencies

- **Blocks:** [sase-nb.5](sase-nb.5.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.6](sase-nb.6.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.7](sase-nb.7.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.2.md) | [sase-nb.2](sase-nb.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`76c332b`](https://github.com/sase-org/sase/commit/76c332bd5d1e15a2753fd1a005242b9040b2d327) | feat: add feature flag registry foundation | [sase-nb.2](sase-nb.2.md) | 2026-08-16 13:53:02 EDT |
