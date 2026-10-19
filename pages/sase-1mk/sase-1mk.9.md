# Bead: sase-1mk.9 — Clear the post-repair Master Gate and Full CI reds and ship sase v0.18.0 through ci\_watch

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1mk.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.land.md) · **Assignee:** `sase-1mk.9.land`
**Created:** 2026-10-18 16:47:59 EDT · **Closed:** 2026-10-19 09:09:30 EDT
**Plan:** [202610/ship\_v0\_18\_0\_post\_repair\_reds.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_post_repair_reds.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/ship_v0_18_0_post_repair_reds.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:9081ec33b5a3236258f4df39 | Release proof for the post-repair landing closeout. |
| related | file:explicit:f26a32de792db684b7c3d8bd | Final release proof for the post-repair landing closeout. |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_post_repair_reds.md

<!-- sase:links:end -->

## Description

sase 0.18.0 is on PyPI, published from release-please PR #299 after ci_watch merged it on a green Master Gate and a fresh green Full CI, with sase-core-rs 0.42.0 published as its core floor. The release is confirmed before landing and recorded in an evidence artifact by the final epic lander, and parent epic sase-1mk is resumed and closed.

## Notes

[2026-10-19T03:42:02Z · sase-1mk.9.6--1] Release-watch closeout for sase-1mk.9.6: verdict FULL_CI_RED (watcher exit 10; monitor outer exit 0). Verdict file: /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202610/18/20261018191228/diagnostics/release_verdict.md. Full CI run 39187446189 on dd963c0fa64a failed full/test on 3.12/3.13/3.14, so sase 0.18.0 was not released (PyPI absent); sase-core-rs 0.42.0 was already on PyPI. Last state line: 2026-10-19T03:36:08Z stage=watch pypi=absent release_pr=#299:open full_ci=39187446189:failure:dd963c0fa64a master_gate=39185847786:failure:dd963c0fa64a publish=39175545978:success core_pypi=0.42.0@2026-10-18T17:18:53Z core_pr=off action=verdict:FULL_CI_RED. Phase bead sase-1mk.9.6 already closed canceled (release not confirmed: FULL_CI_RED); no re-close needed.

[2026-10-19T03:53:35Z · sase-1mk.9.land] LANDING STEP 1-2 + FOLLOW-UP TRIAGE (sase-1mk.9.land, 2026-10-19 ~03:55Z). Release NOT confirmed: watch sase-1mk.9.6 ended FULL_CI_RED (exit 10). PyPI still has sase 0.17.1 and no 0.18.0. PR #299 is OPEN/MERGEABLE/CLEAN at head d797ec0233. sase-core-rs 0.42.0 is on PyPI.
INTEGRATION AUDIT: every phase change is on origin/master dd963c0fa6 and none was reverted: 9.1 research 43e9066b, 9.2 b68b5166ad, 9.4 7f3c8d0965, 9.5 e5c02dc8a4, 9.3 f457166f4a. Full CI 39187446189 at dd963c0fa6 passed lint (research README healed), visual-test (JUMP golden healed), perf-floors, tutorial-tests, ace-page-group-isolation and build-core. No link-follow, New Project, known-continuation or provider-drain node failed there or in any Master Gate since.
Concurrent commits since the epic started: fa1b12db27 (agent-cli), 5fe54b5974 + dd963c0fa6 (core pin to 6a626d10, stats counter=sloc) and 1276b73b8b (procs hue). None conflicts with the epic or duplicates it. The pin bump stays compatible with the 0.42.0 floor: v0.42.0 already has the 'sloc' wire value, and the core diff v0.42.0..6a626d10 adds no pyfunctions and no Python-consumed wire fields.
SOLE REMAINING BLOCKER, CAUSED BY THIS EPIC: e5c02dc8a4 (phase sase-1mk.9.5) moved write_done_marker_and_update_index and write_error_done_marker from open/json.dump to write_json_marker_atomic. That deterministically fails 4 marker-audit nodes in tests/test_agent_artifact_marker_mutation_audit.py (3) and tests/test_agent_artifact_marker_path_passing_audit.py (1) in every Master Gate since 39169961708 (shards 6/7) and every Full CI test leg since (39172267490, 39178872128, 39187446189; 4 failed / ~56,349 passed per leg). Reproduced locally at dd963c0fa6. Task sase-1mt tracks it; it is epic work, so the nested repair epic owns it outright.
epic-symbols: none.
FOLLOW-UP TRIAGE:
(1) 9.2 #1 test_sigterm_leaves_run_running -> +1 sase-1fi.
(2) 9.2 #3 test_blocked_render_is_bounded... -> +1 sase-xo.
(3) 9.3 #1 test_ace_page_restores_fast_startup_overrides_after_success -> +1 sase-1kf.
(4) 9.3 #3 marker-mutation audit failures (proposed against sase-zi) -> declined as a follow-up. It is caused by epic phase 9.5 and owned by the nested repair epic via sase-1mt. sase-zi is a different, already-fixed tuple.
(5) 9.3 #4 test_existing_typeahead_seeds_finder_query NoMatches (Full CI 39164596460 job 117787890929) -> new flake task sase-1mu (large).
(6) 9.3 #6 New Project owner switch -> declined: phase sase-1mk.9.4 (7f3c8d0965) fixed it and no CI since has failed the node.
(7) 9.5 #1 helper_error in test_agent_run_continues_past_all_known_stage -> +1 sase-1k8.
Not a blocker: the Full CI 3.12 leg ran 83-93 min against its 120-min timeout (sase-v8 margin).

[2026-10-19T03:57:11Z · sase-1mk.9.land] ADDITIONAL LANDER FOLLOW-UP: filed bug task sase-1mv (medium). The scoped 'sase tool run check' never selects the source-scanning marker AST audits: there is no import edge, and they are outside the 30 s contract set. That is how e5c02dc8a4 passed its scoped check and still reddened Master Gate and Full CI. The gap predates this epic, so it is a separate task. The nested repair epic fixes only the catalog drift (sase-1mt).

[2026-10-19T03:58:30Z · sase-1mk.9.land] NESTED REPAIR EPIC (Landing step 3, repair path for FULL_CI_RED): proposing child epic plan 'Repair the marker-audit catalog drift from e5c02dc8a4 and ship sase v0.18.0 through ci_watch' with parent_bead sase-1mk.9. The child owns two phases outright. (1) marker-audit (small): teach the marker mutation/path-passing AST audits about write_json_marker_atomic and review write_done_marker_and_update_index and write_error_done_marker, resolving task sase-1mt and all 4 failing nodes. (2) watch (small): the verbatim Phase watch and close table. Its Landing section is this epic's Landing, copied verbatim. This epic stays open, with no close, symvision pass or plan status change. The child's lander resumes this Landing at step 4 through parent_bead after it confirms the release.

[2026-10-19T13:09:30Z · sase-1mk.9.7.land] PARENT LANDING COMPLETE: Re-read this epic and every direct phase note, the canceled watch verdict, and the linked plan. Phases 9.1-9.5 are done, 9.6 remains historically canceled, and nested release repair 9.7 closed normally after all release obligations passed. Release evidence: file:explicit:f26a32de792db684b7c3d8bd. PR #299 and sase v0.18.0 are published; core v0.42.1 is published; Full CI, Master Gate, Publish and fresh install passed; final sase tool run check passed. The marker-audit repair is on origin/master. Follow-ups remain accurately scoped: 1mv and v8 are open, l8/1ky were not falsely closed, and 1i5.9.1/1jz retain their independent scope. All stale 1lh/1kx/1c1 release chains were superseded. No symbols remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.9.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.land.md) | [sase-1mk.9](sase-1mk.9.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1mk.9.2][1] | Need parent epic DECISIONS and phase context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.9.2/README.md

<!-- sase:referenced-by:end -->
