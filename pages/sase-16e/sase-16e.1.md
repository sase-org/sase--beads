# Bead: sase-16e.1 — Durable rescue store and non-refusing sidecar eviction

[Bead Pages](../README.md) / [sase-16e](README.md) / sase-16e.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pc.md) · **Assignee:** `sase-16e.1` · **Size:** medium
**Created:** 2026-09-22 12:13:29 EDT
**Plan:** [202609/self\_healing\_workspace\_prep.md](https://github.com/sase-org/sase--plans/blob/main/202609/self_healing_workspace_prep.md)

## Description

rescue-store: add a best-effort rescue store outside the workspace (git bundles, worktree patches, manifests, retention, one notification per rescue) and change launch-time sidecar protection to publish once, rescue, and always proceed with eviction instead of raising _WorkspaceBeadEvictionRefused.

## Dependencies

- **Blocks:** [sase-16e.2](sase-16e.2.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16e.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.1/README.md) | [sase-16e.1](sase-16e.1.md) | 0 |
