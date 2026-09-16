# Bead: sase-11o.1 — Slim owner manifest, raise manifest caps, scope validation

[Bead Pages](../README.md) / [sase-11o](README.md) / sase-11o.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lt](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lt.md) · **Assignee:** `sase-11o.1` · **Size:** medium
**Created:** 2026-09-16 09:17:28 EDT · **Closed:** 2026-09-16 11:57:47 EDT
**Plan:** [202609/agents\_sync\_manifest\_slim.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_sync_manifest_slim.md)

## Description

slim-manifest-fix: make per-hood manifest `files` optional on read and omitted on write behind a new slim_agents_manifest sunset flag, add dedicated (larger) manifest byte and hood-count read caps plus a pre-write size guard, scope run-file re-hashing to the hoods being written, and lock old-reader lenient-skip compatibility in with tests.

## Notes

[2026-09-16T15:54:53Z · sase-11o.1] PROPOSED FOLLOW-UP: flaky test tests/ace/tui/test_bead_close_modal.py::test_force_selects_non_done_resolution_and_returns_close_contract - failed with textual.pilot.WaitForScreenTimeout during a full `just check` run (42148 passed, 1 failed) but passed in isolation and on a full retry of test-scoped (42149 passed, 0 failed). Unrelated to sase-11o.1 (agents_sync/feature_flags only); looks like a Textual pilot timing flake under parallel load.

[2026-09-16T15:57:47Z · sase-11o.1] Implemented slim-manifest-fix per plan phase 1: made per-hood manifest files optional on read (v2_manifest_io.decode_owner_manifest) and omitted on write behind new sunset flag slim_agents_manifest (bead sase-11p, registry entry added + schema synced via tools/sync_feature_flags_schema); added dedicated MAX_MANIFEST_JSON_BYTES (16MiB)/MAX_MANIFEST_HOODS (16384) read caps in v2_validation.py used only by manifest reads; load_validated_publication now skips the files cross-check when an entry's files is None and scopes verify_run_files to override_snapshots keys (the hoods actually being published) instead of every hood of every owner; added a pre-write check_manifest_write_size guard called from plan_hoods, repair_owner_hood_digests, and _repair_owner_manifest before apply_payload_atomic; refreshed the stale publication_repair.py module docstring. Verified: tools/check_feature_flags (full, incl. bead-status rules) and tools/sync_feature_flags_schema both clean; new tests cover fat/slim decode round-trip, a frozen old-reader lenient-skip lock-in test, the new caps, the write guard, scoped verification (drift in an unpublished hood no longer blocks an unrelated publish; drift in the published hood's own carried-forward run still blocks it), and flag ON/OFF for the writer and both repair paths (tests/agents_sync/test_v2_io.py, test_publication.py, test_publication_repair.py). Ran full `just check`: all lint gates green (ruff, mypy, symvision, toobig, feature flags, etc.); the diff-scoped test lane (42148 tests, broad due to feature_flags/registry.py + v2_validation.py being widely imported) had exactly one failure, tests/ace/tui/test_bead_close_modal.py::test_force_selects_non_done_resolution_and_returns_close_contract, a Textual pilot WaitForScreenTimeout unrelated to this change; confirmed as flaky by passing in isolation and on a full test-scoped retry (42149 passed, 0 failed). No leftover --epic-symbol entries (sase bead epic-symbols sase-11o.1 reported none).

## Dependencies

- **Blocks:** [sase-11o.2](sase-11o.2.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11o.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11o.1/README.md) | [sase-11o.1](sase-11o.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4249ccd`](https://github.com/sase-org/sase/commit/4249ccdc182d1638e3e10f58ef698f1b1fe779b5) | feat(agents-sync): slim per-hood manifests behind slim\_agents\_manifest flag | [sase-11o.1](sase-11o.1.md) | 2026-09-16 11:59:25 EDT |
