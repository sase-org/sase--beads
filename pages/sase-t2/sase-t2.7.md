# Bead: sase-t2.7 — Legacy note bytes survive bead conflict resolution

[Bead Pages](../README.md) / [sase-t2](README.md) / sase-t2.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-t2.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-t2.land.md) · **Assignee:** `sase-t2.7.land`
**Created:** 2026-08-25 09:44:12 EDT
**Plan:** [202608/legacy\_note\_bytes\_in\_conflict\_resolution.md](https://github.com/sase-org/sase--plans/blob/main/202608/legacy_note_bytes_in_conflict_resolution.md)

## Description

Resolving a bead event-stream conflict never rewrites a historical event's legacy `notes` encoding, so a store that predates the structured note log can be rebased and published without tripping the append-only stream guard, and the memory note and templates describing bead notes match the shipped append-only behavior.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t2.7.land/README.md) | [sase-t2.7](sase-t2.7.md) | 0 |
