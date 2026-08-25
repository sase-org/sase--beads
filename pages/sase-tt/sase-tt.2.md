# Bead: sase-tt.2 — Stop revalidating the agent-name registry on every load

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.2` · **Size:** medium
**Created:** 2026-08-25 14:59:12 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

registry: make the process-cached registry stop paying a full source-signature stat sweep and a full per-entry owner-existence sweep on every `load_name_registry()` call, which is 905ms of the Agent pane's 1529ms load.

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tt.2.md) | [sase-tt.2](sase-tt.2.md) | 0 |
