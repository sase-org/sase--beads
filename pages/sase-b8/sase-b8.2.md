# Bead: sase-b8.2 — Lane-scoped SASE\_AGENT commit tag

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.2` · **Size:** small
**Created:** 2026-07-30 14:32:37 UTC · **Closed:** 2026-07-30 15:26:42 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

tag: make the runtime commit-footer tag carry the lane label and the lane page destination, dropping the member anchor, for real commits, PRs, and SDD auto-commits.

## Notes

[2026-07-30T15:26:42Z · sase-b8.2] Implemented lane-scoped SASE_AGENT commit tags. Verified .venv/bin/pytest tests/agents_sync/test_links.py tests/test_commit_runtime_tags.py (43 passed) and just _lint-symvision. just check passed lint but failed SASE validation on existing init-skills/plan-link issues; just test failed only artifact-file query wire schema mismatch (expected 2, got 3).

## Dependencies

- **Depends on:** [sase-b8.1](sase-b8.1.md) ✓
- **Blocks:** [sase-b8.5](sase-b8.5.md) ✓
- **Blocks:** [sase-b8.6](sase-b8.6.md) ◐
- **Blocks:** [sase-b8.7](sase-b8.7.md) ✓
- **Blocks:** [sase-b8.8](sase-b8.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.2/README.md) | [sase-b8.2](sase-b8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`5f94aae`](https://github.com/sase-org/sase/commit/5f94aae4009ad5f260446a26d0f4d8e0c3f47e4e) | fix: tag family agent commits by lane | [sase-b8.2](sase-b8.2.md) | 2026-07-30 15:28:42 |
