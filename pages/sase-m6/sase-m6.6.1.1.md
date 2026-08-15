# Bead: sase-m6.6.1.1 — Define and compile the shared query profile

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.1` · **Size:** medium
**Created:** 2026-08-15 06:17:30 EDT · **Closed:** 2026-08-15 07:01:12 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

profile: define the Python-authored ArtifactQuerySchema and deterministic compiled profile passed into Rust, including fields and types, searchable fields, negation, closed host sigils, zero-argument predicates, macros, boolean mode, canonicalization, validation, and a stable digest; preserve every existing dialect's canonical form and prove profiles for Patches, Stitches, Beads, Plans, Files, and the synthetic provider.

## Notes

[2026-08-15T11:01:12Z · sase-m6.6.1.1--2] just check clean (ruff format/lint + mypy + scoped-escalated-to-full tests), 50/50 new tests passing, profiles proven against real Patch/Beads/Plans/Files/Stitches parsers and the synthetic notes provider fixture

[2026-08-15T11:01:46Z · sase-m6.6.1.1--2] just check clean (ruff format/lint + mypy + scoped-escalated-to-full tests), 50/50 new tests passing, profiles proven against real Patch/Beads/Plans/Files/Stitches parsers and the synthetic notes provider fixture

## Dependencies

- **Blocks:** [sase-m6.6.1.2](sase-m6.6.1.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.3](sase-m6.6.1.3.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.4](sase-m6.6.1.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.1.1.md) | [sase-m6.6.1.1](sase-m6.6.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f9b59c`](https://github.com/sase-org/sase/commit/2f9b59cadb2a25169a15a58c8ab7aa5c05c2cfc4) | feat(ace): define and compile the shared query profile | [sase-m6.6.1.1](sase-m6.6.1.1.md) | 2026-08-15 07:02:27 EDT |
