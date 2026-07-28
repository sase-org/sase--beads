# Bead: sase-ad.4 — Surface quarantined and stalled publications

[Bead Pages](../README.md) / [sase-ad](README.md) / sase-ad.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ad.4` · **Size:** small
**Created:** 2026-07-28 11:43:50 UTC · **Closed:** 2026-07-28 12:45:36 UTC
**Plan:** [202607/fix\_family\_agent\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_family_agent_publication.md)

## Description

visibility: add a doctor check and stronger reporting for the publication outbox so quarantined or long-stalled requests are noticed instead of accumulating unseen for days.

## Notes

[2026-07-28T12:45:12Z · sase-ad.4] Implemented publication outbox visibility: added state.agent_publication_outbox doctor check for quarantined/stalled requests, lock-free explicit-path outbox snapshots, and commit warnings that call out existing quarantined backlogs with the retry command. Verification: focused pytest set passed; just fmt passed; just check passed fmt/lint/mypy/pyscripts/symvision/toobig but failed at existing plan links validation in the plans sidecar (229 errors); just test full run had 4 retry/suite-gate failures that passed when rerun serially/dedicated visual lane.

## Dependencies

- **Depends on:** [sase-ad.2](sase-ad.2.md) ✓
- **Depends on:** [sase-ad.3](sase-ad.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ad.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ad.4/README.md) | [sase-ad.4](sase-ad.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5842f04`](https://github.com/sase-org/sase/commit/5842f04af4d3eabebed72d81b64a6bec477125a3) | feat: surface agent publication outbox health (sase-ad.4) | [sase-ad.4](sase-ad.4.md) | 2026-07-28 12:48:50 |
