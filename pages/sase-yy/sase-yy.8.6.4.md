# Bead: sase-yy.8.6.4 — Accept valid out-of-order tombstones on read surfaces

[Bead Pages](../README.md) / [sase-yy.8.6](sase-yy.8.6.md) / sase-yy.8.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.8.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.land.md) · **Assignee:** `sase-yy.8.6.4` · **Size:** small
**Created:** 2026-09-11 06:54:40 EDT · **Closed:** 2026-09-11 09:36:46 EDT
**Plan:** [202609/artifact\_link\_durable\_truth\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_durable_truth_repairs.md)

## Description

reader_causality: keep missing-predecessor diagnostics without rejecting Rust-valid event sets or reviving legacy rows.

## Notes

[2026-09-11T13:36:13Z · sase-yy.8.6.4] PROPOSED FOLLOW-UP: Reformat src/sase/core/continuation_wire.py — just check currently fails fmt-py-check on committed HEAD formatting unrelated to reader_causality.

[2026-09-11T13:36:46Z · sase-yy.8.6.4] Verified direct focused pytest: .venv/bin/python -m pytest tests/sdd/test_artifact_link_event_store.py -q passed (15 passed); git diff --check passed; sase bead epic-symbols sase-yy.8.6.4 reported no entries. just check reached fmt-py-check and failed on unrelated committed src/sase/core/continuation_wire.py formatting, recorded as PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Depends on:** [sase-yy.8.6.3](sase-yy.8.6.3.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-yy.8.6.6](sase-yy.8.6.6.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.8.6.4/README.md) | [sase-yy.8.6.4](sase-yy.8.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`06b23d9`](https://github.com/sase-org/sase/commit/06b23d9d71e676b027bdd25c22c0166e279ebb44) | fix(artifact-links): accept out-of-order tombstones | [sase-yy.8.6.4](sase-yy.8.6.4.md) | 2026-09-11 09:38:44 EDT |
