# Bead: sase-1bu.2 — On-disk ledger, hot projection, doctor scan, and bindings

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.2` · **Size:** medium
**Created:** 2026-09-27 19:03:19 EDT · **Closed:** 2026-09-27 23:27:00 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

ledger-io: add ledger file I/O in sase-core: STORE.json fence, marker-superset write ordering, append, O(unsettled) hot read, stat-signature projection, history scan, doctor scan and repair, and an I/O probe. Expose them as PyO3 bindings with a thin Python facade and move the core pin.

## Notes

[2026-09-28T03:24:55Z · sase-1bu.2] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_tab_cross_nav.py and test_agent_tab_scope_honesty.py fail at import (clear_agent_tab_index_cache is defined nowhere); breaks -m contract collection on the base tree, untouched by ledger-io

[2026-09-28T03:25:20Z · sase-1bu.2] PROPOSED FOLLOW-UP: symvision flags rail_panel_title, rail_tooltip_text, rail_urgency in src/sase/ace/tui/widgets/_agent_list_render_rail.py (gate triages them KNOWN); pre-existing, untouched by ledger-io

[2026-09-28T03:25:40Z · sase-1bu.2] LAND NOTE: sase-core-revision.txt still at 0e8981a; ledger-io core work is uncommitted in the linked sase-core checkout (host finalizer commits). Ratchet with just ratchet-core-revision after the sase-core commit lands.

[2026-09-28T03:27:00Z · sase-1bu.2] ledger-io done: sase-core goal/ledger (layout/STORE fence, append with marker-superset ordering + stale_basis replan + fault hook, O(unsettled) hot read, stat-signature projection, doctor scan/repair, I/O probe) with 11 Rust tests passing; goals bindings (12 incl. probe/refresh) with 3 round-trip tests; goal_ledger_facade + REQUIRED_BINDINGS/schema checks in both validator tools with new tests; sase-core sase tool run check green; sase check lint+validation stages green with facade symbols whitelisted to sase-1bu (acceptance removes them); tests/core 288 green; 2 pre-existing base-tree failures recorded as PROPOSED FOLLOW-UP (agent_tab import breakage, rail symvision KNOWNs); pin ratchet left for land agent (uncommitted core, host-owned commits)

[2026-09-28T04:16:21Z · sase-1bu.2--1] PROPOSED FOLLOW-UP: just check (full suite after rebase onto 52f7351ae) shows 26 NEW failures unrelated to ledger-io merge resolution — zero file overlap with the 6 ledger-io files and no goal_ledger imports in failing tests; groups: agent/directive completion (12), completion snapshot/kind/zsh (5), axe repeat/wait-chats/vcs env (6), plus timezone guard, config schema, docs wording, marker-path audit, registry rebuild, prompts overlay, header panel, watch highlight; Justfile union + facade/validator content re-verified green (37 focused tests pass)

## Dependencies

- **Depends on:** [sase-1bu.1](sase-1bu.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.3](sase-1bu.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.2.md) | [sase-1bu.2](sase-1bu.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`85beb8a`](https://github.com/sase-org/sase/commit/85beb8a060be362a2e380765977fad3897f1d618) | feat(goals): add goal ledger Python facade, bindings checks, and epic symbols (sase-1bu.2) | [sase-1bu.2](sase-1bu.2.md) | 2026-09-28 00:16:39 EDT |
| sase-core | [`sase-core@cbe70f6`](https://github.com/sase-org/sase-core/commit/cbe70f66fb28a6b14a023a1458f26cf0f75de911) | feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2) | [sase-1bu.2](sase-1bu.2.md) | 2026-09-28 00:19:58 EDT |
