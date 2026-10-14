# Bead: sase-1kl.4 — Prove Full CI green, let ci\_watch merge PR 299, and verify v0.18.0 on PyPI

[Bead Pages](../README.md) / [sase-1kl](README.md) / sase-1kl.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.106](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.106.md) · **Assignee:** `sase-1kl.4` · **Size:** medium
**Created:** 2026-10-13 14:15:37 EDT
**Plan:** [202610/v0\_18\_0\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_unblock.md)

## Description

release: deploy the clock, drive Full CI to green on a tip with the fixes, triage any new reds, confirm ci_watch merges #299, dispatch Publish, verify the PyPI install, and prove the two-hour cadence.

## Notes

[2026-10-13T21:32:38Z · sase-1kl.4] Clock deploy: chezmoi 13164059 on remote and already live in ~/.config/sase/sase_athena.yml (heavy_dispatch_every_hours sase:2 present); bugyi-chops 5828753 on remote BUT primary checkout ~/projects/github/bbugyi200/bugyi-chops still at 285c5ad, so scheduled ci_watch runs pre-dispatcher code. USER ACTION NEEDED: git pull --ff-only in that checkout via /sase_gate (agents must not touch ~/projects). Do not block on it.

[2026-10-13T21:32:45Z · sase-1kl.4] Dispatched Full CI 38471336644 (workflow_dispatch) on fixed tip cf550a0e57 (test-flakes + visual-lane fixes); queued behind in-flight schedule run 38469604023 on 78e967bd in full-ci concurrency group. Master Gate 38469626121 in progress on cf550a0e57. PR #299 OPEN/MERGEABLE/UNSTABLE. Monitor handoff follows for Gate + Full CI completion.

[2026-10-14T03:53:03Z · sase-1kl.4--1] Triage 2026-10-14 (Full CI 38471336644 on cf550a0e57 = FAILURE; Master Gate 38469626121 = success). Monitor fze4qmnv7vpr was a no-op: its jq expression was malformed (\( .status) so it polled nothing for 4.5h; do not reuse that snippet. Full CI reds: (1) lint stale --epic-symbol sase-1kj.7 — already removed on master; (2) test_new_project_source filter test 5s timeout on py3.12/3.13 — root cause: unstubbed describe_repo_creation/probe_repo let an installed provider plugin pin a Create row that steals the highlight (reproduced by forcing describe_repo_creation to return a form); fixed by hermetic stubs in 3 tests; (3) test_launch_context_bar 'opus@xhigh' vs 'o3@high' (py3.13) — app LaunchContextSource late off-thread broadcast overwrote the test's explicit apply_launch_context (reproduced); fixed by silencing the source broadcast in _mounted_bar; (4) visual test_config_center_flags_narrow_png_snapshot SUNSET wait timeout — NOT reproducible (passes 15/15 incl. 12-way contention on 2 CPUs); CI log cut off the frame SVG, so wait_for_state now puts a plain-text frame before the SVG in its timeout message. Master Gate has been red since d69cd499dd/c5e4da7065 (sase-1ko work): lint private imports (_RunManifest, _render_sections_table) — fix was sitting uncommitted in this workspace and verified with symvision; test_delivery_plan stale patch target — fixed; test_cli_bare_git 'unknown provider git' on shard 4/8 gw0 — not reproducible locally (serial chunks and exact shard under -n 3), hardened tests to rebuild the real registry and assert git is present with the provider list in the message.

[2026-10-14T04:20:36Z · sase-1kl.4--1] REMAINING (bead kept open on purpose; release not proven): after the host commits this turn's CI-hardening fixes to master, (1) confirm Master Gate green at that exact HEAD (gh run list -R sase-org/sase --workflow 'Master Gate'); (2) gh workflow run full.yml -R sase-org/sase --ref master, then poll with a CORRECT jq (--jq '.status + ":" + (.conclusion // "")'; the earlier '\( .status)' form never parsed) via sase monitor, ~1h50m; (3) triage per plan Phase release step 3 — if the narrow flags visual test fails again its timeout message now carries last_frame_text; (4) when Full CI is green watch ci_watch for the guarded merge of PR 299 (never merge by hand; needs Gate green at exact HEAD and Full CI <=6h old); (5) gh workflow run publish.yml -R sase-org/sase -f publish_existing=false, monitor tag/build/smokes/upload; (6) verify PyPI JSON lists sase 0.18.0, fresh-venv pip install sase==0.18.0 pulls sase-core-rs 0.39.x, sase --version prints 0.18.0; (7) prove 3 consecutive master Full CI starts <=2h15m apart from the new clock. USER ACTION STILL PENDING: git -C ~/projects/github/bbugyi200/bugyi-chops pull --ff-only through /sase_gate so athena's ci_watch runs the heavy-dispatch code; until then GitHub's own schedule triggers Full CI (~3-9h gaps) and the cadence proof will fail. Note: master moves constantly (sase-1ko agents), so Gate-green-at-exact-HEAD for the merge may need a quiet window.

[2026-10-14T04:20:42Z · sase-1kl.4--1] PROPOSED FOLLOW-UP: bare-git 'unknown provider git' on Master Gate shard 4/8 (xdist gw0) — root cause unproven; tests now rebuild the registry and assert git is present, listing the registry in the message; if it recurs read that message to find the polluting test

[2026-10-14T04:20:47Z · sase-1kl.4--1] PROPOSED FOLLOW-UP: this athena host has a stale sase_core_rs binding that rejects manifest schema_version 2, so ~21 tests/instructions tests plus 14 scoped-lane tests (test_pooled_alias_single_consumption*, test_workflow_executor ShouldHitl x2, test_llm_provider_invoke shadow measurement, test_app_import_budget) fail identically on the clean base tree here; CI is unaffected. Fix the host with sase update / core rebuild rather than any test change (see stale-core-binding-crash memory)

[2026-10-14T04:20:52Z · sase-1kl.4--1] PROPOSED FOLLOW-UP: harden agent monitors against silent no-op polls — a monitor whose command prints only parse errors still exits 0 after its full budget (4h32m lost on fze4qmnv7vpr); consider failing monitors whose output never contains a state line, or a gh-run-wait helper that validates its query

## Dependencies

- **Depends on:** [sase-1kl.1](sase-1kl.1.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kl.2](sase-1kl.2.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kl.3](sase-1kl.3.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kl.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kl.4.md) | [sase-1kl.4](sase-1kl.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a835ca`](https://github.com/sase-org/sase/commit/1a835cad61e7c72bdb704123ee64075143147564) | fix(ci): make flaky New Project, launch-bar tests hermetic and clear Gate reds | [sase-1kl.4](sase-1kl.4.md) | 2026-10-14 00:21:51 EDT |
