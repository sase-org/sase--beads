# Bead: sase-ug.2 — A stale clone may not prove deletion

[Bead Pages](../README.md) / [sase-ug](README.md) / sase-ug.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.2` · **Size:** medium
**Created:** 2026-08-26 14:48:25 EDT · **Closed:** 2026-08-26 15:39:38 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

## Description

freshness: stop treating a companion file's mere existence as proof that a row was deleted, so a behind-HEAD sidecar clone can no longer delete rows another workspace added.

## Notes

[2026-08-26T19:37:08Z · sase-ug.2] PROPOSED FOLLOW-UP: test-wait lint blocks just check — tests/test_notification_gate_durability.py:69 has a positive literal time.sleep without the required # sase-test-wait pragma.

[2026-08-26T19:39:38Z · sase-ug.2] Verified focused aggregate tests (.venv/bin/python -m pytest -q tests/sdd/test_artifact_link_store_aggregate.py), direct ruff on touched files, and just test-scoped (965 passed, 1 skipped). just check ran through fmt/ruff/mypy/feature-flags/pyscripts and is blocked by pre-existing tests/test_notification_gate_durability.py:69 wait-lint failure; proposed follow-up recorded.

## Dependencies

- **Depends on:** [sase-ug.1](sase-ug.1.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.2/README.md) | [sase-ug.2](sase-ug.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9a477bf`](https://github.com/sase-org/sase/commit/9a477bfd1cf8f3aa1fec9e1eae900c9f3cb3970a) | fix(artifact-links): require fresh deletion authority | [sase-ug.2](sase-ug.2.md) | 2026-08-26 15:40:59 EDT |
