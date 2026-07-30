# Bead: sase-4c.1 — Phase 1: Core ProjectSpec Alias Contract

[Bead Pages](../README.md) / [sase-4c](README.md) / sase-4c.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4c.1`
**Created:** 2026-06-04 14:33:17 UTC · **Closed:** 2026-06-04 15:02:56 UTC
**Plan:** [202606/project\_aliases.md](https://github.com/sase-org/sase--plans/blob/main/202606/project_aliases.md)

## Notes

COMMIT: 461decb9f

[2026-07-27T19:16:00Z · sase-a1.6] [2026-06-04T14:57:09Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 1 complete: added PROJECT_ALIASES parsing/update support in sase-core, exposed aliases on ProjectRecordWire and the PyO3/Python facade, added alias validation/collision parse warnings, kept stale Python record payloads backward-compatible, and covered parsing/updating/listing/facade behavior with Rust and Python tests. Validation: just install; .venv/bin/python -m pytest tests/main/test_project_handler.py tests/test_core_facade/test_project_lifecycle.py; cargo test -p sase_core project_aliases --lib; cargo test -p sase_core lifecycle_project_records --lib; just check; just rust-check.

## Dependencies

- **Blocks:** [sase-4c.2](sase-4c.2.md) ✓
- **Blocks:** [sase-4c.3](sase-4c.3.md) ✓
- **Blocks:** [sase-4c.4](sase-4c.4.md) ✓
- **Blocks:** [sase-4c.5](sase-4c.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4c.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4c.1/README.md) | [sase-4c.1](sase-4c.1.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b9b08c2`](https://github.com/sase-org/sase/commit/b9b08c23e4e38936ccae320bfde1a5da14e80f7d) | feat: expose project aliases in lifecycle facade (sase-4c.1) | [sase-4c.1](sase-4c.1.md) | 2026-06-04 15:03:22 |
| [`sase-core@21c137e`](https://github.com/sase-org/sase-core/commit/21c137e82b2d38ca3340e44fdcf7b0e8243ecb58) | feat: add ProjectSpec alias contract (sase-4c.1) | [sase-4c.1](sase-4c.1.md) | 2026-06-04 15:04:07 |
