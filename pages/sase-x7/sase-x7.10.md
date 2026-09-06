# Bead: sase-x7.10 — Delete renamed APIs, command aliases, and TUI test shims

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.10` · **Size:** medium
**Created:** 2026-09-05 18:55:34 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

remove-facades: Replace all actual facade consumers and monkeypatch targets with canonical imports, delete obsolete packages and CLI/UI aliases, remove production mock detection, and preserve canonical coverage while renaming stale test filenames.

## Dependencies

- **Blocks:** [sase-x7.11](sase-x7.11.md) ◐ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.9](sase-x7.9.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.10/README.md) | [sase-x7.10](sase-x7.10.md) | 0 |
