# Bead: sase-r.1 — is\_ready\_to\_work field + sase bead work flip + create-epic prompt update

[Bead Pages](../README.md) / [sase-r](README.md) / sase-r.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 21:20:52 UTC · **Closed:** 2026-04-25 21:39:07 UTC
**Plan:** [202604/epic\_work\_automation.md](https://github.com/sase-org/sase--plans/blob/main/202604/epic_work_automation.md)

## Description

Schema migration adding is_ready_to_work column (Issue dataclass, db.py, jsonl.py). BeadProject.mark_ready_to_work(epic_id) with validation + custom exception. sase bead work <id> parser + handler that only flips the flag and prints a confirmation (launch wiring happens in Phase 4). Update bd/new_epic content in default_config.yml to instruct the agent to run sase bead work <epic_id> after committing. Tests: model round-trip, migration on a pre-column DB, update() rejects the field, plan-only guard, idempotency error, JSONL round-trip.

## Notes

COMMIT: c50f15db

## Dependencies

- **Blocks:** [sase-r.4](sase-r.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`bb7ae76`](https://github.com/sase-org/sase/commit/bb7ae76706fe798f96f2b4b0cf3a7df362c5a9cd) | feat: \`is\_ready\_to\_work\` field + \`sase bead work\` CLI flag-flip (sase-r.1) | [sase-r.1](sase-r.1.md) | 2026-04-25 21:39:11 |
