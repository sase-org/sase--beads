# Bead: sase-b7.2 — Capture policy — the authorship and version-control decision

[Bead Pages](../README.md) / [sase-b7](README.md) / sase-b7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b7.2` · **Size:** medium
**Created:** 2026-07-30 12:53:17 UTC · **Closed:** 2026-07-30 13:17:01 UTC
**Plan:** [202607/vcs\_backed\_artifact\_capture.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_backed_artifact_capture.md)

## Description

capture-policy: add a pure decision module that classifies every capture candidate as store, reference, or skip using a git probe, the repo inventory, the run window, and a per-run byte-copy cap, plus its configuration.

## Notes

[2026-07-30T13:17:01Z · sase-b7.2] Implemented and verified the pure capture decision module, Git durability probe, capture limits/config/schema, and matrix coverage. Final targeted run: 14 passed; full suite: 24,204 passed and 7 skipped. Repeated just check passed all format/lint stages; repository SASE validation remains blocked only by the pre-existing missing reciprocal prompt link for the epic design.

## Dependencies

- **Blocks:** [sase-b7.4](sase-b7.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.2/README.md) | [sase-b7.2](sase-b7.2.md) | 0 |
