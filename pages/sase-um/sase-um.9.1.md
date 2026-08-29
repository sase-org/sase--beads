# Bead: sase-um.9.1 — Scope ci\_watch's release-gate variables per repository

[Bead Pages](../README.md) / [sase-um.9](sase-um.9.md) / sase-um.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.land.md) · **Assignee:** `sase-um.9.1` · **Size:** large
**Created:** 2026-08-28 15:48:58 EDT · **Closed:** 2026-08-28 16:24:30 EDT
**Plan:** [202608/release\_gate\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_completion.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-ve][1] | proposed by phase note #1 while validating ci_watch rollout; unrelated to the phase's per-repo config change |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-ve/README.md

<!-- sase:links:end -->

## Description

chopscope: make ci_watch's merge_method, gating_workflows, heavy_workflows, and heavy_max_age_hours resolvable per repository instead of chop-global, release bugyi-chops, roll the chezmoi config forward, and prove sase-telegram PR #21 and sase-github stop reporting gating_workflow_missing.

## Notes

[2026-08-28T20:17:42Z · sase-um.9.1] PROPOSED FOLLOW-UP: source-env chop doctor Telegram script gap — after installing bugyi-chops 0.9.0 into the source SASE venv, `sase axe chop doctor` still exits ERROR because configured telegram chops `sase_chop_tg_inbound` and `sase_chop_tg_outbound` are not installed in that same venv; ci_watch itself resolves and the dry-run tick succeeds.

[2026-08-28T20:18:11Z · sase-um.9.1] PROPOSED FOLLOW-UP: bugyi-chops default dev env depends on unreleased/current SASE behavior — plain `just check` with PyPI `sase==0.16.0` fails existing toobig typed-launch tests because that package lacks `sase.feature_flags` and `PromptDirectives.if_code`; the source-SASE env passes, so publish/order the matching SASE runtime or ratchet the bugyi-chops dependency before PyPI release.

[2026-08-28T20:24:30Z · sase-um.9.1] Auto-closed by `sase stitch create` after create_commit landed c3d613d ("feat(ci-watch): scope release gates by repository"). No verification is implied by this note. Reopen with `sase bead open sase-um.9.1`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.1.md) | [sase-um.9.1](sase-um.9.1.md) | 0 |
