# Bead: sase-t2.7.1 — Preserve ancestor event bytes through the conflict resolver

[Bead Pages](../README.md) / [sase-t2.7](sase-t2.7.md) / sase-t2.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-t2.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-t2.land.md) · **Assignee:** `sase-t2.7.1` · **Size:** medium
**Created:** 2026-08-25 09:44:13 EDT · **Closed:** 2026-08-25 10:16:01 EDT
**Plan:** [202608/legacy\_note\_bytes\_in\_conflict\_resolution.md](https://github.com/sase-org/sase--plans/blob/main/202608/legacy_note_bytes_in_conflict_resolution.md)

## Description

resolver: stop the bead conflict resolver from re-encoding a conflicted stream's already-published events, so a legacy `notes` field survives a merge byte-for-byte and the append-only publish guard stays satisfied.

## Notes

[2026-08-25T14:15:28Z · sase-t2.7.1] PROPOSED FOLLOW-UP: Fix sidecar clone retry test monkeypatch path — escalated just check full-suite lane failed tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures because sase.sdd._store_link.time.sleep is not importable from _store_link.

[2026-08-25T14:16:01Z · sase-t2.7.1] Implemented raw-event preservation in the conflict resolver. Verified .venv/bin/python -m pytest tests/test_bead/test_conflict_resolver.py -q passed (19 tests) and sase bead epic-symbols reported no entries. Ran just check; all lint/validation stages passed, but the escalated full-suite scoped lane failed unrelated tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t2.7.1/README.md) | [sase-t2.7.1](sase-t2.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c3ec87`](https://github.com/sase-org/sase/commit/8c3ec87f97d35e50cc4b2994ee3c271236a4ca9d) | fix(bead): preserve legacy conflict event bytes | [sase-t2.7.1](sase-t2.7.1.md) | 2026-08-25 10:17:31 EDT |
