# Bead: sase-8w.7.1 — Wire legacy SQLite phase-size relaxation

[Bead Pages](../README.md) / [sase-8w.7](sase-8w.7.md) / sase-8w.7.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8w.7.1` · **Size:** medium
**Created:** 2026-07-23 23:13:01 UTC
**Plan:** [202607/finish\_phase\_sizes.md](https://github.com/sase-org/sase--plans/blob/main/202607/finish_phase_sizes.md)

## Description

'Wire legacy SQLite phase-size relaxation' section: expose and invoke the Rust size-constraint relaxation on compatibility database open, with regression coverage for existing three-size stores.

## Notes

COMMITS:
- sase-core: 32a146d
- sase: b638df32f

## Dependencies

- **Blocks:** [sase-8w.7.3](sase-8w.7.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8w.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8w.7.1/README.md) | [sase-8w.7.1](sase-8w.7.1.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@32a146d`](https://github.com/sase-org/sase-core/commit/32a146df0ce75d4c5c57c792805789cdb492e156) | fix(bead): expose legacy size constraint migration (sase-8w.7.1) | [sase-8w.7.1](sase-8w.7.1.md) | 2026-07-23 23:35:30 |
| [`b638df3`](https://github.com/sase-org/sase/commit/b638df32f1709b59c8c3bed44f6d37abe9b227d3) | fix(bead): relax legacy phase size constraints (sase-8w.7.1) | [sase-8w.7.1](sase-8w.7.1.md) | 2026-07-23 23:35:57 |
