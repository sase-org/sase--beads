# Bead: sase-7z.1 — Core plan schema for phase size and parent\_bead

[Bead Pages](../README.md) / [sase-7z](README.md) / sase-7z.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7z.1`
**Created:** 2026-07-20 01:09:32 UTC
**Plan:** [202607/epic\_phase\_sizes\_and\_child\_epics.md](https://github.com/sase-org/sase--plans/blob/main/202607/epic_phase_sizes_and_child_epics.md)

## Description

'Core plan schema: required phase size and managed parent_bead' section: extend sase-core's plan validator with a required per-phase size enum (authoring errors, launch-mode legacy downgrade) and a managed epic-level parent_bead field, updating schema specs, diagnostics, and Rust parity tests.

## Notes

COMMIT: 9150852

## Dependencies

- **Blocks:** [sase-7z.3](sase-7z.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7z.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7z.1/README.md) | [sase-7z.1](sase-7z.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@9150852`](https://github.com/sase-org/sase-core/commit/915085264240c7b8fc17e163769ac4146e827e02) | feat(plan): validate phase sizing and parent beads (sase-7z.1) | [sase-7z.1](sase-7z.1.md) | 2026-07-20 01:23:08 |
