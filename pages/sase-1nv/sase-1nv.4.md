# Bead: sase-1nv.4 — Explicit repair for existing stale-revision outbox rows

[Bead Pages](../README.md) / [sase-1nv](README.md) / sase-1nv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.4` · **Size:** medium
**Created:** 2026-10-24 07:01:33 EDT · **Closed:** 2026-10-24 11:13:58 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

## Description

stale-row-repair: add a report-first, audited `sase agent sync` repair that maps each stale requested revision to the agent's committed revision, or to linked scope, without dropping any request.

## Notes

[2026-10-24T15:13:58Z · sase-1nv.4] stale-row-repair done and verified. Core: new classify_stale_publication_request (wire+PyO3 binding) classifying unchanged/linked/repaired(S)/unresolved; 6 core unit tests + binding round-trip pass; sase-core gate green except known load flake sase-1gz (listener_creates_private_socket, passes in isolation, tracked). Sase: outbox schema v7 with requested_revision (original preserved on rekey, visible in doctor/JSON); sase agent sync --repair-revisions (report by default, one project per call) + --apply (writes via outbox mutation APIs under the agents-sync lock, audit JSONL beside the outbox); doctor state.agent_publication_outbox counts rows whose requested revision is absent from published run commits and names the repair; docs updated (hood-sync, sidecar-sync runbook, generated CLI + completion snapshots). Tests: 14 new real-git fixture tests (unchanged/parent-case/rebased-case repaired, linked, unresolved, collision; report writes nothing; apply idempotent; completion fulfills repaired row and deferred restore finds its source); just check 13221 passed with only snapshot drift (regenerated via just sync-completion-spec) and symvision new-publics (reports privatized), both re-verified. LANDING ORDER: the sase-core change is uncommitted in the linked checkout — land and push it first, then set sase-core-revision.txt to the landed SHA (ratchet only sees remote HEAD), then land sase; until the pin moves, pin-built wheels lack the new binding (core-floor-probe advisory confirms). pub-closeout re-runs ratchet-core-revision.

## Dependencies

- **Depends on:** [sase-1nv.3](sase-1nv.3.md) ✓ · ⧖ 2026-10-24
- **Blocks:** [sase-1nv.5](sase-1nv.5.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.4.md) | [sase-1nv.4](sase-1nv.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7ec12d2`](https://github.com/sase-org/sase-core/commit/7ec12d2d7ad8e670abe26aa396259a512f330391) | feat(core): classify stale publication requests for revision repair (sase-1nv.4) | [sase-1nv.4](sase-1nv.4.md) | 2026-10-24 11:45:47 EDT |
