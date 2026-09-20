# Bead: sase-133.5.4 — Prove production and live cross-machine parity

[Bead Pages](../README.md) / [sase-133.5](sase-133.5.md) / sase-133.5.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-133.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.land.md) · **Assignee:** `sase-133.5.4` · **Size:** medium
**Created:** 2026-09-19 08:06:13 EDT
**Plan:** [202609/remote\_parity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_parity_landing_repairs.md)

## Description

parity-acceptance: exercise the production path, validate ordered screenshot driving, deploy consistent builds, and save reviewed parity evidence from both hosts.

## Notes

[2026-09-20T13:47:43Z · sase-133.5.4] Partial, NOT closed. Done (uncommitted in workspace): (1) rendered-row parity oracle test_owner_and_catalog_render_equal_rows_and_nested_shell_counts (current + compact-index) in tests/ace/tui/test_owner_facts_oracle.py compares status, chips, stamp and nested-shell count between real owner loader and real catalog; passes. (2) tmux has no 'slash' key name (verified: -p slash types the letters); fixed docs/ace.md and parser_screenshot.py epilog to '-p / -w INSERT --type machine:apollo -w machine:apollo -p enter' plus help test; ordered driving verified locally and --host apollo (both show machine:apollo 0/0, remote_sase_version 0.17.1+957.g6087c0a8e). Focused tests pass. NOT done: live acceptance. sase machine status apollo still reports real skew (gateway 0.34.66 vs local core 0.34.67, fleet v4 vs v5); athena is an editable dev install, so deploying consistent builds on athena+apollo, restarting gateway/AXE, and capturing equal settled owner/viewer PNGs needs these changes landed and released first; just check-full and saved artifacts also not run. Screenshots at /tmp/local.png and /tmp/apollo.png are empty-filter captures, not parity evidence.

## Dependencies

- **Depends on:** [sase-133.5.2](sase-133.5.2.md) ✓ · ⧖ 2026-09-19
- **Depends on:** [sase-133.5.3](sase-133.5.3.md) ✓ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-133.5.4/README.md) | [sase-133.5.4](sase-133.5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`52b0283`](https://github.com/sase-org/sase/commit/52b0283947e67c25ac4b155c2ba138e5575f38e1) | test(fleet): add rendered-row parity oracle and fix screenshot slash key examples | [sase-133.5.4](sase-133.5.4.md) | 2026-09-20 09:49:11 EDT |
