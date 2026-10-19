# Bead: sase-1mk.9.7 — Repair the marker-audit catalog drift from e5c02dc8a4 and ship sase v0.18.0 through ci\_watch

[Bead Pages](../README.md) / [sase-1mk.9](sase-1mk.9.md) / sase-1mk.9.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1mk.9.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.land.md) · **Assignee:** `sase-1mk.9.7.land`
**Created:** 2026-10-19 00:00:08 EDT · **Closed:** 2026-10-19 09:06:44 EDT
**Plan:** [202610/ship\_v0\_18\_0\_marker\_audit\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_marker_audit_repair.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/ship_v0_18_0_marker_audit_repair.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:2c733ef64a6321897a4a45cf | independent 0.18.0 public-install proof; does not close this epic |
| related | file:explicit:588c932adae1aadce88ef449 | attached via sase artifact create --bead |
| related | file:explicit:9081ec33b5a3236258f4df39 | attached via sase artifact create --bead |
| related | file:explicit:f26a32de792db684b7c3d8bd | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_marker_audit_repair.md

<!-- sase:links:end -->

## Description

sase 0.18.0 is on PyPI, published from release-please PR #299 after ci_watch merged it on a green Master Gate and a fresh green Full CI, with sase-core-rs 0.42.0 published as its core floor. The release is confirmed before landing and recorded in an evidence artifact by the final epic lander, and ancestor epics sase-1mk.9 and sase-1mk are resumed and closed.

## Notes

[2026-10-19T11:39:41Z · sase-1mk.9.7.2--1] Release-watch closeout for sase-1mk.9.7.2: verdict INSTALL_FAILED (watcher exit 14); verdict file /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202610/19/20261019010106/diagnostics/release_verdict.md; last state 2026-10-19T11:33:21Z stage=watch pypi=present release_pr=#299:merged full_ci=39229885153:success:850b9fdfcb8e master_gate=39241660845:None:4b7b98153227 publish=39242329155:success core_pypi=0.42.1@2026-10-19T05:52:27Z core_pr=off action=verdict:INSTALL_FAILED. Note: PyPI 0.18.0 present, core 0.42.1 present, PR #299 merged, publish run 39242329155 success; bead sase-1mk.9.7.2 already closed canceled (INSTALL_FAILED) by watcher at 11:33:27Z — closeout left it closed. The install-proof failure looks like a bad probe (bare sase --version exits 2 requiring a command), not a missing release.

[2026-10-19T11:50:06Z · sase-1mk.9.7.land] LANDING AUDIT / FOLLOW-UP TRIAGE (2026-10-19): Read epic and all five child notes, linked plan, commit 850b9fdfcb, current writer/scanner code, and all master commits since epic creation. Marker repair is correct: atomic helper is visible to the mutation audit, both done writers retain immediate index updates, and the inline error-marker path has specific lifecycle coverage. Fresh audit/completion/provider-drain verification: 15 passed in 45.68s at 4b7b981532. No epic-symbol entries. Drift is c2cbd80f1c (triage-test split, no conflict) plus release metadata commits cde1dff6fb/97f5e75f47/4b7b981532 (0.18.0 and core floor >=0.42.0,<0.43.0); none undoes the repair. DECISIONS inherited from sase-1mk remain core_cut=yes and stale_epics=supersede. The watcher honored core_cut and its close-on-every-outcome contract. RELEASE EVIDENCE: PR #299 merged 2026-10-19T11:01:45Z by bbugyi200 at 4b7b981532; GitHub release v0.18.0 exists; Publish 39242329155 succeeded in release/build/install-smoke/install-smoke-core-floor/publish; Full CI 39229885153 was green at 850b9fdfcb, updated 10:58:47Z, and Master Gate 39237716543 was green at pre-merge tip c2cbd80f1c. REMAINING EPIC WORK: watcher install_attempt calls unsupported sase --version in both uv and pip branches (lines 885/911), and its lifecycle test mocks that invalid CLI as successful. The real parser exposes sase version [--json]. This produced INSTALL_FAILED despite publication. Repair the probe, prove the published install, assemble the required release evidence and finish the documented closeout. Do not treat canceled watch as release proof or rewrite its historical resolution. ONE PROPOSED FOLLOW-UP: sase-1mk.9.7.1 note #2 was routed through /sase_new_task to existing sase-120 with +1 (now +17), relaying ToolRun e996bbfb6e8d632139c7686cc9268d44 FLAKY 180-second nested-pytest timeout; no fresh reproduction claimed. Searched all-status flake tasks, swept recent tasks, and reviewed active-epic scopes; no demonstrated causal epic link. No duplicate created, no proposal declined. The unsupported probe is retained as release-epic work, not a separate task. A medium tale will own repair and this epic closeout in one coder turn, followed by readiness-gated parent-plan closeout of sase-1mk.9 and sase-1mk; no wait for its own future commit/push/CI.

[2026-10-19T11:52:40Z · sase-1mk.9.7.land] REMAINING-WORK TALE: sase_plan_release_probe_and_finish_landing.md passed both --explain validation and plain revalidation with zero warnings. It is tier=tale, size=medium: one coder repairs uv/pip install proof to invoke sase version --json and match the host distribution exactly, checks the configured installed-core minimum (currently merely recorded; existing test uses core 0.40.1), adds regression coverage, runs just check, proves the published release, records one evidence artifact, completes task/stale-chain dispositions, closes sase-1mk.9.7 normally, runs symvision, marks its plan done, and independently rechecks/closes only fully complete direct plan ancestors sase-1mk.9 and sase-1mk. The coder must finish landing without waiting for its own future commit, push, or CI. Source repair and release proof remain pending; no successful epic/ancestor close is claimed in this planning turn. Follow-up triage is already complete in the preceding landing note.

[2026-10-19T12:15:22Z · 11n--2] Independent public-release proof for this tale (plan:202610/complete_v0_18_0_release.md), not a close of this epic. PyPI sase 0.18.0 wheel+sdist match tag 4b7b981532 (hashes 398ae5ac… / 6fc09147…). Publish 39242329155 succeeded. Watcher INSTALL_FAILED is the unsupported sase --version probe; sase version -j works on the published wheel. Linux family install this turn: sase 0.18.0 + core 0.42.1 + github 0.2.24 + telegram 0.4.29. Documented install-smoke 39250237504 succeeded on e5f2d768ea after isolating doctor. Leak sase-1kf closed at origin SHA e5f2d768ea. Master Gate 39248628383 success on that SHA. macOS family install succeeded earlier this plan (file:explicit:c1427b09af24705a0b19d2dd); this-turn SSH to tailnet mac timed out. This tale is not closing sase-1mk.9.7 or rewriting the canceled watcher resolution.

[2026-10-19T12:38:45Z · sase-1mk.9.7.land] DISCOVERED ISSUE: Release publication and its install-smoke/install-smoke-core-floor jobs passed, and a clean PyPI venv verified sase 0.18.0 with sase-core-rs 0.42.1. Separate documented workflow run 39243855540 installed successfully but `sase doctor -j` exited 1 from the sase checkout on expected plugins.required and unconfigured llm.default/config.init checks. This is the workflow-contract gap already raised by sase-1le.3, not an install or resolver failure; keep the workflow repair and re-dispatch as separate follow-up. Evidence: file:explicit:588c932adae1aadce88ef449.

[2026-10-19T12:50:37Z · sase-1mk.9.7.land] FINAL VERIFICATION AND EVIDENCE UPDATE: ToolRun e5db254ed09efda1dd895042cec8382c (`sase tool run check`) succeeded with exit 0; all lint, validation, committed-plan, documentation, and scoped-test stages passed, with scoped tests in 13m26s. The final evidence supplement supersedes the earlier draft: file:explicit:9081ec33b5a3236258f4df39.

[2026-10-19T12:55:05Z · sase-1mk.9.7.land] INSTALL-SMOKE FOLLOW-UP UPDATE (2026-10-19): The earlier documented run 39243855540 failed only in the broad checkout doctor step. `origin/master` e5f2d768ea subsequently isolated SASE_HOME and narrowed the check to llm.default; documented install-smoke run 39250237504 succeeded. This resolves the workflow-contract follow-up; no new task remains open. Final evidence supplement: file:explicit:f26a32de792db684b7c3d8bd.

[2026-10-19T13:06:44Z · sase-1mk.9.7.land] LANDED: the install watcher now uses absolute-venv {
  "packages": [
    {
      "code_directory": "/home/bryan/projects/github/sase-org/sase/src/sase",
      "display_version": "0.17.1+2688.g850b9fdfc",
      "distribution_location": "/home/bryan/.local/share/uv/tools/sase/lib/python3.14/site-packages",
      "distribution_version": "0.17.1",
      "git": {
        "commit": "850b9fdfcb8e691ecf9c19926535439e84e003d8",
        "dirty": false,
        "distance": 2688,
        "root": "/home/bryan/projects/github/sase-org/sase",
        "short_commit": "850b9fdfc",
        "tag": "v0.17.1"
      },
      "import_module": "sase",
      "import_path": "/home/bryan/projects/github/sase-org/sase/src/sase",
      "install_type": "editable",
      "name": "sase",
      "plugin_signals": [],
      "role": "host",
      "source_root": "/home/bryan/projects/github/sase-org/sase",
      "source_version": "0.17.1",
      "warnings": []
    },
    {
      "code_directory": "/home/bryan/projects/github/sase-org/sase-core",
      "display_version": "0.42.1",
      "distribution_location": "/home/bryan/.local/share/uv/tools/sase/lib/python3.14/site-packages",
      "distribution_version": "0.42.0",
      "git": {
        "commit": "753fa21aa5b1d042d23112c04d30b0acd4159970",
        "dirty": false,
        "distance": 0,
        "root": "/home/bryan/projects/github/sase-org/sase-core",
        "short_commit": "753fa21aa",
        "tag": "v0.42.1"
      },
      "import_module": "sase_core_rs",
      "import_path": "/home/bryan/projects/github/sase-org/sase-core/crates/sase_core_py/python/sase_core_rs",
      "install_type": "editable",
      "name": "sase-core-rs",
      "plugin_signals": [],
      "role": "core",
      "source_root": "/home/bryan/projects/github/sase-org/sase-core",
      "source_version": "0.42.1",
      "warnings": []
    },
    {
      "code_directory": "/home/bryan/projects/github/sase-org/sase-github/src/sase_github",
      "display_version": "0.2.24+1.g8712c153a",
      "distribution_location": "/home/bryan/.local/share/uv/tools/sase/lib/python3.14/site-packages",
      "distribution_version": "0.2.24",
      "git": {
        "commit": "8712c153aa969eef55bccbabe2e0e94a50764a68",
        "dirty": false,
        "distance": 1,
        "root": "/home/bryan/projects/github/sase-org/sase-github",
        "short_commit": "8712c153a",
        "tag": "v0.2.24"
      },
      "import_module": "sase_github",
      "import_path": "/home/bryan/projects/github/sase-org/sase-github/src/sase_github",
      "install_type": "editable",
      "name": "sase-github",
      "plugin_signals": [
        "distribution_name:sase-github",
        "entry_point:sase_config:sase_github=sase_github",
        "entry_point:sase_macros:sase_github=sase_github",
        "entry_point:sase_task_types:github=sase_github.task_types:GITHUB_TASK_TYPES",
        "entry_point:sase_vcs:github=sase_github.plugin:GitHubPlugin",
        "entry_point:sase_workspace:github=sase_github.workspace_plugin:GitHubWorkspacePlugin",
        "entry_point:sase_xprompts:sase_github=sase_github"
      ],
      "role": "plugin",
      "source_root": "/home/bryan/projects/github/sase-org/sase-github",
      "source_version": "0.2.24",
      "warnings": []
    },
    {
      "code_directory": "/home/bryan/projects/github/sase-org/sase-listen/src/sase_listen",
      "displ

… and 31004 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.9.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.7.land.md) | [sase-1mk.9.7](sase-1mk.9.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`41b0a73`](https://github.com/sase-org/sase/commit/41b0a73b069f0b50fa61aa16d566460c17aab528) | fix(release-watch): verify installed release inventory | [sase-1mk.9.7](sase-1mk.9.7.md) | 2026-10-19 09:15:15 EDT |
| sase--plans | [`sase--plans@8b79b1a`](https://github.com/sase-org/sase--plans/commit/8b79b1ada8e688254333e01c7ff8a7ca599edb4d) | docs(plans): mark release landing plans complete | [sase-1mk.9.7](sase-1mk.9.7.md) | 2026-10-19 09:17:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1mk.9.7.1][1] | Need epic DECISIONS before editing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.9.7.1/README.md

<!-- sase:referenced-by:end -->
