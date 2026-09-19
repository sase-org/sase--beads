# Bead: sase-133.1 — Owner served-set parity

[Bead Pages](../README.md) / [sase-133](README.md) / sase-133.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0na](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0na.md) · **Assignee:** `sase-133.1` · **Size:** large
**Created:** 2026-09-18 16:37:58 EDT · **Closed:** 2026-09-18 17:40:28 EDT
**Plan:** [202609/remote\_dispatch\_agents\_tab\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_agents_tab_parity.md)

## Description

owner-served-set-parity: make the gateway snapshot serve exactly the rows the owner's own TUI presents — retire dead-PID protected waiting rows, honor owner dismissal state, and harden liveness beyond bare kill(pid,0) — with the selection decision unit-tested in sase_core.

## Notes

[2026-09-18T21:39:10Z · sase-133.1] Rule choices: dismissal is evaluated before protection/liveness, so a resolved owner dismissal excludes the candidate even when it still looks protected, alive, or unknown. Waiting/question protection keeps only Alive/Unknown rows current; a protected Dead/NotProcess row takes the same bounded seven-day/200-row terminal path as any other dead leftover. Gateway liveness is the shared host observer: completed records are Dead, missing PIDs are Unknown, invalid PIDs are NotProcess, and a positive PID is Alive only after the strong probe (non-zombie SASE/Python process plus home-marker or project-claim match when that shape exists; workflow records without those claim shapes still get the process classifier). Recycled-PID / wrong-command identity mismatches are excluded from both presentation and history rather than demoted into recent-terminal.

[2026-09-18T21:40:28Z · sase-133.1] Focused tests (host_liveness, fleet_presentation, fleet_reads parity fixture) and sase-core canonical checks (fmt-check, clippy, workspace test suite) verified.

## Dependencies

- **Blocks:** [sase-133.2](sase-133.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.1.md) | [sase-133.1](sase-133.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b7531db`](https://github.com/sase-org/sase-core/commit/b7531dbeae28d447f973381d9d486f7db6e88315) | fix(fleet): honor owner dismissal and strong host liveness in the served set | [sase-133.1](sase-133.1.md) | 2026-09-18 17:42:01 EDT |
