# Bead: sase-zr.7.1.1.5.4.1 — Complete released-core adoption and atomic failure transitions

[Bead Pages](../README.md) / [sase-zr.7.1.1.5.4](sase-zr.7.1.1.5.4.md) / sase-zr.7.1.1.5.4.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-zr.7.1.1.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.7.1.1.5.land.md) · **Assignee:** `sase-zr.7.1.1.5.4.1` · **Size:** medium
**Created:** 2026-09-17 23:21:19 EDT
**Plan:** [202609/finish\_gate\_decision\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_gate_decision_landing.md)

## Description

atomic-lifecycle-completion: ratchet the published sase-core floor to the released gate-decision contract, delete the older-binding capability fallback, make receipt and attempt supersession atomic and correctly acceptance-scoped, preserve current post-response failures across plain replay, retain enough selection identity for every recovery command, and add the missing deterministic transition races.

## Notes

[2026-09-18T03:50:09Z · sase-zr.7.1.1.5.4.1] PROPOSED FOLLOW-UP: Repair published sase-core-rs gate-decision floor — phase implementation removed the Python fallback and added validation, but PyPI currently has no files for 0.34.50; 0.34.48 is incomplete/stale and probe_core_floor reports it missing decide_gate_lifecycle, preventing a coherent pyproject.toml/uv.lock ratchet.

## Dependencies

- **Blocks:** [sase-zr.7.1.1.5.4.2](sase-zr.7.1.1.5.4.2.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.1.1.5.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.1.1.5.4.1/README.md) | [sase-zr.7.1.1.5.4.1](sase-zr.7.1.1.5.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc6d51d`](https://github.com/sase-org/sase/commit/cc6d51d2db9984b76e8128f757c60ceaade3c3cc) | fix(gates): harden gate failure lifecycle transitions | [sase-zr.7.1.1.5.4.1](sase-zr.7.1.1.5.4.1.md) | 2026-09-17 23:52:08 EDT |
