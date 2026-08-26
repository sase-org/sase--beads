# Bead: sase-ud.4 — Rust read-side gate shell rules

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.4` · **Size:** medium
**Created:** 2026-08-26 14:02:53 EDT · **Closed:** 2026-08-26 17:24:39 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

gate-core-rs: add the flat gate fields to AgentMetaWire and DoneMarkerWire, add is_real_gate_member_record, free the runner slot for a pending gate shell in both the Rust and Python admission copies, and extend the scanner and newest-family-shell selection.

## Notes

[2026-08-26T21:24:07Z · sase-ud.4] PROPOSED FOLLOW-UP: Regenerate stale SASE memory artifacts — `just check` currently fails `sase validate` because `init memory --check` reports stale generated files: `sase/artifact_relations.json`, `sase/memory/sase_artifacts.md`, and `sase/memory/README.md` need `sase memory init`, which requires explicit owner approval.

[2026-08-26T21:24:39Z · sase-ud.4] Verified Rust and Python gate-shell read-side wire/scanner/admission changes with focused Rust tests, focused Python tests, and linked sase-core `just check` using the venv Python library path. Main repo `just check` was run and reached validation, but failed on pre-existing stale memory generated artifacts; recorded a PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-ud.3](sase-ud.3.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.6](sase-ud.6.md) ◐ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.4/README.md) | [sase-ud.4](sase-ud.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a82847`](https://github.com/sase-org/sase/commit/5a8284733de96e1aa0665bdcc7d5ac5a82a3be0c) | feat: project gate shell read metadata | [sase-ud.4](sase-ud.4.md) | 2026-08-26 17:26:04 EDT |
