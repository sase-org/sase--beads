# Bead: sase-ij.7 — Add a non-fatal core-floor probe to just check

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.7` · **Size:** medium
**Created:** 2026-08-09 15:20:44 EDT · **Closed:** 2026-08-09 15:46:49 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

early-warning: add a cached, offline-tolerant tools/probe_core_floor that runs the two stdlib probes against the declared floor, names the sase-core commit and release that provides any missing capability, and wire it into just check and just check-full as a warning that can never fail the run.

## Notes

[2026-08-09T19:38:40Z · sase-ij.7] PROPOSED FOLLOW-UP: Fix markdown formatting for build_and_run memory note - `just check` currently fails at `just fmt-md-check` because `sase/memory/build_and_run.md` is not Prettier-formatted; phase workers cannot edit memory files without explicit user permission.

[2026-08-09T19:46:49Z · sase-ij.7] Implemented tools/probe_core_floor, wired it into just check and check-full after SASE validation, optimized the binding scanner cache path, and added tests. Verified: just install; pytest tests/test_check_sase_core_rs_bindings_tool.py tests/test_probe_core_floor_tool.py; just fmt-py-check; just _lint-ruff; just _lint-pyscripts; lint-keep-sorted; _lint-mypy; validate; validate-committed-plans; test-waits/changelog/patch-stitch/symvision/toobig lint lanes; live probe reports blocked_unpublished for parse_merge_summary and vcs_log_wire_schema_version at sase-core 459bbc6 with cache_hit true; forced-unreachable PyPI path exits 0 skipped. just check and just check-full are blocked before this phase by fmt-md-check on sase/memory/build_and_run.md; proposed follow-up was noted.

[2026-08-09T19:48:04Z · sase-ij.7] Verified just install; focused probe/binding pytest passed; lint/validation lanes passed; live advisory probe reports blocked_unpublished for parse_merge_summary at core commit 459bbc6 and cached path hits. just check/check-full are blocked before these lanes by existing fmt-md-check failure in sase/memory/build_and_run.md; test-scoped queued on unavailable pytest worker tokens.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.7/README.md) | [sase-ij.7](sase-ij.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f43d6e4`](https://github.com/sase-org/sase/commit/f43d6e4fea2423cea0e164962e4d86ffaea12aee) | feat(check): add advisory core floor probe | [sase-ij.7](sase-ij.7.md) | 2026-08-09 15:49:17 EDT |
