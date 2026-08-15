# Bead: sase-m6.6.1.4 — Namespace durable query state by pane

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.4` · **Size:** medium
**Created:** 2026-08-15 06:18:00 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

persistence: replace the global saved-query, history, and selection stores with pane-keyed records containing source text, canonical text, profile digest, and ArtifactEntryTarget tokens; add safe read-time migration and write-then-read validation while retaining legacy files until success, surface stale-profile saved views as editable errors, and route slots, pickers, history, help, startup, and selection restore through the active pane without switching tabs.

## Dependencies

- **Depends on:** [sase-m6.6.1.1](sase-m6.6.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.5](sase-m6.6.1.5.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.6.1.4/README.md) | [sase-m6.6.1.4](sase-m6.6.1.4.md) | 0 |
