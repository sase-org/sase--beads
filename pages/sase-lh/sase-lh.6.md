# Bead: sase-lh.6 — Flip user-visible Task text to Proc and refresh snapshots

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.6` · **Size:** medium
**Created:** 2026-08-13 17:20:32 EDT · **Closed:** 2026-08-13 22:24:55 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

labels: change every displayed string that names this feature — Admin Center tab label, pane title and hints, command palette entries, quit-confirm copy, status messages, CLI help — from Task to Proc, then regenerate the affected text and PNG snapshot goldens.

## Notes

[2026-08-14T02:24:55Z · sase-lh.6] Verified with just install; focused Admin Center/Procs/quit/update pytest slices; just test-visual --sase-update-visual-snapshots; just test-visual; and just check passing after rerunning one transient Logs-pane scroll miss exact.

[2026-08-14T02:26:43Z · sase-lh.6] Verified just install, focused Admin Center/Procs/quit/update pytest slices, refreshed and checked PNG visual snapshots, and just check passing.

## Dependencies

- **Depends on:** [sase-lh.3](sase-lh.3.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-lh.4](sase-lh.4.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-lh.5](sase-lh.5.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.7](sase-lh.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.6/README.md) | [sase-lh.6](sase-lh.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eca7753`](https://github.com/sase-org/sase/commit/eca7753b556946c758223cade217d09a5d9b3bcb) | feat(tui): label durable background work as procs | [sase-lh.6](sase-lh.6.md) | 2026-08-13 22:27:34 EDT |
