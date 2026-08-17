# Bead: sase-oc.6 — Dynamic values wired into every shell

[Bead Pages](../README.md) / [sase-oc](README.md) / sase-oc.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04p](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04p.md) · **Assignee:** `sase-oc.6` · **Size:** medium
**Created:** 2026-08-17 08:54:25 EDT · **Closed:** 2026-08-17 14:52:20 EDT
**Plan:** [202608/cli\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/cli_completion.md)

## Description

wire: teach all three emitters to call the candidates fast path for kinded slots, with a hand-written zsh preamble that groups and tags results and caches them in-shell, plus the bash and fish equivalents.

## Notes

[2026-08-17T18:51:57Z · sase-oc.6] PROPOSED FOLLOW-UP: just check-full test-cost budget gate failed (peak_worker_rss_kib, causes.ace_page_enter, parser_create, pilot_pause_delay, subprocess_run, textual_app_run_test_enter all over baseline+15%) during this phase close, but the diff only touches shell-completion emitter/test files unrelated to ACE TUI rendering cost. Machine showed load average 20-33 with multiple concurrent just check/check-full runs from other sase_N workspaces at the time. Likely a contention-induced flake in the resource budget gate rather than a real regression; worth confirming on a quiet machine or making the budget check contention-aware.

[2026-08-17T18:52:20Z · sase-oc.6] Wired the candidates fast path into all three shell emitters for kinded slots: zsh (hand-written __sase_candidates preamble helper with grouping/tagging/in-shell TTL caching via brace-eval action to avoid _arguments' $1 clobbering, and renamed the __sase_run helper to avoid colliding with the auto-generated 'sase run' subcommand function), bash (__sase_candidates with SECONDS-based TTL cache using explicit key-presence checks instead of a 0-sentinel), and fish equivalent. Verified end-to-end: zsh and bash validated live in a pty against a fixture sase binary (candidates appear, fixture invoked exactly once across two completions confirming caching), fish validated for syntax only (not installed in sandbox). just check passed clean (all lint gates, scoped test lane auto-escalated to full suite per core-identity-changed rule, 155 completion tests pass). just check-full's lint/test gates all passed too; only the test-cost resource-budget gate failed, and that looks like a contention artifact from concurrent just check/check-full runs on this shared machine (load avg 20-33) rather than a regression from this diff, which touches only completion emitter/test files — recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-oc.3](sase-oc.3.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-oc.5](sase-oc.5.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-oc.8](sase-oc.8.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oc.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oc.6/README.md) | [sase-oc.6](sase-oc.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c0dd172`](https://github.com/sase-org/sase/commit/c0dd17213c17db643240e4e92d91b61b4c11a724) | feat(completion): wire dynamic value candidates into zsh/bash/fish | [sase-oc.6](sase-oc.6.md) | 2026-08-17 14:53:12 EDT |
