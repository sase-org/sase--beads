# Bead: sase-jx.2 — Record how long a chop actually blocked its tick

[Bead Pages](../README.md) / [sase-jx](README.md) / sase-jx.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ye](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ye/README.md) · **Assignee:** `sase-jx.2` · **Size:** small
**Created:** 2026-08-12 09:06:07 EDT · **Closed:** 2026-08-12 10:10:20 EDT
**Plan:** [202608/axe\_chop\_overrun\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/axe_chop_overrun_indicator.md)

## Description

blocking_duration: persist `script_duration_ms` on chop run entries so an agent-launching run keeps its script wall-clock after lifecycle finalization overwrites `duration_ms`, and make the run-entry reader tolerate unknown keys.

## Notes

[2026-08-12T14:10:20Z · sase-jx.2] Added script_duration_ms field to ChopRunEntry, threaded it through finish_chop_run and finalize_script_chop_run so lifecycle finalization no longer clobbers the script's own wall-clock; hardened read_chop_run to filter unknown keys before dataclass construction. Verified: just install succeeded, just test on the 3 touched test files (65/65 passed, incl. 3 new tests for duration preservation, script_duration_ms recording, and unknown-key tolerance), and just lint passed clean (ruff, mypy, symvision, toobig, changelog/terminology audits) with exit 0.

## Dependencies

- **Blocks:** [sase-jx.3](sase-jx.3.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.2/README.md) | [sase-jx.2](sase-jx.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`46773f6`](https://github.com/sase-org/sase/commit/46773f606446985acdc9ca2ca0112fbca2802d78) | feat(axe): preserve script wall-clock through chop run finalization | [sase-jx.2](sase-jx.2.md) | 2026-08-12 10:10:57 EDT |
