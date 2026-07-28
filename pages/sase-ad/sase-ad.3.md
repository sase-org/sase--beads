# Bead: sase-ad.3 — Self-healing agents sidecar transactions

[Bead Pages](../README.md) / [sase-ad](README.md) / sase-ad.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ad.3` · **Size:** medium
**Created:** 2026-07-28 11:43:45 UTC · **Closed:** 2026-07-28 12:16:57 UTC
**Plan:** [202607/fix\_family\_agent\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_family_agent_publication.md)

## Description

sidecar_tx: guarantee a clean sidecar working tree before every rebase pull, clear stale index locks, and revert uncommitted payload writes on every early-return and exception path so one failed publish cannot wedge all later ones.

## Notes

[2026-07-28T12:16:11Z · sase-ad.3] Implemented scoped, idempotent agents-sidecar payload recovery before every rebase pull and guaranteed cleanup after full-sync and targeted-publication transaction exits. Recovery removes stale index.lock files and restores only regenerable payload paths, preserving non-payload work and local commits. Added regression tests for dirty prior payloads, stale locks, and failures after apply_payload_atomic. Verified focused agents-sync suite (20 passed), isolated alias-override suite after a transient concurrent full-suite failure (14 passed), and a clean rerun of just check.

## Dependencies

- **Blocks:** [sase-ad.4](sase-ad.4.md) ✓
- **Blocks:** [sase-ad.5](sase-ad.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ad.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ad.3/README.md) | [sase-ad.3](sase-ad.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ca5c526`](https://github.com/sase-org/sase/commit/ca5c526c724957db6bdcd273b57fe860df2d0883) | fix(agents-sync): recover sidecar transaction state (sase-ad.3) | [sase-ad.3](sase-ad.3.md) | 2026-07-28 12:18:56 |
