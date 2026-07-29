# Bead: sase-aq.3 — Launch-time key resolution and text substitution

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.3` · **Size:** medium
**Created:** 2026-07-29 13:07:34 UTC · **Closed:** 2026-07-29 14:03:10 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

resolve: add a keyed marker resolver that allocates one token per key under the agent-name lock and rewrites every occurrence in the dispatch's segment text, wire it into the launch funnel, and reject markers that reach a runner.

## Notes

[2026-07-29T14:03:10Z · sase-aq.3] Implemented dispatch-scoped keyed marker allocation/substitution across CWD, ACE TUI, and the shared multi-prompt launcher, plus runner fail-fast for unresolved executable markers. Verified 30 focused tests and the full suite: 23518 passed, 7 skipped. Formatting, ruff, mypy, pyscripts, Symvision, and toobig passed; full just check reached only pre-existing external init-skills drift for 15 generated provider files.

[2026-07-29T14:04:00Z · sase-aq.3] Verified 30 focused tests and the full suite (23,518 passed, 7 skipped); formatting, ruff, mypy, scripts, Symvision, and size checks passed. just check only reported pre-existing external drift in 15 generated provider skill files, which were not modified.

## Dependencies

- **Depends on:** [sase-aq.2](sase-aq.2.md) ✓
- **Blocks:** [sase-aq.4](sase-aq.4.md) ✓
