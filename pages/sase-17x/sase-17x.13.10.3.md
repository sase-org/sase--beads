# Bead: sase-17x.13.10.3 — History walk, menu keys, and compact key hints

[Bead Pages](../README.md) / [sase-17x.13.10](sase-17x.13.10.md) / sase-17x.13.10.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.3` · **Size:** medium
**Created:** 2026-09-25 08:41:43 EDT · **Closed:** 2026-09-25 12:05:28 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

key-routing: reset the history walk cursor on each new walk. Decouple menu movement from the history bindings and fix the menu hint. Render compact `esc` / `^R` key names. Drive the remaining key contracts through real key presses.

## Notes

[2026-09-25T16:05:03Z · sase-17x.13.10.3] PROPOSED FOLLOW-UP: sase tool run check SASE validation (agent prompts validate) fails identically on the clean base tree - prompts/202609/bbugyi200.apollo.2.md cites missing published artifact files/objects/sha256/41/412ed4ed... (artifact-missing; untracked-object variants flake between runs); all lint gates pass - needs a prompt-archive artifact repair owner, unrelated to key-routing.

[2026-09-25T16:05:28Z · sase-17x.13.10.3] key-routing done: history_step no longer pre-assigns _history.anchor so walk() resets the cursor on each new _walk_anchor (prefix filtering + new-walk reset verified through real up/down presses); menu moves on fixed up/down/ctrl-p/ctrl-n/Tab/shift-Tab while rebound history keys only walk when the menu is closed (real-press decoupling test with history_prev=ctrl+b); COMMAND_LINE_MENU_HINTS is now 'esc leave'; _compact_key_display renders escape->esc and ctrl+<k>->^<K> (hint assertions updated to ^R/^J/esc); docs/ace.md menu keys list gains up/down arrows; new real-press tests: history prefix filter+reset, right-accepts-ghost at line end, R rerun-with-y vs notice, i/a/colon back to INSERT, grammar readiness via real loader with in-process CommandLineGrammar. Verified: full tests/ace/tui/command_line suite 205 passed; just-fix clean; lint gates green (ruff/mypy/symvision/keep-sorted); sase validate passes directly; sase tool run check validation failure reproduces identically on clean base (recorded as PROPOSED FOLLOW-UP); toobig tests/tool/test_settlement.py 1048 lines pre-existing at HEAD, out of scope per plan (sase-18h).

## Dependencies

- **Depends on:** [sase-17x.13.10.1](sase-17x.13.10.1.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-17x.13.10.2](sase-17x.13.10.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17x.13.10.4](sase-17x.13.10.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.3/README.md) | [sase-17x.13.10.3](sase-17x.13.10.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e01d346`](https://github.com/sase-org/sase/commit/e01d34651b4a356e463f899649a928f70c38c98e) | fix(command-line): history walk reset, fixed menu keys, compact key hints (sase-17x.13.10.3) | [sase-17x.13.10.3](sase-17x.13.10.3.md) | 2026-09-25 12:07:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.10.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.3/README.md

<!-- sase:referenced-by:end -->
