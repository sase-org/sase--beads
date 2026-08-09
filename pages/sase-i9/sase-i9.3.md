# Bead: sase-i9.3 — Add a fast dev-update cargo profile

[Bead Pages](../README.md) / [sase-i9](README.md) / sase-i9.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wj/README.md) · **Assignee:** `sase-i9.3` · **Size:** medium
**Created:** 2026-08-09 10:11:04 EDT
**Plan:** [202608/fast\_dev\_update.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_dev_update.md)

## Description

fast-profile: add a dev-update-only cargo profile in sase-core that drops LTO and codegen-units=1 in favor of incremental parallel codegen, wire the dev-update recipes to it with an escape hatch, and prove the published wheel/CI profile is untouched and runtime performance does not regress.

## Dependencies

- **Depends on:** [sase-i9.2](sase-i9.2.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.4](sase-i9.4.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.5](sase-i9.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i9.3/README.md) | [sase-i9.3](sase-i9.3.md) | 0 |
