# Bead: sase-1bu.5 — The sase goal command

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.5` · **Size:** medium
**Created:** 2026-09-27 19:03:24 EDT · **Closed:** 2026-09-28 06:38:24 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

cli: add sase goal (list default, show, new, edit, drop, reopen, merge, doctor) with human-only verbs refused inside agent runs. Render terminal output through a Rust renderer, add JSON output, and serve list/show from a lean entry.py fast path under the 50 ms budget. Register completion spec, run policy, and CLI docs rows.

## Notes

[2026-09-28T10:38:06Z · sase-1bu.5--2] PROPOSED FOLLOW-UP: just check test-scoped shows 24 failures triaged as 23 KNOWN + 1 FLAKY (witness 56471cbd76a6995bcc4e14554fa9d36f), no_new_failures; unrelated to goal CLI

[2026-09-28T10:38:24Z · sase-1bu.5--2] goal CLI done: symvision lint green, ruff/mypy/all lint green, tests/goals/test_goal_cli.py 23/23 pass; full just check triaged no_new_failures (23 KNOWN +1 FLAKY, witness 56471cbd), epic-symbols clean

## Dependencies

- **Depends on:** [sase-1bu.4](sase-1bu.4.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.7](sase-1bu.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.5.md) | [sase-1bu.5](sase-1bu.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f79a391`](https://github.com/sase-org/sase/commit/f79a391b53876a5fb8bfe7cad00939fc18054551) | feat(goals): add sase goal CLI with fast-path list/show and human-only verbs | [sase-1bu.5](sase-1bu.5.md) | 2026-09-28 06:57:51 EDT |
| sase-core | [`sase-core@d2d9ec7`](https://github.com/sase-org/sase-core/commit/d2d9ec7fcc5477547bb774ebb9ae38a6c75de01d) | feat(goals): add goal ledger, fast path, and terminal renderer backend | [sase-1bu.5](sase-1bu.5.md) | 2026-09-28 07:12:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bu.5--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.5.md

<!-- sase:referenced-by:end -->
