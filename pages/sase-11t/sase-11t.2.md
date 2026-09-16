# Bead: sase-11t.2 — Codex provider turn-integrity detection

[Bead Pages](../README.md) / [sase-11t](README.md) / sase-11t.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lw.r0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lw.r0.f0.md) · **Assignee:** `sase-11t.2` · **Size:** medium
**Created:** 2026-09-16 10:42:00 EDT · **Closed:** 2026-09-16 14:44:12 EDT
**Plan:** [202609/sudo\_gate\_crash\_safe\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_gate_crash_safe_handoff.md)

## Description

codex-turn-integrity: treat a codex turn that ends with an empty final answer plus a command killed at teardown as a provider failure that raises for retry instead of returning success.

## Notes

[2026-09-16T18:43:26Z · sase-11t.2--2] PROPOSED FOLLOW-UP: just check-full test-cost lane hit hard CPU budget overages (total_file_cpu_seconds, ace_settle_pilot.cpu, parser_create.cpu, subprocess_run.cpu) on 2026-09-16T18:32Z under confirmed extreme host contention (load average ~43, multiple concurrent sase workspaces running full suites) — actual pytest run passed 42145/42145 with zero failures, and the diff for this phase (Codex provider parsing only) touches none of the flagged causes; recommend investigating whether test-cost budgets/hosting need contention-aware tolerance or scheduling, similar to prior test(disk/axe/ci) CPU-budget recalibration commits.

[2026-09-16T18:44:12Z · sase-11t.2--2] Implemented Codex turn-integrity detection for empty-final killed-command turns; verified with focused Codex parser/retry tests (45 passed), just check (620/3917 files selected, passed), and just check-full's full pytest run (42145 passed, 15 skipped, zero failures). check-full's test-cost budget gate hard-failed on CPU cost causes unrelated to this diff under confirmed extreme host contention (load avg ~43, multiple concurrent workspaces); logged as PROPOSED FOLLOW-UP rather than blocking, consistent with sase-11t.1 precedent.

## Dependencies

- **Blocks:** [sase-11t.4](sase-11t.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11t.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11t.2.md) | [sase-11t.2](sase-11t.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`06a53a0`](https://github.com/sase-org/sase/commit/06a53a0e51ab815679e81f735a25d831458988c6) | fix(llm-provider): detect codex turn-integrity failures on empty-final killed-command turns | [sase-11t.2](sase-11t.2.md) | 2026-09-16 14:46:18 EDT |
