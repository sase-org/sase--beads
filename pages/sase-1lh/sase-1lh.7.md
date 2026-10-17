# Bead: sase-1lh.7 — Repair the release watcher and check-mode recapture, then ship sase v0.18.0

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.land.md) · **Assignee:** `sase-1lh.7.land`
**Created:** 2026-10-16 16:46:18 EDT
**Plan:** [202610/sase\_1lh\_landing\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_1lh_landing_repair.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/sase_1lh_landing_repair.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:7452d1d4b006dacd914725b4 | attached via sase artifact create --bead |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/sase_1lh_landing_repair.md

<!-- sase:links:end -->

## Description

The defects that the sase-1lh landing review found in its own watcher, check-mode recapture, and docs_split work are fixed. The watcher treats a stale release-PR head as something to refresh, not as CORE_FLOOR_BLOCKED. A fresh release watch sees sase 0.18.0 install from PyPI. This epic's land agent confirms the release, then resumes the interrupted sase-1lh landing through parent_bead.

## Notes

[2026-10-17T00:20:20Z · sase-1lh.7.land] LANDING AUDIT AND FOLLOW-UP TRIAGE (f6ff20ef2a, 2026-10-17 UTC): incomplete; no close or status: done. Full evidence: file:explicit:7452d1d4b006dacd914725b4. Read this epic, every child and every note, linked plan, parent sase-1lh notes, implementation commits e41b209b24/ec7e86e690/2eb0ca791a, actual sources, and all seven later non-epic commits, plus 367562ba52 and 552b38f7ed integration context.

VERIFIED: nested explicit anchor_target repair and cross-directory tests are correct; watcher staleness/enrichment/one-refresh-per-SHA/fresh-red budget/signal-close work matches approved design; shared recapture driver, persistent node failure status, skipped-node guard and CI 600s configuration exist; authorized tui_screenshot.md zero-unstable proof present, no other authored memory changes by this epic. 149 focused tests pass (43.79s, Python 3.14.7); no check-full run. epic-symbols sase-1lh.7 reports none. Working tree had no code edits in this audit.

REMAINING EPIC WORK: recapture still masks first-pass child/session exit 3 as clean after a matching retry (reproduced), and targeted ACE-only drift/recovery falsely fails for visual_root_unexecuted:pager (reproduced). Strict policy omits child/session/scope/full-structure facts; retry acceptance also needs abnormal-exit/protocol validation. Deadline checks only precede an unbounded all-node subprocess, so 600s does not bound elapsed retry execution. New help test in 2eb0ca791a fails under CI Python 3.12 due to argparse metavar placement. These require repair, not follow-up tasks.

RELEASE: .4 closed canceled honestly, not successful. PR #299 remains OPEN, PyPI has no 0.18.0. Its current same-base head 8fd85e7c5cba... has floor run 38982644527 with 831 passes / 1 project-identity audit failure, not evidence of a deficient core wheel. Full CI 38980994819 at fae5cf5076 contains all repairs and E4 goldens; visual job 117244671206 completed red (33m21s) with four persistent image diffs: three retry E2E images and archive-help. Master Gate 38983979564 is red on deterministic integration tests and five docs anchors. Four representative independent failures reproduce in isolated local pytest. Images were not inspected: CI report artifact downloads returned invalid ZIPs, so next repair must inspect local candidates or a working artifact download.

EVERY PROPOSED FOLLOW-UP OUTCOME:
- sase-1lh.7.1 #1 and sase-1lh.7.3 #1: duplicate interpreter-dependent docs generation; one +1 on existing sase-1lm relays both independent clean-base observations. Current Python 3.14 render_cli --check passes; no new task, no claim of cross-version resolution.
- sase-1lh.7.2 #2: requested newer Full CI proof now exists, run 38980994819. Instruction-bundle-specific goldens are not among its four remaining diffs. No waiting task; remaining archive-help issue recorded on active causal epic sase-1lj.
- sase-1lh.7.2 #4: current init memory --check --diff passes. Historical home projection drift relayed to sase-1lj, which already owns it. Declined new task and +1 on sase-vu because that is a separate live-write-isolation defect and no such write was reproduced.

ADDITIONAL INDEPENDENT BLOCKERS, triaged through sase_new_task after all-status searches, last-week sweep, and active-epic review:
- New small CI task sase-1lw: closed sase-1li commit fae5cf5076 added timestamp extra_env but omitted fake-signature and exact-env assertions in launch approval/TUI/macro-group tests. Related to sase-1li, not duplicate of old sase-ot.
- New small CI task sase-1lx: a9701c36e6 archived-prompt repair uses storage identity without a deliberate audit exemption. Fix the identity-only test contract, never turn a storage key into a display label.
- DISCOVERED ISSUE notes on sase-1le.20.1 for five moved bead-cli anchors and stale root-help assertion caused by 367562ba52; no duplicate tasks.
- Supplementary observation on sase-173 for current retry image drifts. Declined +1/new duplicate/closed sase-13v reopen until actual pixels identify whether random hex IDs or a different cause. Child repair owns classification and resolution for release readiness.

NEXT: validated three-phase child epic sase_plan_finish_recapture_release.md, parent_bead sase-1lh.7: recapture-contract, release-integration, release-watch. --explain validation passed; descriptions refined; revalidation passed with zero warnings. Child epic is justified because host commits repair after coder turn, then separate no-edit watcher observes committed CI/publication. No tale may wait for its own commit. The child lander must confirm the release and then re-audit/close this epic normally, symvision, mark plan:202610/sase_1lh_landing_repair.md done, then re-audit parent sase-1lh including its saved post-release/stale-epic duties. No force-close for successful nested landing.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.land.md) | [sase-1lh.7](sase-1lh.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1w.mus][1] | Child epic status for current release blockers | 1 |
| read-by | [agent:sase-1lh.7.1][2] | Need parent epic scope and decisions | 1 |
| read-by | [agent:sase-1lh.7.3][3] | parent epic context | 1 |
| read-by | [agent:sase-1lh.7.5.2][4] | Need parent epic scope and decisions for this phase | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1w.mus/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.2/README.md

<!-- sase:referenced-by:end -->
