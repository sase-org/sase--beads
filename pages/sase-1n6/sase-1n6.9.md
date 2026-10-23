# Bead: sase-1n6.9 — Cut releases over to release.yml and hand merges to the steward

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.9` · **Size:** medium
**Created:** 2026-10-19 16:40:09 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

handover: release-please goes draft with forced tags, publish.yml keeps only release-please and metadata sync, the steward goes live, ci_watch drops sase releases, and a gate hands over merge authority.

## Notes

[2026-10-20T05:59:54Z · sase-1n6.7.1.land] HANDOVER from child epic sase-1n6.7.1 (observe-only release steward), recorded by its land agent 2026-10-20. Scheduled-run URLs and the closing verification follow in the sase-1n6.7.1 close note.
1) Merge-authority switch: repository variable RELEASE_STEWARD_MERGE_ENABLED. Only the literal `true` enables merges; missing or any other value means disabled (tools/_release_watch.py MERGE_AUTHORITY_ENV, passed through .github/workflows/release-steward.yml). The parent plan's handover text says `RELEASE_STEWARD_MERGE`; the landed contract is RELEASE_STEWARD_MERGE_ENABLED, so the handover gate must use `gh variable set RELEASE_STEWARD_MERGE_ENABLED --body true -R sase-org/sase`.
2) Live mutation: release-steward.yml's schedule always runs `tools/release_watch --tick --json` WITHOUT --live. Only a workflow_dispatch with the boolean input live=true passes --live. "The steward goes live" therefore requires a workflow change in handover: let scheduled ticks pass --live, or add a separate switch. Merge authority stays a separate variable.
3) Credential and scope probe: the job's GITHUB_TOKEN has only contents: read. All GitHub reads and actions use GH_TOKEN=secrets.SASE_RELEASE_TOKEN. The health reader's read-only sase-core Actions probe (ReleaseHealthReader.read_core_actions_access) passed with local interactive gh, and scheduled runs exercise it with SASE_RELEASE_TOKEN. Never probed, so list them in the handover gate: workflow-dispatch WRITE on sase-org/sase (release.yml, publish.yml) and sase-org/sase-core (release-plz.yml); actions:write for job reruns; pull-request merge; issue/label/comment write for the escalation sink; release-asset upload plus title edit for abandonment.
4) Observed live state (read-only `--once --json` on master e10fa95c0d, 2026-10-20 ~05:55 UTC, exit 0, 2m39s):
   - primary: core_lag, pin e0ddc100eb32097393daa0fd099b3017b1b1cfee;
   - train_action: dispatch_core_cut, already_satisfied ("applicable core cut already completed");
   - escalation: open install_broken linux (immediate) was proposed and NOT executed;
   - secondary: install_broken linux and macos. No scheduled install-smoke run has produced install-canary-* artifacts yet; its cron is 07:26 UTC.
5) Reader API for metrics (sase-1n6.8), all read-only:
   - ReleaseFactsReader in tools/_release_watch_facts.py: read_runs(workflow, since=, until=, branch=, include_jobs=), read_releases(since=, until=), read_tags, read_publication_history(since=, until=), read_jobs(run_id, attempt), read_ref_sha, read_source_pin, read_repository, collect_snapshot. Bounds are explicit and pagination is complete.
   - ReleaseHealthReader in tools/_release_watch_health.py: read_core_ensure, read_core_facts, read_canary, read_issues, read_core_actions_access.
   - Transports: GithubTransport and PypiTransport in tools/_release_watch_transport.py.
6) Obsolete docs (proposed by sase-1n6.7.1.5; per the child plan they belong to handover):
   - docs/contribute/rust-backend.md, "Watching a release" (about lines 751-877), still documents the removed `--version`, `--fixed-sha`, `--dry-run`, `-n/--no-dispatch` and `--close-bead`, the polling/finalization semantics, and the deleted _release_watch_api.py and _release_watch_engine.py.
   - The current CLI is --once/-o (default, read-only), --tick/-t [--live/-l], --json/-j, --until-released/-u [VERSION] with --deadline/-d and --poll/-p, and --repo/-r.
   - No other callers of the old flags remain in sase or chezmoi.

[2026-10-20T15:50:19Z · sase-1n6.7.1.land--6] HANDOVER — scheduled Release steward observation proof (2026-10-20 UTC).

Scheduled runs, both completed successfully on master:
- https://github.com/sase-org/sase/actions/runs/39407994122 (head e10fa95c0dec856fe1cc0426bfb35fac1f0834a8): invoked --tick --json without --live; typed result release_watch: core_lag, primary pin dd817d5679409aaa2eefa0c3e517e8cfe91c37ef, train_action disposition already_satisfied, escalation disposition proposed. No action had executed.
- https://github.com/sase-org/sase/actions/runs/39447512070 (head 9ecb80cf0e2f374e36345dd6b94eed5db03c6699): invoked --tick --json without --live; typed result release_watch: core_cut_red (CORE_CUT_RED check=release-plz run=unknown attempt=1), with no train or escalation action.

The run-head workflow sources gate --live to workflow_dispatch with live=true. At both run heads, release_watch appends the ## Release steward summary; the schedule path reports Live mutations: no. The SASE_RELEASE_TOKEN is supplied as GH_TOKEN. The mandatory core_actions_access probe reads sase-core Actions, and the typed outcomes were not BROKEN(core_actions_access); therefore the read-only core Actions access probe passed. This establishes read access only; workflow-dispatch permission was not tested.

Read-only checks found no release-steward issues and no workflow_dispatch runs for release.yml or publish.yml in sase, or release-plz.yml in sase-core, during the scheduled observation window (2026-10-20 10:26:51–15:34:36 UTC). No remote mutation was observed.

Landing evidence: sase-core check passed (ToolRun 8a4be3d1be5ee56baa180c72f255fc3e). The primary check (ToolRun 7eaf7837d9cc9d39ea99f2d13c97cfb7) stopped on unrelated full-suite terminal/renderer/TUI failures; the focused 21-test run for those cases passed. The live read-only --once --json result is retained at file:explicit:fb884a84728efd9ed363ab97 (exit 0, core_lag). Existing handover note #1 already records ReleaseFactsReader/ReleaseHealthReader APIs and the obsolete Watching a release documentation that sase-1n6.9 owns.

## Dependencies

- **Blocks:** [sase-1n6.10](sase-1n6.10.md) ◐ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.6](sase-1n6.6.md) ◐ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.7](sase-1n6.7.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.8](sase-1n6.8.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.9/README.md) | [sase-1n6.9](sase-1n6.9.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:13d][1] | Research which agents stalled the sase-1n6 epic: in-progress phases | 1 |
| read-by | [agent:research.2a.cld][2] | E3 readiness: E2 status | 1 |
| read-by | [agent:research.2a.grk][3] | Need remaining open E2 phase statuses and blockers before designing E3 | 1 |
| read-by | [agent:research.2a.mus][4] | E3 readiness: remaining E2 phases status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.13d/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.grk/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.mus/README.md

<!-- sase:referenced-by:end -->
