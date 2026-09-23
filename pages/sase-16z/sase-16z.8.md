# Bead: sase-16z.8 — CLI capability cache for usage probes

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.8` · **Size:** medium
**Created:** 2026-09-23 11:06:17 EDT · **Closed:** 2026-09-23 14:55:38 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

capability-cache: add a fingerprint-keyed, TTL-bounded on-disk cache of CLI version and help capability results so warm Claude probes spawn 2 processes instead of 5, and agy/grok skip `--version` spawns. Invalidate an entry on fingerprint change, TTL expiry, or a drift/unsupported-version result.

## Notes

[2026-09-23T18:55:02Z · sase-16z.8] PROPOSED FOLLOW-UP: just check symvision gate is red on pre-existing stale --epic-symbol sase-16y(MemberJumpSection) in Justfile (bead sase-16y is closed); owned by that epic, blocks all agents check runs

[2026-09-23T18:55:38Z · sase-16z.8] capability-cache landed: new usage/_capability_cache.py (fingerprint-keyed JSON under sase_home/cache/usage_probe_capabilities, 24h TTL, atomic writes, corrupt-tolerant reads); claude caches --version/-p --help/auth-status --help (warm probe 2 spawns not 5), agy/grok cache --version; unsupported_cli_version/vendor_drift outcomes delete the entry. Verified: 13 new tests in tests/llm_provider/test_usage_capability_cache.py pass (warm/cold counts, fingerprint change, corrupt, drift/unsupported invalidation), 77 neighbor usage tests pass, ruff+mypy clean. Full sase tool run check stops at pre-existing unrelated symvision failure (stale sase-16y MemberJumpSection symbol, recorded as follow-up); no --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-16z.5](sase-16z.5.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.8/README.md) | [sase-16z.8](sase-16z.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5e50d27`](https://github.com/sase-org/sase/commit/5e50d27f599b8b5e5e63376bbcf216825ae32331) | feat(llm-provider): add CLI capability cache for usage probes | [sase-16z.8](sase-16z.8.md) | 2026-09-23 14:56:56 EDT |
