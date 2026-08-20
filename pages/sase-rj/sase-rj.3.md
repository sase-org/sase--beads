# Bead: sase-rj.3 — Complete responsive directive support in the ACE prompt widget

[Bead Pages](../README.md) / [sase-rj](README.md) / sase-rj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08s](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08s.md) · **Assignee:** `sase-rj.3` · **Size:** medium
**Created:** 2026-08-20 13:44:20 EDT · **Closed:** 2026-08-20 15:49:18 EDT
**Plan:** [202608/xprompt\_directive\_completion\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_directive_completion_parity.md)

## Description

prompt-widget: replace the prompt widget's private directive tables and token classifier with the shared contract, wire warm dynamic catalogs for bead, identity, model, and path values, and preserve the non-blocking completion path.

## Notes

[2026-08-20T19:20:17Z · sase-rj.3] PROPOSED FOLLOW-UP: flake — tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_wall_clock_budget[flag] failed at 800ms vs 450ms CI budget during an escalated just check, then passed serially in 160ms; the test file itself calls the wall-clock check inherently flaky.

[2026-08-20T19:20:49Z · sase-rj.3] PROPOSED FOLLOW-UP: landing depends on an unpublished sase-core-rs — just check core-floor-probe reports directive_contract, directive_completion_context, and directive_completion_candidates first appear in sase-core 04c27f2 with no release tag yet; local just install builds the linked checkout, but published 0.29.5 cannot serve ACE adapters until a core release includes those bindings.

[2026-08-20T19:49:18Z · sase-rj.3--2] ACE prompt-widget directive completion now uses sase_core_rs.directive_contract, directive_completion_context, and directive_completion_candidates. Wait paren offers documented bead= first; colon %wait: does not advertise structured keywords; %xprompts_enabled is completed. Identity/conflict filtering and warm bead inventory (mtime-keyed raw_wait_bead_inventory off-thread) are wired. Fast-forwarded master cleared stale closed sase-ri.4 --epic-symbol entries. just check passed (all lint gates including symvision; scoped tests selected 438 of 3148 files, exit 0). sase bead epic-symbols sase-rj.3 reported no leftovers.

[2026-08-20T19:50:44Z · sase-rj.3--2] ACE prompt-widget directive completion now uses sase_core_rs.directive_contract, directive_completion_context, and directive_completion_candidates. Wait paren offers documented bead= first; colon %wait: does not advertise structured keywords; %xprompts_enabled is completed. Identity/conflict filtering and warm bead inventory (mtime-keyed raw_wait_bead_inventory off-thread) are wired. Workspace was fast-forwarded to origin/master so stale closed sase-ri.4 --epic-symbol entries no longer fail symvision. just check passed (fmt, lint including symvision, SASE validation, scoped tests). epic-symbols for sase-rj.3 reported no leftovers. Existing proposed follow-ups remain: CLI latency flake on test_candidates_fast_path_wall_clock_budget, and landing depending on unpublished sase-core-rs bindings first shipped in 04c27f2.

## Dependencies

- **Depends on:** [sase-rj.1](sase-rj.1.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rj.4](sase-rj.4.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rj.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rj.3.md) | [sase-rj.3](sase-rj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1830524`](https://github.com/sase-org/sase/commit/1830524b09be6ce7c5e62ca007d400e8655734b7) | feat(ace): complete prompt-widget xprompt directive completion | [sase-rj.3](sase-rj.3.md) | 2026-08-20 15:52:16 EDT |
