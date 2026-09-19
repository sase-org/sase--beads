# Bead: sase-11l.11.5 — Ratchet the hold-deadlock source pin

[Bead Pages](../README.md) / [sase-11l.11](sase-11l.11.md) / sase-11l.11.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.land.md) · **Assignee:** `sase-11l.11.5.land`
**Created:** 2026-09-19 04:37:23 EDT · **Closed:** 2026-09-19 06:19:39 EDT
**Plan:** [202609/hold\_deadlock\_core\_pin.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_deadlock_core_pin.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/hold_deadlock_core_pin.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/hold_deadlock_core_pin.md

<!-- sase:links:end -->

## Description

SASE's pinned Rust core contains the hold-deadlock binding used by production Python code.

## Notes

[2026-09-19T10:19:39Z · sase-11l.11.5.land] Verified sase-11l.11.5 complete. Sole child sase-11l.11.5.1 is closed; its four notes (ratchet 8261449c v0.34.61 -> 093eb2dc v0.34.62 -> 44b82c3e -> 39602c95 v0.34.63, then install/test/check) match the tree. Commit 0fc51c2998 is the only epic stitch and only changes sase-core-revision.txt to 39602c950f8882d71dab1e3b74c17d2751e8b1cf. Linked core at that SHA is origin/master v0.34.63, a descendant of 0a7301ca435d (agent_hold_deadlock_reaches), and the PyO3 binding is present in crates/sase_core_py/src/lib.rs. Installed sase-core-rs 0.34.63 exposes the binding; tests/test_run_agent_wait_slot_hold_deadlock.py 14 passed; tools/ratchet_core_revision --check is clean; production call remains src/sase/axe/run_agent_wait_slot_candidate.py:require_rust_binding("agent_hold_deadlock_reaches"). pyproject.toml and uv.lock still declare >=0.34.48,<0.35.0 as required.

Integration: commits since the epic started excluding 0fc51c2998 are 9cfa200675 (ToolRun V1; already fast-forwarded by the phase), 485a6082e1 (service tests), and 423316a051 (project-owned tool catalog). None touch the pin, hold-deadlock production path, or deadlock tests, and none duplicate or should consume this epic's pin. No PROPOSED FOLLOW-UP notes on this epic's children. The published-package floor remains owned by ready task sase-10d (already +1 from sase-11l.11.4) and in-progress epic sase-12y.4; declined a new task. No --epic-symbol entries for sase-11l.11.5.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.11.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.5.land.md) | [sase-11l.11.5](sase-11l.11.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48d0a69`](https://github.com/sase-org/sase/commit/48d0a69287b73187704633273473296143167e58) | chore(hold): persist sase-11l.11 land continuation checkpoint | [sase-11l.11.5](sase-11l.11.5.md) | 2026-09-19 08:32:28 EDT |
