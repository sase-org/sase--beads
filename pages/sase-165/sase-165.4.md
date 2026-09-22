# Bead: sase-165.4 — Core pin ratchet workflow opens its PR

[Bead Pages](../README.md) / [sase-165](README.md) / sase-165.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0p2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0p2.md) · **Assignee:** `sase-165.4` · **Size:** small
**Created:** 2026-09-22 08:18:24 EDT · **Closed:** 2026-09-22 09:55:04 EDT
**Plan:** [202609/sase\_core\_p0\_agent\_maintainability.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_p0_agent_maintainability.md)

## Description

pin-ratchet-bot: make core-pin-ratchet.yml tolerate the apply path's exit 2 so it reaches the push and PR steps. Behavior-test the step script (sase-15v).

## Notes

[2026-09-22T13:53:55Z · sase-165.4] PROPOSED FOLLOW-UP: just check has 11 pre-existing deterministic failures on clean tree (test_commit_bead_hooks x3, at_path_values x1, usage_config x4, test_shards x1, epic_panel_arrival_frames x1, session_proc_reporter x1) — partly tracked by sase-15z, sase-14v/sase-14u, sase-14r; arrival_frames and session_proc_reporter have no duplicate found

[2026-09-22T13:54:23Z · sase-165.4] PROPOSED FOLLOW-UP: plugins-browser pane update tests (sase_update_mixed, update_confirm) failed in full just check lane but pass in isolation — probable flakes, no duplicate found

[2026-09-22T13:55:04Z · sase-165.4] Workflow apply step now captures exit status and only fails on non-0/non-2, so exit 2 reaches push/PR; tool exit-2 contract unchanged per plan decision 7. Verified: new test_core_pin_ratchet_apply_tolerates_exit_two failed before and passes after (28 passed across workflow+tool test files); shell probe of the real guard lines shows exit 0/2 continue and exit 3 aborts while the old bare call aborted on 2; ruff/mypy/symvision lint green. Full just check still red from 11 pre-existing failures proven identical on the clean tree (noted as PROPOSED FOLLOW-UPs). No epic-symbol entries remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-165.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.4/README.md) | [sase-165.4](sase-165.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1404010`](https://github.com/sase-org/sase/commit/1404010b1e255bdc42711b34202c6f0c2d83a27c) | fix(core-pin): tolerate ratchet apply exit 2 so the bot reaches push and PR | [sase-165.4](sase-165.4.md) | 2026-09-22 09:56:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-165.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.4/README.md

<!-- sase:referenced-by:end -->
