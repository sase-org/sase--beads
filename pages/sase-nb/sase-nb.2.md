# Bead: sase-nb.2 — The typed registry, resolver, and snapshot

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.2` · **Size:** large
**Created:** 2026-08-16 12:24:35 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

registry: build the code-owned flag registry, the layered resolver and its immutable per-process snapshot, the strict SASE_FEATURE_FLAGS transport, and the generated feature_flags block in the config JSON Schema.

## Notes

[2026-08-16T16:49:43Z · sase-nb.2] PROPOSED FOLLOW-UP: project-scoped flags are pinned by the launching process — epic decision 7 exports the full resolved snapshot in SASE_FEATURE_FLAGS, so an agent runner inherits the launcher ACE process resolution (which excludes project-local config) instead of resolving scope:"project" flags against its own workspace; harmless while consumer ships only scope:"global" flags, but needs a decision before the first project-scoped flag

## Dependencies

- **Blocks:** [sase-nb.5](sase-nb.5.md) ◐ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.6](sase-nb.6.md) ◐ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.7](sase-nb.7.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.2.md) | [sase-nb.2](sase-nb.2.md) | 0 |
