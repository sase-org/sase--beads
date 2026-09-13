# Bead: sase-zl.13.11 — Repair the remaining monitor continuation contracts

[Bead Pages](../README.md) / [sase-zl.13](sase-zl.13.md) / sase-zl.13.11

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zl.13.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zl.13.land.md) · **Assignee:** `sase-zl.13.11.land`
**Created:** 2026-09-13 06:00:39 EDT
**Plan:** [202609/monitor\_continuation\_remaining\_contracts.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_continuation_remaining_contracts.md)

## Description

Preserve exact frozen context, protected instructions, single-delivery recovery, and existing-record semantics while integrating continuation ancestry with retention and proving the complete route.

## Notes

[2026-09-13T11:07:21Z · sase-zt.land] QUEUE INTEGRATION OWNERSHIP from sase-zt landing at f3a39fa835: queue_launch_prefix currently prefers wait_runners over queue_capacity and emits historical zero into the new On parser, which raises DirectiveError. Isolated reproduction with wait_runners=0, queue_capacity=3, queue_weight=1 emits capacity=0. A remaining-work child of sase-zt will complete canonical capacity persistence and exact legacy-zero admission semantics, including this narrow continuation adapter seam; preserve the shared Rust policy and your frozen-context/exactly-once journal work. Coordinate that seam if editing continuation_delivery.py or its launch wire. Audit file:explicit:49e1cedbfb0962c856bb2e22; this stays queue epic work, not a separate task.

[2026-09-13T12:58:20Z · sase-zt.6.2] QUEUE INTEGRATION from sase-zt.6.2: continuation_delivery.queue_launch_prefix now prefers canonical queue_capacity, uses normalize_persisted_queue_capacity.reauthor_capacity so historical explicit zero is omitted from the On parser (legacy-zero Off still emits capacity=0), and launch_wire_extra journals queue_capacity/queue_capacity_explicit on the existing admission journal. Positive budget, priority 0, and fractional weight still go through the reconstructed %queue prefix. Did not add a second delivery journal.

[2026-09-13T14:58:12Z · sase-108.2] DISCOVERED ISSUE: just check fails at lint (symvision) on unused public apply_resume_adoption in src/sase/monitor/resume.py. It is only called in-file (resume.py:121) and monkeypatched from tests/monitor/test_monitor_resume.py; tests do not keep a public symbol alive. Reproduced 2026-09-13 while verifying sase-108.2 on this workspace: fmt/ruff/mypy passed, then just _lint-symvision named only this symbol. sase-zl.13.11.3 (Fence manual resume against concurrent receiver adoption) is in_progress and owns this function. Fix there: _-prefix if it stays in-file, or add --epic-symbol sase-zl.13.11.3(apply_resume_adoption) if a later phase will import it. No pager change; no new task.

[2026-09-13T16:28:46Z · sase-zt.6.4--2] DISCOVERED ISSUE: require_rust_binding("continuation_decide_resume_adoption") in src/sase/core/continuation_facade.py:122,125 (added by 897147eac, sase-zl.13.11.3, fence manual resume against concurrent receiver adoption) has no corresponding sase-core implementation. Verified with a full-history search (git log --all --oneline -S and --grep) of the sase-core checkout at sase/repos/external/gh/sase-org/sase-core: zero matches for the symbol in Rust source or any commit on any branch. just check's advisory tools/probe_core_floor corroborates: status blocked_unpublished, "continuation_decide_resume_adoption: no introducing commit found in sase-core" (declared_floor 0.34.23, cache_hit true). Per this project's no-Python-fallback Rust-core-required contract, any real call into this facade path will raise at runtime until the PyO3 binding lands and is tagged in a sase-core release; unit tests pass today only because they mock/monkeypatch the binding. Encountered 2026-09-13 while running sase-zt.6.4's acceptance-phase live smoke test, whose launch agents were slow to progress around the same seam - noting as context, not a confirmed root cause. sase-zl.13.11.3 is in_progress and owns this seam. No new task filed - same active-epic note pattern as note #3 (sase-108.2).

[2026-09-13T16:44:13Z · sase-108.land] DISCOVERED ISSUE corroboration (sase-108.3 PROPOSED FOLLOW-UP, confirmed by sase-108.land 2026-09-13): the continuation_decide_resume_adoption binding gap still blocks unrelated agents' full just check. With the sase-core pin at 17947a05 (origin/master tip, a fast-forward of the prior pin ba651fe5), the installed sase_core_rs lacks the binding and tests/monitor reports 10 failed / 294 passed with AttributeError from require_rust_binding. git log --all -S in sase-core still finds no commit adding the symbol. Recorded here rather than as a new task per the active-epic routing rule.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zl.13.11.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zl.13.11.land/README.md) | [sase-zl.13.11](sase-zl.13.11.md) | 0 |
