# Bead: sase-ku.6 — --idle-timeout for commands that hang without exiting

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.6` · **Size:** small
**Created:** 2026-08-13 09:03:03 EDT · **Closed:** 2026-08-13 09:59:08 EDT
**Plan:** 202608/monitor\_hardening.md

## Description

idle: add an opt-in idle timeout that fires when a monitored command has produced no output for N seconds, so `--timeout` can be generous without being useless.

## Notes

[2026-08-13T13:57:58Z · sase-ku.6] PROPOSED FOLLOW-UP: Fix built-in artifact ref provider spec registration — full-suite tests reject builtin plan/beads providers because ArtifactRefProviderSpecWire now requires icon, leaving registry.ref_providers_by_id empty and sidecar doctor checks WARN.

[2026-08-13T13:58:33Z · sase-ku.6] PROPOSED FOLLOW-UP: Break project_handler fresh-interpreter import cycle — importing sase.main.project_handler can cycle project_aliases -> xprompt.loader_memory -> memory.read_log -> project_aliases and fail before tests collect.

[2026-08-13T13:59:08Z · sase-ku.6] Implemented --idle-timeout plumbing and supervisor enforcement. Verified focused monitor/CLI/TUI tests passed (72 passed) and git diff --check passed; just check reached the full-suite test lane but failed on unrelated ref-provider/sidecar and project_handler import-cycle failures recorded as PROPOSED FOLLOW-UP notes.

[2026-08-13T14:00:04Z · sase-ku.6] Verified idle-timeout implementation with focused monitor/TUI/parser tests; just check reached the full-suite lane and only failed on unrelated existing ref-provider registry and project_handler import-cycle issues recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-ku.1](sase-ku.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.2](sase-ku.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.9](sase-ku.9.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.6/README.md) | [sase-ku.6](sase-ku.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`49f6b98`](https://github.com/sase-org/sase/commit/49f6b98a49614be766b6d03edca49762daba075a) | feat(monitor): add idle timeout support | [sase-ku.6](sase-ku.6.md) | 2026-08-13 10:01:00 EDT |
