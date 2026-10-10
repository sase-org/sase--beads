# Bead: sase-1jc.3 — Make queue capacity budgets unconditional

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.3` · **Size:** medium
**Created:** 2026-10-09 22:28:24 EDT · **Closed:** 2026-10-10 04:19:42 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

queue-budget: Follow phase 3 and the shared removal checklist. Retire queue_capacity_budget and close sase-zv across Rust parsing/admission/editor behavior and Python launch, bead, and TUI adapters. Delete the Off threshold semantics and finished launch/editor flag plumbing, including already-retired constant shims where proven unused. Preserve supported persisted queue records and percent-hold behavior. Verify the Rust core and Python checkout sequentially.

## Notes

[2026-10-10T08:19:21Z · sase-1jc.3] PROPOSED FOLLOW-UP: Epic auto-decision macro_memory=no skipped the macros.md typed-Proc wording update; a later phase should describe queue capacity budgets as unconditional there

[2026-10-10T08:19:25Z · sase-1jc.3] PROPOSED FOLLOW-UP: Epic auto-decision refresh_memory=no skipped the tui_perf.md rule-14 flag-condition update; a later phase should describe refresh tokens as unconditional there

[2026-10-10T08:19:33Z · sase-1jc.3] PROPOSED FOLLOW-UP: just check background failures reproduce identically on the clean base tree (verified via git stash): test_config_schema spare_process_patterns mismatch, completion mutex 21-vs-20 plus snapshot drift x2, agents help sort order, TUI import budget 3518-vs-3513, just lint toobig on agent/auto_restart/healer.py; remaining 9 failures carry KNOWN/FLAKY triage witnesses from run 3bf7953374ad8e69fa77b4c242fa0c38 — land agent to triage/file

[2026-10-10T08:19:42Z · sase-1jc.3] queue_capacity_budget retired: registry definition removed and schema regenerated; Off threshold/zero-drain branches deleted across Rust queue parsing/admission/editor/LSP and Python launch/bead/TUI adapters; persisted queue records, multiplier/weight semantics, and percent-hold behavior preserved; sase-zv closed. Verified: sase-core sase tool run check GREEN (8a4cc08f); sase sase tool run check (3bf79533) all lint gates green plus 54558 scoped tests pass — 2 failures fixed in-phase (directive vocab suggestions, arg-completion re-export), the rest reproduce identically on the clean base tree or carry KNOWN/FLAKY triage witnesses. Both repos dirty for host finalization; sase-core-revision.txt pin must move past the core commit.

## Dependencies

- **Depends on:** [sase-1jc.2](sase-1jc.2.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.4](sase-1jc.4.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.3/README.md) | [sase-1jc.3](sase-1jc.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c24b650`](https://github.com/sase-org/sase-core/commit/c24b6500d5336de7a7b21b370f37cb85cdb315e1) | feat(launch): retire queue\_capacity\_budget opt-out; unconditional capacity budgets | [sase-1jc.3](sase-1jc.3.md) | 2026-10-10 04:20:58 EDT |
| sase | [`b816732`](https://github.com/sase-org/sase/commit/b81673283a8ff921652a2370f8a6d6f7b55865f8) | feat(flags): retire queue\_capacity\_budget; queue capacity budgets unconditional | [sase-1jc.3](sase-1jc.3.md) | 2026-10-10 04:25:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jc.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.3/README.md

<!-- sase:referenced-by:end -->
