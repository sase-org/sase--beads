# Bead: sase-16k.1 — Detachable identity header in prompt-panel documents

[Bead Pages](../README.md) / [sase-16k](README.md) / sase-16k.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pi](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pi.md) · **Assignee:** `sase-16k.1` · **Size:** medium
**Created:** 2026-09-22 13:53:07 EDT · **Closed:** 2026-09-22 16:01:28 EDT
**Plan:** [202609/sticky\_agent\_header\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/sticky_agent_header_panel.md)

## Description

document: prompt-panel builders can split the identity header out of the metadata document into an IdentityHeader (expanded and two-row compact forms) that travels with the document and is published to an optional sink; nothing attaches a sink yet, so rendering is unchanged.

## Notes

[2026-09-22T20:00:38Z · sase-16k.1] PROPOSED FOLLOW-UP: just check red on pristine HEAD — symvision flags agent_env_refusal_reason in src/sase/service/platform.py as unused public (only in-file use at apply_service_init); verified pre-existing via stash, unrelated to sase-16k.1

[2026-09-22T20:01:28Z · sase-16k.1] document phase done: IdentityHeader detach in prompt-panel builders (agent/family/proc/gate/monitor/step/workflow/tribe/attempt-pinned) with sink plumbing; no sink attached so rendering unchanged. Verified: 27 new tests pass, 198 existing header/tribe/workflow/hint/section tests pass, ruff+mypy+fmt green. just check blocked only by pre-existing symvision flag on agent_env_refusal_reason (verified on pristine HEAD, noted as follow-up). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-16k.3](sase-16k.3.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16k.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16k.1/README.md) | [sase-16k.1](sase-16k.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2822794`](https://github.com/sase-org/sase/commit/28227947e135f66042f61aa3fac9428d1defad6e) | feat(agents): detachable identity header in prompt-panel documents | [sase-16k.1](sase-16k.1.md) | 2026-09-22 16:03:37 EDT |
