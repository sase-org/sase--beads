# Bead: sase-k3.3 — Deferred persisted diff-badge classification

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.3` · **Size:** medium
**Created:** 2026-08-12 11:37:29 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

badges: stop classifying persisted diff badges inside the loader's status-override pass and compute them for visible rows only in a coalesced background pass modeled on the existing bead-warmup and live-hint mixins, with carry-over across reloads so badges do not flicker on refresh.

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.3/README.md) | [sase-k3.3](sase-k3.3.md) | 0 |
