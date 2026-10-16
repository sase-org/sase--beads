# Bead: sase-1lh.7 — Repair the release watcher and check-mode recapture, then ship sase v0.18.0

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.land.md) · **Assignee:** `sase-1lh.7.land`
**Created:** 2026-10-16 16:46:18 EDT
**Plan:** [202610/sase\_1lh\_landing\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_1lh_landing_repair.md)

## Description

The defects that the sase-1lh landing review found in its own watcher, check-mode recapture, and docs_split work are fixed. The watcher treats a stale release-PR head as something to refresh, not as CORE_FLOOR_BLOCKED. A fresh release watch sees sase 0.18.0 install from PyPI. This epic's land agent confirms the release, then resumes the interrupted sase-1lh landing through parent_bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.land/README.md) | [sase-1lh.7](sase-1lh.7.md) | 0 |
