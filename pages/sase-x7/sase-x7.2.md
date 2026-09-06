# Bead: sase-x7.2 — Build and rehearse the temporary migration tooling

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.2` · **Size:** large
**Created:** 2026-09-05 18:55:28 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

migration-kit: Plan and implement a bounded offline migration kit with dry-run manifests, conflict detection, semantic verification, crash recovery, and restore rehearsals. Keep shared conversion logic in Rust core and keep the kit out of normal runtime startup.

## Notes

[2026-09-05T23:30:40Z · sase-x7.2] Planning handoff: authored a child EPIC plan (sase_plan_migration_kit.md), not a tale. Rationale recorded here so the land agent can audit the tier choice: (1) the kit needs a new sase_core migration module plus sase_core_rs bindings, and the host cannot call them until a core release is published, pyproject sase-core-rs floor (>=0.32.19,<0.33.0) is raised, and sase-core-revision.txt is ratcheted -- CI job release-core-floor-smoke runs tools/check_sase_core_rs_bindings against the declared floor, so this is a real second landing the parent epic forbids collapsing; (2) an apply path must not exist before a proven backup path, making backup-before-driver a safety ordering, not scheduling; (3) the macOS leg needs an isolated clone plus a from-source Rust build over best-effort SSH to a laptop that is offline unless open. Four serial medium phases: kit-contract, kit-backup, kit-driver, kit-rehearsal. Scope was TIGHTENED against the census, not widened: only four shipped operations (import-purge, procs-residue, state-residue, lock-residue). The model-alias and memory-note-type conversions were dropped from kit scope because the census report shows canonical-producers needs one chezmoi edit and one memory-workflow edit; Tier E format conversions stay with shared-format-bridge, which registers into the kit catalog. No feature flag: the kit is additive with no automatic route, and enforce-and-verify (sase-x7.14) already owns its deletion.

## Dependencies

- **Depends on:** [sase-x7.1](sase-x7.1.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.3](sase-x7.3.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.4](sase-x7.4.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.5](sase-x7.5.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.6](sase-x7.6.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.md) | [sase-x7.2](sase-x7.2.md) | 0 |
