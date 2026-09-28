# Bead: sase-1c1.8 — Fix chrome layout resize failures

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.8` · **Size:** medium
**Created:** 2026-09-28 07:09:33 EDT · **Closed:** 2026-09-28 10:45:37 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

tui-resize-layout: root-cause why a terminal resize sometimes has no effect in the two test_chrome_layout nodes (sase-1a6) and make recompose and popup reclamp settle deterministically.

## Notes

[2026-09-28T11:51:18Z · sase-1c1.8] Root cause: Textual stores App Resize until _on_idle then forwards it to the screen; ACE event-driven pause does not wait for that hop, so two pauses left frame.outer_size and popup card.x stale under CI shard load (Master Gate 36415385228: 200==96 and 34<34). Production on_resize/_layout_popup already recompose and reclamp. Tests now wait_for screen size, border label budget, and popup card x. Verified the 3 resize nodes 10/10 and the 241-test command_line suite under xdist. Tracking bead sase-1a6; land agent can close it after green-master.

[2026-09-28T12:55:26Z · sase-1c1.8--1] PROPOSED FOLLOW-UP: test_no_system_clock_display_sites is KNOWN on clean-base just check (tool run 2727d4d63642735e22c240559e0d6db6) — already tracked by sase-1bp; contract-drift sase-1c1.4 also lists the system-clock sites. This phase did not touch those files.

[2026-09-28T12:55:37Z · sase-1c1.8--1] PROPOSED FOLLOW-UP: test_default_config_matches_public_schema is KNOWN (ace.keymaps additional property tool_runs) — already in scope of contract-drift sase-1c1.4 (add the two schema properties). Closed flake bead sase-u1 is a different parallel-lane leak, not this mismatch.

[2026-09-28T14:45:37Z · sase-1c1.8--3] Resize settle is deterministic: tests wait for Textual idle hop (screen size), border recompose, and popup reclamp. 3 resize nodes passed here; just check 6d4b69a40911d7dc193aabea73ee612e was no_new (2 KNOWN: timezone display sase-1bp, schema tool_runs sase-1c1.4). Production on_resize/_layout_popup already recompose. No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1c1.12](sase-1c1.12.md) ◐ · ⧖ 2026-09-28
- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.8.md) | [sase-1c1.8](sase-1c1.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f760d30`](https://github.com/sase-org/sase/commit/f760d30a9115a0c5d1c7fd0b341a6142888f58bc) | fix(ace-tui): wait for chrome layout resize settle (sase-1c1.8) | [sase-1c1.8](sase-1c1.8.md) | 2026-09-28 11:54:36 EDT |
