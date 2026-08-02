# Bead: sase-e7.2 — Make every prompt interface canonical

[Bead Pages](../README.md) / [sase-e7](README.md) / sase-e7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rt/README.md) · **Assignee:** `sase-e7.2` · **Size:** medium
**Created:** 2026-08-02 13:28:35 UTC · **Closed:** 2026-08-02 14:11:02 UTC
**Plan:** [202608/finish\_dh\_canonical\_archive.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_dh_canonical_archive.md)

## Description

canonical-interfaces: retire the export path that writes prompt Markdown into the plans store, retarget prompt search at the canonical agents archive, delete plans-snapshot discovery once nothing calls it, and add the regression test that enforces the invariant.

## Notes

[2026-08-02T14:10:34Z · sase-e7.2] PROPOSED FOLLOW-UP: Harden bead mutation contention regression under saturated test hosts — the first full just check failed test_concurrent_bead_mutations_wait_past_the_old_lock_timeout while the host had zero free pytest tokens and heavy concurrent load; an isolated rerun passed in 6.47s and the final full just check passed.

[2026-08-02T14:11:02Z · sase-e7.2] Retired prompt export --sdd with actionable --out and sase agent prompts guidance; prompt search now resolves and reads canonical agents-sidecar prompts/YYYYMM/*.md, exposes archive as the canonical source while retaining sdd as a deprecated alias, and includes plan/artifact metadata. Removed plans-snapshot search and commit-hook discovery paths. Verified 284 focused prompt/archive/link/path/commit tests pass, live archive JSON search returns canonical path/plan/artifact_count, git diff --check passes, obsolete discovery-symbol audit is empty, and final just check passes including formatting, Ruff, mypy, Symvision, SASE/plan validation, and the full test suite.

[2026-08-02T14:11:28Z · sase-e7.2] Retired prompt export --sdd with actionable --out and sase agent prompts guidance; prompt search now resolves and reads canonical agents-sidecar prompts/YYYYMM/*.md, exposes archive as the canonical source while retaining sdd as a deprecated alias, and includes plan/artifact metadata. Removed plans-snapshot search and commit-hook discovery paths. Verified 284 focused prompt/archive/link/path/commit tests pass, live archive JSON search returns canonical path/plan/artifact_count, git diff --check passes, obsolete discovery-symbol audit is empty, and final just check passes including formatting, Ruff, mypy, Symvision, SASE/plan validation, and the full test suite.

## Dependencies

- **Blocks:** [sase-e7.4](sase-e7.4.md) ✓
- **Blocks:** [sase-e7.5](sase-e7.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.2/README.md) | [sase-e7.2](sase-e7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`53b1fc0`](https://github.com/sase-org/sase/commit/53b1fc0378c8e8b7441ce638abbc17e9af70b3fc) | feat(prompt)!: use the canonical prompt archive | [sase-e7.2](sase-e7.2.md) | 2026-08-02 14:13:30 |
