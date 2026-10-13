# Bead: sase-1jx.13.6 — Finish New Project wizard repairs before sase-1jx.13 lands

[Bead Pages](../README.md) / [sase-1jx.13](sase-1jx.13.md) / sase-1jx.13.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.land.md) · **Assignee:** `sase-1jx.13.6.land`
**Created:** 2026-10-12 19:35:34 EDT · **Closed:** 2026-10-13 00:10:44 EDT
**Plan:** [202610/new\_project\_wizard\_final\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_final_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/new_project_wizard_final_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_final_repairs.md

<!-- sase:links:end -->

## Description

Fix the epic-caused defects that the sase-1jx.13 land audit still found after its five phases closed, so that wizard creates work for every provider, the Projects pane integrates every outcome in the real app, the Source stage tears down cleanly and meets its spec, and Master Gate has no New Project failures. After this child epic lands, its land agent resumes the sase-1jx.13 landing, which then resumes the sase-1jx landing.

## Notes

[2026-10-13T03:12:03Z · sase-1jx.13.6.land] LANDING TRIAGE at c69c31236f (before remaining-work proposal). Reviewed all four child scopes and every note, approved plan, committed source in sase/sase-core/sase-github, and drift since creation/first epic commit. Outcomes for every PROPOSED FOLLOW-UP: .3 #1 narrow Projects hints capture is DECLINED as a separate task because projects-pane item 9 explicitly requires an 80-column capture at the smallest height where hints paint. Current config_center_projects_tab_80x24.png still contains no hint row; finish that in remaining epic work without redesigning old Admin Center chrome. .2 #1, .3 #2/#4 and .4 #1 Project: fake/tmp test failures -> +1 on sase-1k4 with relayed retained check evidence. .3 #3 and import failures in .2 #1/.4 #1 -> +1 on sase-1ic (same 3517-vs-3513, phase measured +0 vs master). SDD nested git-identity failure in .2 #1 ToolRun 273cb3e17344009dabc48497edf90d4c -> +1 on sase-120. Node-finder dismissal/coalescing, Archive quitting grouping, both revive-vs-archive legend tests, and revive_agent_modal.py stale exemption from .2 #1/.3 #4/.4 #1 -> DISCOVERED ISSUE corroboration on active sase-1jm, whose notes #11/#12 already own these epic-caused issues. No new task or umbrella: ci/flake/bug searches and last-week sweeps plus active-epic scopes checked. Logs inspected: 273cb3e and 4d3a221e have independent KNOWN witnesses/touched=false; rapid_keystrokes is FLAKY in the former and KNOWN in the latter. No fresh full-suite rerun or reproduction claimed for relayed reports. Remaining epic defects: pin still 546afe32, behind core strict-default fix 2fc3d775; narrow hints golden missing; pane-lifetime _last_integrated_project_key suppresses later independent show-project outcomes. Real mounted AcePage probe: first Show alpha selects alpha, manual next selects beta, second Show alpha stays beta while status says Showing alpha. Inherited human_only_record=no/glossary_project=yes honored; no memory edits. epic-symbols empty. Will propose one bounded tale that fixes these and performs this epic and ready plan-ancestor closeouts.

[2026-10-13T04:10:44Z · sase-1jx.13.6.land] Verified landing of sase-1jx.13.6 at origin/master c69c31236f with no later drift. Phases .1-.4 stay closed and match their notes. The three remaining land-audit items are done:

Pin: sase-core-revision.txt is now 2fc3d7754a3585180d0d2d7bd7ca1e034de31cdc (the committed strict-mode repair). Strict template plus explicit default-true add_readme conflicts; explicit false stays valid and omitted. The facade contract test exercises the real binding.

Dedupe: Projects integration skip is operation-scoped, keyed by durable proc_id. Duplicate delivery of the same completion plus its matching Ready dismiss integrates once. Empty operation_id always integrates. Later independent show / show-project / added outcomes for the same key reload and select again. Ready dismiss shares _apply_proc_id including handle rotation. Tests cover duplicate delivery vs separate operations, two Show-alpha outcomes separated by beta navigation, and an independent filtered outcome after a completion.

Narrow hints: 80x24 remains the named legacy clipped chrome (list, detail, and hints clip off-screen). Added config_center_projects_tab_narrow_hints_80x40.png at the smallest visual-fixture height where hints actually paint. Hints occupy visible screen space, lead with "n new", and include dropped-hints "? help". Targeted just fix-tui-screenshots --check twice, second with TZ=UTC, both check clean. Region-on-screen at height 34 is not paint-visible; 80x40 is the useful capture.

Follow-up dispositions (no new tasks; lander triage stands):
- .3 #1 narrow hints: completed here
- .2 #1, .3 #2/#4, .4 #1 Project: fake/tmp: existing ready sase-1k4
- import 3517 vs 3513: existing ready sase-1ic
- SDD nested git-identity: existing ready sase-120
- revive_agent_modal stale exemption, node-finder, Archive grouping: existing active sase-1jm notes 11/12; the exemption also fails on clean master c69c31236f

Verification: focused facade/pane/apply/rendering/prefs 72 passed; source/creation/planning 68 passed; just fix; just symvision clean; sase bead epic-symbols sase-1jx.13.6 empty. sase tool run check c6ccfe967798431cd3a8bba13a1f74a9: 2095 passed, 2 failed = KNOWN create-flow witness 0c18cf2d6c4cf95e93ad199602868cf6 plus NEW stale revive_agent_modal.py path-label exemption that also fails on clean master (already on sase-1jm). No check-full, no live create, no global reinstall in this turn.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.6.land.md) | [sase-1jx.13.6](sase-1jx.13.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`826cad0`](https://github.com/sase-org/sase/commit/826cad0513d0aea1cabd3222adfe73a12d562b58) | fix(projects): finish New Project wizard landing gaps | [sase-1jx.13.6](sase-1jx.13.6.md) | 2026-10-13 00:16:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.13.6.1][1] | Need epic DECISIONS for phase 13.6.1 | 1 |
| read-by | [agent:sase-1jx.13.6.2][2] | Need the parent epic decisions and phase context | 1 |
| read-by | [agent:sase-1jx.13.6.3][3] | Need parent epic DECISIONS and phase list | 1 |
| read-by | [agent:sase-1jx.13.6.4][4] | epic decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.4/README.md

<!-- sase:referenced-by:end -->
