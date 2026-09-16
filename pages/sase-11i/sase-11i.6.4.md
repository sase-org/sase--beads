# Bead: sase-11i.6.4 — Verify actual frontends, snapshots, and input latency

[Bead Pages](../README.md) / [sase-11i.6](sase-11i.6.md) / sase-11i.6.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11i.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11i.land.md) · **Assignee:** `sase-11i.6.4` · **Size:** medium
**Created:** 2026-09-16 00:36:16 EDT
**Plan:** [202609/finish\_argument\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_argument_highlighting.md)

## Description

real-parity: replace the synthetic LSP mapping check with real-server parity and complete visual and performance acceptance.

## Notes

[2026-09-16T06:56:33Z · sase-11i.6.4] PROPOSED FOLLOW-UP: TUI key-to-paint benchmark exceeds budgets on this host — `just test-slow tests/ace/tui/bench_tui_jk.py -s` failed 5/10 cases under 14 workers and `SASE_PYTEST_WORKERS=1 just test-slow tests/ace/tui/bench_tui_jk.py -s` still failed 4/10 with 250-375ms outliers.

[2026-09-16T06:56:35Z · sase-11i.6.4] PROPOSED FOLLOW-UP: Visual PNG snapshot lane has broad renderer drift/noise in this workspace — `just test-visual` failed with 602 snapshot mismatches across unrelated UI areas (first mismatch 250/1,520,532 pixels), so visual acceptance could not be used without a renderer/snapshot triage pass.

## Dependencies

- **Depends on:** [sase-11i.6.2](sase-11i.6.2.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11i.6.3](sase-11i.6.3.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.6.4/README.md) | [sase-11i.6.4](sase-11i.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9da164c`](https://github.com/sase-org/sase/commit/9da164cb06b589e4aeb31e2c84ce225ba4d39c1b) | test(xprompt): verify real lsp argument parity | [sase-11i.6.4](sase-11i.6.4.md) | 2026-09-16 02:58:25 EDT |
