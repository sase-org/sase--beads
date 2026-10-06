# Bead: sase-1h3.5 — Shadow render at every root provider invocation, behind one boundary

[Bead Pages](../README.md) / [sase-1h3](README.md) / sase-1h3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.5` · **Size:** medium
**Created:** 2026-10-06 12:43:30 EDT · **Closed:** 2026-10-06 16:29:54 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

## Description

invocation-hook: route all three root provider.invoke sites through one fail-open boundary that writes per-invocation bundle and manifest artifacts, the agent_meta summary, and SASE_INSTRUCTIONS_FILE behind the instruction_shadow_render sunset flag, guarded by an architecture test and route tests.

## Notes

[2026-10-06T19:52:01Z · sase-1h3.5] Smoke (fake provider, real compiler, this checkout as project root): manifests /tmp/smoke_real/artifacts/instructions/00-fakey.json (cold miss, render_ms=389.0) and 01-fakey.json (warm hit, render_ms=37.7, wall 64ms); identical bundle sha 89d182ead262, common bae7477ddfc6, 16802 bytes. Warm p95 budget (250ms) holds on this host.

[2026-10-06T20:29:54Z · sase-1h3.5--2] invocation-hook boundary done: per-invocation bundle/manifest + agent_meta + SASE_INSTRUCTIONS_FILE behind instruction_shadow_render. Verified: sase tool run check 4670c9d92cad67ebf0f0d2d36f408e3d verdict no_new_failures; lint(feature flags) passes (prior out-of-sync fixed); remaining 2 KNOWN symvision + 1 FLAKY oracle test. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1h3.3](sase-1h3.3.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h3.6](sase-1h3.6.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.5.md) | [sase-1h3.5](sase-1h3.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`620e531`](https://github.com/sase-org/sase/commit/620e5310d48952dc5994d0eca91d750fd9789785) | feat(instructions): shadow render bundles at provider invoke boundary | [sase-1h3.5](sase-1h3.5.md) | 2026-10-06 16:31:23 EDT |
