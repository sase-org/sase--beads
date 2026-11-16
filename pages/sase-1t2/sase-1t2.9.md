# Bead: sase-1t2.9 — Hijack WAITING, QUEUED, and booting turns that hold a numbered workspace

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.9

**Status:** ◐ in_progress · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.9` · **Size:** medium
**Created:** 2026-11-15 20:00:11 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Previously Closed

> ↺ Closed 2026-11-16T09:31:52Z · done
>
> (none)
>
> Reopened 2026-11-16T09:37:46Z by an epic work preclaim

## Description

waiter_branch: allow WAITING/QUEUED/booting turns with a numbered claim (terminate the parked runner, or take the processless branch when it is dead), cancel the turn's own wait marker while waiters of it stay parked, redirect claimless %wait turns to kill-and-edit with a reason, and make Continue relaunch a turn that never reached its provider.

## Notes

[2026-11-16T09:31:52Z · sase-1t2.9] Implemented claim-backed hijacks for WAITING, QUEUED, and booting turns, including processless custody, wait-marker cancellation, claimless kill-and-edit redirect, and unstarted Continue prompts. Verified Python/Rust formatting, clean diff checks, and no remaining epic symbols. Primary just fmt stopped at generated docs because sase_core_rs was unavailable; no tests were run.

[2026-11-16T09:37:46Z · sase-1t2.9] STITCH FAILED: host finalization failed (stitch_failed) for run 20261115200202 (sase-1t2.9); reopening this run's still-current done closes.
Repositories without landing proof: main (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22; no landing marker).
Preserved commit-message paths: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.sase/finalizers/commit-message-499917-1794821710923904197.txt; /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.sase/finalizers/commit-message-499917-1794821829592356212.txt.
Failure evidence: sase stitch create failed for main: stdout: ℹ️ Bead sase-1t2.9 is already closed; explicit -B close is idempotent.
🔄 Running before commit hook: sase_git_fix
ℹ️ Before commit hook evidence: 
/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/15/2026111
5200202/commit_hooks/20261116T093723.463761Z.before.f857384cb380.326904.f5ae53a6
.json
❌ Before commit hook failed (exit 1): sase_git_fix
⚠️ Before commit hook evidence: 
/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/15/2026111
5200202/commit_hooks/20261116T093723.463761Z.before.f857384cb380.326904.f5ae53a6
.json | stderr: Local commands in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/sase.yml were skipped (no-acknowledgment); run `sase config trust allow /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/sase.yml` after review.
---- before commit hook output tail ----
[stdout]

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
13552 files left unchanged

---------- Fixing Python with ruff... ----------
All checks passed!

---------- Rendering generated docs... ----------

---------- Rendering sase-backed docs... ----------
[stderr]
.venv-format/bin/ruff format src/ tests/
.venv-format/bin/ruff check --fix src/ tests/
.venv-format/bin/python tools/render_docs --format-only
.venv/bin/python tools/render_docs --sase-only
[render_docs] keymap-macro-reference: sase_core_rs is not importable in this environment but is a hard runtime dependency of sase; run `just install-venv` in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22.
error: recipe `docs-gen` failed on line 573 with exit code 1
---- end before commit hook output ----
Commit message preserved at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/.sase/finalizers/commit-message-499917-1794821829592356212.txt — re-run with the same -M flag after fixing..
Hook output tail: [stdout]

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
13552 files left unchanged

---------- Fixing Python with ruff... ----------
All checks passed!

---------- Rendering generated docs... ----------

---------- Rendering sase-backed docs... ----------
[stderr]
.venv-format/bin/ruff format src/ tests/
.venv-format/bin/ruff check --fix src/ tests/
.venv-format/bin/python tools/render_docs --format-only
.venv/bin/python tools/render_docs --sase-only
[render_docs] keymap-macro-reference: sase_core_rs is not importable in this environment but is a hard runtime dependency of sase; run `just install-venv` in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22.
error: recipe `docs-gen` failed on line 573 with exit code 1.
Evidence locations: /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/15/20261115200202; /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/15/20261115200202/final_declaration_recovery_evidence.md; /home/bryan/.sase/projects/gh_sase-org__sase/rescue/202611/20261116T093745Z-ws22-main-3aaaaab6064c/manifest.json.
Bead: sase-1t2.9
Close event: sase-1t2:000099:issue_closed:sase-1t2.9:7f096b9a9c55e988d6389385049edf68e313a35c1f27672c7939ff1d7fcb8fcb

[2026-11-16T11:04:31Z · sase-1t2.9] PROPOSED FOLLOW-UP: Fix pre-existing sase-core Clippy needless_bool errors — sase tool run check failed identically on the changed tree (e7da0ea2a052e5cb4a97993217cea33e) and clean base 20b8133e (a8c883da6ae8f249f057b8d18f8d18bd): plan/decisions/grammar.rs:900, prompt_prediction/tokenize.rs:514 and :838, tool_run/store/demand.rs:47. Rust 1.100 Clippy denies these warnings before tests; this phase changes only hijack tests in sase-core.

## Dependencies

- **Blocks:** [sase-1t2.13](sase-1t2.13.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.7](sase-1t2.7.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.9/README.md) | [sase-1t2.9](sase-1t2.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@20b8133`](https://github.com/sase-org/sase-core/commit/20b8133ea3e82a852ccd17a2228820c6a1c97160) | feat(agent-hijack): add pre-provider decisions | [sase-1t2.9](sase-1t2.9.md) | 2026-11-16 04:34:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.9][1] | Reconfirm phase scope and notes before closing the completed implementation | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.9/README.md

<!-- sase:referenced-by:end -->
