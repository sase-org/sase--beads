# Bead: sase-1kx.5.3.3 — Finish the remaining capture races and confirm sase 0.18.0 publication

[Bead Pages](../README.md) / [sase-1kx.5.3](sase-1kx.5.3.md) / sase-1kx.5.3.3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kx.5.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.3.land.md) · **Assignee:** `sase-1kx.5.3.3.land`
**Created:** 2026-10-14 22:37:10 EDT
**Plan:** [202610/v0\_18\_0\_capture\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_capture_convergence.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_0_capture_convergence.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:9dbb8a7a761400203c1c56f0 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_capture_convergence.md

<!-- sase:links:end -->

## Description

The remaining visual capture defects are repaired, the full visual lane is clean, and the committed repairs ship in an installable sase 0.18.0 through the guarded release path.

## Notes

[2026-10-15T09:51:12Z · sase-1kx.5.3.3.land] LANDING AUDIT — incomplete; remaining-work child plan required.

Verification: read the epic's linked plan plan:202610/v0_18_0_capture_convergence.md, both children and every note, and the ancestor plans/landing notes through sase-1kx. Neither current child has a PROPOSED FOLLOW-UP entry. Reviewed the complete be73b6021ac29d8fcad2cb897192bc6455a47e2b diff and actual caller/production paths for Main selection/document generations, Tool Runs load/cache/paint, top-bar density, and Logs telemetry. The nine-file fixture change preserves visual expectations and the accepted core_release=dispatch / stale_epic_1jz=notes decisions. Phase .1's local evidence is genuine: ToolRun 76cc0322368c97df8ee8485040deffd4 just check succeeded, exit 0 / triage pass, 8m54s overall (3m11s in its note is the scoped-test stage); full UTC visual monitor 4njkqnvs5b2p succeeded with 1366 passed, 1 skipped, clean, created=0 updated=0 unchanged=1100 stale=0. Phase .2 honestly closed canceled with FULL_CI_RED; that is not release completion.

Integration: fetched origin and inspected commit history since the first epic commit. HEAD and origin/master both be73b6021ac29d8fcad2cb897192bc6455a47e2b; the only commit in that interval is the epic's own phase .1 commit, so there is no intervening base implementation to integrate. Reviewed the preceding parent repair as well. No tracked source or golden changes were made by this audit; no just check-full was run.

Remaining epic work: raw Full CI logs on the exact repair SHA expose Tool Runs details loaded but never painted (38698824253, job 116305071749), renamed-session Reply selection with Context chrome and pending=None (38683274240, job 116275103654), and single Main automatic layout stuck in spread (38698824253). A deterministic real document/view probe proves the first issue: placeholder and loaded documents receive the same summary digest, show_document dedupes before replacing the stored document, only one paint occurs, and stage text remains absent. update_display can also skip complete details on that same signature. Main layout/scroll roots need controlled investigation; the visible inconsistent states are confirmed, not a proved common cause. Preserve the new assertions and repair current presentation state instead of enlarging timeouts or rebaselining.

Release verification: Master Gate 38680491171 is green on be73; both Full CI 38683274240 and 38698824253 failed. The latter report is failed, not drift or a clean zero-comparison result. Latest Full CI 38713421385 remains in progress on be73; no duplicate was dispatched. PR #299 is still open (735922478413edaa3e4d3276f0a2b17007d4a2ad). Publish 38682622881 only ran metadata work; actual build/publish/install jobs were skipped. Fresh PyPI JSON still has sase 0.17.1, no 0.18.0; core 0.40.0 is published and satisfies the unchanged pin. No manual merge, global install, deployment, forced close, or termination of waiting agents was attempted.

Durable evidence for all observations, exact node IDs, log excerpts, rendered SVG text, and executable probe: file:explicit:9dbb8a7a761400203c1c56f0 (registered and audited-read). The local check and full visual success were independently inspected rather than inferred from phase summaries.

Follow-up triage completed under /sase_new_task, including targeted all-status searches, recent-task sweeps, plausible task reads, and active-epic scope review. All four unrelated failures below occurred in 38683274240 and passed in 38698824253 on the unchanged be73 SHA (one observed failure and one later pass; no serial local reproduction claimed). They originate in this lander's review of phase sase-1kx.5.3.3.2 note #2, not explicit child proposals:
1. Corroborated sase-1a0 with +1 and the evidence reference: exact test_persist_monitor_result_stamps_needs_recovery_after_bounded_wait, 2.189018621 seconds versus <2.0, Python 3.13. Declined a duplicate task.
2. Created ready large flake sase-1l7 for test_ctrl_t_before_reveal_reveals_without_inserting, Python 3.14: Ctrl+T inserts review before the supposed reveal-only assertion. Added a related link to sase-1g8; declined duplicate corroboration because its midword visibility/pending failure has no established shared root.
3. Created ready large flake sase-1l8 for test_new_project_bare_git_create_and_review_hide_visibility_png_snapshots: availability/create checks remain pending at the 15-second bound. No semantic duplicate or causal active epic found.
4. Created ready large flake sase-1l9 for the textual-dark test_prompt_codeblock_highlight_solo_png_snapshot: no stable frames while prompt-artifact-ref-kinds:0 stays pending for 30 seconds. Added a related link to sase-hx; declined reopening that older invalidation-result task because the in-flight worker symptom does not establish the same defect.
The three new tasks carry concrete provenance and the durable evidence ref. Their roots remain unconfirmed and require CI/harness investigation, so default large sizing is intentional.

Added DISCOVERED ISSUE evidence to causally related active epic sase-1jz, citing its phase .3 / 4b99e45907 and the deterministic Tool Runs probe; current epic retains repair ownership via the remaining-work plan, so no separate Tool Runs/Main task was filed. Declined a new omnibus FULL_CI_RED task: specific failures now have owners. Did not +1 sase-1ii for the new automatic-paged node, since its neighboring spread-sticky/committed-search failures do not prove a common root. Reviewed other plausible active epics (sase-kp, sase-rj, sase-11i.6) without claiming topical overlap as causality. Preserve the prior ancestor landing notes' follow-up outcomes; do not recreate their tasks.

sase bead epic-symbols sase-1kx.5.3.3 reports no entries. The epic and plan stay open because actual promised capture behavior and publication are incomplete, not because of a check-full-only failure. A validated child epic plan will use one medium coding phase and one small no-edit publication phase. This split preserves the accepted requirement to observe the future repair commit in guarded CI/publication; the coder must not wait for its own commit. The child parent_bead is sase-1kx.5.3.3. Its lander must resume this epic and the ready plan ancestors only after full readiness and drift checks, normal symbol cleanup/close, symvision, and linked-plan status updates. No force-close is authorized to advance successful nested landing.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.5.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.3.3.land.md) | [sase-1kx.5.3.3](sase-1kx.5.3.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kx.5.3.3.1--2][1] | Need the parent epic decisions this phase must preserve while completing and closing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.5.3.3.1.md

<!-- sase:referenced-by:end -->
