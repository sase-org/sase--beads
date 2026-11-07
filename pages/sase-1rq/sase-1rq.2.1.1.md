# Bead: sase-1rq.2.1.1 — Keep Master Gate green at the master tip

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.1` · **Size:** medium
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

master-gate: Master Gate is red at tip 0ba9cfc9 (run 42373447720). Its only failure is test (3) at tests/ace/tui/test_epic_panel_arrival_frames.py::test_selection_stays_highlighted_and_scrolled_into_view ('frame 11: row 14 outside scroll 2+12'). Prove whether it is deterministic or flaky on an unchanged tree. Root-cause it if you can; otherwise quarantine it with a flake follow-up. Then fix any other Master Gate red at the current tip.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.1/README.md) | [sase-1rq.2.1.1](sase-1rq.2.1.1.md) | 0 |
