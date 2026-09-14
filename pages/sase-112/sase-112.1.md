# Bead: sase-112.1 — Additive provenance section merging

[Bead Pages](../README.md) / [sase-112](README.md) / sase-112.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kt](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kt.md) · **Assignee:** `sase-112.1` · **Size:** medium
**Created:** 2026-09-14 14:03:47 EDT · **Closed:** 2026-09-14 14:30:13 EDT
**Plan:** [202609/provenance\_refresh\_conflicts.md](https://github.com/sase-org/sase--plans/blob/main/202609/provenance_refresh_conflicts.md)

## Description

additive-provenance-merge: make refresh_association_sections and both refresh callers union locally derived AGENTS/COMMITS entries with the plan file's existing entries (derived side wins per-key metadata, no entry is ever dropped for being outside the local view), with deterministic ordering pinned by idempotence and merge-stability tests.

## Notes

[2026-09-14T18:30:13Z · sase-112.1] Implemented additive AGENTS/COMMITS provenance merging with derived metadata wins and deterministic convergence; verified targeted pytest for plan header/link refresh plus just fmt and just check (scoped lane escalated to the full suite).

## Dependencies

- **Blocks:** [sase-112.2](sase-112.2.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-112.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-112.1/README.md) | [sase-112.1](sase-112.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f692235`](https://github.com/sase-org/sase/commit/f692235fc3c0fe2161bc1ef5e92699b9d567d89f) | fix(sdd): merge plan provenance entries additively | [sase-112.1](sase-112.1.md) | 2026-09-14 14:32:00 EDT |
