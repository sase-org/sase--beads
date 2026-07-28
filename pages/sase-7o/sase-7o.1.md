# Bead: sase-7o.1 — Replace the family positional form with family=

[Bead Pages](../README.md) / [sase-7o](README.md) / sase-7o.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7o.1`
**Created:** 2026-07-19 19:41:33 UTC
**Plan:** [202607/id\_kwargs\_tribe\_family.md](https://github.com/sase-org/sase--plans/blob/main/202607/id_kwargs_tribe_family.md)

## Description

'Phase 1: Replace the family positional form with family=' section: rework parse_name_directive_args so %id(<suffix>, family=<parent>) replaces %id(parent, suffix) with a migration error for the old form, introduce the kwarg mutual-exclusion scaffold, reword every family error string, and update completion, docs, and tests.

## Notes

COMMIT: 5cfb3b80c

## Dependencies

- **Blocks:** [sase-7o.2](sase-7o.2.md) ✓
- **Blocks:** [sase-7o.3](sase-7o.3.md) ✓
- **Blocks:** [sase-7o.4](sase-7o.4.md) ✓
- **Blocks:** [sase-7o.5](sase-7o.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7o.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7o.1/README.md) | [sase-7o.1](sase-7o.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`c8f80b2`](https://github.com/sase-org/sase/commit/c8f80b24a1869bc425810e431a5c0801c69ebb8b) | feat!: require family keyword for name directives (sase-7o.1) | [sase-7o.1](sase-7o.1.md) | 2026-07-19 20:49:07 |
