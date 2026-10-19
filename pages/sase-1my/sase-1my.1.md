# Bead: sase-1my.1 — Protected-set retention in sase-core, failing closed

[Bead Pages](../README.md) / [sase-1my](README.md) / sase-1my.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11s.md) · **Assignee:** `sase-1my.1` · **Size:** medium
**Created:** 2026-10-19 10:16:26 EDT · **Closed:** 2026-10-19 10:45:55 EDT
**Plan:** [202610/e1\_installable\_family.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_installable_family.md)

## Description

retention: derive a consumer-driven protected set in pypi_retention.py, add a delete-list validator, enforce it in pypi_delete.py before any login, and make the script tests run with packaging.

## Notes

[2026-10-19T14:45:55Z · sase-1my.1] Implemented consumer-derived retention, protected-file validation, and the pre-credential delete guard. Verified 78 release-script tests and the full core check (ToolRun 46c9cae90d3218bd3915b0cd735ebe98); live plan protects 0.42.0 and 0.42.1 with five files each, planted version and wheel lists are refused, the delete driver refuses before credentials, and forced PyPI unavailability fails without writing a list. Epic-symbol audit found no leftovers.

## Dependencies

- **Blocks:** [sase-1my.4](sase-1my.4.md) ◐ · ⧖ 2026-10-19
- **Blocks:** [sase-1my.6](sase-1my.6.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1my.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1my.1/README.md) | [sase-1my.1](sase-1my.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9876b3a`](https://github.com/sase-org/sase-core/commit/9876b3ae557e7dfacb012507d80b22ebb2a6dc7f) | feat(releases): protect PyPI consumer windows | [sase-1my.1](sase-1my.1.md) | 2026-10-19 10:46:42 EDT |
