# Bead: sase-165.6 — Managed-tmp reaper covers the root agents actually use

[Bead Pages](../README.md) / [sase-165](README.md) / sase-165.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0p2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0p2.md) · **Assignee:** `sase-165.6` · **Size:** medium
**Created:** 2026-09-22 08:18:27 EDT
**Plan:** [202609/sase\_core\_p0\_agent\_maintainability.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_p0_agent_maintainability.md)

## Description

reaper-root: capture SASE_TMPDIR (and sibling SASE path overrides) in the service env, and warn when the reaper's managed root differs from the launch root, so per-run cargo targets are really reaped (sase-15q). This is a prerequisite for larger incremental target dirs.

## Notes

[2026-09-22T13:49:38Z · sase-165.6] Landing one-time host command: run `sase service init --yes` from an interactive shell (with SASE_TMPDIR exported, e.g. via ~/.profile) on each host so the captured service env picks up SASE_TMPDIR/SASE_HOME; then confirm the next managed_tmp_reap result names the effective root (e.g. ~/.cache/sase/tmp) in its log line

## Dependencies

- **Blocks:** [sase-165.7](sase-165.7.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-165.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.6/README.md) | [sase-165.6](sase-165.6.md) | 0 |
