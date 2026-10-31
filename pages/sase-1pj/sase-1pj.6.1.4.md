# Bead: sase-1pj.6.1.4 — Complete partially published gates on replay

[Bead Pages](../README.md) / [sase-1pj.6.1](sase-1pj.6.1.md) / sase-1pj.6.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) · **Assignee:** `sase-1pj.6.1.4` · **Size:** medium
**Created:** 2026-10-31 08:56:55 EDT · **Closed:** 2026-10-31 12:43:30 EDT
**Plan:** [202610/staged\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md)

## Description

gate-replay: resume partial gate publication under its existing request and member identities, repairing claim and notification effects without duplicating the gate or changing its frozen creator and policy.

## Notes

[2026-10-31T16:43:30Z · sase-1pj.6.1.4] Request-id replay now validates kind/workspace/creator identity, fingerprints completed durable results, repairs pending claim and notification work under the original member, and refuses failed-unpublished plus payload-mismatch retries. Verified with sase tool run check (60044f089ef34ae26378e5416a93e507) and tests/gate_turn/test_publication_replay.py across custom/sudo/launch/run/hitl. No leftover --epic-symbol rows.

## Dependencies

- **Depends on:** [sase-1pj.6.1.1](sase-1pj.6.1.1.md) ✓ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.6](sase-1pj.6.1.6.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.4/README.md) | [sase-1pj.6.1.4](sase-1pj.6.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d9129cf`](https://github.com/sase-org/sase/commit/d9129cfd4ba20fc48fe10707a6833c44bf4eb8ee) | feat(gate-turn): finish partial gate publication on request-id replay | [sase-1pj.6.1.4](sase-1pj.6.1.4.md) | 2026-10-31 12:45:33 EDT |
