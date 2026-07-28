# Bead: sase-ac.6.2 — Canonicalize the prompt-bar VCS-tag workspace lookup

[Bead Pages](../README.md) / [sase-ac.6](sase-ac.6.md) / sase-ac.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.6.2` · **Size:** small
**Created:** 2026-07-28 13:14:15 UTC · **Closed:** 2026-07-28 13:28:00 UTC
**Plan:** [202607/xprompt\_identity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_identity_landing.md)

## Description

prompt_bar_identity: normalize the project the prompt-bar xprompt selector derives from the VCS tag before looking up its workspace, so project-local `sase.yml` xprompts stop being silently dropped.

## Dependencies

- **Blocks:** [sase-ac.6.5](sase-ac.6.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.6.2/README.md) | [sase-ac.6.2](sase-ac.6.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a0a2e40`](https://github.com/sase-org/sase/commit/a0a2e4007ae03a801a00f85d79a286683dc2c515) | fix(ace): canonicalize prompt-bar VCS-tag xprompt lookup (sase-ac.6.2) | [sase-ac.6.2](sase-ac.6.2.md) | 2026-07-28 13:29:24 |
