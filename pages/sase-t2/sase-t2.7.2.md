# Bead: sase-t2.7.2 — Correct the bead-notes documentation that still promises replacement

[Bead Pages](../README.md) / [sase-t2.7](sase-t2.7.md) / sase-t2.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-t2.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-t2.land.md) · **Assignee:** `sase-t2.7.2` · **Size:** small
**Created:** 2026-08-25 09:44:14 EDT · **Closed:** 2026-08-25 10:18:24 EDT
**Plan:** [202608/legacy\_note\_bytes\_in\_conflict\_resolution.md](https://github.com/sase-org/sase--plans/blob/main/202608/legacy_note_bytes_in_conflict_resolution.md)

## Description

memory: rewrite the generated bead memory note's Notes And History section and its packaged template for the append-only log, and fix the one stale code comment that still justifies itself with `--notes` overwrite semantics.

## Notes

[2026-08-25T14:17:53Z · sase-t2.7.2] PROPOSED FOLLOW-UP: tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures fails on a clean tree (git stash reproduces it) with ImportError: import error in sase.sdd._store_link.time: No module named sase.sdd._store_link.time; sase.sdd._store_link is not a package — a monkeypatch target in the test references a nonexistent submodule path, unrelated to this phase's doc-only changes.

[2026-08-25T14:18:24Z · sase-t2.7.2] Rewrote sase/memory/sase_beads.md and src/sase/main/init_memory/templates/memory-sase-beads.template.md Notes And History sections for the append-only note log (note/update --note append, --notes is a removed tombstone, note --edit/--remove is the repair path, history --lost-notes is a historical repair); fixed the stale --notes-overwrite rationale in _git_commit_dispatch.py's _amend_bead_changes docstring. Regenerated via .venv/bin/sase memory init --no-commit (the global sase CLI resolves to a different checkout and must not be used for this repo's own dev changes); .venv/bin/sase init memory --check is clean. just check passed except tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures, confirmed pre-existing/unrelated via git stash and noted as a PROPOSED FOLLOW-UP.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-t2.7.2.md) | [sase-t2.7.2](sase-t2.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7cb0eab`](https://github.com/sase-org/sase/commit/7cb0eab8eca0995f812d8598bcd1337de0d04741) | docs(beads): rewrite bead-notes memory for the append-only note log | [sase-t2.7.2](sase-t2.7.2.md) | 2026-08-25 10:19:22 EDT |
