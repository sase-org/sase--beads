# Bead: sase-9l.4 — Verify and purge the leaked fixture beads

[Bead Pages](../README.md) / [sase-9l](README.md) / sase-9l.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9l.4` · **Size:** small
**Created:** 2026-07-25 14:56:37 UTC · **Closed:** 2026-07-25 17:53:47 UTC
**Plan:** [202607/bead\_store\_pytest\_isolation.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_store_pytest_isolation.md)

## Description

'Verify and purge the leaked beads' section: re-identify the leaked pytest-fixture beads against the live store, remove them atomically, and confirm the open backlog and ready queue contain only real work.

## Notes

Purged 11 leaked pytest-fixture beads from the shared plans-sidecar store: sase-97, sase-9a, sase-9b, sase-9c, sase-9d, sase-9e, sase-9f, sase-9g, sase-9h, sase-9i, sase-9j.

Re-identification (run against the live store after 'sase repo open plans' refreshed it to origin/main, 2039 records): scanned issues.jsonl for the fixture signature — non-closed, tier=epic, type=plan, no children, generic title (Epic/Created/Created Epic), and a design that is a temp/pytest path (pytest, popen-gw, .pytest_cache, localtmp, /tmp) or one of the fixture literals plan.md / sdd/plans/202605/roadmap.md. Two broader control scans (any non-closed bead with a temp-ish design at any tier; any non-closed bead with a generic title) returned the same 11 and no others. Matched the plan's starting list exactly — no new leaks since planning.

Each candidate was verified individually with 'sase bead show' immediately before removal: all 11 open, tier=epic, type=plan, no parent, no children, and no other bead depends on them. Removed atomically with a single 'sase bead rm' (11 IDs), which auto-committed as dcc80efa 'chore(beads): remove sase-97 ... sase-9j' and pushed to the shared sidecar.

Confirmation: store is now 2028 records; re-running the signature scan returns 0 matches; none of the 11 IDs remain. 'sase bead ready' returns only real work (sase-95, sase-9l, sase-9m, sase-9m.4, sase-9n). Plans sidecar working tree clean and in sync with origin/main.

Not done (out of scope per plan): sase-8q and sase-8s remain previously-closed fixture beads with permanently consumed IDs.

## Dependencies

- **Depends on:** [sase-9l.3](sase-9l.3.md) ✓
