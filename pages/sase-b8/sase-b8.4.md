# Bead: sase-b8.4 — Family containers carry their lane commits

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.4` · **Size:** medium
**Created:** 2026-07-30 14:32:44 UTC · **Closed:** 2026-07-30 15:08:19 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

snapshot: extend the v2 hood snapshot so family containers own lane-attributed commits, keep the strict decoder and import path in agreement, and render them on the family page.

## Notes

[2026-07-30T15:08:19Z · sase-b8.4] Implemented v2 family-container commits with optional legacy reads and always-present writes, strict sorted/unique SHA and clan-empty validation, import preservation, Rust relationship-schema isolation, and family-page lane/member deduplication. Verified 35 focused agents-sync tests pass; formatting, Ruff, mypy, scripts, changelog, Symvision, size checks, and committed-plan validation pass. Full suite: 24,262 passed, 7 skipped, with 7 unrelated failures (artifact query wire mismatch, gate broken pipe, and retry visual timing).

[2026-07-30T15:09:38Z · sase-b8.4] Verified 35 focused agents-sync tests pass; formatting, Ruff, mypy, scripts, changelog, Symvision, size checks, and committed-plan validation pass; full suite completed with 24,262 passed, 7 skipped, and 7 unrelated failures.

## Dependencies

- **Depends on:** [sase-b8.1](sase-b8.1.md) ✓
- **Blocks:** [sase-b8.5](sase-b8.5.md) ✓
- **Blocks:** [sase-b8.8](sase-b8.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.4/README.md) | [sase-b8.4](sase-b8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`59b0ecd`](https://github.com/sase-org/sase/commit/59b0ecd227a23891e7c6ed0eb588376a9a3b7135) | feat(agents-sync): preserve family lane commits | [sase-b8.4](sase-b8.4.md) | 2026-07-30 15:12:22 |
