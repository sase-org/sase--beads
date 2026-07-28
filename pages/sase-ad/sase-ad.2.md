# Bead: sase-ad.2 — Make hood publication tolerate container-named requests

[Bead Pages](../README.md) / [sase-ad](README.md) / sase-ad.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ad.2` · **Size:** small
**Created:** 2026-07-28 11:43:39 UTC · **Closed:** 2026-07-28 12:17:21 UTC
**Plan:** [202607/fix\_family\_agent\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_family_agent_publication.md)

## Description

publish: resolve an outbox request that names a pure family/clan container to a concrete run in that hood so publication succeeds instead of raising "absent from project inventory" and quarantining.

## Notes

[2026-07-28T12:16:59Z · sase-ad.2] Implemented container-name tolerant targeted agent-hood publication: publish_agent_hood now resolves the requested local hood and allows absent exact local-agent names when that hood has inventory runs, while preserving errors for empty hoods. Added regression tests for pure family-container requests and empty-hood rejection. Verified with .venv/bin/pytest tests/agents_sync/test_publication.py -q and just check; first just check hit a flaky unrelated TUI filtering failure that passed on direct rerun, second just check passed.

## Dependencies

- **Blocks:** [sase-ad.4](sase-ad.4.md) ✓
- **Blocks:** [sase-ad.5](sase-ad.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ad.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ad.2/README.md) | [sase-ad.2](sase-ad.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`53e94ca`](https://github.com/sase-org/sase/commit/53e94ca4a5e8456316a32ffbb5af8222a0d0c385) | fix(agents-sync): allow container-named hood publication (sase-ad.2) | [sase-ad.2](sase-ad.2.md) | 2026-07-28 12:19:41 |
