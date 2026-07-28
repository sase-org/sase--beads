# Bead: sase-11.2 — Phase 2: Rework #sase/pylimit\_split to launch detached split agents

[Bead Pages](../README.md) / [sase-11](README.md) / sase-11.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-11.2`
**Created:** 2026-04-28 14:46:00 UTC · **Closed:** 2026-04-28 15:08:42 UTC
**Plan:** [202604/chop\_agent\_visibility\_and\_pylimit\_split.md](https://github.com/sase-org/sase--plans/blob/main/202604/chop_agent_visibility_and_pylimit_split.md)

## Description

Keep the pylimit_split xprompt as the entry point, build a deduplicated multi-prompt with %wait after the first segment, and launch it through the detached run path.

## Notes

COMMIT: b1b09946

## Dependencies

- **Depends on:** [sase-11.1](sase-11.1.md) ✓
- **Blocks:** [sase-11.3](sase-11.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`25bf05d`](https://github.com/sase-org/sase/commit/25bf05d00c0fff3a3a3e9525bcb32c97f3b731ec) | feat(xprompt): launch pylimit split agents via detached %wait chain (sase-11.2) | [sase-11.2](sase-11.2.md) | 2026-04-28 15:08:46 |
