# Bead: sase-158.5 — Mode switch, dry-run, and documentation

[Bead Pages](../README.md) / [sase-158](README.md) / sase-158.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1d.md) · **Assignee:** `sase-158.5` · **Size:** small
**Created:** 2026-09-21 07:49:33 EDT · **Closed:** 2026-09-21 14:55:14 EDT
**Plan:** [202609/sase\_update\_live\_progress.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress.md)

## Description

wire-mode-switch-dry-run-docs: move --to mode switches onto the same live session after confirmation, show a transient timeline while --dry-run plans its fetches, and update the plugins.md and cli.md docs with the new output and the --verbose flag.

## Notes

[2026-09-21T18:55:14Z · sase-158.5] Mode-switch runs in live session after confirmation (header 'switch to dev|pypi', restart+completions rows, final frame, log_path in JSON, 130 on interrupt); dry-run shows transient live timeline on terminals only with no log file; plugins.md/cli.md docs updated. Verified: 11 new tests pass, 74 neighbor update/switch tests pass, ruff/mypy/fmt gates green; real 'sase update -n' exits 0. Pre-existing unrelated failures noted: symvision flags ace notification_modal symbols (commit 03fff9dcb), 3 notify/snippet help-text tests fail (other lanes).

## Dependencies

- **Depends on:** [sase-158.4](sase-158.4.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-158.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.5/README.md) | [sase-158.5](sase-158.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc29531`](https://github.com/sase-org/sase/commit/cc2953128a4ad317b4dc9f0720f629a678bcfaa6) | feat(update): run mode-switch in live session, transient dry-run timeline, docs | [sase-158.5](sase-158.5.md) | 2026-09-21 14:58:00 EDT |
