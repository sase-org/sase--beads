# Bead: sase-10r.3 — Reap sibling pytest scratch roots

[Bead Pages](../README.md) / [sase-10r](README.md) / sase-10r.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.0l](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.0l.md) · **Assignee:** `sase-10r.3` · **Size:** small
**Created:** 2026-09-14 06:56:22 EDT · **Closed:** 2026-09-14 07:53:13 EDT
**Plan:** [202609/apollo\_disk\_reclaim\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/apollo_disk_reclaim_1.md)

## Description

pytest-scratch-sibling-reap: make tools/run_pytest also reap stale runs in other /var/tmp/sase-<sha8> roots owned by the user and remove empty stale roots, with tests.

## Notes

[2026-09-14T11:51:30Z · sase-10r.3] PROPOSED FOLLOW-UP: Symvision cannot see monitor store module-attribute consumers — just check fails on public monitor_records/project_records in src/sase/monitor/store.py even though src/sase/monitor/store_lane.py consumes them via the store module to preserve monkeypatchability.

[2026-09-14T11:53:13Z · sase-10r.3] Implemented default-only sibling pytest scratch reaping. Verified focused module with .venv/bin/python -m pytest -q tests/test_run_pytest_tmpdir.py (19 passed). Ran just check; it passed fmt, ruff, mypy, feature flags, pyscripts, test waits, changelog, and terminology, then failed unrelated symvision monitor_records/project_records; PROPOSED FOLLOW-UP noted on this bead. epic-symbols reported none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-10r.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-10r.3/README.md) | [sase-10r.3](sase-10r.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df5fbba`](https://github.com/sase-org/sase/commit/df5fbbaccf07646c34dfcf75eb3bd74f30ef4d71) | fix(test): reap sibling pytest scratch roots | [sase-10r.3](sase-10r.3.md) | 2026-09-14 07:56:13 EDT |
